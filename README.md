# BlackRoad Cloud

Unified SPA for the BlackRoad OS web presence — 22 routes covering landing pages, dashboards, chat, terminal, and brand system. React 19 + Vite, deployed to Cloudflare Pages.

## Stack

| Layer | Technology |
|-------|-----------|
| Framework | React 19 + Vite 7 |
| Routing | react-router-dom |
| Charts | Recharts |
| Payments | Stripe (via Cloudflare Worker) |
| Hosting | Cloudflare Pages |
| Build | ~1 MB (`dist/`) |

## Routes

| Path | Description |
|------|-------------|
| `/` | Landing page with pricing |
| `/dashboard` | Internal metrics and charts |
| `/os` | Desktop OS with 9 apps |
| `/status` | System status monitor |
| `/chat` | Chat interface |
| `/terminal` | Lucidia terminal emulator |
| `/explorer` | File/data explorer |
| `/chain` | RoadChain blockchain explorer |
| `/docs` | Documentation |
| `/about` | Company info |
| `/auth` | Authentication |
| `/settings` | Settings panel |
| `/onboarding` | User onboarding flow |
| `/roadmap` | Product roadmap |
| `/brand` | Brand system reference |
| `/pricing` | Stripe pricing + checkout |

## Development

```bash
npm install
npm run dev        # http://localhost:5173
npm run build      # Build to dist/
```

## Deploy

```bash
npx wrangler pages deploy dist --project-name blackroad-cloud --commit-dirty=true
```

Auto-deploys on push to `main` via GitHub Actions.

## Stripe Integration

Worker at `stripe.blackroad.io` handles checkout, portal, webhooks, and price queries.

| Plan | Price |
|------|-------|
| Operator | Free |
| Pro | $49/mo |
| Sovereign | $299/mo |
| Enterprise | Custom |

## Libraries

| File | Purpose |
|------|---------|
| `src/lib/config.js` | Central config (endpoints, Stripe keys) |
| `src/lib/hybrid-memory.js` | Hybrid memory engine |
| `src/lib/trinary-memory.js` | Base-3 trinary memory |

## License

Copyright 2026 BlackRoad OS, Inc. All rights reserved.
