# Next.js + Sanity

Stack addendum for Next.js App Router projects with Sanity.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **CMS** → **Sanity** → **Next.js**.

Next.js checklist: [next.md](next.md).
Sanity checklist: [sanity.md](sanity.md) (also walk [cms.md](cms.md)).

---

## Dev Principles

### Next.js

- [`next-sanity`](https://github.com/sanity-io/next-sanity) / [`@sanity/client`](https://www.sanity.io/docs/js-client); fetch in Server Components where possible.
- Draft mode via [`draftMode()`](https://nextjs.org/docs/app/building-your-application/configuring/draft-mode) + preview secret.
- Revalidation via [`revalidateTag`](https://nextjs.org/docs/app/api-reference/functions/revalidateTag) / webhook on publish.
- Live preview or [Presentation tool](https://www.sanity.io/docs/visual-editing) wired if used.
- Sanity tokens never exposed client-side.
- Route handlers for forms/webhooks separate from page data fetching.
- Hydration-safe inputs: focus and value must not reset after hydration.
- URL as state: filters, tabs, pagination in the URL (shareable; Back/Forward works).
- Optimistic updates where appropriate: update UI immediately; rollback on failure.
- Suspense / loading: min show delay (~150–300 ms) to avoid flicker on fast responses.
- Keep client components small; profile re-renders if interactions feel sluggish.

### Sanity

- Schema as single source in Studio; types shared with frontend.
- [GROQ](https://www.sanity.io/docs/groq): parameterized queries; no string interpolation of user input.
- Images via Sanity CDN / [`@sanity/image-url`](https://www.sanity.io/docs/apis-and-sdks/image-urls) as agreed.
- Studio deployed; [CORS](https://www.sanity.io/docs/cors) set for prod + preview domains.
- Content maps cleanly to frontend components (no one-off query shapes per page).

### Resources

- [`next-sanity`](https://www.sanity.io/plugins/next-sanity) – official Next.js toolkit (previews, Studio embedding, webhooks)
- [`@sanity/code-input`](https://www.sanity.io/plugins/code-input) – code editor with syntax highlighting
- [`sanity-plugin-media`](https://www.sanity.io/plugins/sanity-plugin-media) – media browser for managing assets
- [Official Sanity plugins](https://www.sanity.io/exchange/type=plugins/by=sanity)
- [Sanity Recipes](https://www.sanity.io/recipes) – schema & code snippets
