# screenpipe

## Snapshot

- Website / docs: https://screenpipe.com and https://docs.screenpi.pe
- Repo: https://github.com/screenpipe/screenpipe
- Company / maintainer: Screenpipe
- Status: Production desktop app, local daemon, API, and published MCP package
- Open source: Source-available under the Screenpipe Commercial License. Source builds permit personal non-commercial, nonprofit, educational, and research use; commercial use requires a paid license. Official prebuilt apps have separate terms and free/paid plans. Earlier MIT-licensed versions remain under MIT.
- Deployment: Desktop app and local daemon on macOS, Windows, and Linux. Capture data is stored in local SQLite and media files by default; cloud AI, integrations, archive, sync, and team sharing are optional paths.
- Primary users: Individuals and teams that want automatic work-context capture for search, review, and AI-agent workflows
- Best second-brain role: Continuous local collection and retrieval of screen, audio, input, browser, and meeting context
- Profile reviewed: 2026-07-14; license and setup refreshed: 2026-09-16

## One-line Summary

screenpipe continuously captures work context on a computer, stores it locally, and exposes it through a desktop timeline, local REST API, CLI, scheduled pipes, and an MCP server for AI tools.

## Second-Brain Fit

screenpipe is strongest at Collect and Use. It gathers context that people usually do not save manually, including screen text, audio transcripts, input events, browser metadata, and meetings, then makes those records searchable by a person or an agent. It also provides meaningful Govern controls for pausing capture, excluding sources, managing retention, and deleting data. It is weaker as an automatic Organize or Evolve layer: raw activity can be tagged, summarized, or converted into explicit memories by users, pipes, or agents, but it does not become a governed knowledge graph automatically.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Desktop app and local daemon on macOS, Windows, and Linux. Screen, audio, input, browser, and meeting data is stored under the local screenpipe data directory by default. Optional AI providers, integrations, archive, sync, and team sharing can send selected or encrypted data off-device. |
| Context capture | Built-in screen capture with accessibility text and OCR fallback, microphone and system-audio transcription, input events, browser metadata, and meeting records. |
| Knowledge organization | Timestamped local records support search filters, meetings, speakers, tags, activity summaries, and explicit memories. Pipes and agents can create summaries or other artifacts, but there is no automatic governed knowledge graph. |
| Memory evolution | Partial. Users, MCP tools, and scheduled pipes can create or update memories, tags, meetings, and artifacts; automatic consolidation, deduplication, and stale-memory refresh are not the primary built-in model. |
| Retrieval / use | Desktop timeline and search plus a local REST API. The stdio MCP server supports content, keyword, element, meeting, speaker, memory, device, and pipe workflows; the optional HTTP MCP transport currently has narrower tool coverage. |
| Agent activation / write-back | The published `screenpipe-mcp` package connects Codex, Claude, Cursor, and other MCP clients. Its full stdio tool set can search captured context and write back through memories, tags, meeting updates, notifications, and pipe management. |
| Personal / team scope | Personal-first local memory. Team features share encrypted pipe and recording-policy configurations; broader organization search and administration are separate enterprise surfaces. |
| Feedback / correction | Built-in controls cover pausing capture, included or excluded windows and URLs, audio and clipboard capture, speaker/meeting edits, tags, explicit memories, retention, archive, and permanent range deletion. |
| Privacy / control | Local-first by default, with documented boundaries for every optional cloud or integration path. Controls include ignored sources, API authentication, local or enclave PII filtering, retention modes, archive, and deletion. |
| Setup / operations | Low-medium. Install the app, let it capture data, and use the built-in timeline; agent access adds an MCP connection. The app can configure it through Settings → Connections; manual setup uses `npx -y screenpipe-mcp@latest` and the local API key documented in the setup guide. Continuous capture still requires storage, privacy, and retention choices. |

## Strengths

- Captures work context that note- and connector-based systems often miss, including cross-app screen activity and conversations.
- Keeps capture, search, and storage local by default while documenting the optional paths that can send data elsewhere.
- Provides multiple activation surfaces: desktop UI, local API, CLI, scheduled pipes, and a published MCP server.
- Gives users direct controls over capture sources, retention, archive, redaction, and deletion.

## Limitations

- Raw activity does not automatically become a curated or governed knowledge base; organization and consolidation require user, pipe, or agent workflows.
- Continuous capture creates privacy, consent, disk-usage, and retention responsibilities even when storage is local.
- The current repository is source-available under a commercial license, not an OSI-approved open-source license.
- The optional HTTP MCP transport has narrower tool coverage than the full stdio server.

## Best For

- People who want automatic, local work-history capture instead of manually saving every useful tab, call, or action.
- Agent users who need searchable evidence of what actually happened across apps and conversations.
- Teams evaluating task mining, workflow reconstruction, SOP generation, or automation discovery from real work context.

## Not Ideal For

- Users who want an automatically consolidated knowledge graph with mature review and correction workflows out of the box.
- Environments where continuous screen or audio capture is unacceptable, even with source filters and local storage.
- Commercial self-hosting or embedding use cases that require an OSI-approved license.

## Tradeoffs

screenpipe trades automatic knowledge curation for unusually broad, local-first collection. It can give a second brain or agent much richer evidence about real work, but users still need to decide what should be retained, excluded, summarized, promoted into durable memory, or shared with an external model or team.

## Official Setup / Evaluation Links

- [Desktop and CLI installation](https://github.com/screenpipe/screenpipe#install)
- [MCP server setup](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp)
- [Official app plans](https://screenpipe.com/pricing)
- [Local REST API reference](https://docs.screenpi.pe/cli-reference)
- [Privacy data flow](https://docs.screenpi.pe/privacy-data-flow)
- [Team configuration and encryption](https://docs.screenpi.pe/teams)

## Sources

- [screenpipe repository and product overview](https://github.com/screenpipe/screenpipe)
- [Screenpipe Commercial License](https://github.com/screenpipe/screenpipe/blob/main/LICENSE.md)
- [privacy data-flow documentation](https://docs.screenpi.pe/privacy-data-flow)
- [MCP package documentation](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp)
- [local API documentation](https://docs.screenpi.pe/cli-reference)
- [team documentation](https://docs.screenpi.pe/teams)
