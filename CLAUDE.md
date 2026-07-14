# Thaicharoen Plastic — Website

## What this is
A marketing website for **Thaicharoen Plastic Co., Ltd.**, a Thai plastic
supplier based in Samut Sakhon, supplying commodity plastics — Polypropylene
(PP), Polyethylene/LLDPE (PE), and High-Density Polyethylene (HDPE). The site
exists to establish an online presence, present the company's credibility,
showcase its product range, and give prospective clients a way to get in
touch or request a quote.

## Goal
Ship a **working static website** that promotes the company. No backend,
no database, no build step — plain HTML + Tailwind (via CDN) + a little
vanilla JS, deployed as static files on Vercel, with a custom `.com`/`.net`
domain attached once one is chosen.

"Done" means: all pages are complete and accurate, content is real (not
placeholder), it looks good and works on mobile and desktop, and it's live
on Vercel at a real domain.

## Current state
Three static HTML pages, no framework, no package.json:

- `index.html` — Home. Hero, stats bar, "our story", "why choose us",
  product teaser (PP / PE / HDPE), CTA, footer.
- `products.html` — Full product catalog detail (PP / PE(LLDPE) / HDPE
  sections + comparison table).
- `contact.html` — Contact page: real contact details, inquiry form, map
  placeholder.
- `vercel.json` — Deployment config (`cleanUrls: true`, `trailingSlash: false`).

Each page is self-contained: loads Tailwind from `cdn.tailwindcss.com`,
Google Fonts (Inter), and defines its own `tailwind.config` inline. Shared
design tokens (brand blue `brand-900/700/500/100/50`, amber `accent`) are
duplicated across pages rather than centralized — keep them in sync manually
when editing colors/fonts.

## Real company info (filled in 2026-07-14)
- **Phone**: 085-112-1182 (sales — this is the only real number; there is no
  separate company/office line).
- **Email**: thaicharoen1999@gmail.com (single real address, used for
  general inquiries, orders, and quotes).
- **Address**: 88/58 Moo 9, Na Di, Mueang Samut Sakhon, Samut Sakhon 74000,
  Thailand.
- LINE/WhatsApp contact block was removed from `contact.html` — not a real
  channel the company uses.
- Product lineup is **PP / PE (LLDPE) / HDPE**, not PP/PE/LDPE. The old
  "PE" section used to cover both HDPE and LLDPE as sub-grades; it's now
  narrowed to LLDPE (flexible/film) only, and HDPE (rigid/bottles/pipes)
  has its own dedicated section, to avoid duplicating HDPE content twice.
- The homepage "Our Story" / stats section no longer claims a specific
  founding year, ISO certification date, or client count (1990/2005/2015
  timeline and "500+ clients"/"100% quality assured" stats were fabricated
  placeholders and have been replaced with honest, non-dated language). If
  real founding year/milestones/verified numbers become available, this
  section can be rewritten to be more specific and impressive.

## Open TBDs (explicitly deferred, not forgotten)
- **Contact form has no real backend.** `contact.html`'s `#inquiry-form`
  still just fakes a success message client-side via `handleSubmit()` in
  its `<script>` — it does not send the inquiry anywhere. Decide between a
  static form service (e.g. Formspree, Web3Forms — no backend needed) or a
  `mailto:` fallback before this counts as production-ready.
- **Business hours** shown in `contact.html` are unverified placeholder
  hours (Mon–Fri 8:00–5:30, Sat 8:00–12:00) — confirm real hours.
- **Domain not chosen yet** (.com vs .net vs other). Nothing in the code
  hardcodes a domain, so this has no code impact — just attach the domain
  in the Vercel project dashboard once picked.
- **No real photography** — the site uses icons/gradients only, no actual
  product or facility photos.
- **Google Maps embed** on `contact.html` is still a styled placeholder
  linking out to `maps.google.com`, not a real embedded map for the
  Samut Sakhon address.

## Conventions
- Static HTML only — don't introduce a JS framework or build tooling unless
  asked; the site is intentionally simple and dependency-free.
- Tailwind classes are used directly in markup (CDN build, no config file
  on disk) — keep the inline `tailwind.config` block consistent across all
  three pages if you change theme colors or fonts.
- Navigation, footer, and header markup are duplicated per page (no
  templating) — when changing nav/footer/contact info, update all three
  HTML files.
- Deployed on Vercel as a static site (see `vercel.json`); no server code.

## Next steps toward the goal
1. Decide the contact form's real submission path (form service vs mailto)
   and wire it up.
2. Confirm real business hours.
3. Add real product/company photography if available.
4. Deploy to Vercel (`vercel deploy` / `vercel --prod`) and verify the live
   site end-to-end in a browser (all links, mobile menu, scroll animations,
   tel/mailto links).
5. Pick and register `.com` or `.net`, then attach it to the Vercel project.
