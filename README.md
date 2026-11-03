# Tipz.co — Early-Access Landing Page

A premium, one-screen **lead-capture** landing page for Tipz.co. Visitors request
early access via a short form (name, email, interest). The page is deliberately
minimal, dark, and on-brand, and is designed to fit a single screen with **no
vertical scroll** on common desktop, laptop, and mobile viewports.

## Going live — set `FORM_ENDPOINT`

The page is fully self-contained in [`index.html`](index.html) (inline CSS + JS).
Near the top of the inline `<script>` there is a single constant:

```js
// Paste your Formspree (or compatible) endpoint here to go live, e.g. https://formspree.io/f/xxxxxxxx
const FORM_ENDPOINT = "";
```

- **Empty (default):** demo / review mode. On submit the form validates the email,
  shows a short loading state, then shows the success confirmation **without making
  any network request** — so review links and previews work out of the box.
- **Set to a URL:** live mode. On submit the form POSTs the fields as JSON
  (`Content-Type: application/json`, `Accept: application/json`) to the endpoint
  (Formspree-compatible). Success shows the confirmation; failure shows an inline
  error and re-enables the button.

Set `FORM_ENDPOINT` to your Formspree form URL (or any compatible JSON endpoint)
before launch, then commit and deploy.

## Brand implementation
- Tip / Diamond gem mark, recreated as **inline SVG** (no external PNG dependency)
- Purple `#6C00FF` (primary), Orange `#FF6A00` (accent)
- Deep neutral `#0F0B2D`, background base `#09071D`
- Inter typography (loaded from Google Fonts + system fallback)
- One-color `Tipz.co` wordmark with an orange period

## Files
- `index.html` — the entire self-contained page (inline CSS + JS)
- `assets/favicon.svg`, `assets/apple-touch-icon.png`
- `assets/og-tipz-coming-soon.png` — Open Graph / social preview image
- `assets/logo-primary-dark-1600.png`, `assets/mark-dark-1024.png` — brand assets
- `CNAME` — apex domain `tipz.co`

## Deployment
Static, no build step. Served via GitHub Pages at the apex domain `tipz.co`.
Upload the folder contents to the web root. Before launch, set `FORM_ENDPOINT`
and verify HTTPS and canonical root/www routing.
