# Watchlist

These projects are relevant to AI second-brain architecture but are not yet full-profile entries in this repo. Move a project into `solutions/` only after source-backed research and clear official setup/evaluation links are ready.

| Project | Why it matters | Current status |
|---|---|---|
| Letta / MemGPT | Stateful agent architecture with memory blocks, archival memory, and agent-managed context. | Baseline candidate for agent-framework memory. |
| Mem.ai | AI notes app with API/MCP and consumer knowledge assistant positioning. | Candidate for AI notes / PKM product category. |
| Tana | Structured knowledge graph notes with Supertags and AI commands. | Candidate for schema-heavy PKM category. |
| Reflect | Encrypted AI notes app with backlinks and graph-oriented notes. | Candidate for AI notes / PKM category. |
| Capacities | Object-based knowledge studio. | Candidate for object-centric PKM category. |
| TideMind | Local-first AI second-brain positioning with knowledge graph claims. | Emerging local-first candidate. |
| Dory | Local-first shared memory daemon for MCP-aware agents. | Emerging local-first second-brain candidate. |
| Open Second Brain | Obsidian-native memory layer for agents. | Emerging Obsidian/MCP candidate; separate from OpenHuman. |
| MAGI | Persistent memory for AI agents. | Emerging AI-memory candidate. |
| [AccInt](https://github.com/maxbaluev/accreted-intelligence) | Local-first Work Model for coding agents that records commitments, approval gates, outcomes, and reusable runtimes, then uses outcome-scored memory to predict and replay verified paths through MCP. | Emerging agent-memory candidate for Use/Govern workflows; public repo ships installer/docs/plugins while the core memory engine is currently distributed as a private binary, so it is not yet a full evaluated profile. |
| [tracecraft](https://github.com/Arrmlet/tracecraft) | Serverless multi-agent coordination substrate using S3-compatible or Hugging Face storage for shared state, task claims, handoffs, and session traces. | Emerging coordination-substrate candidate; adjacent to agent memory but not a memory layer or second-brain system itself. |
| [screenpipe](https://github.com/screenpipe/screenpipe) | Local-first 24/7 screen and microphone capture daemon that indexes OCR, accessibility, and audio transcripts into a queryable SQLite store, with MCP, REST, and SDK access for AI tools and agents. | Emerging local-first context-collection candidate; covers the Collect lifecycle stage for second-brain workflows but leaves knowledge organization and memory evolution to layers above it. |
| [BrainTube](https://github.com/lildaddyo/braintube-mcp) | Hosted personal knowledge-base MCP server that ingests YouTube saves, articles, PDFs, Notion, and Obsidian into a per-user vector + graph store and exposes 52 tools (semantic search, entity/timeline traversal, resurfacing) over Streamable HTTP with OAuth 2.0 or API-key auth. | Emerging Use-layer activation candidate; hosted-only today with a Chrome capture extension and Official Registry / Smithery / Glama listings, so setup burden and personal/team governance surfaces still need source-backed evaluation before a full profile. |
| [Enhanciar](https://enhanciar.in) | Hosted company brain that answers from Slack, Gmail, Drive, Notion, Jira, Linear, GitHub, Zendesk and Postgres with a source link on every claim, then drafts the follow-up (reply, ticket, doc or calendar event) for a person to approve. Reachable from the web app, Slack, mobile, the API and a remote MCP server with API-key auth. | Emerging team-scope candidate for Use/Govern workflows; hosted-only and paid with bring-your-own AI key, so setup burden and retrieval quality still need source-backed evaluation before a full profile. |

## Promotion Rule

A watchlist item can become a core profile when it has:

- official docs or repo evidence
- deployment model
- setup burden and official setup links
- AI-tool activation surface
- context capture and retrieval/use model
- known limitations
- tradeoffs
