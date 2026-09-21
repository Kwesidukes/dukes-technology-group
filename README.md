# Dukes Technology Group — Website

The public marketing website for **Dukes Technology Group (DTG)**, a Perth-based
technology advisory practice covering technology strategy, business analysis,
Microsoft 365/security governance, data & analytics, and project advisory.

This is a static site (no build step, no backend, no database) with a
black-and-gold brand identity. It is designed to be served as-is by any
static host, and is configured for production deployment on Vercel at
`dukestg.com.au`.

## File structure

```
.
├── index.html                    # Home
├── services.html                 # Services
├── approach.html                 # Approach
├── sigma-technology.html         # Sigma Technology
├── about.html                    # About / founder
├── contact.html                  # Contact details and enquiry addresses
├── privacy.html                  # Privacy Policy
├── terms.html                    # Website Terms of Use
├── style.css                     # Full responsive visual system (single stylesheet)
├── script.js                     # Mobile nav toggle, footer year
├── favicon.ico                   # Rounded gold DTG crown — shortcut icon
├── apple-touch-icon.png          # Rounded gold DTG crown — iOS/Safari icon (180x180)
├── site.webmanifest              # Web-app manifest (PWA icon set)
├── assets/
│   ├── favicon-32.png            # Rounded gold DTG crown — 32x32 tab icon
│   ├── favicon-64.png            # Rounded gold DTG crown — 64x64 tab icon
│   ├── dtg-avatar.png            # Circular crown monogram (header/footer)
│   ├── dtg-hero-logo.png         # Gold wordmark/logo used in the hero section
│   ├── dtg-letterhead.png        # Letterhead-style brand asset
│   ├── dtg-sigma-brand.png       # Sigma Technology brand asset
│   └── kwesi-dtg-polo.png        # About page portrait
├── vercel.json                   # Pins framework to null — served as static files
└── README.md
```

All page links, image sources, and script/style references use paths
relative to the site root, so the site works unmodified from a repo root,
a static host root, or a subfolder deploy. Favicon/manifest links use
root-relative paths (`/favicon.ico`, `/assets/favicon-32.png`, etc.) with a
`?v=3` cache-busting query string — bump that version number on any future
icon change to force browsers to fetch the new file.

## Business details

- Dukes Technology Group Pty Ltd
- ABN 61 702 524 310 · ACN 702 524 310
- Perth, Western Australia
- Contact addresses: `hello@`, `accounts@`, `support@`, `security@`,
  `legal@`, `privacy@dukestg.com.au`

## Local preview

No build tools are required. From the project root, run any static file
server, for example:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

or open `index.html` directly in a browser.

## Deployment (Vercel)

1. In the [Vercel dashboard](https://vercel.com/dashboard), click **Add New… → Project**.
2. Import the `Kwesidukes/dukes-technology-group` repository.
3. Framework Preset: **Other** — this is a plain static site. No build
   command, no install command, no output directory beyond the repo root;
   `vercel.json` already pins `framework: null` so Vercel serves the root
   files directly.
4. Click **Deploy**. Vercel assigns a `*.vercel.app` preview URL
   immediately.
5. Verify the preview URL thoroughly (all pages, nav links, favicon,
   contact links) **before** attaching the custom domain.
6. Under **Settings → Domains**, add `dukestg.com.au` as the primary
   production domain, and add `www.dukestg.com.au` configured to
   redirect permanently to `https://dukestg.com.au`.
7. Update DNS at the registrar (Crazy Domains) only after step 5 passes,
   replacing only the web-hosting A/CNAME records with the exact values
   Vercel's Domains page shows for this project. Leave MX, SPF, DKIM,
   DMARC and all other email/verification records untouched.
8. Keep the previous hosting deployment and DNS live until the Vercel
   deployment is confirmed working over HTTPS on the custom domain.

## Branding

Do not redesign the black-and-gold visual identity unless something is
functionally broken. Visual changes should be deliberate, incremental
updates to `style.css`, not a rebuild. Every page's favicon/apple-touch-icon/
manifest must always point at the rounded gold DTG crown assets listed
above — never a generic or placeholder icon.
