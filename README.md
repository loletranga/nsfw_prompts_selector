# NSFW Prompt Selector

A single-file, offline prompt builder for adult (NSFW) image generation. Browse 825 curated English keywords across 15 categories, toggle them into a prompt, roll one random keyword per category, and copy the result to your clipboard — all from one HTML file with zero dependencies.

> ⚠️ **Explicit content — 18+ only.** This repository contains sexually explicit terminology. Do not view or use it if you are a minor or if such material is illegal in your jurisdiction.

![Screenshot](docs/screenshot.png)

## Features

- **825 keywords / 15 categories** — positions, poses, foreplay, group play, body types, outfits, adult toys, scenarios, and more.
- **Toggle to compose** — click a keyword to add it to the prompt box, click again to remove it; the side nav and every category header show live selection counts
- **Random** — roll one random keyword from *every* category at once (15 keywords per roll)
- **Copy** — one click copies the composed prompt to the clipboard
- **Trilingual interface** — Chinese / Japanese / English category names and glossaries, switchable in the header; keywords always stay in English; your choice is remembered between visits
- **Zero dependencies** — one self-contained `index.html`; works offline, straight from a double-click
- **Responsive & accessible** — dark UI that scales from phones to ultrawide monitors; keyboard-operable with visible focus; honors `prefers-reduced-motion`

## Getting started

No build step and no server required:

1. Clone or download this repository
2. Open `index.html` in any modern browser
3. Pick keywords, hit **Random** if you feel lucky, then **Copy**

To put it online, enable GitHub Pages (*Settings → Pages → deploy from branch*) — `index.html` sits at the repo root, so it is served automatically.

## Repository layout

```
.
├── index.html    # the entire app: markup, styles, logic, and keyword data
├── prompts.md    # source keyword tables (English keyword + Japanese gloss per category)
└── docs/
    └── screenshot.png
```

## Modifying the data

The keyword data is compiled into `index.html` as a JSON array at the top of the `<script>` block:

```js
const DATA = [
  {
    name: "体位",            // original Japanese category name
    zh: "体位",              // Chinese category name
    en: "Sex Positions",     // English category name
    items: [
      ["missionary position", "正常位", "传教士式"],  // [keyword, Japanese, Chinese]
      ...
    ],
  },
  ...
];
```

Edit entries directly in `index.html` and reload — that's it. 
