---
title: "Day 02 - 16/09/2026 (On-site)"
weight: 2
---

## Work Completed

- Reviewed fundamental React theory (components, props, state, Virtual DOM, hooks, etc.).
- Researched and compared React with Next.js.
- Explored core Next.js concepts (App Router, SSR/SSG/ISR, API Routes, etc.).

## A. Theory

### Part 1. React Fundamentals

**1. What is React?**

React is a JavaScript library (developed by Meta/Facebook) used to build user interfaces (UI), particularly for Single Page Applications (SPAs). React focuses on building UI through reusable components and updates the interface efficiently using the Virtual DOM.

**2. What is a Component in React? How many types are there?**

A component is an independent, reusable UI block that accepts input (props) and returns a UI (JSX). There are 2 main types:

- **Function Component**: written as a JavaScript function, uses Hooks to manage state/lifecycle (the current standard).
- **Class Component**: written as a class extending `React.Component`, has its own state and lifecycle methods (rarely used in new code).

**3. What is JSX?**

JSX (JavaScript XML) is a syntax extension that allows writing HTML-like code directly inside JavaScript. JSX is compiled (via Babel) into `React.createElement()` calls to produce the Virtual DOM.

**4. What are Props?**

Props (properties) are data passed from a parent component down to a child component. Props are read-only — a child component cannot modify the props it receives.

**5. What is State? How does State differ from Props?**

State is a component's internal data that can change over time; when it changes, the component re-renders.

Difference: Props are passed from outside (parent → child) and cannot be modified by the child; State is managed inside the component itself and is updated using functions like `setState`/`useState`.

**6. What is the Virtual DOM? Why does React use it?**

The Virtual DOM is a lightweight in-memory copy of the real DOM, used by React to compare (diff) the old and new states before updating the real DOM. React uses it because direct manipulation of the real DOM is expensive; through diffing and reconciliation, React only updates the parts that actually changed, improving performance.

**7. What are Hooks? Name some common React Hooks.**

Hooks are special functions that allow function components to use state, lifecycle, and other React features without writing a class. Common hooks include: `useState`, `useEffect`, `useContext`, `useRef`, `useMemo`, `useCallback`, `useReducer`.

**8. What is useState used for?**

`useState` is used to declare and manage state in a function component. It returns a pair `[state value, state updater function]`; calling the updater function causes the component to re-render with the new value.

**9. What is useEffect used for?**

`useEffect` is used to perform side effects in a component such as calling APIs, subscribing/unsubscribing to events, manipulating the DOM, updating the document title, etc. It runs after the component renders, can be configured to re-run based on a dependency array, and can return a cleanup function to run when the component unmounts or before the effect runs again.

**10. What are the lifecycle phases of a React Component?**

There are 3 main phases:

- **Mounting**: the component is created and inserted into the DOM for the first time.
- **Updating**: the component re-renders when props or state change.
- **Unmounting**: the component is removed from the DOM.

In class components these correspond to methods like `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`; in function components they are replicated using `useEffect` with different dependency arrays.

**11. What is Client-Side Rendering (CSR)?**

CSR is a rendering approach where the browser downloads a nearly empty HTML file along with a JavaScript bundle; JavaScript then runs on the client (browser) to build the entire UI. This is the default rendering method of plain React (e.g. Create React App).

**12. What is React Router?**

React Router is a third-party library that manages routing (navigation between pages/URLs) in plain React applications, since React itself has no built-in routing.

**13. Does plain React support Routing, SEO, and an API Server?**

No. Plain React is only a UI library: it has no built-in routing (requires React Router), no built-in SEO optimization (the initial HTML is nearly empty due to client-side rendering), and no built-in API server capability (requires a separate backend such as Node/Express).

**14. What is the Context API? When should it be used?**

The Context API is a React mechanism for sharing data (state) across the component tree without passing props through every intermediate level (avoiding "prop drilling"). It should be used when global data is needed by many components at different levels, for example: theme, logged-in user info, or language settings.

