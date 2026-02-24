# AOAI Landing Page

Marketing landing page for Autobahn Consultants' AI Division at [autobahnconsultants.ai](https://autobahnconsultants.ai).

## Overview

Single-page site with a futuristic dark aesthetic — glassmorphism panels, scanning green borders, grid overlays, and scroll-triggered animations. Embeds the interactive 3D pricing app from [Package-Selection](https://github.com/hudsonshank/Package-Selection) via iframe.

## Structure

Everything lives in one file (`index.html`) plus static assets:

```
aoai-landing/
├── index.html              # Full site (HTML + CSS + JS)
├── assets/
│   ├── logo-white.png      # Nav logo
│   ├── logo-hero.png       # Hero logo
│   ├── hero-bg.mp4         # Hero background video
│   └── cta-bg.mp4          # CTA section background video
└── pricing/
    ├── index.html           # Pricing app entry point
    ├── assets/              # Built JS/CSS bundles
    └── models/              # 3D car model files (GLB)
```

## Sections

- **Hero** — Full-screen video background with animated logo reveal
- **About** — "Who We Are" with unfold animation
- **Packages** — Embedded 3D pricing app (iframe with `?embed=true`)
- **Services** — Six capability cards with staggered scroll animations
- **Process** — Four-step workflow with slide-in reveals
- **CTA** — Video background with contact buttons
- **Footer**

## Running Locally

```bash
python3 -m http.server 8080
```

Opens at [http://localhost:8080](http://localhost:8080).

## Updating the Pricing App

The `pricing/` directory contains pre-built static files from the Package-Selection repo. To update:

```bash
cd /path/to/Package-Selection/autobahn-pricing
npx vite build
rm -rf /path/to/aoai-landing/pricing/assets
cp -r dist/assets /path/to/aoai-landing/pricing/assets
cp dist/index.html /path/to/aoai-landing/pricing/index.html
```

## License

Proprietary — Autobahn Consultants
