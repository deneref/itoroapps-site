# itoroapps.com

Static site of itoroapps: app page, privacy policy, terms and support for léxito, and the aviso legal.
GitHub Pages from `main` / `/docs`, custom domain `itoroapps.com` (`docs/CNAME`), HTTPS by GitHub.
No scripts, cookies, analytics or external requests — so no cookie banner.

| URL | File | Used by |
|---|---|---|
| `/lexito/` | `docs/lexito/index.html` | App Store Marketing URL |
| `/lexito/privacy/` | `docs/lexito/privacy/index.html` | App Store Privacy Policy URL, app settings, paywall |
| `/lexito/support/` | `docs/lexito/support/index.html` | App Store Support URL |
| `/lexito/terms/` | `docs/lexito/terms/index.html` | paywall, store description |
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

Local preview: `python3 -m http.server 8766 --bind 127.0.0.1 --directory docs`.
