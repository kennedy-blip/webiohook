# WebhookPulse

A full-stack webhook inspector, request bin, payload simulator, and HMAC-SHA256 verification studio. Built with Vite, React, TypeScript, Tailwind CSS v4, and Vercel Serverless Functions.

## Development

```bash
npm install
npm run dev
```

The Vite development server starts the frontend. For the real in-memory serverless API locally, use `npx vercel dev` (after linking the project). If the API is unavailable, the UI falls back to a clearly labelled local demo mode.

## Build

```bash
npm run build
```

## Deploy

Import this repository into Vercel. The project uses the root directory, Vite output directory `dist`, and `/api` serverless functions. No environment variables are required for the demo; set `WEBHOOKPULSE_SECRET` to configure a default signing secret.

## API

- `GET /api/webhook` — captured events and endpoint stats
- `POST /api/webhook` — capture an incoming JSON webhook
- `POST /api/trigger` — simulate a signed outgoing webhook dispatch

**Storage note:** event storage is in-memory and is reset when a serverless instance is recycled. Use a database for durable production history.
