# @aw-webflow/catalyst_case_study_page

Custom GSAP animations and TOC linking for the Catalyst case study page on Webflow.

## Features

- **Hero staggered fade-up** — logos (`.aw_logo_top`, `.cross_icon`, `.catalyst_logo_top`) animate in sequence
- **Word-by-word text reveal** — `#hero_txt` splits into words and fades up with stagger
- **Section fade-ups** — `.in-convo-with` and `.pm-pointers-wraper` fade in after hero text
- **Scroll-triggered content reveal** — `.case_study_toc_wrapper` and `.case_study_block` fade up when `#content_section` enters the viewport
- **TOC smooth scroll** — `.toc-link` elements scroll to their target with navbar offset
- **Active link highlighting** — current section's TOC link turns purple and bold on scroll
- **Mobile TOC** — auto-collapse `#m-toc` on link click and click-outside-to-close (below 991px)

## Dependencies

GSAP and ScrollTrigger must be loaded via CDN **before** this script:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
```

## Usage via jsDelivr CDN

After publishing to npm, use the jsDelivr CDN link in your Webflow project's custom code (before `</body>`):

```html
<script src="https://cdn.jsdelivr.net/npm/@aw-webflow/catalyst_case_study_page@1.0.0/script.min.js"></script>
```

To always use the latest version:

```html
<script src="https://cdn.jsdelivr.net/npm/@aw-webflow/catalyst_case_study_page@latest/script.min.js"></script>
```

## Deployment Workflow

1. Make changes to `script.js`
2. Bump the version in `package.json`
3. Commit and push to GitHub
4. Publish to npm:
   ```bash
   npm publish --access public
   ```
5. jsDelivr automatically picks up the new version from npm
6. If using a pinned version in Webflow, update the version number in the script tag

## Local Development

```bash
npm install
npm start
```

## License

ISC
