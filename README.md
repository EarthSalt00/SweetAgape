# Sweet Agape 🍰

A single-file, glass-pastel bakery website. Open `index.html` in any modern browser to preview — no build step.

## Preview

```bash
# Any of these work:
xdg-open index.html         # Linux
open index.html             # macOS
python3 -m http.server 8080 # then visit http://localhost:8080
```

## What's inside

- `index.html` — the entire site (HTML + CSS + JS): pastel theme, glossy buttons, scroll-triggered hero video, p5.js alpha-mask vignette, newsletter capture modal (stored in `localStorage` under `sweetagape:newsletter`).
- `manifest.webmanifest` — PWA manifest. Makes it installable from **Open-WebUI-Client-for-Android** and other PWA-aware Android shells.
- `docs/SSH_SETUP.md` — how to authenticate to GitHub with SSH keys instead of passwords / PATs. **No private keys are committed.**

## Design notes

- **Pastel font palette** — gradient-clipped headings (pink → lilac → sky → mint), rounded UI font stack.
- **Glossy reflective buttons** — universal shading via layered gradients + inset highlights + soft drop shadows. See the `.btn` rule in `index.html`.
- **Scroll-triggered media** — the hero video stays paused until you scroll, then plays via `IntersectionObserver` and a scroll listener.
- **p5.js alpha mask** — a pastel gradient field is masked through a soft cherry silhouette, inspired by [p5js.org alpha-mask example](https://p5js.org/examples/imported-media-alpha-mask/).
- **n8ao-webgpu inspiration** — referenced for its soft glassy AO look; cards/buttons evoke a similar vibe via layered inset shadows + radial highlights, without requiring WebGPU. To add real WebGPU AO, drop [n8ao-webgpu](https://github.com/MarioAndF/n8ao-webgpu) into a Three.js/WebGPU canvas — left as a hookable extension.
- **ar.io / permaweb compatibility** — fully static, relative-paths only. It will work behind any [ar-io-console](https://github.com/ar-io/ar-io-console) gateway / ArNS name. To deploy, upload the folder via your preferred ar.io tooling and point an ArNS name at the manifest TX.
- **Open-WebUI-Client-for-Android compat** — `viewport-fit=cover`, `theme-color`, PWA manifest, tap-friendly button sizes.

## Newsletter

The modal stores subscribers locally for demo purposes. To wire it to a real list, replace the `localStorage.setItem(...)` block in `index.html` with a `fetch('/your-endpoint', {...})` call.

## Security

The GitHub PAT shared in chat should be considered compromised — see `docs/SSH_SETUP.md` step 5 to rotate, and use SSH for pushes.
