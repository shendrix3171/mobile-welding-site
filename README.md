# Twisted C Mobile Welding — Mobile Welding Website

A static marketing website (plain HTML + CSS + JavaScript, no build step) for a mobile welding service.
It is inspired by the structure of a contractor marketing site: sticky header with a phone call-to-action,
a full-width hero, feature cards, testimonials, and a footer with address and hours.

## How to view it

Just open `index.html` in any web browser. No server or build tools required.

(Optional) To serve it locally with a simple web server:

```bash
# Python 3
python -m http.server 8000
# then visit http://localhost:8000
```

## File structure

```
mobile-welding-site/
├── index.html              # Home
├── mobile-welding.html     # Mobile / on-site welding services
├── custom-fabrication.html # Custom fabrication + gallery thumbs
├── projects.html           # Projects & past clients
├── gallery.html            # Photo gallery (with lightbox)├── testimonials.html       # Customer testimonials
├── contact.html            # Contact form, address, hours, map
├── css/
│   └── styles.css          # All shared styling
├── js/
│   └── main.js             # Mobile menu, sticky header, lightbox, contact form
└── assets/
    ├── logo.png            # Site logo (Twisted C wordmark)
    ├── hero.svg            # Placeholder hero background
    └── placeholder.svg     # Generic image placeholder
```

## Editing the placeholders

All content you need to replace is marked with a searchable token: **`[[PLACEHOLDER]]`** (and labels
like `Twisted C Mobile Welding`, `430-359-9173`, `[[ADDRESS]]`, `[[SERVICE AREA]]`, `[[YEAR]]`, `[[EMAIL]]`).

1. Search the project for `[[` to find every spot that needs real content.
2. Replace the placeholder text with your real business details.
3. The phone number appears in the header CTA, footer, and contact page — update all instances
   (it's also used inside `href="tel:..."` links, so update those too).

### Replacing images

- Drop your real photos into `assets/` (JPG/PNG/WEBP are all fine).
- Update the `src="assets/placeholder.svg"` (and `assets/hero.svg`) references in the HTML to point
  at your files. Keep the `alt="..."` text descriptive.

## Wiring up the contact form (later)

The contact form in `contact.html` is **front-end only** — on submit, `js/main.js` shows a success
message but does not send anything anywhere. To make it actually deliver messages, you can either:

- Point the `<form>` at a form-handling service (e.g. Formspree, Basin, Netlify Forms) by setting the
  form's `action` and `method`, and removing the JS `preventDefault` handling, or
- Add your own backend endpoint and POST to it from `js/main.js`.

## Theme / colors

Defined as CSS variables at the top of `css/styles.css`:

- `--accent` (safety orange) — change here to re-brand the whole site at once.
- `--bg`, `--surface`, `--text`, etc. control the dark steel base palette.

## Out of scope (not included)

Real backend/form delivery, CMS, real photos/branding, and domain/hosting setup.
