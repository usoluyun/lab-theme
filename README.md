# lab-theme

A small, dependency-free CSS design standard with an editorial "field notes"
look — warm paper, Fraunces + Hanken Grotesk, vermillion/deep-green accents, and
a calm card grid with a sticky activity rail.

![status: building](https://img.shields.io/badge/status-building-2f5d4f)

## Use

1. Add the Google Fonts `<link>` and `theme.css` to your page.
2. Use the classes documented in [`DESIGN.md`](DESIGN.md).

Or just copy [`starter.html`](starter.html) and replace its content.

```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,900;1,9..144,500&family=Hanken+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet" />
<link rel="stylesheet" href="theme.css" />
```

Re-skin by overriding the `:root` tokens (see DESIGN.md) — no need to edit
`theme.css`.

## Files

- `theme.css` — the stylesheet (single file, no build).
- `DESIGN.md` — tokens, fonts, and the component class cheat-sheet.
- `starter.html` — a copy-to-start template.

## License

MIT — see [`LICENSE`](LICENSE).
