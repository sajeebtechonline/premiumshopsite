# AGENTS.md

This document describes the NetShield Store project for developers and AI agents.

## Project Overview

NetShield Store is a dark-themed e-commerce storefront for VPN and IP Proxy subscriptions. Orders are fulfilled entirely via Telegram — there is no payment processing or backend database. All product data is hardcoded.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | TanStack Start |
| Frontend | React 19, TanStack Router v1 (file-based) |
| Build | Vite 7 |
| Styling | Tailwind CSS 4 + custom CSS (CSS variables) |
| Language | TypeScript 5 |
| Deployment | Netlify |

## Directory Structure

```
src/
  data/products.ts        — All 12 products (VPN + proxy); TELEGRAM_LINK constant here
  routes/
    __root.tsx            — Shell: sticky 4-tab nav + footer
    index.tsx             — Home: hero banner + full product grid
    vpn.tsx               — VPN-only filtered product page
    ip-proxy.tsx          — IP Proxy-only filtered product page
    contact.tsx           — Contact info, Telegram CTA, FAQ
  components/
    ProductCard.tsx       — Card: SVG icon, discount badge, BDT price, Buy Now → Telegram
  styles.css              — Tailwind import, CSS vars, component classes, animations
  router.tsx              — TanStack Router setup (do not edit routeTree.gen.ts manually)
```

## Key Conventions

- **Theming**: CSS variables in `:root` inside `styles.css` define all colours. Edit there to retheme the whole site.
- **Product data**: The `TELEGRAM_LINK` constant in `src/data/products.ts` controls all "Buy Now" button links. Each product has `category: 'vpn' | 'proxy'`, BDT pricing, and brand colour/background for the SVG placeholder.
- **No backend**: No API routes, no database, no auth. Pure static catalog.
- **Routing**: File-based. `routeTree.gen.ts` is auto-generated — never edit it manually.
- **Fonts**: `Rajdhani` (`.font-display`) for headings/numbers; `Figtree` for body copy.

## Non-obvious Decisions

- `shellComponent` in `__root.tsx` is the TanStack Start HTML shell pattern — receives `children` instead of rendering `<Outlet />` explicitly.
- `BrandIcon` inside `ProductCard.tsx` generates inline SVGs (VPN = shield, proxy = network graph) so no image assets are needed.
- `hidden-mobile` class hides the nav "Order Now" badge on small screens to keep the navbar clean.

## Development Commands

```bash
npm run dev      # Start dev server (port 3000)
npm run build    # Production build
```
