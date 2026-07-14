# Data Olympus

## Snapshot

- Website / docs: https://github.com/knaisoma/data-olympus
- Package: https://pypi.org/project/data-olympus/
- Company / maintainer: Knaisoma / Data Olympus maintainers
- Status: Pre-1.0 beta, current release v0.5.0
- Open source: Yes, Apache-2.0
- Deployment: Local or self-hosted. The source of truth is a git-backed Markdown knowledge directory; the CLI, streamable HTTP MCP server, and REST endpoints are activation surfaces.
- Primary users: Engineering teams and agent operators who need reviewed standards, decisions, runbooks, and project knowledge to govern later agent work
- Best second-brain role: Governed local workspace for authoritative project and engineering knowledge
- Last reviewed: 2026-07-14
- Reviewed evidence: Data Olympus main at `a55f4b2` (v0.5.0 release batch), README, quickstart, benchmark guide, specification, and PyPI 0.5.0

## One-line Summary

Data Olympus is a git-native, governed knowledge workspace for coding agents that separates reviewed, currently applicable standards and decisions from proposals, superseded records, expired guidance, and general remembered context.

## Second-Brain Fit

Data Olympus fits the part of a second brain that must be treated as reviewed organizational knowledge rather than automatic recall. Teams keep standards, architecture decisions, workflows, and project guidance as Markdown with typed YAML frontmatter and links. Agents query that workspace through MCP, CLI, or REST and can propose changes through a pending review path instead of silently making new content authoritative.

Its primary layer is a local workspace because the adopted source of truth is the git repository, not the MCP service or search index. The service activates the workspace for agents and coordinates writes, but the files remain directly readable, reviewable, portable, and versioned without a proprietary client.

This is not a general personal-memory product, conversational memory extractor, code-search engine, or connector platform. It is most useful when the question is not only "what context is relevant?" but "which reviewed rule or decision is currently allowed to govern this work?"

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local or self-hosted. Knowledge lives in a git-backed Markdown directory. The Python package is published on PyPI, and Docker deployment is documented. Operators own the repository, server, index, backups, and update path. |
| Context capture | Partial and deliberate. Users can author Markdown, import existing `CLAUDE.md`, `AGENTS.md`, `GEMINI.md`, `.cursorrules`, ADR, and OKF corpora into draft records, or let agents submit proposed memories and edits. It does not passively collect chats, email, calendars, or application data. |
| Knowledge organization | Built-in typed Markdown/frontmatter with stable ids, controlled `type`, `status`, and `tier` fields, hierarchical project/stack/component placement, links, indexed outlines, and lifecycle relationships such as `supersedes` and `superseded_by`. |
| Memory evolution | Governed rather than automatic. Proposed writes enter a pending path, accepted records can be superseded, validity windows distinguish upcoming and expired guidance, and git history plus audit events preserve change provenance. There is no autonomous dream or consolidation cycle. |
| Retrieval / use | Full-text retrieval with filters for status, type, tier, category, validity, and currently in-force guidance. An abstention mode returns no result when a query has no discriminating knowledge signal. Optional local embeddings improve semantic retrieval, but the default stack remains lexical. |
| Agent activation / write-back | Built-in streamable HTTP MCP server, CLI, and REST endpoints. MCP tools cover search, get, list, outline, consultation, proposals, pending review, resolution, audit, and health. Setup and enforcement tooling supports Claude Code, Codex, Gemini, OpenCode, and advisory Copilot paths with different documented enforcement tiers. |
| Personal / team scope | Best suited to project, engineering-team, and organization knowledge. Tiers and workspace/component paths provide scope, while git and server deployment provide sharing. It does not ship a user-facing team-membership or per-document RBAC product. |
| Feedback / correction | Humans can edit and review Markdown through normal git workflows or resolve agent proposals through the pending queue. Status changes, validity metadata, and supersession preserve retired guidance instead of erasing it. |
| Privacy / control | Strong local ownership. The knowledge graph is plain Markdown in git, the index is derived, and the service is self-hosted. Network exposure, repository access, authentication, and backup policy remain operator responsibilities. |
| Setup / operations | Medium. The package is available through `uvx` or `uv tool install`, and a setup wizard can wire supported agents, but Python 3.13+, `uv`, a git-initialized bundle, an MCP server process, and ongoing repository/service operations are still required. |

## Strengths

