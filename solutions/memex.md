# memex

## Snapshot

- Website / docs: https://github.com/timurgaleev/memex
- Repo: https://github.com/timurgaleev/memex
- Release: https://github.com/timurgaleev/memex/releases/tag/v1.131.0
- Company / maintainer: Timur Galeev (timurgaleev), independent, solo-maintained
- Status: Open-source, self-hosted MCP knowledge service, tagged release v1.131.0 (2026-09-13)
- Open source: Yes, MIT-licensed repository (recognized by GitHub)
- Deployment: Self-hosted in the user's own AWS account. Terraform provisions one EC2 host (Docker), RDS Postgres 16 with pgvector, EFS, and Secrets Manager; Amazon Bedrock provides embeddings and utility LLM calls. Public ingress is a Cloudflare Tunnel by default, or Caddy with Let's Encrypt as an alternative.
- Primary users: Developers and MCP-agent users (Claude Code, Cursor, Codex) who want one private, cloud-hosted brain for their notes and code that they operate themselves
- Best second-brain role: Self-hosted agent memory layer that indexes Markdown notes and source code and serves cited retrieval to any MCP client
- Last reviewed: 2026-09-18
- Reviewed evidence: official repo at tag `v1.131.0`, commit `2489b9c7504ae7b56d4ad3cac0684f0f07dde467`, README, `docs/HOW-IT-WORKS.md`, `docs/CONFIGURATION.md`, `docs/DEPLOYMENT.md`, `deploy/memex/docs/API.md`, and `deploy/memex/docs/OPERATIONS.md`

## One-line Summary

memex is a self-hosted retrieval service that indexes Markdown notes, source code, and content pushed over MCP into Postgres + pgvector inside the user's AWS account, and returns ranked, source-cited evidence to any MCP client; the client, not memex, writes the answer.

## Second-Brain Fit

memex fits as a developer-operated memory backend for people who work through MCP agents and want their notes and code searchable from every agent through one endpoint, without handing the data to a hosted memory vendor. It is useful when the second brain should live in infrastructure the user owns (their AWS account), when retrieval should return evidence with citations instead of a generated answer, and when code structure (callers and callees) matters alongside prose.

It is closest to Mnemosyne, taOSmd, Vestige, Mem0/OpenMemory, and Supermemory in this repo's landscape. Compared with the local-first options, it runs as a cloud service in the user's own AWS account rather than on one machine, so any MCP client that can reach the endpoint shares one index. Compared with hosted memory products, the user operates the infrastructure and pays AWS directly. It is not a notes app, has no end-user UI for browsing the brain, and has no built-in OAuth connectors to SaaS sources.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted in one AWS account the user controls. Terraform brings up EC2, RDS Postgres 16 + pgvector, EFS, and Secrets Manager; a Postgres database is the source of truth. A PGLite engine exists for local and migration use. The maintainer's cost table estimates about $28/month at light personal use. |
| Context capture | Built-in indexers sweep configured Markdown vault directories and code checkouts (TypeScript and Python through tree-sitter); MCP write tools (`page_put`, `page_append`, `add_fact`, `add_timeline_event`, `index`) let agents push content such as mail, calendar entries, or documents. There are no built-in OAuth connectors to SaaS apps; external sources need an agent or a custom collector. |
| Knowledge organization | Pages, chunks, entities, links, tags, facts, and timelines in Postgres. Facts are extracted from writes, matched back to existing entity pages, and retired when superseded; a user-declared `## Facts` block on a page is kept as authoritative. A code call graph is built from indexed source. |
| Memory evolution | Built-in background cycle every few hours: indexes new content, re-embeds only changed chunks, and supersedes stale facts. Opt-in (off by default) LLM synthesis distils notes into concepts, "takes", reflections, and cross-session patterns in a separate store without editing the original notes. A nightly eval probe records retrieval quality over time. |
| Retrieval / use | Hybrid pipeline: vector search (Titan Text Embeddings v2) plus keyword search, LLM query-intent classification and expansion (Claude Haiku), Reciprocal Rank Fusion, deduplication, optional LLM rerank, and top-k results with citations to the source document. Also graph traversal, entity recall, `code_callers`/`code_callees`, and `volunteer_context`, which proposes relevant pages for a supplied conversation. |
| Agent activation / write-back | MCP JSON-RPC over HTTPS (`POST /mcp`); `tools/list` currently reports 91 tools. Documented setup for Claude Code; any MCP client that supports a remote HTTP server with a bearer header can connect. Write tools are available internally and to scoped OAuth/PAT clients; on the public bearer they are blocked unless `MEMEX_PUBLIC_WRITE=1`. A CLI runs inside the container for operators. |
| Personal / team scope | Single-operator by default. Opt-in source-based tenancy: each OAuth client or PAT carries one write source and a read set, writes to another tenant's path are refused, and per-client daily spend ceilings can be set. This is credential scoping, not a team workspace product with roles or a shared UI. |
| Feedback / correction | Page versions with restore and revert, soft delete plus purge, `forget_fact`, tag and link edits, a take-review lifecycle (`list_takes`, `takes_search`, `set_take_status`), `find_contradictions`, and an `advisor` tool that ranks maintenance issues. All through MCP or CLI; there is no graphical review UI. |
| Privacy / control | No telemetry. Data stays in the user's AWS account, but embeddings and LLM calls go to Amazon Bedrock and public traffic passes through Cloudflare unless the Caddy ingress is used. The public surface is two routes (`GET /health`, `POST /mcp`) with bearer auth, per-IP rate limiting, and note bodies redacted on the public path by default. `migrate-engine` copies the whole database to a portable PGLite file for export or account moves. |
| Setup / operations | High. Needs an AWS account, Terraform 1.6+, Docker Compose v2, and a domain; `make init`, `make audit`, `make plan`, and `make apply` bootstrap the stack. The user owns AWS cost, bearer rotation, backups, upgrades, and cost flags for the paid LLM stages. |

