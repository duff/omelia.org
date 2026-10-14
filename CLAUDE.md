# omelia.org

Static family homepage, served by GitHub Pages at https://omelia.org.

## Deploying
- The only branch is `gh-pages`; pushing to it *is* the deploy (legacy Pages build, no build step).
- Plain HTML/CSS/JS — edit `index.html` directly. Images live in `images/`.
- Don't delete or edit `CNAME`; it holds the custom domain.
- Changing the custom domain in GitHub Settings → Pages commits to `CNAME` on this branch — pull afterwards.
- `_config.yml` excludes this file from the published site; add any other repo-only files there too.

## DNS & HTTPS
- DNS is hosted at DNS Made Easy (DigiCert). Records:
  - `omelia.org` A → 185.199.108.153, .109.153, .110.153, .111.153
  - `www` CNAME → duff.github.io
- HTTPS is a GitHub-managed Let's Encrypt cert (auto-renews) and "Enforce HTTPS" is on.
  It only works while DNS points at the IPs above; the old 192.30.252.x IPs break it.
- Check status: `gh api repos/duff/omelia.org/pages` and `gh api repos/duff/omelia.org/pages/health`.
