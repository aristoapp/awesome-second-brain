# Solutions

Solution profiles explain what role each product or project can play in an AI-native second brain. They are landscape profiles, not replacement setup docs.

The profiles stay in one directory for stable links, but they are grouped by primary layer below. Some systems span multiple layers; the grouping reflects the role this repo evaluates first.

## End-To-End Apps

These systems package collection, organization, retrieval, and user-facing workflows together.

| Solution | Best second-brain role | Status |
|---|---|---|
| [Membase](membase.md) | Fastest end-to-end hosted second brain | Core |
| [OpenHuman](openhuman.md) | Local-first personal AI with automatic memory capture | Core, early beta |
| [Khoj](khoj.md) | Personal AI over local files and notes | Core |
| [Hjarni](hjarni.md) | AI-native Markdown notes app with built-in MCP | Core, source-backed |

## Local Workspaces

These systems center local files, wiki pages, vaults, or self-hosted brain operations that users and agents can inspect or maintain.

| Solution | Best second-brain role | Status |
|---|---|---|
| [GBrain](gbrain.md) | Local or self-hosted brain operations layer | Core, hands-on researched |
| [Data Olympus](data-olympus.md) | Governed local workspace for authoritative project knowledge | Core, pre-1.0 beta |
| [obsidian-wiki](obsidian-wiki.md) | Agent-agnostic local knowledge-compilation framework for Obsidian | Core, source-backed |
| [Hermes Agent + LLM Wiki](hermes-llm-wiki.md) | Agent-operated local Markdown wiki | Core |
| [Hermes Agent + Obsidian + Honcho](hermes-obsidian-honcho.md) | Local-first second brain with agent memory and email (multi-component stack) | Core, hands-on researched |
| [Obsidian/Logseq + AI bridge](obsidian-logseq.md) | Local-first PKM source of truth | Core |
| [Pad](pad.md) | Self-hosted, agent-operated project and context workspace | Core |

## Agent Memory Layers

These systems expose APIs, SDKs, MCP servers, or managed services that add memory to agents and products.

| Solution | Best second-brain role | Status |
|---|---|---|
| [Supermemory](supermemory.md) | Hosted memory API and connector layer | Core |
| [Hyperspell](hyperspell.md) | Hosted company/user context layer for AI agents | Core, private beta caveat |
| [Honcho](honcho.md) | Stateful agent memory and user-modeling layer | Core, source-backed |
| [Hindsight](hindsight.md) | Agent memory API with memory banks | Core, source-backed |
| [Mnemosyne](mnemosyne.md) | Local-first agent memory layer with MCP and Hermes integration | Core, source-backed |
| [taOSmd](taosmd.md) | Local-first, offline agent memory layer with a zero-loss archive | Core, source-backed |
| [Vestige](vestige.md) | Local-first agent memory layer with FSRS-6 decay, active forgetting, and backward causal recall | Core, source-backed |
| [Mem0/OpenMemory](mem0-openmemory.md) | Developer memory layer with hosted and self-hosted paths | Core |

## Memory Substrates

These systems are closer to graph, retrieval, or knowledge infrastructure that applications build on.

| Solution | Best second-brain role | Status |
|---|---|---|
| [Zep/Graphiti](zep-graphiti.md) | Temporal knowledge graph memory for applications | Core |
| [Cognee](cognee.md) | Knowledge graph memory SDK with MCP/plugins | Core |

## Platform Baselines

These systems are useful baselines inside one AI platform or bounded research surface.

| Solution | Best second-brain role | Status |
|---|---|---|
| [ChatGPT Memory](chatgpt-memory.md) | ChatGPT-native personalization baseline | Baseline |
| [Claude Projects/Claude Code](claude-projects-code.md) | Claude-scoped project knowledge and developer context | Baseline |
| [NotebookLM](notebooklm.md) | Source-grounded research notebook baseline | Baseline |

## Profile Rule

Every profile should answer deployment/ownership, context capture, knowledge organization, memory evolution, retrieval/use, feedback/correction, personal/team scope, privacy/control, agent activation/write-back, setup/operations, best-fit users, non-fit users, tradeoffs, and official setup/evaluation links. Use `Unknown` when a claim is not source-backed.
