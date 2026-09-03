# Next.js

Checklist for Next.js projects.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md).

---

## Checklist

- [ ] Draft mode protected; not open in production
- [ ] On-demand revalidation tested after CMS publish
- [ ] No preview `noindex` leaking to production routes
- [ ] Env vars set on host (e.g. Vercel); ISR/SSR shows fresh content after publish
