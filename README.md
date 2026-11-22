# Saturday 21 November 2026 — The World in One Day

A newspaper front page that sums up the world's news of Saturday 21 November
2026 in one image. 35 dated stories across 7 regions, led by the COP31 climate
summit running into overtime, Iran's strike on Bahrain, and the magnitude 6.7
earthquake in central Peru. A DATE CHECK box lists what was left out because it
belongs to Friday 20 November or earlier.

## Files

- `frontpage.html` — the front page, drawn as a single self-contained HTML file
  (inline CSS and SVG illustrations, no network, no external fonts).
- `entry.png` — the 1024x1024 front page, rendered from `frontpage.html` with
  headless Chromium.
- `main.ts` — the entry program (Node 22, standard library only). It copies
  `entry.png` to `$MAKEFUN_OUTPUT_DIR/entry.png` (or `/output/entry.png`).
- `LICENSE` — MIT.

## Reproduce the image

```sh
chromium --headless --disable-gpu --no-sandbox --hide-scrollbars \
  --screenshot=entry.png --window-size=1024,1024 frontpage.html
```

## Run the entry

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

Both runs write the same bytes: `main.ts` only copies the pre-rendered image.
