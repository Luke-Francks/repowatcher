# repowatcher

A lightweight, single-file GitHub repository monitor designed as an ambient second-monitor dashboard. Leave it open while you code — it watches your repo so you don't have to keep checking.

![repowatcher dark theme](https://img.shields.io/badge/theme-dark%20%7C%20mocha%20%7C%20light%20%7C%20latte-blue?style=flat-square)
![No dependencies](https://img.shields.io/badge/dependencies-none-green?style=flat-square)
![Single file](https://img.shields.io/badge/size-single%20HTML%20file-orange?style=flat-square)

---

## Features

- **Live repo stats** — stars, watchers, forks, open issues, branches, repo size
- **Latest commit** — message, author, avatar, and relative timestamp (updates every 30s)
- **Branch list** — up to 8 branches with default branch highlighted
- **Open issues** — up to 8 issues with labels and timestamps
- **Language breakdown** — segmented bar + percentage list with language colors
- **4 built-in themes** — Dark, Catppuccin Mocha, Light, Catppuccin Latte
- **Zero dependencies** — vanilla HTML, CSS, and JS. Just open the file.

---

## Usage

1. Download `repowatcher.html`
2. Open it in any browser
3. Type an `owner/repo` slug (e.g. `torvalds/linux`) and hit **LOAD**

That's it. No install, no build step, no server.

---

## Themes

Open `repowatcher.html` in a text editor and find the config block near the top of the `<script>` tag:

```js
// Change ACTIVE_THEME to switch themes:
// "dark" | "catppuccin-mocha" | "light" | "catppuccin-latte"
const ACTIVE_THEME = "dark";
```

Change the value and save. Done.

| Theme | Background | Accent | Overlays |
|---|---|---|---|
| `dark` | `#0a0c0f` | `#4a9eff` | Scanlines + grain |
| `catppuccin-mocha` | `#1e1e2e` | `#89b4fa` | None |
| `light` | `#f4f6fb` | `#1a6ef5` | None |
| `catppuccin-latte` | `#eff1f5` | `#1e66f5` | None |

---

## GitHub API & Rate Limits

Repowatcher uses the public GitHub REST API — no authentication required for public repositories. The unauthenticated rate limit is **60 requests/hour per IP**. Each repo load makes 5 requests in parallel.

If you hit the limit, repoatcher will show a warning banner. Rate limits reset hourly.

---

## Contributing

PRs welcome. Ideas worth contributing:

- Additional themes
- More stat cards (release count, contributor count, etc.)
- Auto-refresh on a configurable interval
- Electron/Tauri wrapper for true desktop app experience

---

## Author

Made by [Luke-Francks](https://github.com/Luke-Francks)
