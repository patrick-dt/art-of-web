# Astro + Sanity

Stack addendum for content-driven Astro sites with Sanity Studio.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **CMS** → **Sanity** → **Astro**.

Astro-specific rules: [astro.md](astro.md).

---

## Dev Principles

### Sanity

- Schema as single source in Studio; types shared with frontend.
- [GROQ](https://www.sanity.io/docs/groq): parameterized queries; no string interpolation of user input.
- Images via Sanity CDN / [`@sanity/image-url`](https://www.sanity.io/docs/apis-and-sdks/image-urls) as agreed.
- Preview route or [visual editing](https://www.sanity.io/docs/visual-editing) configured; drafts not on production.
- Studio deployed; [CORS](https://www.sanity.io/docs/cors) set for prod + preview domains.
- Content maps cleanly to frontend components (no one-off query shapes per page).
