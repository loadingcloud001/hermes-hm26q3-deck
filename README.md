# Hermes Agent — Install & Use (HM26Q3)

A step-by-step Slidev deck that walks new users through installing, configuring, and using Hermes Agent.

- **Live URL:** https://hm26q3.loadingtechnology.app
- **Worker:** `hermes-hm26q3` on Cloudflare Workers Assets
- **Ref ID:** HM26Q3
- **Author:** Charles Lo · 2026-07

## Dev

```bash
npm install
npm run dev
```

Local URL: `http://127.0.0.1:3031/` (port 3030 is held by the `conai-cl26q3-deck`).

## Build

```bash
npm run build
```

Outputs `dist/`. The `postbuild` hook strips `dist/_redirects` to avoid the Cloudflare `100324` self-loop on deploy.

## Deploy

Push to `main` — Cloudflare Pages picks up the rebuild automatically via the GitHub connection configured for this repo.