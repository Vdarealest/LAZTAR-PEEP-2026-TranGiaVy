---
title: "Day 03 - 17/09/2026 (Remote)"
weight: 4
---

# Day 03 - 17/09/2026 (Remote)

**Daily Report - Day 03**
Work mode: Remote | Project: Hạt Nâu cafe landing page

## A. Practical work

### 1. Objective

Today I worked remotely on a landing page for Hạt Nâu, a fictional specialty coffee shop in District 3, Ho Chi Minh City. The shop roasts its own beans in small batches and positions itself as a quiet place to work in the morning. My goal was to turn this concept into a responsive landing page driven entirely by typed mock data, so it could be presented as a portfolio project and satisfy the exercise requirement of using interfaces and mock data rather than hard-coded content.

### 2. Product definition and UI/UX planning

- Defined the brand before coding: name, tagline, target customers (regulars who work from the shop, office workers nearby, corporate catering), and the selling points the page needed to communicate — same-day roasting, direct sourcing from farms in Cầu Đất, a quiet workspace, and fast delivery.
- Planned the page flow: hero → rolling message band → why-us highlights → origin story → menu → key figures → space gallery → customer feedback → visit information → footer.
- Chose a warm, calm visual direction: white base with stone and amber accents, generous spacing, rounded cards and subtle borders. Photography carries the atmosphere, so I avoided decorative illustrations.
- Selected Playfair Display for headings and Be Vietnam Pro for body text, both loaded with the Vietnamese subset so diacritics render correctly.

### 3. Landing page implementation

- Built with Next.js App Router, React, TypeScript and Tailwind CSS on a create-next-app scaffold, using pnpm as package manager. I wrote the icons by hand as inline SVG components instead of adding an icon library, to keep dependencies minimal.
- Kept all content in typed local data (`src/data/mock.ts`) behind interfaces defined in `src/types/index.ts`: `MenuItem`, `MenuCategory`, `Highlight`, `Testimonial`, `GalleryImage`, `OpeningHour`, `ContactInfo`, `NavLink`, `FooterLinkGroup` and `SocialLink`. Prices are stored as numbers and formatted through `Intl.NumberFormat("vi-VN")` rather than written as strings.
- Implemented the sticky navigation with a mobile menu, a dark hero with a photo that bleeds off the right edge of the viewport, an infinite marquee band, four highlight cards, the origin story section, the menu grid, a statistics band, the gallery mosaic, three customer reviews with star ratings, a visit section with address, opening hours and contact links, and the footer.
- Built an interactive menu filter that switches between all items, coffee, other drinks and pastries. Together with the mobile menu these are the only Client Components; the remaining sections stay Server Components since they render static content.
- Used remote images from Unsplash and Pravatar through `next/image`, with both hostnames declared under `images.remotePatterns` in `next.config.ts` — without this declaration Next.js refuses to render them.
- Accessibility work: `aria-label` and `aria-expanded` on the menu toggle, descriptive alt text on every image, semantic `figure`/`figcaption` and `dl` markup, `lang="vi"` on the document, and a `prefers-reduced-motion` rule that disables the marquee animation.

### 4. Verification and issues resolved

- Ran ESLint, TypeScript checking through the production build, and confirmed both pass cleanly.
- Verified the rendered output from the dev server: every section is present, and all 174 optimised image URLs return HTTP 200 through `/_next/image`. I could not capture browser screenshots because the headless browser download was blocked on this network, so I verified the markup and image responses over HTTP instead and reviewed the rendering visually in my own browser.
- Menu photos did not match the item names. I had chosen Unsplash photo IDs from memory and only checked that the URLs returned 200 — not what the photos actually showed. The iced milk coffee displayed a hot cappuccino, the peach tea displayed a plate of cookies, and a savoury dish displayed a café interior. I fixed this by downloading each candidate and inspecting it before assigning it, and renamed one item to match the only suitable verified photo. I also corrected every alt text that described the wrong image.
- Gallery grid was visibly misaligned. The featured image used a 16:10 ratio while its neighbour was square, leaving a gap under the shorter image. I replaced it with a four-column mosaic where the featured image spans two columns and two rows with fixed row heights, which tiles exactly with five images and leaves no empty cells.
- The page felt empty on wide screens. I widened the container from `max-w-6xl` to `max-w-7xl`, let the hero image and the gallery run to the edge of the viewport, and added the marquee band to break the rhythm — while capping paragraph width so line length stays readable.
- Tooling problem: the pnpm command on this machine resolved to a broken Corepack shim that pointed at a missing file, because pnpm 12 changed to a native binary launcher. I resolved it with `corepack disable` so the working installation takes over.

### 5. Deployment

- Pushed the project to GitHub and imported it into Vercel with the Next.js preset and the repository root as the root directory, after confirming the lockfile was committed and build artefacts were not.
- Found that GitHub Pages had been enabled on the repository and was serving a Jekyll page generated from the README rather than the application. Rather than converting the project to a static export outright — which would have broken the Vercel deployment by moving the site under a sub-path and disabling image optimisation — I made the configuration conditional on a `GITHUB_PAGES` environment variable that is only set inside a GitHub Actions workflow. I verified both build modes locally and confirmed the exported HTML applies the correct base path and contains no image-optimiser calls.
- Remaining: switch the Pages source to GitHub Actions and push the workflow. The Vercel link stays the primary URL.

## B. Summary

### What I learned

- Defining the brand and section flow before coding made the implementation far more consistent, and centralising everything in typed mock data meant content changes only ever touched one file.
- Next.js Server Components suit static landing-page content, while interactive pieces such as the menu filter and the mobile menu need Client Components — keeping that boundary small keeps the shipped JavaScript small.
- Remote images in Next.js must be declared in `next.config.ts` before they will render, and a returned HTTP 200 only proves an image exists — not that it shows what you expect.
- Layout that looks fine at one width can leave obvious gaps at another; row spans and fixed row heights are more reliable than aspect ratios when tiling a grid.

### Challenges and how I addressed them

- **Images that contradicted their labels**: I stopped trusting URL checks and inspected each photo before using it, then adjusted one menu item to match the imagery I could actually verify. Alt text was rewritten to describe the real content, which matters for screen-reader users.
- **Empty space on wide screens**: I widened the container and used full-bleed images and a marquee band to fill the width, while keeping text in a narrow column so readability did not suffer.
- **Two deployment targets with conflicting requirements**: Vercel serves at the domain root with image optimisation, GitHub Pages serves static files from a sub-path. A conditional configuration keyed on an environment variable lets both work without one breaking the other.

**Link repo:** [https://github.com/Vdarealest/LangdingPage](https://github.com/Vdarealest/LangdingPage)

**URL PAGE:** [https://landing-page-jade-beta-35.vercel.app/](https://landing-page-jade-beta-35.vercel.app/)
