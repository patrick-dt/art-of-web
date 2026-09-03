# Supabase

Checklist for projects using Supabase for auth, database, or storage.

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md).

---

## Checklist

- [ ] Project URL + anon key in env vars; **service role key server-only** (never in client bundle)
- [ ] [Row Level Security](https://supabase.com/docs/guides/database/postgres/row-level-security) enabled on all public tables; policies tested for anon vs authenticated
- [ ] Auth redirect URLs set for production + preview domains
- [ ] Auth flows tested (sign up, sign in, sign out, password reset if used)
- [ ] [Storage](https://supabase.com/docs/guides/storage) buckets: public/private as intended; RLS on buckets if private
- [ ] Forms / mutations hit production Supabase project (not staging/local)
- [ ] Realtime subscriptions cleaned up on unmount (if used)
