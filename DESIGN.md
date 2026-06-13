# lab-theme — design standard

An editorial "field notes" aesthetic: warm paper, a characterful serif display
face, restrained vermillion/green accents, and a calm card grid with a sticky
activity rail. Built to feel like a printed journal, not a generic dashboard.

> Drop in two fonts + `theme.css`, then use the classes below. No build step, no
> dependencies.

---

## 1. Fonts

Add to `<head>` (Fraunces = display serif, Hanken Grotesk = body sans):

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,900;1,9..144,500&family=Hanken+Grotesk:wght@400;500;600;700&display=swap"
  rel="stylesheet"
/>
<link rel="stylesheet" href="theme.css" />
```

Body text is Hanken Grotesk; headings, card titles, stats, and the activity feed
use Fraunces (often italic for flourishes via `h1 em` and `.panel h2`).

## 2. Tokens (`:root`)

| Token        | Hex        | Use                                              |
|--------------|------------|--------------------------------------------------|
| `--paper`    | `#f4f0e8`  | page background (with a dotted texture)          |
| `--paper2`   | `#ebe5d8`  | secondary paper surface                          |
| `--card`     | `#faf7f0`  | card & panel surface                             |
| `--ink`      | `#1c1a17`  | primary text                                     |
| `--soft`     | `#6b6459`  | muted / secondary text                           |
| `--line`     | `#d6cebd`  | hairline borders & dividers                      |
| `--line2`    | `#c7bda8`  | stronger border, disabled/`na` state             |
| `--accent`   | `#c4452f`  | vermillion — primary accent, `paused`, bad/down  |
| `--accent2`  | `#2f5d4f`  | deep green — `building`/`shipped`, ok/up         |

Override any token in your own `:root` to re-skin without touching `theme.css`.

## 3. Components (class cheat-sheet)

### Page shell
```html
<div class="wrap">
  <header>
    <div class="brand">
      <span class="eyebrow">live · poc lab</span>
      <h1>The <em>Lab.</em></h1>
      <p class="sub">A short editorial standfirst goes here.</p>
    </div>
    <div class="stat-strip">
      <div class="stat"><div class="n">4</div><div class="l">projects</div></div>
    </div>
  </header>
  <!-- content -->
  <footer>“The work is the proof.”</footer>
</div>
```
`.eyebrow` shows a pulsing accent dot; `h1 em` renders an italic accent word.

### Layout (two-column: content + sticky rail)
```html
<div class="layout">
  <main class="grid"><!-- .card items --></main>
  <aside class="panel">
    <h2>Recent activity</h2>
    <div class="feed"><!-- .ev items --></div>
  </aside>
</div>
```
`.grid` is a responsive 2-col card grid; `.panel` is a sticky sidebar.

### Card + status pill
```html
<article class="card">
  <div class="card-top">
    <span class="pname">project name</span>
    <span class="status s-building">building</span>
  </div>
  <p class="ptag">One-line description.</p>
  <!-- .signals -->
  <div class="tags"><span class="tag">rust</span></div>
</article>
```
Status variants: `s-idea`, `s-building`, `s-paused`, `s-shipped`. Cards lift and
grow an accent side-bar on hover.

### Signal rows
```html
<div class="signals">
  <div class="sig"><span class="k">Build / test</span>
    <span class="v"><span class="ok">passing</span></span></div>
  <div class="sig"><span class="k">Service</span>
    <span class="v"><span class="dot up"></span> live</span></div>
</div>
```
Value states: `.ok` (green), `.bad` (vermillion), `.na` (muted). Status dots:
`.dot.up`, `.dot.down`, `.dot.none`.

### Activity feed
```html
<div class="ev">
  <div class="msg">scaffold</div>
  <div class="meta"><b>lab-viewer</b> · 1h ago</div>
</div>
```
A vertical timeline with accent nodes; `.msg` is Fraunces, `.meta` is uppercased.

### Tags & footer
`.tags` wraps `.tag` chips (each prefixed with an em-dash). `footer` is centered
italic Fraunces.

## 4. Quick start

Copy `starter.html` and replace its content, or add the fonts `<link>` +
`theme.css` to any page and use the classes above.

---

Upstream: https://github.com/usoluyun/lab-theme · MIT.
