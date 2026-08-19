# Dukes Technology Group — Website

The public marketing website for **Dukes Technology Group (DTG)**, a Perth-based
technology advisory practice covering technology strategy, business analysis,
Microsoft 365/security governance, data & analytics, and project advisory.

This is a static site (no build step, no backend, no database) with a
black-and-gold brand identity. It is designed to be served as-is by any
static host.

## Live status

This is a **pre-launch preview**. The contact form does not send or store
any data — see [Pre-launch checklist](#pre-launch-checklist) below.

## File structure

```
.
├── index.html        # Home page — hero, services, approach, about, contact
├── privacy.html       # Draft privacy policy
├── terms.html          # Draft website terms of use
├── style.css            # Full responsive visual system (single stylesheet)
├── script.js              # Mobile nav toggle, footer year, preview-only contact form
├── assets/
│   ├── favicon.png            # Browser tab icon
│   ├── dtg-avatar.png          # Circular crown monogram (header/footer/about)
│   ├── dtg-hero-logo.png        # Gold wordmark/logo used in the hero section
│   └── dtg-letterhead.png        # Letterhead-style brand asset
└── README.md
```

All page links, image sources, and script/style references use paths
relative to the site root, so the site works unmodified from a repo root,
a static host root, or a subfolder deploy.

## Local preview

No build tools are required. From the project root, run any static file
server, for example:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

or open `index.html` directly in a browser.

## Deployment

### Vercel (recommended — already connected to GitHub)

1. In the [Vercel dashboard](https://vercel.com/dashboard), click **Add New… → Project**.
2. Import the `Kwesidukes/dukes-technology-group` repository.
3. Framework Preset: choose **Other** (this is a plain static site — no
   build command, no output directory needed; `vercel.json` in this repo
   already pins the framework to `null` so Vercel serves the root files
   directly).
4. Leave **Build Command** and **Install Command** empty, and **Output
   Directory** as the project root.
5. Click **Deploy**. Vercel will assign a `*.vercel.app` preview URL
   immediately; a production domain can be attached later under
   **Settings → Domains**.
6. Every future push to the branch connected as Production (typically
   `main`) will auto-deploy; other branches get their own preview URLs.

### Alternative static hosts

The site is portable to GitHub Pages, Netlify, or Cloudflare Pages with no
changes — just point the host at the repository root with no build step.

## Pre-launch checklist

Business details are intentionally left as **pending** until finalised:

- [ ] Register the ABN and replace `ABN: pending registration` in
      `index.html` with the issued number.
- [ ] Finalise the DTG business email address and wire up real contact-form
      delivery (currently `script.js` only prepares an enquiry in the
      browser and explicitly does **not** transmit or store form data).
- [ ] Confirm and attach the production custom domain in Vercel
      (**Settings → Domains**).
- [ ] Legal review of `privacy.html` and `terms.html` — both are marked as
      drafts pending business contact details.
- [ ] Swap or confirm final brand assets in `assets/` if the logo/monogram
      changes before launch.
- [ ] Re-check all internal links, the mobile nav toggle, and both legal
      pages on a deployed preview URL before flipping any custom domain to
      production.

## Branding

Do not redesign the black-and-gold visual identity unless something is
functionally broken. Visual changes should be deliberate, incremental
updates to `style.css`, not a rebuild.
