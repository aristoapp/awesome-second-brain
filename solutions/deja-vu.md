# deja-vu

## Snapshot

- Website / docs: https://vshulcz.github.io/deja-vu/
- Repo: https://github.com/vshulcz/deja-vu
- Release: https://github.com/vshulcz/deja-vu/releases
- Package: Homebrew (`brew install vshulcz/tap/deja-vu`), prebuilt Go binaries, npm wrapper (`dsh-deja`)
- Company / maintainer: vshulcz, independent
- Status: Open-source Go CLI, MCP server, and local web viewer (`deja view`) with automated releases across macOS, Linux, and Windows
- Open source: Yes, MIT-licensed repository (recognized by GitHub)
- Deployment: Local-first. Single zero-CGO Go binary that runs on-demand via CLI or as a local stdio MCP server (`deja mcp`) with a local browser UI (`deja view`). No cloud, Docker, API key, or external LLM is required; all indexing and search stay on the machine.
- Primary users: Developers and agent operators who use one or more AI coding agents and want retroactive, shared local memory across all of them
- Best second-brain role: Retroactive cross-agent coding session memory layer with BM25F + temporal/causal graph retrieval, cross-agent handoff, and uncommitted code recovery
- Last reviewed: 2026-11-10

## One-line Summary

deja-vu (`deja`) is a local-first memory and recovery layer for AI coding agents, shipped as a single Go binary with an embedded MCP server (`deja mcp`), CLI, and local browser viewer (`deja view`). Instead of requiring agents to log memories ahead of time, it retroactively indexes the native session transcripts that 44 coding agents — including Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Antigravity, OpenCode, Zed, Cline, and Aider — already write to disk, combining field-weighted BM25F, temporal/file-overlap graph propagation, contradiction/abandonment detection, explicit rule pinning (`remember`), cross-agent session handoff (`handoff`), and file-level recovery of overwritten uncommitted code (`deja restore`).

## Second-Brain Fit

deja-vu fits best when your "second brain" problem is specifically coding-agent amnesia: repeating architectural explanations after `/compact`, switching between Claude Code, Codex, Cursor, or OpenCode mid-task, re-debugging errors solved weeks ago on the same machine, or losing uncommitted work when an agent overwrites a file. Because it reads the native JSONL and SQLite session logs that coding agents already store on disk, it works retroactively on months of existing history the moment it is installed.

