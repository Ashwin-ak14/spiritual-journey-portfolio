# [SITE NAME] — Personal Spiritual / Editorial Portfolio

A responsive, single-page website built with semantic HTML, CSS and vanilla JavaScript. No build step is required; deploy the project root as a Cloudflare Pages static site.

## Preview locally

From this directory run:

```bash
python3 -m http.server 4173
```

Then open http://localhost:4173.

## Project structure

```text
index.html
css/styles.css
js/main.js
assets/images/portrait-original.jpg
assets/images/portrait-640.webp
assets/images/portrait-960.webp
assets/images/portrait-979.avif
_headers
_redirects
```

## Customize

1. Search `index.html` for `[YOUR NAME]`, `[YOUR TITLE]`, `[SITE NAME]`, `[EYEBROW LINE]`, `[YOUR PURPOSE]`, `[TAGLINE]`, `[BIO]`, `[YEAR]`, and replace the clearly marked placeholders.
2. Replace the stat values in each `.counter[data-count]` and their labels.
3. Replace the collection cards, timeline entries and gallery tiles with your real content. Add gallery images under `assets/images/` and update each tile's `data-lightbox` and `img src`.
4. Replace `[LINKEDIN_URL]`, `[INSTAGRAM_URL]`, and `[YOUR_EMAIL]` with your real contact links.
5. Replace the portrait files in `assets/images/` with your retouched portrait, keeping the same filenames or updating the `picture` sources in `index.html`.
6. Change the design tokens in `:root` at the top of `css/styles.css` to adjust the palette.

## Contact form setup

The form performs browser-side required-field and email validation. To receive messages, create a form at [Formspree](https://formspree.io/), copy its endpoint, and set it as the `data-endpoint` value on `#contactForm` in `index.html`. The JavaScript posts the form data to that endpoint and reports success or failure. Until an endpoint is configured, the form intentionally does not pretend to send messages.

## Search and interaction

- Search input indexes the page's placeholder sections and responds as you type.
- `Ctrl/Cmd + K` opens the search overlay; `Escape` closes it.
- Quick chips filter the collection cards.
- Theme preference is stored in `localStorage`.
- Counters, reveal transitions, timeline progress, lightbox, responsive navigation, cursor and ember effects are vanilla JS/CSS.
- `prefers-reduced-motion` disables nonessential motion.

## Cloudflare Pages deployment

1. Push the repository to GitHub with the default branch named `main`.
2. In Cloudflare Dashboard, open **Workers & Pages → Create → Pages → Connect to Git**.
3. Select the repository and branch `main`.
4. Framework preset: **None**. Build command: leave blank. Build output directory: `.` (project root).
5. Save and deploy. Future pushes to `main` trigger automatic deployments.
6. Add a custom domain in the Pages project if desired.

`_headers` supplies basic browser security headers and long-lived caching for versioned/static assets. `_redirects` provides SPA-style fallback routing.

## Accessibility / performance notes

- Keyboard focus styles, semantic landmarks, labelled controls, meaningful portrait alt text and reduced-motion support are included.
- Hero image is eager/high priority; gallery content is lazy-loaded.
- Responsive WebP sources are provided with JPEG fallback.
- Google Fonts are loaded remotely (Manrope + DM Sans); self-host them if you want to avoid third-party font requests.
- Lighthouse scores depend on the final deployed domain, network, image replacement and third-party resources; no score is claimed without a real audit.
