# Beyond the Walls — expedition site

The public site for Marcus's **$0 to $1,000 MRR expedition** (PracticeLoop), live at
[beyondthewalls.quest](https://beyondthewalls.quest).

## How deploys work

This repo is the source of truth for the site. Every push to `main` runs the
GitHub Actions workflow in `.github/workflows/deploy.yml`, which deploys the
repo root to the Cloudflare Pages project **beyond-the-walls** with Wrangler:

```
wrangler pages deploy . --project-name=beyond-the-walls --branch=main
```

Required repository secrets (Settings → Secrets and variables → Actions):

- `CLOUDFLARE_API_TOKEN` — scoped token, Account → Cloudflare Pages → Edit only
- `CLOUDFLARE_ACCOUNT_ID` — the Cloudflare account ID

The site is a single self-contained `index.html` (no build step, no external
assets besides Google Fonts).
