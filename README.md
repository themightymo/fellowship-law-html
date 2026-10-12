# fellowship-law-html
The Fellowship Law HTML site - Oct. 2026

## Layout

- `home.html`, `about.html` — the pages
- `images/` — logos and artwork shared by all pages
- `fonts/` — self-hosted fonts (Zaslia)
- `js/` — the runtime `about.html` needs to render (`support.js`, `vendor/react*.js`)

Some browsers block the page scripts over `file://`, so serve the folder to view it:
`python3 -m http.server`, then open http://localhost:8000/home.html
