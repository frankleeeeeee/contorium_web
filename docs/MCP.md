# Contorium MCP (Codex + Claude Code + Cursor)

stdio MCP server exposing Contorium **runtime memory** tools. Works alongside the **VS Code / Cursor extension** (sidebar + scanners); does not replace the extension UI.

## Tools

| Tool | Description |
|------|-------------|
| `store_memory` | Persist key/value memory under `.contora/mcp/memories.json` |
| `search_memory` | Keyword search over MCP memory entries |
| `get_memory` | Fetch one entry by key |
| `get_workspace_context` | Read `.contora/state.json` from the extension (focus, Git, files) |

## Build

From the repository root (installs `packages/mcp` deps automatically):

```bash
npm run build:mcp
# or
npm run compile
```

Portable entry: `bin/contorium-mcp-launch.cjs`  
stdio entry: `packages/mcp/dist/server.js` (after build)

## Platforms

| Platform | Plugin manifest | MCP config |
|----------|-----------------|------------|
| Codex | `.codex-plugin/plugin.json` | `.mcp.json` |
| Claude Code | `.claude-plugin/plugin.json` | `.mcp.claude.json` |
| Cursor | `.cursor-plugin/plugin.json` | `mcp.json` |

## Codex

After `npm run build:mcp`:

```bash
codex mcp add contorium -- node ./bin/contorium-mcp-launch.cjs
```

Install as plugin: [Codex plugins](https://developers.openai.com/codex/plugins/build). Local marketplace example: `.agents/plugins/marketplace.example.json` in the repo.

## Claude Code (plugin)

After `npm run build:mcp`, load locally:

```bash
claude --plugin-dir .
```

Or add MCP only (project scope):

```bash
claude mcp add --scope project contorium -- node ./bin/contorium-mcp-launch.cjs
```

Plugin MCP config uses `${CLAUDE_PLUGIN_ROOT}` and `${CLAUDE_PROJECT_DIR}` (see `.mcp.claude.json`).

Environment variables:

- `CONTORIUM_WORKSPACE` — workspace root (default: cwd, or walk up to find `.contora/state.json`)
- `CLAUDE_PROJECT_DIR` — set by Claude Code when spawning MCP (preferred for plugin installs)
- `CLAUDE_PROJECT_ROOT` — alias accepted by some integrations

## Cursor Agent (MCP)

Point Cursor MCP to root `mcp.json` (uses `${workspaceFolder}/packages/mcp/dist/server.js`). Requires `npm run build:mcp`. Detailed Cursor Agent docs on the [MCP page](../mcp/) — coming soon.

## VS Code extension

Install the **Contorium** VSIX for sidebar, event tracking, and **Copy AI-ready context**. MCP adds agent-callable tools for Codex, Claude Code, and Cursor Agent without duplicating the UI layer.
