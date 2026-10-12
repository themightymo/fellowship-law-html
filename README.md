# fellowship-law-html
The Fellowship Law HTML site - Oct. 2026

## Layout

- `index.html`, `about.html` — the pages
- `home.html` — redirect from the homepage's old URL to `index.html`
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

`.htaccess` is not copied over wholesale: the deploy swaps the repo's
`# BEGIN/END fellowship-law-html` block into the server's `.htaccess`, so rules
SiteGround adds there (e.g. HTTPS enforcement) survive. Put new server rules
inside that block.
