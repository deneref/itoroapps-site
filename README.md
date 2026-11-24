# itoroapps.com

Static site of itoroapps: app pages, privacy policies and support for léxito and Verbisto, and the aviso legal.
GitHub Pages from `main` / `/docs`, custom domain `itoroapps.com` (`docs/CNAME`), HTTPS by GitHub.
No scripts, cookies, analytics or external requests — so no cookie banner.

| URL | File | Used by |
|---|---|---|
| `/lexito/` | `docs/lexito/index.html` | App Store Marketing URL |
| `/lexito/privacy/` | `docs/lexito/privacy/index.html` | App Store Privacy Policy URL, app settings, paywall |
| `/lexito/support/` | `docs/lexito/support/index.html` | App Store Support URL |
| `/lexito/terms/` | `docs/lexito/terms/index.html` | paywall, store description |
| `/verbisto/` (EN), `/verbisto/ru/` | `docs/verbisto/index.html`, `docs/verbisto/ru/index.html` | Verbisto: App Store Marketing URL |
| `/verbisto/[ru/]privacy/`, `/verbisto/[ru/]support/` | `docs/verbisto/…/index.html` | Verbisto: App Store Privacy / Support URL |
| `/legal/` | `docs/legal/index.html` | footer of every page (LSSI art. 10) |
| `/meticulo/…` | redirect pages (`meta refresh` + `canonical`) | builds 1.0–1.0.3 open these forever — never delete |

Rules
- Policy text changes first here, then the app release; bump «Last updated» in the same change.
- Contact mailbox on every page: `lexito@itoroapps.com` (owner 21.11.2026; the app sends feedback there too, FIX-139).
- iPhone mock-ups in `docs/lexito/img/*.webp` are screenshots flattened into Apple's iPhone 17 Pro bezel
  (Apple Design Resources licence: mock-up depictions only — never commit the bare bezel PNG).
  Re-made with `bin/landing_bezel.swift` in the app repo.
- Requisites `{{OWNER_*}}` are filled once by `bin/legal_site.py` in the app repo.
- Spec, decisions and history: app repo `docs/legal/README.md`, TASK-20, TASK-22.

Search engines (owner 24.11.2026: one setup for both apps)
- `docs/robots.txt` lists two sitemaps: `docs/sitemap.xml` (home, léxito, legal — hand-written; add new léxito pages here) and `/verbisto/sitemap.xml` (generated).
- Home page: JSON-LD Organization `#org` + both apps — to add once the new home page lands.
- IndexNow key `docs/93833476d0c3446e3902c664fc65b705.txt` sits at the root, so one request may list pages of both apps.
- Never index `/meticulo/` (redirect stubs) — keep them out of sitemaps.

Local preview: `python3 -m http.server 8766 --bind 127.0.0.1 --directory docs`.

Verbisto
- `docs/verbisto/` is generated — never edit by hand. Source and build: repo `cerstys/verb`, `python3 -I design/instrumenty/sobrat.py`
  (writes this folder from the accepted design; images → WebP, font subset, SEO, sitemap, llms.txt, IndexNow key).
- Old `verbisto.itoroapps.com/*.html` pages are redirect stubs in `cerstys/verb` — keep them (App Store metadata links).