In this repo's landscape, it sits alongside local-first agent memory layers like Vestige, Mnemosyne, and taOSmd, with two major structural differences:
1. **Retroactive transcript ingestion vs. write-path logging:** Rather than relying solely on agents calling a write tool during conversations, `deja` continuously indexes raw transcripts across 44 coding harnesses directly from disk, plus supports explicit durable decisions via `remember`.
2. **Zero-LLM / zero-embedding local retrieval:** Retrieval runs in milliseconds using a custom pure-Go BM25F + temporal/file/command co-occurrence graph and deterministic causal/error extraction (`fix`, `blame`, `how`, `orient`), avoiding local embedding model downloads or external API calls.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. Single zero-CGO Go binary installed via `install.sh`, Homebrew, or `go install`, running locally as a CLI and stdio MCP server (`deja mcp`). All indices and pinned memories live on the local filesystem. Zero cloud, Docker, API keys, or model downloads required. Prebuilt binaries cover macOS (ARM64/x86_64), Linux, and Windows. |
| Context capture | Automatic and retroactive across 44 local coding agents (Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Antigravity, OpenCode, Cline, Zed, Aider, Goose, Kimi, etc.) by parsing their native on-disk session logs incrementally. Also supports explicit agent/user memory writes via `remember`. |
| Knowledge organization | Indexes sessions into structured turns, files touched, shell commands, exit codes, error traces, git branches, and settled decisions (`remember`), linked by file/symbol overlap and temporal session chains. |
| Memory evolution | Incremental transcript re-indexing as sessions grow; detects dead-end / abandoned approaches and user rejections in transcripts so recalled hits carry warning markers rather than blindly repeating failed attempts; explicit `remember` rules persist project-scoped conventions. |
| Retrieval / use | Eight specialized MCP/CLI modes: `recall` (1–3 exact terms), `context` (full session story), `blame` (which session wrote/deleted a file or line), `fix` (what command resolved a specific error output on this machine), `how` (project build/test commands actually run), `orient` (recent project activity), `remember` (pin a rule), and `handoff` (resume another agent's session). Also includes `deja restore` to recover overwritten files from session logs and `deja view` for interactive timeline browsing. |
| Agent activation / write-back | Built-in stdio MCP server (`deja mcp`), auto-configured across detected coding agents via `deja install --auto`, plus native skills/plugins and CLI commands. Agents can query all retrieval modes and write durable project rules via `remember`. |
| Personal / team scope | Personal / single-machine by default, with per-repository and per-harness scoping filters (`project`, `harness`). Includes `deja export` for portable bundle sharing, though there is no hosted multi-user permission layer. |
| Feedback / correction | Transcript parser automatically flags user rejections/rollbacks on recalled steps; users and agents can inspect full session provenance (`context`, `blame`, `deja view`), manage pinned decisions, and Preview/Restore exact file states via `deja restore`. |
| Privacy / control | Strictly local-first and offline: no network telemetry, no cloud sync, and no external LLM or embedding API calls. |
| Setup / operations | Low. One shell or Homebrew command plus `deja install --auto` wires MCP configs and skills across installed coding agents; indexing ~19,000 sessions takes ~13.6 seconds locally with no external database or model server to maintain. |

## Strengths

- **Retroactive across 44 coding agents:** Immediately searches months of existing sessions from Claude Code, Codex, Cursor, Windsurf, OpenCode, Gemini CLI, and 38 more tools without prior instrumentation.
- **Zero-LLM, zero-model-download architecture:** Uses deterministic BM25F, command/error extraction, and session-graph scoring in a single Go binary, requiring no API keys, GPU, or local ONNX/embedding downloads.
- **Workflow-specific coding modes (`fix`, `blame`, `how`, `handoff`, `restore`):** Goes beyond generic text search to answer "which session changed this line," "what command fixed this exact error," "hand off my Claude Code session to Codex," and "restore the file an agent just overwrote."
- **Published LongMemEval-S benchmark reproducibility:** Documents a 97.2% Recall@5 result on LongMemEval-S with reproducible benchmark scripts in the repository.

## Limitations

- Purpose-built for AI coding agents and software engineering transcripts; it is not a general-purpose consumer second brain for email, calendar, PDFs, or OAuth SaaS apps.
- Retrieval relies on lexical/structural BM25F, identifier matching, and session-graph signals rather than dense vector embeddings, which excels on exact identifiers, paths, and error strings but is not designed for pure cross-lingual conceptual paraphrase without shared tokens.
- Local to the developer's machine; there is no hosted cloud service, team RBAC dashboard, or mobile app.

## Best For

- Developers using multiple AI coding tools (e.g., Claude Code + Cursor + Codex) who want shared session memory and 1-command cross-agent handoff (`deja handoff`).
- Engineers who want agents to stop repeating past mistakes or forgetting project build/test commands after `/compact`.
- Users who want strictly offline, zero-API-key, zero-LLM memory that indexes existing session logs in seconds.
- Recovering uncommitted code changes lost to accidental `git checkout`, `rm`, or agent overwrites via `deja restore`.

## Not Ideal For

- Non-technical second-brain workflows centered on web clipping, Notion/Google Docs OAuth connectors, email, or meeting audio.
- Teams looking for a managed cloud memory API or multi-tenant enterprise governance console.
- Workflows that require dense vector similarity over unstructured prose with no exact identifiers, file paths, or domain terms.

## Tradeoffs

deja-vu trades away general-purpose OAuth SaaS connectors and dense vector/LLM synthesis in exchange for instant, zero-dependency, retroactive indexing of every coding agent session already on your disk. Compare it directly with Vestige, Mnemosyne, and taOSmd when choosing a local-first MCP memory layer for coding agents: weight Vestige or Mnemosyne higher if you want dense vector embeddings and cognitive decay/consolidation loops over agent-logged facts, and weight deja-vu higher if you want immediate retroactive search across 44 coding harnesses, cross-agent session handoff, error-to-fix lookup, and uncommitted file recovery with zero model downloads.

## Official Setup / Evaluation Links

- Repository: https://github.com/vshulcz/deja-vu
- Website & live search demo: https://vshulcz.github.io/deja-vu/
- Interactive session viewer demo: https://vshulcz.github.io/deja-vu/view/
- Releases: https://github.com/vshulcz/deja-vu/releases

## Sources

- https://github.com/vshulcz/deja-vu
- https://github.com/vshulcz/deja-vu/blob/main/README.md
- https://vshulcz.github.io/deja-vu/
