# Kai Reads — Website

Marketing site for the Kai Reads app, served by GitHub Pages at
[kaireads.townsville.cc](https://kaireads.townsville.cc) (custom domain on the
`townsville.cc` Cloudflare zone, HTTPS enforced).

**Kai Reads is live on the [App Store](https://apps.apple.com/us/app/kai-reads/id6790004296).**

- `index.html` — landing page (also the App Store **Support URL**)
- `privacy.html` — privacy policy (required for the App Store kids category, also the App Store **Privacy Policy URL**)
- `assets/` — app icon + screenshots exported from the app repo's `AppStoreConnect/` folder
- `CNAME` — pins the custom domain; don't delete unless you mean to detach it (see below)

Plain static HTML/CSS, no build step. Deploys automatically on merge to `main`
via GitHub Pages.

## Updating

Edit `index.html` / `privacy.html` on a branch and open a PR — direct pushes
to `main` are blocked by a repo ruleset. Once merged, Pages rebuilds in under
a minute. To refresh a screenshot, re-export it from the app repo's
`AppStoreConnect/Screenshots/` into `assets/` here.

## If the HTTPS certificate ever gets stuck

GitHub Pages certificate provisioning can occasionally stall on the generic
`*.github.io` wildcard cert instead of issuing one for the custom domain. Fix:
remove the `CNAME` file (temporarily detaching the custom domain), let Pages
rebuild, then add it back — this re-triggers certificate issuance. Both steps
need to go through a PR since `main` requires one.

## Related repos

- [KaiReads](https://github.com/hibikipr/KaiReads) — the app itself
- [kaireads-content](https://github.com/hibikipr/kaireads-content) — live game content