**15. What is a SPA (Single Page Application)?**

A SPA is a web application that loads a single HTML page and then uses JavaScript to dynamically update content as the user navigates, without reloading the entire page. It provides a smoother experience but requires extra handling for SEO and initial load performance.

### Part 2. Comparing React and Next.js

**1. What is Next.js?**

Next.js is a framework built on top of React that adds features such as built-in routing, server-side rendering, static site generation, API routes, image optimization, and more — enabling a more complete "full-stack" React application without extensive third-party configuration.

**2. What is the core difference between React and Next.js?**

React is a library focused solely on building UI; Next.js is a full-featured framework built on React that provides routing, multiple rendering strategies (SSR/SSG/ISR), API routes, and SEO/image optimization out of the box with minimal extra configuration.

**3. How does routing differ between React and Next.js?**

Plain React has no built-in routing — a third-party library (React Router) must be installed and configured. Next.js uses file-based routing: the folder/file structure inside `pages/` or `app/` is automatically mapped to routes with no manual configuration required.

**4. How does rendering differ between React and Next.js?**

Plain React defaults to client-side rendering (CSR) only. Next.js supports a variety of rendering strategies — SSR, SSG, ISR, and CSR — allowing the most appropriate approach to be chosen per page.

**5. Why does Next.js support SEO better than plain React?**

Because Next.js can render fully populated HTML on the server (SSR/SSG) before sending it to the browser, allowing search engines to read the content immediately. Plain React (CSR) returns nearly empty HTML, making it difficult for search bots to index content if they do not support running JavaScript.

**6. How does First Load performance differ between React and Next.js?**

With plain React (CSR), the browser must download and execute the full JS bundle before displaying anything, resulting in a slower first load and a potential white screen. With Next.js (SSR/SSG), the HTML already contains content when it arrives, so content appears sooner.

**7. How does project structure differ between React and Next.js?**

React (CRA/Vite) has a flexible structure (you define `src/components`, `src/pages`, etc.) and requires manual routing/build configuration. Next.js has a convention-based structure (the `pages/` or `app/` directory, `public/`, `next.config.js`), with routing and build largely automated by convention.

**8. Does Next.js replace React? Why?**

Not exactly — Next.js is built on top of React and still uses React's components, JSX, and hooks. Next.js is a framework layer that adds capabilities (routing, rendering strategies, optimizations) to React; it is not an independent technology that replaces React.

**9. When should you use plain React vs. Next.js?**

Use plain React when building internal tools, dashboards, or SPAs that do not require SEO, or when you want full control over the architecture. Use Next.js when good SEO is needed (public-facing websites, landing pages, blogs, e-commerce), when SSR/SSG is required, or when you want routing, API routes, and performance optimizations available without heavy manual configuration.

### Part 3. Next.js

**1. What are the App Router and Pages Router in Next.js?**

The Pages Router is Next.js's traditional routing system based on the `pages/` directory, where each file is a route and data fetching uses `getStaticProps`/`getServerSideProps`. The App Router is the new routing system (introduced in Next.js 13+) based on the `app/` directory, supporting React Server Components, nested layouts, streaming, and direct data fetching inside async components.

**2. How do Server Components and Client Components differ?**

Server Components are rendered on the server, send no JavaScript to the client, and are ideal for static sections or data fetching — reducing bundle size. Client Components run in the browser (marked with `"use client"`), and are used when interactivity, state, hooks like `useState`/`useEffect`, or DOM event handling is needed.

**3. What is SSR (Server-Side Rendering)?**

SSR is a technique where a complete HTML page is rendered on the server for every incoming request and then sent to the browser. Content is available immediately on page load and is good for SEO, but consumes more server resources since rendering happens on every request.

**4. What is SSG (Static Site Generation)?**

