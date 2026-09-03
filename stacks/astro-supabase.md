# Astro + Supabase

Stack addendum for Astro projects with Supabase auth, database, or storage.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **Supabase** → **Astro**.

Astro-specific rules + checklist: [astro.md](astro.md).
Supabase checklist: [supabase.md](supabase.md).

---

## Dev Principles

### Supabase

- Use [`@supabase/supabase-js`](https://supabase.com/docs/reference/javascript/introduction) via [`@supabase/ssr`](https://supabase.com/docs/guides/auth/server-side) for cookie-based auth in SSR routes.
- Follow [Astro + Supabase quickstart](https://supabase.com/docs/guides/getting-started/quickstarts/astro) patterns for client vs server usage.
- Auth/session in middleware or Astro endpoints; never expose service role key.
- Database access: parameterized queries; [RLS](https://supabase.com/docs/guides/database/postgres/row-level-security) as the security boundary (not app-layer checks alone).
- [Storage](https://supabase.com/docs/guides/storage): use signed URLs for private assets; CDN/public URLs only when intentionally public.
- Keep Supabase calls in `.astro` frontmatter or API routes; use `client:*` only for auth UI that needs browser session.
- Realtime subscriptions cleaned up on unmount (if used).

### Astro

- Reuse [astro.md](astro.md) rules for components, `<Image>`, static-first.

