# FuseOne Agents — landing page

The public landing page for [FuseOne Agents](https://github.com/fuseone-io/fuseone-agents),
the governed, self-hosted AI-agent platform.

Pure static site: one `index.html`, one stylesheet, the brand SVGs and two
self-hosted variable fonts. No build step, no framework, no font CDN — the
page reports nothing to anyone.

## Design source

The page is generated from the approved design canvas; palette and type come
from the product's own tokens (`fuseone-agents/web/src/styles/tokens`):
Fuse Aqua over cool slate, Geist and Geist Mono.

## Local preview

```sh
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy — Cloudflare Pages

Either path works; the connected repo is the one that keeps itself deployed.

**Connected to GitHub (recommended):** Cloudflare dashboard → Workers & Pages →
Create → Pages → Connect to Git → pick this repository. Framework preset
*None*, build command *empty*, output directory `/`. Every push to `main`
deploys.

**One-off from a checkout:**

```sh
npx wrangler login
npx wrangler pages deploy . --project-name fuseone-agents-site
```

## Updating the version chip

The hero shows the current platform release (`v0.79.0`). Bump it in
`index.html` when a release is cut.
