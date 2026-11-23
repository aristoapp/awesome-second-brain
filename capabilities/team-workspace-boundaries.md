# Personal / Team Scope

## What This Capability Means

Personal and team scope defines who can read, write, update, delete, and share memory across personal, project, workspace, team, and organization contexts.

## Evaluation Questions

- Does the system support projects, collections, sources, users, sessions, groups, or workspaces?
- Are reads and writes scoped?
- Can teams share knowledge without exposing personal memory?
- Can admins audit or revoke access?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Partial | Memory project tags and Wiki collections for scoped search/filtering. | Full team/workspace separation is coming soon; verify governance details for the target plan. |
| OpenHuman | Not primary fit | Personal local app and connected sources. | Team/workspace governance is not the core fit. |
| GBrain | Built-in but operational | Brains, sources, source-scoped OAuth clients, federated reads, mounts, Postgres/Supabase, and HTTP MCP. | Directory-only scoping is convention-based; enforced team isolation needs explicit source/OAuth design. |
| Hermes Agent + LLM Wiki | Partial | Separate wiki directories, schemas, vaults, or repos can create project boundaries. | Permissions, shared review, and team governance are external filesystem/sync/process concerns. |
| Supermemory | Integration | Project scoping and connector metadata. | Team governance should be verified. |
| Hyperspell | Built-in for app builders | Multi-tenant app user IDs, user tokens, source selection, metadata, collections, resource filters, and folder policies. | Team/workspace governance UX is app-owned; account/plan behavior should be verified. |
| Honcho | Built-in for app builders | Workspaces isolate apps/environments; peers and sessions model users, agents, groups, and other entities. | End-user governance UX and permission flows are app-owned. |
| Mnemosyne | Partial | Memory banks and global/session scope can separate domains or agent contexts. | Team permissions, admin controls, and review workflows are external to the memory backend. |
| taOSmd | Partial | Per-agent shelves with cross-agent reads separate agent contexts and projects. | Team permissions, admin controls, and review workflows are not part of the memory layer. |
| Vestige | Partial | Per-project code memory and local scoping separate contexts. | Memory is single-machine and local-only; team permissions, admin controls, and shared-workspace review are not part of the memory layer. |
| [ClickHouse Loom](https://github.com/ClickHouse/loom) | Built-in but operational | Self-hosted shared agent memory; tokens scope access to namespaces and read or write roles. | Team deployment requires server operation and authenticated namespace grants. |
| Mem0/OpenMemory | Built-in | User, session, and organizational memory. | Requires careful scope design. |
| Zep/Graphiti | Built-in | Projects, users, sessions, groups. | Best as app infrastructure. |
| Cognee | Built-in in API mode | Shared backend/API mode. | Standalone mode isolates clients. |
| Khoj | Partial | Deployment and source choices. | Primarily personal. |
| Obsidian/Logseq + AI bridge | Partial | Shared vault/sync and permissions. | Team memory discipline is user-owned. |
| ChatGPT Memory | Partial | Workspace/admin behavior depends on ChatGPT plan and settings. | Not designed as portable team memory. |
| Claude Projects/Claude Code | Built-in on team plans | Team/Enterprise project sharing and permissions. | Scope remains Claude project/workspace oriented. |
| NotebookLM | Partial | Sharing/collaboration depends on Google account and product tier. | Notebook boundaries are not full second-brain governance. |

## Sources

- [Membase attached vs universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell core concepts](https://docs.hyperspell.com/core/concepts)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne repository](https://github.com/AxDSan/Mnemosyne)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Mem0 memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [ClickHouse Loom v1.3.0 namespaces and sharing](https://github.com/ClickHouse/loom/blob/47b479dcdae4c089aef2690428fa4c9a8f54554c/docs/features/namespaces-and-sharing.md)
