# djmac.eu — Developer Portfolio

Personal developer portfolio site.

## Stack

- **Astro** — static output only (`output: 'static'` in `astro.config.mjs`, no SSR/adapter)
- **Tailwind CSS** for styling
- **nginx** serves the built static files directly on this machine (no Node process in production)
- Domain: `djmac.eu`

## Commands

- `npm run dev` — local dev server
- `npm run build` — builds static site to `dist/`
- `npm run preview` — preview the production build locally

## Deployment

Build output (`dist/`) is served as static files by nginx. There is no server-side runtime in production — do not introduce Astro SSR, API routes, edge functions, or anything requiring a Node server. If nginx config changes are needed, call that out explicitly rather than editing nginx config directly.

## Conventions

- Keep pages/components in `src/pages` and `src/components` per Astro defaults.
- Prefer Tailwind utility classes over custom CSS; only add custom CSS for things Tailwind can't express.
- Keep the site fully static — no client-side framework (React/Vue/etc.) unless explicitly requested; use Astro's islands (`client:*`) only when interactivity is genuinely needed.
- Optimize for fast load and good Lighthouse scores — this is a portfolio site, first impressions matter.
