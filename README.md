# WebhookPulse

Full-stack webhook inspector, request bin, payload simulator, and HMAC-SHA256 verification studio. Built with Vite, React, TypeScript, Tailwind CSS v4, and Vercel Serverless Functions.

## Development
```bash
npm install
npm run dev
```
Vite runs the frontend. For the real serverless API locally, use `npx vercel dev` after linking the project. If the API is unavailable, the UI switches to a labelled local demo mode.

## Build
```bash
npm run build
```

## Deploy
Import this repository into Vercel using the repository root. Vite outputs to `dist`; API functions live in `/api`. No environment variables are required for the demo. Optionally set `WEBHOOKPULSE_SECRET` for the default signing secret.

## API
- `GET /api/webhook` — captured events and endpoint stats
- `POST /api/webhook` — capture an incoming JSON webhook
- `DELETE /api/webhook` — clear captured events
- `POST /api/trigger` — simulate a signed outgoing webhook dispatch

**Storage note:** event storage is in-memory and resets when a serverless instance is recycled. Use a database for durable production history.