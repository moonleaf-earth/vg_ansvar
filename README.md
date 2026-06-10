# vg_ansvar — Göteborg Natural Environment Responsibility Dashboard

A static, map-free, bilingual (EN/SV) responsibility dashboard for Göteborg's
natural environment. It lays out — in plain HTML and CSS, with no build step and
no map — who is responsible for what across the city's natural environment, so the
division of duties is legible at a glance. Language can be toggled between English
and Swedish (EN/SV) directly in the page.

## Live site

https://ansvar.moonleafearth.com — _deploying soon_ (DNS not yet wired).

## Local preview

The site is plain `index.html` + `styles.css`, so any static file server works.
From the project root:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 in a browser.

## Deployment

Hosted on Vercel as a static deployment (no build step). Configuration lives in
[`vercel.json`](./vercel.json) at the project root: the framework preset is set to
`null` ("Other") and the repo root is served as-is, with a `Cache-Control` header on
`styles.css`.

Wiring the custom domain (DNS + adding it in the Vercel project's Domains tab) is a
manual owner step — see [`DEPLOY-MANUAL-STEPS.md`](./DEPLOY-MANUAL-STEPS.md).