## Strengths

- One remote MCP endpoint in infrastructure the user owns, so every MCP client shares a single index instead of re-indexing per app.
- Retrieval returns source-cited evidence and leaves answer writing to the client, which keeps grounding inspectable.
- Indexes code as well as notes and answers caller/callee questions from a real call graph.
- Small attack surface: two HTTP routes behind a tunnel, no open EC2 ports, secrets in Secrets Manager, and optional daily bearer rotation.
- Background maintenance re-embeds only changed chunks, supersedes stale facts, and tracks retrieval quality with a nightly eval probe.
- LLM synthesis is opt-in and writes to a separate store, so original notes are never rewritten.
- MIT license, Terraform-defined infrastructure, and a documented cost model.

## Limitations

- AWS-only deployment path; the standard setup depends on Bedrock, and on Cloudflare unless the Caddy ingress is chosen.
- Setup burden is high compared with a desktop app or a single-binary local server: Terraform, a domain, and an AWS bill.
- No built-in SaaS connectors (Slack, Gmail, Drive, and similar); collection beyond Markdown vaults and code needs an agent or custom work.
- No end-user UI for browsing, reviewing, or editing memory; inspection and correction go through MCP tools or the CLI.
- Solo-maintained with an early user base, so long-term support depends on one maintainer.
- Multi-tenant use is credential scoping over one brain, not a team product with roles and admin UI.
- Retrieval quality claims come from the maintainer's own eval probe, not independent evaluation.

## Best For

- Developers who live in Claude Code, Cursor, or Codex and want one private brain for notes and code reachable from all of them.
- Users who want their second brain in their own cloud account rather than on a vendor's servers or tied to one laptop.
- Workflows where agents must cite the exact source note or file for what they claim.
- Codebases where caller/callee questions matter alongside documentation.

## Not Ideal For

- Users who want a no-ops app with a UI and built-in connectors.
- People without AWS access or who do not want to run Terraform and pay for cloud infrastructure.
- Teams that need workspace roles, admin controls, and a governance UI out of the box.
- Fully offline or air-gapped use, since embeddings and LLM stages call Bedrock.

## Tradeoffs

memex gives cloud-hosted, self-owned memory with cited retrieval, code awareness, and a small public surface, but it moves infrastructure, cost, and maintenance to the user and offers no graphical interface or SaaS connectors. Compare it with Mnemosyne, taOSmd, and Vestige when the choice is between local single-machine memory and a self-hosted service reachable from many clients, and with Supermemory or Mem0/OpenMemory when the choice is between a hosted memory API and running the stack yourself.

## Official Setup / Evaluation Links

- Repository: https://github.com/timurgaleev/memex
- Release v1.131.0: https://github.com/timurgaleev/memex/releases/tag/v1.131.0
- How it works: https://github.com/timurgaleev/memex/blob/main/docs/HOW-IT-WORKS.md
- Deployment: https://github.com/timurgaleev/memex/blob/main/docs/DEPLOYMENT.md
- Configuration: https://github.com/timurgaleev/memex/blob/main/docs/CONFIGURATION.md
- MCP API reference: https://github.com/timurgaleev/memex/blob/main/deploy/memex/docs/API.md
- Claude Code setup: https://github.com/timurgaleev/memex/blob/main/deploy/memex/docs/CLAUDE-CODE.md

## Sources

- https://github.com/timurgaleev/memex
- https://github.com/timurgaleev/memex/blob/main/README.md
- https://github.com/timurgaleev/memex/blob/main/ARCHITECTURE.md
- https://github.com/timurgaleev/memex/blob/main/deploy/memex/docs/OPERATIONS.md
- https://github.com/timurgaleev/memex/releases/tag/v1.131.0
