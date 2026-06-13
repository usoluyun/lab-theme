# lab-theme

A small, dependency-free CSS design standard with an editorial **"field notes"**
look — warm paper, Fraunces + Hanken Grotesk, vermillion / deep-green accents, and a
calm card grid with a sticky activity rail. Feels like a printed journal, not a generic
dashboard.

![status: building](https://img.shields.io/badge/status-building-2f5d4f)
![css: no build](https://img.shields.io/badge/css-no%20build-c4452f)

## Quick start

Add the fonts and the stylesheet to your page, then use the documented classes:

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,900;1,9..144,500&family=Hanken+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="theme.css" />
```

Or just copy [`starter.html`](starter.html) and replace its content.

## Design tokens (`:root`)

Re-skin by **overriding these in your own CSS** — never edit `theme.css`.

| Token | Hex | Use |
|-------|-----|-----|
| `--paper` | `#f4f0e8` | page background (dotted texture) |
| `--paper2` | `#ebe5d8` | secondary paper surface |
| `--card` | `#faf7f0` | card & panel surface |
| `--ink` | `#1c1a17` | primary text |
| `--soft` | `#6b6459` | muted / secondary text |
| `--line` | `#d6cebd` | hairline borders & dividers |
| `--line2` | `#c7bda8` | stronger border, disabled / `na` |
| `--accent` | `#c4452f` | vermillion — primary accent, `paused`, bad/down |
| `--accent2` | `#2f5d4f` | deep green — `building`/`shipped`, ok/up |

Body text = Hanken Grotesk; headings, card titles, stats and activity = Fraunces.

## Components

A quick map — see [`DESIGN.md`](DESIGN.md) for copy-paste snippets of each:

- **Page shell** — `.wrap` › `header` (`.brand`, `.eyebrow`, `h1 em`, `.sub`) + `.stat-strip`/`.stat`
- **Layout** — `.layout` (2-col) › `.grid` (cards) + `.panel` (sticky rail)
- **Card** — `.card` › `.card-top`, `.pname`, `.status.s-{idea|building|paused|shipped}`, `.ptag`, `.signals`, `.tags`
- **Signal row** — `.sig` › `.k`/`.v` with states `.ok` / `.bad` / `.na` and `.dot.{up|down|none}`
- **Activity feed** — `.feed` › `.ev` (`.msg`, `.meta`)

## Files

- `theme.css` — the stylesheet (single file, no build step).
- `DESIGN.md` — philosophy, tokens, fonts, and the full component class cheat-sheet.
- `starter.html` — a copy-to-start template.

## Used by

- [`lab-viewer`](https://github.com/usoluyun/lab-viewer) — consumes `theme.css` via git submodule.
- A bundled Claude Code skill (`lab-theme`) applies it on demand in any project.

## License

MIT — see [`LICENSE`](LICENSE).
