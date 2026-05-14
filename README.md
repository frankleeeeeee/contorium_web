# Contora Web

Static marketing site for **Contora** — a persistent memory layer for AI-assisted coding in [VS Code](https://code.visualstudio.com/) and [Cursor](https://cursor.com/). The page explains workspace awareness, Git context, session recovery, and local-first behavior, and links to the extension and source repository.

## Contents

| File        | Role                                      |
| ----------- | ----------------------------------------- |
| `index.html` | Page structure, copy, and inline scripts |
| `styles.css` | Layout and visual styling                |
| `logo.png`   | Favicon and header logo (referenced in HTML) |

No build step or package manager is required.

## Preview locally

Open `index.html` in a browser, or serve the folder so asset paths and fonts behave like production:

```bash
# Python 3
python -m http.server 8080

# Node (npx)
npx --yes serve .
```

Then visit `http://localhost:8080` (port may vary with `serve`).

## Related links

- **Extension repository:** [github.com/frankleeeeeee/contora](https://github.com/frankleeeeeee/contora)
- **VS Marketplace:** search for “contora” in the [Visual Studio Marketplace](https://marketplace.visualstudio.com/vscode) to install the extension.
