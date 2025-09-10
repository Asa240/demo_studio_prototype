# Demo Studio Prototype

Single-page Vue 3 + Vuetify prototype bundled in one `index.html` for rapid iteration on:
- Navigation information architecture
- Getting Started template (overview, screenshots lightbox, video stub, quick start steps, resources, limitations, version, CTA)
- Dark mode theming + comfort styling (radial accents, soft translucent panels)

## Tech Stack
- Vue 3 (global build) + Vuetify 3 (CDN) – no build tooling required
- Material Design Icons (CDN)
- Pure CSS variables for design tokens & theming

## Running Locally
Just open `index.html` in a modern browser. (Optional) Use a simple static server for correct relative paths:

```bash
python3 -m http.server 8000
# then browse to http://localhost:8000/
```

## Project Structure
```
index.html         # Entire SPA (HTML + CSS + JS)
vuetify.min.css/js # Vendor (unchanged)
materialdesignicons.min.css
screenshots/       # Screenshot assets & GIF placeholder(s)
```

## Theming & Dark Mode
Color system uses CSS custom properties. Dark mode is activated by either:
- Setting `data-theme="dark"` on `<html>`, or
- Vuetify applying `.v-theme--dark` / `.v-theme--customDark` to scope.

Custom variables (excerpt):
- `--color-*` (primary, secondary, feedback, text, borders)
- Panel layer: `--panel-bg`, `--panel-bg-alt`, `--panel-soft-border`
- Quick start: `--quick-start-step-bg`, hover variant
- CTA glow: `--cta-glow`

Search / form fields receive explicit dark overrides to force correct text / placeholder / outline colors.

## Key Features
- Data‑driven navigation groups (supports multi-level collapse)
- Getting Started metadata object per tool powering all dynamic sections
- Screenshot carousel + thumbnail strip + custom in‑page lightbox (excludes nav)
- Quick Start panel with numbered steps + GIF embed (`screenshots/instance_cloning.gif` placeholder)
- Accessibility touches: focusable lightbox, alt text on images, reduced‑motion respects `prefers-reduced-motion`

## Editing Guidance
All custom logic & styles live inside `index.html`. To adjust:
- Tokens/theme: edit the `:root` and dark-mode blocks near top
- Navigation + page metadata: search for `gettingStartedPages` JS object
- Quick start GIF: replace file path or swap with video component later

## Potential Next Enhancements
- Lightbox keyboard arrow navigation & ESC trapping improvements
- Automated contrast audit (WCAG) pass for all text-on-translucent layers
- Extract CSS & JS into modular files (prep for build tooling)
- Add linting / formatting config if repo evolves beyond prototype phase
- Unit tests for metadata rendering (if converted to a build setup)

## Deployment (GitHub)
1. Create a new GitHub repo.
2. Upload all files (keep relative paths).
3. (Optional) Enable GitHub Pages (root) to host directly from `index.html`.

## License
Prototype UI – add license text as required.
