# Astro

Stack addendum for Astro-only projects (no CMS).

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **Astro**.

---

## Dev Principles

- Reusable [`.astro` components](https://docs.astro.build/en/basics/astro-components/) for repeated patterns (buttons, sections, cards).
- Use Astro [`<Image>`](https://docs.astro.build/en/guides/images/) for local / optimized images.
- Prefer static where possible; add client JS only when needed ([`client:*` directives](https://docs.astro.build/en/reference/directives-reference/#client-directives)).
- Keep page files thin; markup lives in components. Keep page-specific copy in those files, not in a central `data.ts`.
- Fully embed code or hand over a sandbox (no half-wired embeds).
- Default local preview: [`http://localhost:4321/`](http://localhost:4321/). Reuse it; don't spawn a second `dev` server. If another project already owns that port, use the next free one.

---

## Checklist

- [ ] Rebuild or webhook fires on publish (static generation)
- [ ] No half-wired embeds / sandbox on handoff
