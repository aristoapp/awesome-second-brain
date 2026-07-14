<div align="center">

# Awesome AI Second Brain

[![Context Engineering Banner](assets/awesome-second-brain.png)](https://membase.so/?utm_source=github&utm_medium=organic_social&utm_campaign=readme&utm_content=awesome-second-brain)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

English | [한국어](README.ko.md)

</div>

> Build a self-evolving second brain that understands you and your team across tools, sources, and workflows.

A curated comparison of second brain, AI memory, and knowledge systems for people who want AI to understand their personal context, team knowledge, and working history. It focuses on the full lifecycle: collecting scattered context, organizing it into durable knowledge, keeping it fresh over time, and making it useful when people or AI tools work.

## Second-Brain Lifecycle

Use this repo to decide how you want your second brain to work end to end:

| Stage | Key question | What to compare |
|---|---|---|
| Collect | How does context from chats, docs, apps, notes, calendars, Slack, email, code, and files enter the brain? | Connectors, imports, APIs, manual notes, custom collectors |
| Organize | Does raw context become structured knowledge instead of a pile of embeddings? | Entities, facts, links, summaries, timelines, tags, Wiki/pages |
| Evolve | Does memory improve as new context arrives and old context gets stale? | Consolidation, deduping, correction, refresh, dream/maintenance loops |
| Use | Can the right context show up when a person or AI tool is doing real work? | Search, grounding, filters, citations, AI-tool access, write-back |
| Govern | Can users and teams inspect, correct, delete, export, scope, and trust the brain? | UI, provenance, activation evidence, permissions, personal/team boundaries, local/cloud control |

## Choose by Lifecycle Gap

Start with the second-brain lifecycle stage that is blocking you most. If you want an optimized end-to-end second-brain solution that covers Collect, Organize, Evolve, Use, and Govern without hand-assembling local collectors, graph jobs, or memory infrastructure, [Membase](solutions/membase.md) is the default starting point. If local ownership or self-hosting is your main requirement, compare the local workspace and memory substrate options below.

| If your lifecycle gap is... | Start with | Why |
|---|---|---|
| Collect scattered context | [Membase](solutions/membase.md), [OpenHuman](solutions/openhuman.md), [Supermemory](solutions/supermemory.md), [Hyperspell](solutions/hyperspell.md), [Khoj](solutions/khoj.md), [obsidian-wiki](solutions/obsidian-wiki.md), or [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Use these when chats, docs, notes, files, apps, and workspace sources are not yet flowing into a usable brain. |
| Organize raw context into durable knowledge | [Membase](solutions/membase.md), [GBrain](solutions/gbrain.md), [Data Olympus](solutions/data-olympus.md), [obsidian-wiki](solutions/obsidian-wiki.md), [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md), [Hermes Agent + Obsidian + Honcho](solutions/hermes-obsidian-honcho.md), [Mnemosyne](solutions/mnemosyne.md), [taOSmd](solutions/taosmd.md), [Vestige](solutions/vestige.md), [Honcho](solutions/honcho.md), [Hjarni](solutions/hjarni.md), [Zep/Graphiti](solutions/zep-graphiti.md), [Cognee](solutions/cognee.md), or [Pad](solutions/pad.md) | Use these when raw context needs memory records, wiki pages, facts, links, graphs, timelines, or other durable structure. |
| Evolve memory over time | [Membase](solutions/membase.md), [GBrain](solutions/gbrain.md), [Data Olympus](solutions/data-olympus.md), [obsidian-wiki](solutions/obsidian-wiki.md), [Hermes Agent + Obsidian + Honcho](solutions/hermes-obsidian-honcho.md), [Hyperspell](solutions/hyperspell.md), [Honcho](solutions/honcho.md), [Hindsight](solutions/hindsight.md), [Mnemosyne](solutions/mnemosyne.md), [taOSmd](solutions/taosmd.md), [Vestige](solutions/vestige.md), [Zep/Graphiti](solutions/zep-graphiti.md), or [Cognee](solutions/cognee.md) | Use these when new context should update, consolidate, dedupe, refresh, or re-reason over existing memory. |
| Use context inside AI tools and workflows | [Membase](solutions/membase.md), [Supermemory](solutions/supermemory.md), [Hyperspell](solutions/hyperspell.md), [Honcho](solutions/honcho.md), [Hindsight](solutions/hindsight.md), [Mnemosyne](solutions/mnemosyne.md), [taOSmd](solutions/taosmd.md), [Vestige](solutions/vestige.md), [Hjarni](solutions/hjarni.md), [Data Olympus](solutions/data-olympus.md), [obsidian-wiki](solutions/obsidian-wiki.md), [Mem0/OpenMemory](solutions/mem0-openmemory.md), [Claude Projects/Claude Code](solutions/claude-projects-code.md), or [Pad](solutions/pad.md) | Use these when the main need is MCP, API, SDK, plugin, dashboard chat, or platform access that puts memory into active work. |
| Govern, inspect, correct, or control memory | [Membase](solutions/membase.md), [GBrain](solutions/gbrain.md), [Data Olympus](solutions/data-olympus.md), [obsidian-wiki](solutions/obsidian-wiki.md), [taOSmd](solutions/taosmd.md), [Vestige](solutions/vestige.md), [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md), [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md), [Hjarni](solutions/hjarni.md), [ChatGPT Memory](solutions/chatgpt-memory.md), [Claude Projects/Claude Code](solutions/claude-projects-code.md), or [Pad](solutions/pad.md) | Use these when visibility, review, correction, deletion, ownership, permissions, or local/cloud control matter most. |

## Solution Snapshot

This snapshot compares each system by the lifecycle stages where it is strongest, grouped by the kind of system you are adopting.

### End-To-End Apps

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Membase](solutions/membase.md) | Collect, Organize, Evolve, Use, Govern | You want a useful cross-tool second brain without operating collectors, graph jobs, or memory infrastructure. | Hosted path means less local infrastructure control. |
| [OpenHuman](solutions/openhuman.md) | Collect, Organize, Use | You want automatic app capture and a productized local desktop assistant. | Early beta status and local setup details may vary. |
| [Khoj](solutions/khoj.md) | Collect, Use | You want chat and search over local notes, files, documents, and web sources. | More focused on personal assistant/search than full memory governance. |
| [Hjarni](solutions/hjarni.md) | Organize, Use, Govern | You want a simple hosted Markdown notes app that Claude and ChatGPT can read, search, and write via built-in MCP. | Capture is manual note-writing with no automatic collectors, and it is hosted-only. |

### Local Workspaces

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [GBrain](solutions/gbrain.md) | Organize, Evolve, Use, Govern | You want agents to operate a structured local brain with pages, graph, timeline, CLI/MCP, and maintenance jobs. | More setup and operational ownership. |
| [Data Olympus](solutions/data-olympus.md) | Organize, Evolve, Use, Govern | You need reviewed standards, decisions, and project knowledge to remain distinguishable from proposals and general memory when agents act. | Pre-1.0, Python-based, and operator-run; no passive connectors, hosted UI, or independently reproduced benchmarks. |
| [obsidian-wiki](solutions/obsidian-wiki.md) | Collect, Organize, Evolve, Use, Govern | You want one inspectable Obsidian knowledge base maintained across multiple coding agents through portable skills. | Agent quality, review, sync, and maintenance cadence remain user-operated. |
| [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md) | Organize, Use, Govern | You want an inspectable local wiki that an agent can compile, query, lint, and maintain. | You still own the wiki discipline and workflow design. |
| [Hermes Agent + Obsidian + Honcho](solutions/hermes-obsidian-honcho.md) | Collect, Organize, Evolve, Use, Govern | You want a local-first second brain with agent memory, email integration, and inspectable Markdown, and you're willing to assemble the stack. | Higher setup burden; you own the integration and operations of multiple components. |
| [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Collect, Organize, Govern | You want a local PKM source of truth with optional AI bridges. | AI memory behavior depends on plugins, imports, or custom bridges. |
| [Pad](solutions/pad.md) | Organize, Use, Govern | You want a self-hosted, agent-operated workspace where typed collections, conventions, and playbooks give agents durable project context through a native skill, MCP, API, and CLI. | Structured/keyword retrieval only — no semantic recall or automatic consolidation. |

### Agent Memory Layers

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Supermemory](solutions/supermemory.md) | Collect, Organize, Use | You need hosted memory, connectors, MCP, API, SDK, and plugins for AI workflows or products. | App owners still need to verify how retrieved context is used. |
| [Hyperspell](solutions/hyperspell.md) | Collect, Organize, Evolve, Use | You need workspace context, metadata, live search, procedural memory, and agent-facing APIs. | Private beta and product availability may affect adoption. |
| [Honcho](solutions/honcho.md) | Organize, Evolve, Use | You need peer representations, conclusions, session context, and user or agent modeling over time. | Developer integration and hosting choices matter. |
| [Hindsight](solutions/hindsight.md) | Organize, Evolve, Use | You need memory banks, observations, consolidation, and multi-mode recall for agents. | Retrieval-to-action evidence depends on the surrounding workflow. |
| [Mnemosyne](solutions/mnemosyne.md) | Organize, Evolve, Use | You need local SQLite memory with MCP, SDK, CLI, Hermes integration, tiers, and consolidation. | Local operation and agent logging still need owner attention. |
| [taOSmd](solutions/taosmd.md) | Organize, Evolve, Use, Govern | You want an offline, local-first agent memory layer on modest or single-board hardware, with a zero-loss verbatim archive, source-linked verifiable recall, and MCP, HTTP, API, and CLI access. | You run a local LLM and embedding model yourself, and there is no PyPI package or hosted option yet. |
| [Vestige](solutions/vestige.md) | Organize, Evolve, Use, Govern | You want a local-first MCP memory layer with FSRS-6 decay, prediction-error gated writes, consolidation, reversible active forgetting, and a backward causal-recall path, installed as one Rust binary for coding agents. | Single-machine and local-only; no OAuth connectors, hosted option, or team permissions, and AGPL-3.0 licensing. |
| [Mem0/OpenMemory](solutions/mem0-openmemory.md) | Evolve, Use | You need user/run-scoped memory for apps with hosted or self-hosted paths. | More of an app memory primitive than a complete second-brain workflow. |

### Memory Substrates

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [Zep/Graphiti](solutions/zep-graphiti.md) | Organize, Evolve, Use | You need temporal graph memory and Graph RAG under an application. | Not a complete user-facing second brain by itself. |
| [Cognee](solutions/cognee.md) | Organize, Evolve, Use | You need graph-oriented memory infrastructure with SDK, MCP, API, plugins, or cloud paths. | Requires application or workflow integration above it. |

### Platform Baselines

| Solution | Strongest lifecycle coverage | Best when | Main tradeoff |
|---|---|---|---|
| [ChatGPT Memory](solutions/chatgpt-memory.md) | Collect, Evolve, Use | You already live in ChatGPT and want platform-local personalization. | Platform-controlled visibility, retrieval, and export. |
| [Claude Projects/Claude Code](solutions/claude-projects-code.md) | Collect, Organize, Use | Your work lives inside Claude Projects, Claude Code, or Claude connectors. | Context is scoped to Claude workflows and plan/workspace controls. |
| [NotebookLM](solutions/notebooklm.md) | Collect, Organize, Use | You need grounded work over a bounded source set. | Not designed as a cross-tool evolving second brain. |

## Deep Dives

| Page | Use it for |
|---|---|
| [Chooser](comparisons/chooser.md) | Pick a starting solution by lifecycle gap and tradeoff. |
| [Solution Layers](comparisons/solution-layers.md) | Understand the app, workspace, API layer, substrate, or platform shape after choosing a lifecycle gap. |
| [Capability Matrix](comparisons/capability-matrix.md) | Compare lifecycle support, governance, operating burden, activation surfaces, and setup time. |
| [Capability Definitions](capabilities/README.md) | Understand the evaluation dimensions behind the matrix. |
| [Activation Evidence](capabilities/activation-evidence.md) | Evaluate whether retrieved memory was loaded, cited, refused, written back, or actually used. |
| [Setup Burden](comparisons/setup-burden.md) | See what you actually have to operate. |
| [Agent Activation](comparisons/agent-access.md) | Compare MCP, API, SDK, CLI, and plugin access as second-brain activation channels. |
| [Local vs Cloud](comparisons/local-vs-cloud.md) | Decide where memory should live. |
| [Personal vs Team](comparisons/personal-vs-team.md) | Compare solo, project, team, and organization fit. |
| [Assembled Stack vs App](comparisons/assembled-stack-vs-app.md) | Decide between a single product and a multi-tool local stack. |
| [Setup Guides](setup-guides/README.md) | Add hands-on setup notes only after verification. |
| [Examples](examples/README.md) | Describe concrete second-brain workflows and scenarios. |
| [Watchlist](watchlist.md) | Track promising systems that are not yet fully evaluated. |

## Sources

Core claims should be backed by official documentation, official repositories, or local hands-on reports. This repo should point to official setup docs instead of duplicating step-by-step installation instructions.

## How To Contribute

1. Pick the smallest contribution type that fits your evidence: core solution, capability/comparison update, setup guide, example, or watchlist entry.
2. Use [templates/system-profile.md](templates/system-profile.md) or [templates/capability-page.md](templates/capability-page.md).
3. Use primary sources or mark unverified fields as `Unknown`.
4. For core solution profiles, link the solution from the relevant chooser, comparison, and capability pages so readers can evaluate it through the main decision paths.
5. Open a PR with sources, verification notes, and any known limitations.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.

## Star History

<a href="https://www.star-history.com/?repos=aristoapp%2Fawesome-second-brain&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
 </picture>
</a>
