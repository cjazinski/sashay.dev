# sashay.dev — website

Marketing site for [Sashay](https://github.com/cjazinski/Sashay), served by
GitHub Pages at **https://sashay.dev**.

Single `index.html`, zero JavaScript, zero dependencies. Icon lives at
`icon.png` (same asset the app builds its `.icns` from).

## Custom domain setup (once the domain is registered)

The `CNAME` file already declares `sashay.dev`. When the registrar account is
live, point DNS at GitHub Pages:

**If the domain is on Cloudflare** (CNAME flattening, easiest):

| Type  | Name  | Target                | Proxy    |
| ----- | ----- | --------------------- | -------- |
| CNAME | `@`   | `cjazinski.github.io` | DNS only |
| CNAME | `www` | `cjazinski.github.io` | DNS only |

**If the registrar is Porkbun (or anywhere without apex CNAMEs)**: four A
records on `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
`185.199.111.153`, plus the `www` CNAME above.

Then: repo → Settings → Pages → confirm the custom domain shows `sashay.dev` →
wait for the DNS check → enable **Enforce HTTPS** (the certificate can take up
to an hour to provision). `.dev` is HSTS-preloaded, so HTTPS is mandatory —
GitHub provisions it automatically.

## Editing

Change `index.html`, push to `main`. Pages redeploys in ~a minute.