- Makes the authority boundary explicit: retrieved observations and agent proposals are not automatically treated as approved company knowledge.
- Uses plain Markdown and git as the durable source of truth, with no proprietary storage format required to inspect, edit, diff, or export the corpus.
- Supports status-aware and validity-aware retrieval so agents can request only guidance currently in force.
- Preserves decision history through typed supersession links, git history, and operational audit events.
- Uses a single-writer proposal pipeline with pending review, advisory locks, isolated worktrees, and a durable push queue for concurrent agent writes.
- Provides MCP, CLI, and REST activation surfaces plus optional consultation enforcement for several coding-agent environments.
- Includes reproducible maintainer-published retrieval benchmarks with synthetic and small committed real-corpus runs, documented caveats, generated result tables, and CI drift checks.

## Limitations

- Pre-1.0 beta. Format, runtime, and operational surfaces can still change.
- The project is designed to be readable by Google Open Knowledge Format consumers, but executable conformance testing against OKF reference tooling is not complete and remains tracked in [issue #82](https://github.com/knaisoma/data-olympus/issues/82).
- Python 3.13+ and `uv` are required for the packaged setup. Users still operate the git repository, service, agent wiring, and backups.
- No passive connector layer for chats, email, calendars, SaaS applications, or broad document ingestion. Imports and agent proposals are deliberate workflows.
- No end-user web knowledge editor, hosted service, or built-in team administration and document-level permissions.
- Default retrieval is lexical. The project documents weak performance on token-disjoint paraphrases; local embeddings are optional and off by default.
- Published benchmark results are produced by the project maintainers. The recipes and artifacts are reproducible, but the results should not be treated as independently reproduced third-party evaluation.
- The governed scope is intentionally narrower than a general second brain: it focuses on standards, decisions, runbooks, and project knowledge rather than personal conversational memory.

## Best For

- Engineering teams that need coding agents to consult reviewed standards and architecture decisions before making governed changes.
- Agent operators who want proposed knowledge changes to pass through review before becoming authoritative.
- Teams that prefer git-native, inspectable Markdown over an opaque hosted memory store.
- Workflows where validity, supersession, provenance, and an auditable authority boundary matter more than passive capture.
- Organizations that already maintain `AGENTS.md`, `CLAUDE.md`, ADR, `.cursorrules`, or OKF material and want to migrate it into a governed workspace.

## Not Ideal For

- Users looking for automatic personal-memory capture from chats, email, calendars, and consumer applications.
- Non-technical users who want a hosted UI with no local runtime or repository operations.
- Applications that primarily need high-recall semantic memory over large unstructured corpora.
- Teams that need built-in identity administration, document-level ACLs, or a managed multi-tenant service.
- Code navigation and reference search, which remain better served by language servers and code-search tools.

## Tradeoffs

Data Olympus gives teams an inspectable and enforceable boundary between useful context and currently authoritative guidance. That boundary requires explicit metadata, review, git discipline, and service operation. It trades the convenience and adaptive recall of a hosted or self-mutating memory system for deterministic lifecycle rules, human approval, and portable history. It is therefore complementary to conversational memory layers and connector-heavy second brains rather than a replacement for them.

## Official Setup / Evaluation Links

- [Repository and README](https://github.com/knaisoma/data-olympus)
- [PyPI package](https://pypi.org/project/data-olympus/)
- [v0.5.0 release](https://github.com/knaisoma/data-olympus/releases/tag/v0.5.0)
- [Quickstart](https://github.com/knaisoma/data-olympus/blob/main/docs/quickstart.md)
- [Adoption and import guide](https://github.com/knaisoma/data-olympus/blob/main/docs/adoption.md)
- [Enforcement guide](https://github.com/knaisoma/data-olympus/blob/main/docs/enforcement.md)
- [Format specification](https://github.com/knaisoma/data-olympus/blob/main/SPEC.md)
- [Benchmark methodology and reproduction](https://github.com/knaisoma/data-olympus/blob/main/benchmarks/README.md)
- [Comparison and benchmark results](https://github.com/knaisoma/data-olympus/blob/main/docs/comparison.md)

## Sources

- https://github.com/knaisoma/data-olympus
- https://pypi.org/project/data-olympus/
- https://github.com/knaisoma/data-olympus/releases/tag/v0.5.0
- https://github.com/knaisoma/data-olympus/blob/main/docs/quickstart.md
- https://github.com/knaisoma/data-olympus/blob/main/docs/adoption.md
- https://github.com/knaisoma/data-olympus/blob/main/docs/enforcement.md
- https://github.com/knaisoma/data-olympus/blob/main/SPEC.md
- https://github.com/knaisoma/data-olympus/blob/main/benchmarks/README.md
- https://github.com/knaisoma/data-olympus/blob/main/docs/comparison.md
