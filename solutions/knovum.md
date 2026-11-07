# Knovum

## Snapshot

- Website / repo: https://github.com/madebyzan/knovum
- Company / maintainer: Zan (@madebyzan)
- Status: Active public repo (releases v0.3.x)
- Open source: Yes (MIT)
- Deployment: Cross-platform desktop application built on Tauri 2 + Rust + Vue 3 for macOS and Windows. Local SQLite and embedded LanceDB vector database; 100% on-device model execution.
- Primary users: Researchers, developers, and knowledge workers who want visual spatial synthesis, audio capture, and grounded citations without cloud lock-in.
- Best second-brain role: Local-first 2D spatial canvas and knowledge workspace with on-device speech recognition, JSON Canvas interoperability, and bidirectional MCP connectivity.
- Last reviewed: 2026-11-07
- Reviewed evidence: Public repository `README.md`, release notes (`v0.3.0`, `v0.3.1`, `v0.3.2`), and architecture documentation (`docs/architecture.md`, `docs/system-architecture.md`).

## One-line Summary

Knovum is a desktop-native, local-first AI knowledge workspace on an infinite 2D canvas featuring bidirectional JSON Canvas support, auditable grounded citations, on-device Whisper dictation, and embedded LanceDB vector search.

## Second-Brain Fit

Knovum approaches the second brain through **spatial synthesis and citation provenance**: instead of a chat-only interface or flat document list, notes and sources live on an infinite 2D canvas (supporting the open [JSON Canvas](https://jsoncanvas.org/) standard). Users and local models arrange cited source chunks, audio transcripts, media cards, and connected cards into visual clusters. Grounded citations maintain bidirectional links between extracted facts and source documents. All model inference (Whisper speech-to-text, speaker diarization, VoxCPM2 speech synthesis, Big LaMa inpainting, and text embeddings) runs locally inside a native Rust worker layer, ensuring strict data sovereignty and zero telemetry.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Native desktop application for macOS and Windows built with Tauri 2 and Rust. Structured metadata is stored in local feature-owned SQLite databases with automated schema migrations; vector embeddings live in an embedded LanceDB store. All data resides in standard local application data directories. |
| Context capture | Live system-wide push-to-talk dictation with automatic 16 kHz mono resampling feeding on-device Whisper models; speaker diarization via Pyannote/CAM++; interactive link cards with media previews (powered by embedded yt-dlp); local image inpainting (Big LaMa) with depth layer separation; and multi-section canvas export. |
| Knowledge organization | Bidirectional JSON Canvas (.canvas) support allowing seamless interoperability with Obsidian; structured knowledge graphs with real-time health auditing (detecting orphaned items, circular references, and broken links); and cross-Space content transfer that moves derived items together with source assets to preserve dependency integrity. |
| Memory evolution | Knowledge graph health checks identify stale or disconnected cards; Task Center provides resilient background job enrichment that pauses gracefully when model weights are missing; and selection export captures arbitrary spatial arrangements into reusable shareable units. |
| Retrieval / use | Hybrid retrieval fusing SQLite full-text search with embedded LanceDB vector search. Grounded citations provide auditable provenance back to source documents, avoiding unverified hallucinated recall. |
| Agent activation / write-back | Bidirectional Model Context Protocol (MCP) support: connects to external desktop coding agents (Claude Code, Codex CLI, Cursor) through an interactive login shell environment adapter, while exposing a loopback MCP server over your local knowledge space. |
| Personal / team scope | Local personal desktop knowledge space. Spaces can be partitioned by domain or project. No mandatory cloud accounts or external telemetry. |
| Feedback / correction | Visual 2D canvas with direct interactive manipulation; customizable keyboard shortcuts across 11 languages with chord conflict detection; and clear citation provenance allowing users to trace and correct synthesized statements back to raw source text. |
| Privacy / control | 100% local-first and on-device. No telemetry, no cloud API prerequisites, and fully open source under the MIT license. |
| Setup / operations | Installable via prebuilt GitHub Releases (.dmg for macOS, .msi/.exe for Windows). Configurable domestic mirror support (`HF_ENDPOINT`) for downloading on-device model weights. |

## Strengths

- True local-first architecture: native Rust engine with zero Python runtime bloat in release builds.
- Multimodal on-device matrix: combines Whisper speech recognition, diarization, local TTS, image inpainting, and vector embeddings in one unified desktop binary.
- Open format interoperability via standard JSON Canvas (.canvas) and plain Markdown.
- Strong citation provenance prevents agent hallucinations from contaminating durable notes.

## Limitations

- Single-user desktop focus: does not provide built-in multi-user real-time sync server out of the box (sync depends on local file sync or git).
- Model weights require initial local disk space (Whisper, inpainting, and embedding weights).

## Best For

Users and researchers who prefer visual, spatial organization over chatbot threads, need on-device audio dictation and transcription, and demand strict offline privacy without cloud dependencies.
