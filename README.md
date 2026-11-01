# mem20-org-redirect

Redirect layer for **mem20.org** and **www.mem20.org** → https://mem20.com

## Why this repo exists

GitHub Pages allows **exactly one custom domain per repository**. The main site lives at
`bythewayz66-glitch/mem20` with `docs/CNAME` = `mem20.com`, so `mem20.org` cannot also be
registered there: its DNS resolves to GitHub Pages, but GitHub has no site registered for
that hostname and answers with its 9,115-byte *"Site not found · GitHub Pages"* 404.

The fix is one tiny Pages repository per extra hostname. This is the `mem20.org` one.

## Files

| File | Purpose |
|---|---|
| `CNAME` | `mem20.org` — this repo's single registered custom domain |
| `.nojekyll` | skip Jekyll; there is nothing to build |
| `index.html` | client-side redirect preserving path, query and hash |
| `404.html` | same redirect for any deep path that is not mirrored |

## DNS it expects (already in place, do not change)

- `mem20.org`  A → 185.199.108.153 / .109.153 / .110.153 / .111.153
- `www.mem20.org` CNAME → `bythewayz66-glitch.github.io`

No DNS change is required for this repo to work; only the Pages custom-domain
registration (which writes the `CNAME` file above).
