# Sanity

Checklist for projects using Sanity Studio or Sanity content.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Also walk [CMS checklist](cms.md).

---

## Dev Principles

- Default Studio preview: [`http://localhost:3333/`](http://localhost:3333/). Reuse it; don't spawn a second Studio. The frontend still uses its own default (Astro `4321`, Next.js `3000`).

---

## Checklist

- [ ] Studio deployed and reachable
- [ ] CORS origins set for production + preview domains
- [ ] Preview / visual editing tested end-to-end
- [ ] Published vs draft content verified on production
- [ ] Image alt text populated in Sanity fields where applicable

## Resources

- [`sanity-plugin-media`](https://www.sanity.io/plugins/sanity-plugin-media) – media browser
- [`@sanity/code-input`](https://www.sanity.io/plugins/code-input) – code editor with syntax highlighting
- [`next-sanity`](https://www.sanity.io/plugins/next-sanity) – official Next.js toolkit
- [`sanity-astro`](https://www.sanity.io/plugins/sanity-astro) – official Astro integration
- [Official Sanity plugins](https://www.sanity.io/exchange/type=plugins/by=sanity)
- [Sanity Recipes](https://www.sanity.io/recipes) – schema & code snippets
