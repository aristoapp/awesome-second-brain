# Local vs Cloud

| Solution | Local / self-hosted | Hosted / cloud | Best reason to choose it | Main tradeoff |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Not the primary model | Yes | Fast end-to-end second brain without running the stack | Less local infrastructure control. |
| [OpenHuman](../solutions/openhuman.md) | Yes, local memory/runtime state and Markdown vault | Yes, managed services for sign-in, model routing, search proxying, OAuth/integrations | Productized local-first personal AI | Local-first does not mean fully offline by default. |
| [Hjarni](../solutions/hjarni.md) | No | Yes | Agent-readable and writable Markdown notes without running any stack | Hosted-only storage; no self-hosted or local deployment (Markdown export keeps the shape portable). |
| [GBrain](../solutions/gbrain.md) | Yes, local PGLite and self-hosted Postgres/Supabase paths | HTTP MCP can be deployed remotely | Maximum control over second-brain operations | PGLite fits local personal use; shared/team deployments add Postgres/Supabase, OAuth, sync, embeddings, collectors, and maintenance. |
| [Data Olympus](../solutions/data-olympus.md) | Yes, git-backed Markdown workspace plus a local or self-hosted MCP/REST service | No managed hosted product; operators may deploy the service remotely | Reviewed standards and decisions remain portable, inspectable, and distinguishable from proposals or retired guidance | Python 3.13+, `uv`, repository governance, service operation, and access control remain operator responsibilities. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Yes, local/server Hermes runtime plus Markdown wiki directory | Optional only through chosen hosting, sync, or model providers | Inspectable agent-maintained wiki | No managed connector/governance layer; user owns wiki hygiene and runtime configuration. |
| [obsidian-wiki](../solutions/obsidian-wiki.md) | Yes, local Markdown/Obsidian vault and local CLI/skills | Optional only through the chosen agent, model, search index, and sync providers | One inspectable second brain shared across multiple coding-agent clients | No managed connector, API, permission, or sync layer; users own review and operations. |
| [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md) | Partial: Obsidian vault, Hermes gateway, and optionally Honcho run locally | Yes: AgentMail is a hosted email API; Honcho managed service is an alternative to self-hosting | Local-first second brain with agent memory and inspectable Markdown; requires assembling multiple components | Higher setup burden; you own integration and operations of multiple components. |
| [Supermemory](../solutions/supermemory.md) | No verified self-hosted core memory product | Yes | Hosted memory API with connectors | Hosted convenience with platform boundaries. |
| [Hyperspell](../solutions/hyperspell.md) | No verified self-hosted core memory platform | Yes | Hosted connector, context graph, and retrieval layer for agents | Private beta availability and less local infrastructure control; public client surfaces do not make the core platform self-hosted. |
| [Honcho](../solutions/honcho.md) | Yes, self-hosted FastAPI server | Yes, managed service and hosted MCP | Stateful agent memory with hosted or owned deployment paths | Self-hosting adds service, provider-key, storage, and update operations. |
| [Mnemosyne](../solutions/mnemosyne.md) | Yes, local SQLite database through package, MCP, SDK, or Hermes plugin | Not the primary model | Local-first agent memory for MCP and Hermes workflows | You operate embeddings, memory scope, consolidation, and agent integration behavior. |
| [taOSmd](../solutions/taosmd.md) | Yes, local-first and offline; local SQLite, ONNX embeddings, and a local LLM (Ollama or RKLLM on RK3588) | Not a hosted product; an optional remote client can target your own taosmd serve instance | Offline, local-first agent memory on modest or single-board hardware with a zero-loss archive | You run and operate the local LLM and embedding model yourself. |
| [Vestige](../solutions/vestige.md) | Yes, local-first; single Rust binary, local SQLite (optional SQLCipher), local embeddings; runs offline after a one-time model download | Not a hosted product | Local-first MCP memory for coding agents with decay, consolidation, active forgetting, and backward causal recall | Single-machine and local-only; no hosted or team option, and cross-machine portability is user-operated. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Yes through self-hosted server and library paths | Yes through Mem0 Platform | Developer memory layer with hosted or owned stack | Requires memory scope and governance design. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Graphiti can run as the application-owned graph memory layer; Zep itself is managed | Yes through Zep | Temporal graph memory for apps | Product engineering and backend/provider choices required. |
| [Cognee](../solutions/cognee.md) | Yes, SDK/local setup and optional Docker MCP | Yes, API/Cloud mode/shared backend | Knowledge graph memory SDK with MCP/plugins | Mode choice affects sharing and isolation. |
| [Khoj](../solutions/khoj.md) | Yes | Yes | Personal AI over files with privacy option | Self-hosting still requires source and model setup. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Yes | Optional sync/services | Human-owned local notes | AI memory requires plugins or custom bridges. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | No | Yes | Native ChatGPT personalization | Platform-bound and not portable. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Claude Code has local terminal/IDE/desktop surfaces; project knowledge is platform-hosted | Yes | Claude-native project context and developer-agent workflows | Platform-scoped unless external MCP memory is added. |
| [NotebookLM](../solutions/notebooklm.md) | No | Yes | Source-grounded research notebook | Static imported sources and platform-bound workflow. |

## Guidance

Local-first systems are better for ownership, auditability, custom schema work, and long-lived personal archives. Hosted systems are better when setup speed, OAuth connectors, background organization, and ready-to-use retrieval matter more than operating the storage layer.

## Source Availability Notes

Local, self-hosted, and open source are related but separate checks.

- A local or self-hosted path means the user can run some or all of the system on owned infrastructure. It does not automatically mean the project is FOSS.
- A hosted or proprietary product can still belong in this repo when its public behavior is useful, source-backed, and clear about data and deployment boundaries.
- Use `Open source: Yes` only when the project declares a recognized open-source license in an official source.
- For a public repository without a declared license, use `Public repo; license not declared`.
- Use `Unknown` or `Not disclosed` when official sources do not establish license, cloud boundary, export, or air-gapped behavior.

When source availability or deployment control is the deciding factor, check each solution profile's `Open source` and `Deployment` fields before treating a row as fully local, self-hostable, FOSS, proprietary, or hosted-only.
