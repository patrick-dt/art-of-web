# Next.js

Checklist for Next.js projects.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md).

---

## Dev Principles

- Default local preview: [`http://localhost:3000/`](http://localhost:3000/). HMR on that process is enough; don't spawn a second `dev` server. If another project already owns that port, don't kill it: use the next free one, or the URL this project already printed. See [Local preview](../PRINCIPLES.md#local-preview).

---

## Checklist

- [ ] Draft mode protected; not open in production
- [ ] On-demand revalidation tested after CMS publish
- [ ] No preview `noindex` leaking to production routes
- [ ] Env vars set on host (e.g. Vercel); ISR/SSR shows fresh content after publish
