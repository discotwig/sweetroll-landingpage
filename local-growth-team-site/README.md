# Sweetroll — Website

A single-page static site for Sweetroll, a two-person local business growth team (Schuyler — growth strategy, Ryan — systems execution). Built with plain HTML and CSS — no build tools, no frameworks, no dependencies.

## What's here

```text
index.html   — page structure and copy
styles.css   — all styling (CSS variables, layout, responsive rules)
README.md    — this file
```

## Running it locally

No server or build step required. Just open `index.html` in a browser:

- Double-click `index.html`, or
- Right-click → Open with → your browser

If you want to preview it the way a real web server would serve it (recommended before deploying), run a simple local server from this folder:

```bash
# Python 3
python -m http.server 8000

# Node (if you have npx)
npx serve .
```

Then visit `http://localhost:8000`.

## Editing content

All copy lives directly in `index.html`, organized by numbered sections:

- Hero — `<section id="top" class="hero">`
- The Problem — `<section id="problem">`
- The Team — `<section id="team">`
- The Offers — `<section id="services">`
- The Process — `<section id="how-we-work">`
- Sound Familiar — `<section id="problems">`
- Local positioning — `<section id="local">`
- Contact — `<section id="contact">`

To change text, find the matching section by its `id` and edit the HTML directly. Headings are `<h1>`/`<h2>`/`<h3>`, body copy is in `<p>` tags.

### Contact info

The site has a single call-to-action: the "Book a Call" button in the sticky header, plus a plain text link in the closing section and footer. All three point to `mailto:bishopryant@gmail.com`. The footer also lists the location placeholder `Atlanta, GA` — update if it should be different.

### Team links

The Team section (`#team`) links to each partner's LinkedIn directly:

- Schuyler O'Malley: `https://www.linkedin.com/in/omalleyschuyler/`
- Ryan Bishop: `https://www.linkedin.com/in/bishopryant/`

### Adjusting pricing

The three rows in the Services section (`Digital Tune-Up`, `Growth Sprint`, `Revenue System Rebuild`) each have an `.offer-duration` span (typical turnaround) and an `.offer-price` span (price range). Edit those directly. The `.price-note` paragraph beneath clarifies these are example ranges, not fixed public pricing.

## Editing styles

All styling is in `styles.css` and driven by CSS variables defined at the top in `:root`:

- Colors: `--color-bg`, `--color-dark`, `--color-accent`, etc.
- Spacing: `--space-xs` through `--space-2xl`
- Type: `--font-display` (serif headlines), `--font-base` (sans body)

Changing a variable updates it everywhere it's used. The layout is mobile-first, with `@media (min-width: 700px/800px)` breakpoints adding multi-column layouts for tablets and desktops. Sections alternate between a light background and a near-black `.section-dark` background for visual rhythm.

## Deployment options

This is a static site, so any static host works. No build step is needed — just upload the three files (or point the host at this folder).

### GitHub Pages

1. Push this folder to a GitHub repository (or a subfolder of one).
2. In the repo settings, go to **Pages**.
3. Set the source to the branch and folder containing `index.html`.
4. GitHub will publish the site at `https://<username>.github.io/<repo>/`.

### Netlify

1. Drag and drop this folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect the GitHub repo.
2. No build command is needed — leave the build settings blank and set the publish directory to this folder.
3. Netlify will give you a live URL immediately; you can attach a custom domain afterward.

### Cloudflare Pages

1. Connect the repository in the Cloudflare Pages dashboard, or use direct upload.
2. Leave the build command empty and set the output/publish directory to this folder.
3. Cloudflare will deploy and give you a `*.pages.dev` URL, with custom domain support available.

## Notes for future improvements

- Add an actual contact form (e.g. via Netlify Forms or Formspree) if `mailto:` links aren't enough.
- Add Open Graph / Twitter meta tags once a real domain and logo exist, for better link previews.
- Consider adding a favicon (`<link rel="icon" ...>` in `<head>`).
- Color contrast was chosen to meet WCAG AA; re-check contrast ratios if the color variables are changed.
