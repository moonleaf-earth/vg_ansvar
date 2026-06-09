# Manual steps for YOU (owner) — publishing vg_ansvar at ansvar.moonleafearth.com

The agent tickets configure the code and the Vercel build, but a few things can only be
done by a human with account/registrar access. Do these in order. The automated tickets
do **not** touch DNS or buy any domain.

Target URL: **https://ansvar.moonleafearth.com**

## 1. Own the domain
- [ ] Confirm you own / control **moonleafearth.com** at your registrar.
      (It's already used by `birds.moonleafearth.com`, so the domain itself should
      exist — you just need access to its DNS settings.)

## 2. Vercel project
- [ ] Log in to Vercel with the account that owns the moonleaf-earth projects.
- [ ] Import / link the `moonleaf-earth/vg_ansvar` repo as a Vercel project
      (New Project → import the repo). It's a static site, so accept the static /
      "Other" framework preset; no build command needed.
- [ ] Trigger a first deployment and confirm the `*.vercel.app` preview URL serves the
      dashboard correctly (page loads, `styles.css` applies, EN/SV toggle works).

## 3. Add the custom domain in Vercel
- [ ] In the Vercel project → **Settings → Domains**, add `ansvar.moonleafearth.com`.
- [ ] Vercel will show the DNS record it wants — usually a **CNAME**:
      `ansvar` → `cname.vercel-dns.com`.

## 4. DNS at the registrar
- [ ] At your DNS provider for `moonleafearth.com`, create the record Vercel asked for:
      - Type: **CNAME**
      - Name/Host: **ansvar**
      - Value/Target: **cname.vercel-dns.com** (use the exact value Vercel shows)
- [ ] Save. DNS can take minutes to a few hours to propagate.

## 5. Verify
- [ ] Back in Vercel → Domains, wait until `ansvar.moonleafearth.com` shows **Valid**
      / a green checkmark and an SSL certificate is issued automatically.
- [ ] Open **https://ansvar.moonleafearth.com** and confirm the page loads over HTTPS.

## Optional decisions you may want to give the agents later
- [ ] If any institution's formal EN/SV name on the page looks wrong to you, note the
      correct form and file a follow-up change ticket.
- [ ] If you'd prefer the apex `moonleafearth.com` (or a different subdomain) instead of
      `ansvar.`, tell me and I'll update the deploy ticket + this file.

---
*Generated alongside tickets: replace-chinese-authority-label, bilingual-language-toggle,
vercel-deploy-config.*
