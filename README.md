# Sweet Agape

Bakery Website.

## Preview

Three ways to view the working site, easiest first.

### 1. GitHub Pages (shareable URL, no install)

1. Push this branch (already done).
2. On GitHub, go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. Pick branch `claude/add-preview-functionality-mrGTp` (or `main` after merge), folder `/ (root)`, and click **Save**.
5. Wait ~1 minute. GitHub will show a URL like `https://earthsalt00.github.io/sweetagape/`. Open it.

### 2. Local preview (one command, no install beyond Python)

From the repo root:

```
python3 -m http.server 8000
```

Then open <http://localhost:8000> in a browser.

### 3. Open the file directly

Double-clicking `index.html` will **not** work — the site is a JavaScript module bundle and browsers block ES modules loaded from `file://`. Use option 1 or 2.

## What's here

- `index.html` — entry page
- `assets/` — compiled JS, CSS, and cake images
- `favicon.svg` — site icon
