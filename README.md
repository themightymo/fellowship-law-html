# fellowship-law-html
The Fellowship Law HTML site - Oct. 2026

## Layout

- `index.html`, `about.html` — the pages
- `images/` — logos and artwork shared by all pages
- `fonts/` — self-hosted fonts (Zaslia)
- `js/` — the runtime `about.html` needs to render (`support.js`, `vendor/react*.js`)

Some browsers block the page scripts over `file://`, so serve the folder to view it:
`python3 -m http.server`, then open http://localhost:8000/

## Deploy

Every push to `main` deploys to https://fellowshiplaw.notstaging.dev/ via
`.github/workflows/deploy.yml` (rsync over SSH to SiteGround). It needs these
repo secrets: `SG_SSH_KEY` (private key whose public half is imported in
SiteGround's SSH Keys Manager), `SG_HOST`, `SG_USER`, `SG_PORT` (usually
18765) and `SG_PATH` (e.g. `www/fellowshiplaw.notstaging.dev/public_html/`).
