# ISER — New Website Design

A complete redesign and rebrand of the **IZER** company website (https://izer.ie) into
**ISER — Software & Technology**. Built as a single, self-contained, animation-rich landing page.

## Files

| File | Description |
|------|-------------|
| `index.html` | **Home page** (v2 — "Engineered / Blueprint"). |
| `project.html` | **Portfolio detail page** — data-driven; one template renders all projects via `?id=<slug>` (e.g. `project.html?id=linkly`). |
| `assets/iser.css` | Shared stylesheet for both pages (single source of truth). |
| `assets/projects/` | Real project images pulled from the old izer.ie site (one per project, named by slug). |
| `index-v1-backup.html` | First version (dark glassmorphism, Stitch-based). Kept for reference. |
| `stitch-original.html` | Raw, unedited Stitch output (reference only). |
| `logo.png` | **Official ISER logo** (used in the header & footer). |
| `logo-white.png` | Official white logo (for dark/photo backgrounds). |
| `iser-logo.svg` | Standalone angular logo mark (colour gradient, optional). |
| `iser-logo-white.svg` | White version of the mark (optional). |

> The only external request is **Google Fonts** (Chakra Petch, IBM Plex Sans, IBM Plex Mono). All
> graphics are inline SVG / CSS plus the logo PNGs — no Tailwind, no icon CDN.

## Portfolio detail pages

Clicking any project on the home page opens `project.html?id=<slug>`. A single template is populated
from the `PROJECTS` array inside `project.html` (title, client, category, services, description,
feature list, live website link, prev/next). To add or edit a project, just update that array — no
new files needed. Slugs: `linkly`, `nestfood`, `pm-academy`, `irish-statues`, `gh-hospital`,
`kildare-icc`, `scc`, `sky-ly`, `digital-menu`. Live client URLs are wired in (SKY LY is marked
private). Because the pages share `assets/iser.css`, **serve the folder** (e.g. `npx serve .`) rather
than opening via `file://` for links/relative paths to resolve reliably.

## Design direction — "ISER Engineered"

The first version looked like a generic AI landing page (dark glass + floating orbs + Space Grotesk).
v2 commits to a distinctive, brand-specific aesthetic derived from the **ISER logo's angular,
faceted, blade-like geometry** — a technical *blueprint / engineered* look that nothing else online
shares:

- **Cut-corner / chamfered panels** (clip-path) instead of rounded glass — echoes the logo's blades.
- **Blueprint grid backdrop** with a slow pan, fine cyan rule lines, and a subtle noise/grain overlay.
- **Blade / shard motifs** floating with mouse parallax, plus an engineered "FIG.01" schematic figure.
- **Custom crosshair-reticle cursor** (desktop) — fits the blueprint theme.
- **Monospace technical labels** (`// SYSTEM.STATUS`, `S/01`, `PHASE 01`) for an instrument-panel feel.
- **Distinctive type:** Chakra Petch (angular, technical display) + IBM Plex Sans / Mono.
- **Light / dark theme toggle** in the nav (brand-true light palette, choice saved to `localStorage`).
- **SEO + social ready:** Open Graph / Twitter meta, inline-SVG favicon, `theme-color`.
- **Accessible:** skip link, keyboard focus rings (the cursor is hidden, so focus styling matters), `prefers-reduced-motion`, labelled controls.

## Brand identity (from the ISER logo)

- **Gradient:** `#0A6CE4` (electric blue) → `#1E9BF0` (bright blue) → `#2BD0F5` (vivid cyan)
- **Backgrounds:** `#060A12` / `#0A0F1A` · **Text:** `#E7F0FB` / muted `#8DA2BC`
- **Tagline:** *Building Digital Brands* · **Subline:** *Software & Technology*

## Logo

The header and footer use the **official ISER logo** (`logo.png`), sourced from the existing site
assets (`ISER/90Dgrz/FrontStyle/img/logo.png`). The white variant (`logo-white.png`) is included for
use on photos/coloured panels. To replace with an updated file, just overwrite `logo.png` — the
markup references it via `<img src="logo.png" class="brand-logo">`.

## Sections

Sticky nav → Hero (rise-up headline + rotating word + live "system status" panel) → Capability
marquee → Stats counters → Who We Are (+ schematic figure) → Services (6) → Process (4 phases) →
Portfolio (9 projects, asymmetric grid) → CTA band → Contact (details + working form) → Footer.

## Animations

Scroll-progress blade · crosshair cursor + trailing dot · headline rise-up reveal · word rotator ·
animated blueprint grid · grain overlay · floating + parallax shards · scan-line on the hero panel ·
SVG line-draw + pulse on the schematic · scroll-reveal (staggered) · count-up stats + progress bars ·
infinite marquee · service top-bar + icon tilt on hover · angular portfolio hover fills · magnetic
button lifts · active-nav highlighting · animated mobile menu (clip-path reveal) · back-to-top · form
submit feedback. All gated behind `prefers-reduced-motion`.

## Contact details used

- **Email:** isertech1@gmail.com
- **Phone:** +353 85 726 1600
- **Address:** Doolin House, Clare Village, Malahide Rd, Donaghmede, Dublin 17, Ireland
- **Social:** Facebook · Instagram (@iser0pp) · LinkedIn · X (@isertech)

## Preview locally

```bash
# from the New-ISER folder — any static server works, e.g.:
npx serve .
```
Or simply double-click `index.html`.
