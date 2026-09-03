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

### Resources

- [`sanity-astro`](https://www.sanity.io/plugins/sanity-astro) – official Sanity integration for Astro
- [`@sanity/code-input`](https://www.sanity.io/plugins/code-input) – code editor with syntax highlighting
- [`sanity-plugin-media`](https://www.sanity.io/plugins/sanity-plugin-media) – media browser for managing assets
- [Official Sanity plugins](https://www.sanity.io/exchange/type=plugins/by=sanity)
- [Sanity Recipes](https://www.sanity.io/recipes) – schema & code snippets
