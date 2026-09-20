# Consensus integration

Consensus is ScholarFlow's primary provider for academic discovery and evidence synthesis. Use only the official streamable HTTP MCP endpoint:

`https://mcp.consensus.app/mcp`

## Connection check

Before literature discovery, inspect the tools actually available in the current session. If a Consensus search tool is present, use it. Do not infer connection from this file, the dependency declaration, or the user's account state.

If it is missing, explain that ScholarFlow is installed but its Consensus dependency is not connected. Give the official Codex commands:

```text
codex mcp add consensus --url https://mcp.consensus.app/mcp
codex mcp login consensus
```

Ask the user to restart Codex after connecting. Do not enter credentials, create API keys, or claim authentication succeeded without observing the connected tool.

## Search strategy

1. Translate the research profile into focused academic queries using the equation or object, phenomenon or solution type, method, synonyms, exclusions, and date window.
2. Run at least one Consensus search for discovery or evidence synthesis. Use separate queries only for materially different concepts, such as topic search, author/seed-paper expansion, or citation relationships.
3. Preserve the exact query and links to underlying papers. Record Consensus as the provider.
4. Treat generated summaries as navigation aids. Verify theorem assumptions, mathematical claims, DOI metadata, and quotations against the paper or authoritative publisher record.
5. Supplement thin or highly specialized results with the open sources in `retrieval.md`, clearly labeling which candidates came from which provider.
6. Merge and deduplicate all candidates before the `精读 / 保存 / 忽略` gate.

## Failure and quota handling

- Missing or unauthenticated tool: stop and offer connection instructions; use open sources only if the user chooses that fallback.
- Empty or weak results: broaden terminology once, then supplement with specialist/open sources.
- Rate limit or quota error: do not loop. Report it and offer to continue with open sources.
- Never expose tokens, credentials, private profile content, or unpublished ideas in a search query. Query only the minimum public research concepts needed.
