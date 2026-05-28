# Contorium Web

Static marketing site for **Contorium** — runtime memory infrastructure for AI coding agents (Cursor, Claude Code, Codex, MCP). Covers installation, MCP setup, and architecture.

## Site structure

| Path | Page |
| ---- | ---- |
| `index.html` | Home — hero, problem, demo, how it works, MCP overview, memory, features |
| `mcp/` | MCP setup per [docs/MCP.md](docs/MCP.md) and [mcp/README.md](mcp/README.md) |
| `architecture/` | Memory engine pipeline and `.contora/` layout |
| `docs/` | Extension install, MCP quick start, BYOK |
| `blog/` | Planned articles (AI memory, MCP, agent workflows) |

## Files

| File | Role |
| ---- | ---- |
| `index.html` | Home page |
| `styles.css` | Shared layout and styling |
| `logo.png` | Favicon and header logo |
| `contorium.mp4` | Hero demo video |
| `docs/MCP.md` | MCP reference (tools, build, Claude Code, Cursor) |

No build step required.

## Preview locally

```bash
python -m http.server 8080
# or
npx --yes serve .
```

Visit `http://localhost:8080` — subpages at `/mcp/`, `/architecture/`, `/docs/`, `/blog/`.

## Related links

- **Repository:** [github.com/ContoriumLabs/contorium](https://github.com/ContoriumLabs/contorium)
- **VS Marketplace:** [marketplace.visualstudio.com](https://marketplace.visualstudio.com/search?term=contorium&target=VSCode&category=All%20categories&sortBy=Relevance)
- **Open VSX:** [open-vsx.org](https://open-vsx.org/?search=contorium&sortBy=relevance&sortOrder=desc)
- **MCP docs:** [docs/MCP.md](docs/MCP.md)
