# Agent Activation / Write-back

## What This Capability Means

Agent activation and write-back define how AI tools search, retrieve, cite, write, update, or maintain the second brain while doing work. Some systems also expose a first-party chat surface, which matters when users want to query the brain before wiring up an external agent.

## Evaluation Questions

- Is access available through MCP, API, SDK, CLI, plugins, or platform-only tools?
- Can AI tools write back?
- Is access scoped by user, source, project, or workspace?
- Can you verify the host AI tool actually used the memory surface?

## Scoring Guidance

Use this capability to decide whether the second brain is actually usable during AI-assisted work, not just whether storage is configured. A solution scores higher when an external AI tool can read and write memory through a documented surface, scope calls correctly, and show evidence that the host actually invoked the memory surface during work.

For the per-solution comparison, see [../comparisons/agent-access.md](../comparisons/agent-access.md).

## Sources

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Hyperspell MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Vestige repository](https://github.com/samvallad33/vestige)
- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Tale MCP knowledge retrieval](https://docs.tale.dev/develop/mcp-endpoint)
- [Tale editor configurations](https://docs.tale.dev/develop/use-tale-from-your-editor)
