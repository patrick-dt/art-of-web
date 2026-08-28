# Web Principles & Checklist

Single source of truth. Shared build rules + pre-launch checklist.

1. Follow **Dev Principles** while building.
2. Open your **stack addendum** for framework- and CMS-specific rules.
3. Before launch, walk **All projects**, then only the checklist sections that match your stack.

---

## Stack addenda

| Stack | Dev rules | Checklist sections |
|-------|-----------|-------------------|
| Astro only | [stacks/astro.md](stacks/astro.md) | All projects → Astro |
| Astro + Sanity | [stacks/astro-sanity.md](stacks/astro-sanity.md) | All projects → CMS → Sanity → Astro |
| Next.js + Sanity | [stacks/next-sanity.md](stacks/next-sanity.md) | All projects → CMS → Sanity → Next.js |

---

## Dev Principles

- Fluid sizing. Prefer relative units over fixed.
- Size in `rem`. Never absolute `px` (borders/outlines ok).
- A11y: semantic HTML, contrast, `focus-visible`.
- One `h1` per page; heading order without skips.
- Interactive elements: keyboard reachable + visible focus.
- Optimize images (size, format, lazy-load below fold).
- No ugly / auto-generated class names (e.g. `DivBlock234`).
- Prefer reuse over one-off markup.

### CSS / Tailwind

- Utility-first (Tailwind). Custom CSS only when utilities can't.
- Colors via design tokens / CSS vars (e.g. `--color-*`). No raw hex in components.
- Spacing via scale / tokens — no magic numbers.
- Typography via project `text-*` / type scale. No ad-hoc font sizes.
- Fonts: load once (e.g. `@font-face`); use designated font utilities only.
- Breakpoints: `md:` (768px), `lg:` (1024px) unless project defines otherwise.
- Pair `:hover` with `:focus-visible` on interactive elements.
- Avoid `!important` unless overriding third-party.
- Keep class lists readable; extract repeated patterns into components.

### Motion

- CSS first for hover, focus, and simple transitions (`transition`, `@keyframes`).
- No JS for motion unless CSS can't do it (timeline, scroll-driven, sequenced, interruptible).
- When JS is needed: GSAP. Use clear easing (e.g. `power2.out`, `power3.inOut`) — avoid linear unless intentional.
- Prefer `autoAlpha` over `opacity` (also toggles `visibility`).
- Prefer transforms + `autoAlpha` over layout props (`top`, `height`, etc.).
- Use `gsap.matchMedia()` for breakpoint-specific motion.
- Kill / clean up GSAP on unmount or page leave (no orphaned tweens / ScrollTriggers).
- Respect `prefers-reduced-motion`: reduce or disable non-essential motion.

---

## Pre-Launch Checklist

Walk **All projects** on every launch. Then walk the technology sections that apply to your stack (see table above).

### All projects

#### Access
- [ ] DNS access confirmed — or contact person informed / reachable

#### Legal & Utility
- [ ] Cookies / consent banner
- [ ] Imprint
  - [ ] Link with UTM, e.g. `?utm_source=ClientName&utm_medium=referral&utm_campaign=imprint`
- [ ] Privacy policy
- [ ] 404 page

#### Content & Assets
- [ ] No placeholder / lorem / dummy links
- [ ] Final logos, images, copy, contact details
- [ ] Favicon (+ apple-touch if needed)

#### Forms
- [ ] All fields work (required, validation, error states)
- [ ] Success / error messaging
- [ ] Submit delivers to correct destination
- [ ] Spam protection (honeypot / captcha if needed)
- [ ] Labels + a11y (focus, keyboard)
- [ ] Tested on mobile

#### SEO
- [ ] Image alt tags
- [ ] Unique title + description per indexable page
- [ ] Open Graph image & settings
- [ ] Social share preview checked
- [ ] Schema.org
- [ ] Semantic tags (nav, section, heading, footer)
- [ ] Heading hierarchy matches outline
- [ ] Canonical URLs
- [ ] `robots.txt` + sitemap
- [ ] 301 redirects (Excel)
  - [ ] UTMs not passed through redirects
  - [ ] Google Ads redirects checked
  - [ ] No redirect chains

#### Analytics
- [ ] Tracking installed (GA4 / GTM / agreed tool)
- [ ] Consent mode / cookie gate respects choice
- [ ] Key events fire (form submit, CTA clicks, etc.)
- [ ] No double-counting
- [ ] Test in debug / preview before go-live

#### Google Search Console
- [ ] Property verified
- [ ] Sitemap submitted
- [ ] No critical coverage / indexing errors
- [ ] Inspect key URLs (homepage + main landing pages)

#### Performance
- [ ] LCP, CLS, INP in acceptable range (mobile + desktop)
- [ ] Images sized / compressed; lazy-load below fold
- [ ] Fonts not blocking render (subset / `font-display`)
- [ ] No unused heavy scripts
- [ ] Caching / CDN as agreed

#### Links
- [ ] Footer links
- [ ] Menu links
- [ ] Deadlink check passed

#### Go-live
- [ ] HTTPS live
- [ ] Correct production domain (www vs non-www)
- [ ] No staging URLs; no leftover `noindex`
- [ ] Forms hit production endpoint (not test)

#### A11y
- [ ] Heading hierarchy
- [ ] Skip link or equivalent landmark nav
- [ ] Contrast check on key text / CTAs

#### Testing
- [ ] Mobile
- [ ] Tablet / mid width
- [ ] Desktop
  - [ ] Chrome
  - [ ] Edge
  - [ ] Firefox
  - [ ] Safari
- [ ] Hover / focus states present
- [ ] Reduced-motion path verified
- [ ] No console errors on key pages

#### Handoff
- [ ] Webflow only: code fully embedded — or sandbox handed over
- [ ] Client credentials / access documented

### CMS

For any project with a content backend.

- [ ] Collection Lists — sorting, filter, visibility
- [ ] CMS handoff doc for editors
- [ ] No placeholder / draft slugs indexed

### Sanity

When using Sanity Studio or Sanity content.

- [ ] Studio deployed and reachable
- [ ] CORS origins set for production + preview domains
- [ ] Preview / visual editing tested end-to-end
- [ ] Published vs draft content verified on production
- [ ] Image alt text populated in Sanity fields where applicable

### Astro

When building with Astro (alone or with Sanity).

- [ ] Rebuild or webhook fires on publish (static generation)
- [ ] No half-wired embeds / sandbox on handoff

### Next.js

When building with Next.js (+ Sanity).

- [ ] Draft mode protected; not open in production
- [ ] On-demand revalidation tested after CMS publish
- [ ] No preview `noindex` leaking to production routes
- [ ] Env vars set on host (e.g. Vercel); ISR/SSR shows fresh content after publish
