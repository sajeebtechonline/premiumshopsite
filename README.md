# NetShield Store

A premium dark-themed e-commerce storefront for VPN and IP Proxy subscriptions, built for Telegram-based order fulfillment.

## Tech Stack

- **Framework**: TanStack Start (React, SSR)
- **Styling**: Tailwind CSS v4 + custom CSS (dark cyberpunk theme)
- **Routing**: TanStack Router (file-based, type-safe)
- **Fonts**: Rajdhani (display) + Figtree (body) via Google Fonts
- **Deployment**: Netlify

## Features

- 4-tab navigation: Home, VPN, IP Proxy, Contact
- Hero banner with animated stats strip
- Product grid with discount badges, BDT pricing, and Telegram buy buttons
- 12 product listings (6 VPN + 6 IP Proxy)
- Fully responsive (mobile-first grid layout)
- Contact page with Telegram CTA and FAQ section

## Running Locally

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Telegram Integration

All "Buy Now" buttons link to `https://t.me/your_telegram_bot_link`. Replace this placeholder in `src/data/products.ts` with your actual bot link.
