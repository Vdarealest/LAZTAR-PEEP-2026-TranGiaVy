+++
title = "Day 04 - 18/09/2026 (Remote)"
weight = 4
+++

## Work completed

### Refactored the landing page into a component-based bilingual architecture

- Consolidated the sections into `LandingPage.tsx` — both language routes share one UI, receiving the copy and locale through props.
- Converted 10 components to receive their content via props: Hero, Marquee, Highlights, Story, Menu, Stats, Gallery, Testimonials, Visit, Footer. Each component only receives the exact slice of data it needs (types such as `SiteCopy["hero"]`, `SiteCopy["menu"]`...), so when the content structure changes, TypeScript reports the error right at the component concerned.
- Two root layouts via route groups: `(en)` for `/` and `(vi)` for `/vi`. This gives each language its own `<html lang>` and metadata — something a single shared layout cannot do. Fonts were extracted into `fonts.ts` so both layouts share one instance.
- Declared hreflang: both pages have their own canonical plus an alternate pointing to the other version.
- Locale-aware price formatting: `formatPrice` now takes a locale — EN renders 35,000₫, VI renders 35.000₫.
- Cleanup: removed `mock.ts` (no longer imported), removed the old `layout.tsx`/`page.tsx`, and removed the commented-out legacy code block in `Navbar.tsx`.
- Verification: the build succeeds and produces 2 static routes, `/` and `/vi`; ESLint is clean; verified on the dev server: correct `lang` per page, correct title per language, correct translated content, the EN/VI switch pointing the right way, and all 164 images on each route returning 200.
