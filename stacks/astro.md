# Astro

Stack addendum for Astro-only projects (no CMS).

Shared rules and checklist: [PRINCIPLES.md](../PRINCIPLES.md). Walk **All projects** → **Astro**.

---

## Dev Principles

- Reusable [`.astro` components](https://docs.astro.build/en/basics/astro-components/) for repeated patterns (buttons, sections, cards).
- Use Astro [`<Image>`](https://docs.astro.build/en/guides/images/) for local / optimized images.
- Prefer static where possible; add client JS only when needed ([`client:*` directives](https://docs.astro.build/en/reference/directives-reference/#client-directives)).
- Keep page files thin; logic and markup live in components.
- Fully embed code or hand over a sandbox (no half-wired embeds).
