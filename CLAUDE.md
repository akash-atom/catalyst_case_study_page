# CLAUDE.md

## Project Overview

Custom JavaScript for the Catalyst case study page hosted on Webflow. The script is published to npm as `@aw-webflow/catalyst_case_study_page` and consumed via jsDelivr CDN.

## Architecture

- `script.js` — Single entry point containing all TOC logic and GSAP animations
- No build step required for production — the raw `script.js` is what gets served via CDN
- GSAP and ScrollTrigger are loaded externally via CDN on the Webflow page (not bundled here)
- Parcel is included only for local dev/testing

## Key Conventions

- All code uses `var` and ES5 syntax (no arrow functions, no `let`/`const`) for maximum browser compatibility
- GSAP is available as a global (`gsap`, `ScrollTrigger`) — do not import it
- CSS class names and IDs must match the Webflow page elements exactly
- Animation timing uses `power2.out` easing and 40px vertical travel as the standard pattern

## Webflow Element Selectors

### Hero Section
- `.aw_logo_top`, `.cross_icon`, `.catalyst_logo_top` — hero logos
- `#hero_txt` — hero heading text (word-by-word animation)
- `.in-convo-with` — "in conversation with" section
- `.pm-pointers-wraper` — PM pointers below hero

### Content Section
- `#content_section` — scroll trigger target
- `.case_study_toc_wrapper` — table of contents sidebar
- `.case_study_block` — main content block

### TOC
- `.toc-link` — individual TOC navigation links
- `#m-toc` — mobile TOC dropdown toggle

## Deployment

1. Push to GitHub
2. `npm publish --access public`
3. jsDelivr serves it at `https://cdn.jsdelivr.net/npm/@aw-webflow/catalyst_case_study_page@<version>/script.js`
