# Personal vs Team

| Solution | Personal fit | Project fit | Team fit | Notes |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Strong | Strong | Possible / coming soon | Memory projects and Wiki collections support project-level scoping today; full team/workspace separation is coming soon. |
| [OpenHuman](../solutions/openhuman.md) | Strong | Possible | Not primary fit | Local-first personal desktop AI with many integrations. |
| [Hjarni](../solutions/hjarni.md) | Strong | Strong | Strong | Personal brain plus shared team spaces with member management and per-folder and per-team AI instructions; folders (containers) scope projects. Team spaces are a paid Teams-plan feature. |
| [GBrain](../solutions/gbrain.md) | Strong | Strong | Strong / operational | Company-brain path uses sources, source-scoped OAuth clients, federated reads, HTTP MCP, and usually Postgres/Supabase; directory-only scoping is convention-based. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Strong | Strong | Partial / operational | Multiple wiki directories, schemas, vaults, or repos can separate projects, but team permissions are external to the skill. |
| [obsidian-wiki](../solutions/obsidian-wiki.md) | Strong | Strong | Partial / operational | Named vault profiles and project pages separate contexts, but shared-vault sync, concurrent editing, permissions, and approvals are external. |
| [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md) | Strong | Strong | Partial / operational | Obsidian vault is single-user; Honcho supports multiple peers. Team use requires shared vault (git/sync) and Honcho workspace configuration. |
| [Supermemory](../solutions/supermemory.md) | Strong | Strong | Possible | Project scoping and connectors help, but team governance must be checked. |
| [Hyperspell](../solutions/hyperspell.md) | Strong | Strong | Strong for app builders | Multi-tenant user model, user tokens, metadata, collections, source selection, and folder policies help, but app teams own governance UX. |
| [Honcho](../solutions/honcho.md) | Strong | Strong | Strong for app builders | Workspaces isolate apps/environments; peers and sessions can model users, agents, groups, and other entities, but end-user governance UX is app-owned. |
| [Mnemosyne](../solutions/mnemosyne.md) | Strong | Strong | Partial / operational | Memory banks and global/session scope can separate contexts, but team permissions and review flows are external to the memory layer. |
| [taOSmd](../solutions/taosmd.md) | Strong | Strong | Partial / operational | Per-agent shelves with cross-agent reads separate contexts, but team permissions and review flows are not part of the memory layer. |
| [Vestige](../solutions/vestige.md) | Strong | Strong | Not primary fit | Per-project code memory and local scoping separate contexts, but memory is single-machine and local-only, with no team-permission or shared-workspace product surface. |
| [memex](../solutions/memex.md) | Strong | Strong | Partial | Single-operator by default; opt-in source-based tenancy scopes each OAuth client or PAT to its own write source and read set, but there are no team roles or shared UI. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Strong | Strong | Strong | User, session, and organizational memory make it product-friendly. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Possible | Strong | Strong | Best as app infrastructure for users, sessions, groups, and business data. |
| [Cognee](../solutions/cognee.md) | Strong | Strong | Strong in API mode | Standalone mode isolates clients; API mode centralizes sharing. |
| [Khoj](../solutions/khoj.md) | Strong | Possible | Partial | Better as a personal AI than a universal team memory layer. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Strong | Strong | Partial | Great source of truth, but team reuse depends on sync, permissions, and bridge discipline. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Strong | Partial | Partial | Memory is user/platform scoped; enterprise controls vary by workspace, and memory sources depend on plan/region/settings. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Strong | Strong | Strong on Team/Enterprise | Projects support knowledge bases and team sharing on work plans. |
| [NotebookLM](../solutions/notebooklm.md) | Strong | Strong | Partial | Strong for shared source analysis, but not a living team memory system by default. |

## Guidance

Personal second brains can optimize for convenience and ownership. Team second brains need explicit source boundaries, access control, auditability, and a plan for who can write, correct, or delete shared memory.