SSG is a technique where HTML pages are pre-generated at build time, with no re-rendering on each request. Pages are served directly as static files, load very fast, and are ideal for content that changes infrequently (blogs, documentation, landing pages).

**5. What is ISR (Incremental Static Regeneration)?**

ISR is a mechanism that allows statically generated pages (built with SSG) to be regenerated after a set interval (revalidate) without rebuilding the entire application — combining the speed benefits of SSG with the ability to serve fresh data like SSR.

**6. How does file-based routing work in Next.js?**

Next.js automatically creates routes based on the folder/file structure inside `pages/` or `app/`. For example, `pages/about.js` maps to the `/about` route, or in the App Router, `app/about/page.tsx` maps to `/about` — no manual route declaration is needed.

**7. What are Dynamic Routes in Next.js?**

Dynamic routes have path segments that are variable, defined by wrapping the file or folder name in square brackets. For example, `pages/post/[id].js` or `app/post/[id]/page.tsx` matches URLs like `/post/1`, `/post/2`, etc., and the `id` value is accessed via `params`.

**8. What is layout.tsx used for in the App Router?**

`layout.tsx` defines a shared UI wrapper (layout) that surrounds the child pages within the same route segment — for example, a header, sidebar, or footer. The layout is not re-rendered when navigating between child routes inside it, preserving state and improving performance.

**9. What are API Routes (Route Handlers) in Next.js?**

This feature allows writing API endpoints (backend logic) directly within a Next.js project without needing a separate server. In the Pages Router they are placed under `pages/api/`; in the App Router, a `route.ts` file inside the `app/` directory (Route Handlers) handles HTTP methods such as GET and POST.

**10. What are getStaticProps and getServerSideProps? When are they used?**

Both are functions used in the Pages Router to fetch data for a page before rendering:

- **getStaticProps**: runs at build time, used for SSG — suitable when data does not change frequently.
- **getServerSideProps**: runs on the server for every request, used for SSR — suitable when the latest data is needed on each visit.

**11. How does next/image optimize images?**

The `next/image` component automatically optimizes images: it resizes them to the display size, converts them to modern formats (WebP/AVIF), lazy loads them (only fetching when scrolled into view), and caches the optimized versions — reducing payload size and improving performance compared to a standard `<img>` tag.

**12. What is Middleware in Next.js?**

Middleware is code that runs before a request reaches its destination route, allowing interception of the request/response at the edge — for example: checking authentication, redirecting, rewriting URLs, or modifying headers — before the page is actually rendered.

**13. How do you navigate between pages in Next.js?**

Use the `<Link>` component (from `next/link`) for declarative navigation in JSX (client-side navigation, no full page reload), or use the `useRouter()` hook / `router.push()` (Pages Router) or `useRouter` from `next/navigation` (App Router) for programmatic navigation in code.

**14. How are Metadata and SEO handled in Next.js?**

In the Pages Router, the `<Head>` component is typically used to manually declare titles and meta tags. In the App Router, Next.js supports exporting a `metadata` object or a `generateMetadata()` function from a page or layout file to declaratively define title, description, Open Graph tags, etc., which are automatically rendered into the `<head>`.

**15. Does Next.js support TypeScript?**

Yes. Next.js has built-in TypeScript support — simply add a `tsconfig.json` file or rename files to `.ts`/`.tsx` and Next.js will automatically detect and apply the necessary configuration.

**16. What platforms can a Next.js project be deployed to?**

It can be deployed to Vercel (the official platform, most optimized for Next.js), or other platforms such as Netlify, AWS (Amplify/EC2/Lambda), self-hosted Docker containers, Railway, Render, etc. — as long as the platform supports a Node.js runtime (for SSR pages) or static hosting (for SSG/static export).

## B. Exercises

Landing page demo: [https://landing-cyan-zeta-54.vercel.app/](https://landing-cyan-zeta-54.vercel.app/)

Repo link: [https://github.com/Vdarealest/Portfolio](https://github.com/Vdarealest/Portfolio)