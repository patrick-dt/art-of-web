# Next.js

Checklist for Next.js projects.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md).

---

## Dev Principles

- Default local preview: [`http://localhost:3000/`](http://localhost:3000/). Reuse it; don't spawn a second `dev` server. If another project already owns that port, use the next free one.

---

## Checklist

- [ ] Draft mode protected; not open in production
- [ ] On-demand revalidation tested after CMS publish
- [ ] No preview `noindex` leaking to production routes
- [ ] Env vars set on host (e.g. Vercel); ISR/SSR shows fresh content after publish
