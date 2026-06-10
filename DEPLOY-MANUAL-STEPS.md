# Deploy — manual owner steps

The repository is configured for a Vercel static deployment via
[`vercel.json`](./vercel.json). The steps below are **manual owner actions** that this
ticket deliberately does **not** perform (they require account access and DNS control):
registering/buying the domain, wiring DNS, and attaching the domain in Vercel.

Target URL: **https://ansvar.moonleafearth.com**
(subdomain `ansvar.` — the apex `moonleafearth.com` and `birds.` are used elsewhere.)

## 1. Connect the project to Vercel

1. In the Vercel dashboard, import this repository as a new project (or link it with
   `vercel link` from the project root).
2. Leave the framework preset as **Other** and the build/output settings empty —
   `vercel.json` already sets `framework: null` and serves the repo root as-is.
3. Trigger a deploy (push to the connected branch, or run `vercel --prod`). Confirm
   `index.html` is served at the deployment root with `styles.css` loading.

## 2. Add the custom domain in Vercel

1. Open the project's **Settings → Domains** tab.
2. Add `ansvar.moonleafearth.com`.
3. Vercel will show the DNS record it expects (a `CNAME` — see step 3).

## 3. Wire DNS

At the DNS provider for `moonleafearth.com`, add:

```
CNAME   ansvar   cname.vercel-dns.com
```

(Use the exact target Vercel shows in the Domains tab if it differs.)

## 4. Verify

1. Wait for DNS to propagate and for Vercel to issue the TLS certificate.
2. Confirm https://ansvar.moonleafearth.com loads the dashboard over HTTPS.
3. Once live, update the "deploying soon" note in [`README.md`](./README.md).
