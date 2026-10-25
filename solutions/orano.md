# Orano

## Snapshot

- Website / docs: https://oranoai.com/ (MCP overview: https://oranoai.com/mcp)
- Company / maintainer: ORANO (founder: Manu Parasuraman)
- Status: Active (shipped iOS and Android apps)
- Open source: No
- Deployment: Hosted. Mobile apps on iOS and Android; a personal read-only MCP server over streamable HTTP with bearer personal API keys (no OAuth yet); machine-readable connection details at https://oranoai.com/mcp.json
- Primary users: Individuals who save short-form video and web content (builders, upskillers, learners, researchers)
- Best second-brain role: Capture-to-action layer: turns saved social and web content into structured projects and agent-readable personal memory
- Last reviewed: 2026-09-05

## One-line Summary

Orano is a hosted mobile app that turns saved Reels, videos, articles, and PDFs into structured projects (summary, key takeaways, ordered tasks, research, learning roadmaps) and exposes that library to the user's own AI agent through a personal read-only MCP server.

## Second-Brain Fit

Orano is strong on the Collect and Organize stages for social and web content: ingestion fetches transcripts, captions, and page context, and an LLM pipeline produces durable structure (projects, tasks, memory facts, embeddings) from raw saves. Use is covered through in-app search and chat plus MCP read access for external agents. It is not a general workspace: capture is oriented to saved content rather than arbitrary local files, and agent access is read-only by design.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted SaaS; no self-hosting. Apps are free to download; ORANO Pro is an in-app subscription and MCP access requires a paid plan. |
| Context capture | Automatic from saved sources: iOS Share Extension, Android share target, paste-a-link, and uploads (including local video and PDF). Ingestion fetches captions, transcripts, page text, and bounded visual context. |
| Knowledge organization | LLM extraction into projects with summary, key takeaways, category, priority, estimated time/cost, ordered tasks, and optional research context and learning roadmaps; curated, user-editable memory facts; pgvector embeddings. |
| Memory evolution | Partial: curated memory facts carry confidence and decay scoring; background workers refresh embeddings and profile preferences. No full consolidation/dream cycle. |
| Retrieval / use | In-app global and per-project search and chat assistant; MCP tools: list_projects, get_project, get_project_context, search_library, get_memory_facts, get_pending_handoffs (see https://oranoai.com/mcp.json). |
| Agent activation / write-back | Read-only MCP server for the user's own agents (ChatGPT, Claude, Cursor, Ollama and other MCP clients) with bearer personal API keys and a 240 calls/hour per-user budget. No agent write access by design; app-triggered handoffs are acknowledged through get_pending_handoffs. |
| Personal / team scope | Personal scope only; no team or shared workspaces. |
| Feedback / correction | Projects, tasks, and memory facts are user-editable in the app; account and data deletion paths are documented. |
| Privacy / control | Personal API keys (max 10 active) with required scope orano:read; MCP is per-user and read-focused; documented privacy policy and account deletion (https://oranoai.com/delete-account/). |
| Setup / operations | Low: install the app, save content; MCP access requires a paid web plan and manual key creation. |

## Strengths

- Strong automatic capture for short-form video and social content, which most second-brain tools treat as out of scope.
- Saves become actionable structure (ordered tasks, roadmaps), not just stored links.
- Personal read-only MCP server lets a user's existing agent read their library without giving it write access.
- Curated memory facts are inspectable and editable in the app.

## Limitations

- Hosted and closed-source; no self-hosting or local deployment.
- Agent access is read-only; agents cannot create or update projects, tasks, or memory through MCP.
- No OAuth for MCP yet: users create a bearer key manually.
- Personal scope only; no team spaces.

## Best For

- People whose input is mostly Reels, Shorts, videos, and articles and who want structure and tasks out of them.
- Users who want their existing AI agent (ChatGPT, Claude, Cursor) to read their saved library through MCP.
- Learners who want study roadmaps generated from saved educational content.

## Not Ideal For

- Teams needing shared knowledge bases or write-back from agents.
- Self-hosting or local-first users.
- Users who primarily capture handwritten notes or arbitrary local file trees.

## Tradeoffs

Compared with note-first systems (Hjarni, Obsidian, Logseq), Orano captures and structures automatically but gives up direct authorship control and self-hosting. Compared with memory APIs (Supermemory, Mem0), it is consumer-oriented: capture comes from a mobile app rather than developer integrations.

## Official Setup / Evaluation Links

- Product and workflow: https://oranoai.com/
- MCP overview and connection details: https://oranoai.com/mcp
- Machine-readable MCP manifest: https://oranoai.com/mcp.json
- Support and FAQs: https://oranoai.com/support.html

## Sources

- Official site pages listed above (reviewed 2026-09-05).
- App Store listing: https://apps.apple.com/us/app/orano-ai/id6791454509
- Google Play listing: https://play.google.com/store/apps/details?id=com.oranoai.app
