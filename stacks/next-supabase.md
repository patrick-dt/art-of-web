# Next.js + Supabase

Stack addendum for Next.js App Router projects with Supabase.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **Supabase** → **Next.js**.

Next.js checklist: [next.md](next.md).
Supabase checklist: [supabase.md](supabase.md).

---

## Dev Principles

### Next.js

- Follow [Supabase SSR guide for Next.js](https://supabase.com/docs/guides/auth/server-side/nextjs) (`@supabase/ssr`, cookie handling in middleware).
- Server Components / Route Handlers for data; Client Components only for auth UI and realtime.
- Service role key: Route Handlers / Server Actions only; never `NEXT_PUBLIC_*`.
- Route handlers for webhooks (e.g. Stripe) separate from page data fetching.
- Hydration-safe inputs: focus and value must not reset after hydration.
- URL as state: filters, tabs, pagination in the URL (shareable; Back/Forward works).
- Optimistic updates where appropriate: update UI immediately; rollback on failure.
- Suspense / loading: min show delay (~150–300 ms) to avoid flicker on fast responses.
- Keep client components small; profile re-renders if interactions feel sluggish.

### Supabase

- Use [`@supabase/supabase-js`](https://supabase.com/docs/reference/javascript/introduction) via [`@supabase/ssr`](https://supabase.com/docs/guides/auth/server-side).
- [RLS](https://supabase.com/docs/guides/database/postgres/row-level-security) policies documented and tested; use [Supabase Auth](https://supabase.com/docs/guides/auth) patterns for session refresh.
- Database access: parameterized queries; RLS as the security boundary (not app-layer checks alone).
- [Storage](https://supabase.com/docs/guides/storage): use signed URLs for private assets; CDN/public URLs only when intentionally public.
- Realtime subscriptions cleaned up on unmount (if used).

If a project also uses Sanity, walk **CMS** → **Sanity** sections too; stacks are composable.
