# Next.js + Sanity

Stack addendum for Next.js App Router projects with Sanity.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md) — walk **All projects** → **CMS** → **Sanity** → **Next.js**.

---

## Dev Principles

### Next.js

- `next-sanity` / `@sanity/client`; fetch in Server Components where possible.
- Draft mode via `draftMode()` + preview secret.
- Revalidation via `revalidateTag` / webhook on publish.
- Live preview or Presentation tool wired if used.
- Sanity tokens never exposed client-side.
- Route handlers for forms/webhooks separate from page data fetching.
- Hydration-safe inputs — focus and value must not reset after hydration.
- URL as state — filters, tabs, pagination in the URL (shareable; Back/Forward works).
- Optimistic updates where appropriate — update UI immediately; rollback on failure.
- Suspense / loading: min show delay (~150–300 ms) to avoid flicker on fast responses.
- Keep client components small; profile re-renders if interactions feel sluggish.

### Sanity

- Schema as single source in Studio; types shared with frontend.
- GROQ: parameterized queries; no string interpolation of user input.
- Images via Sanity CDN / `@sanity/image-url` as agreed.
- Studio deployed; CORS set for prod + preview domains.
- Content maps cleanly to frontend components (no one-off query shapes per page).
