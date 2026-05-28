# shotandcut.net

Minimal one-page portfolio / showreel landing for **Shotandcut** — director / editor.

Static HTML + CSS only. No build step, no framework, no JS dependencies. GitHub Pages-ready.

## Files

```
shotandcut-site/
├── index.html                  # The whole page
├── styles.css                  # All styling
├── CNAME                       # GitHub Pages custom domain (shotandcut.net)
├── assets/
│   └── shotandcut-stencil.jpg  # Logo / brand mark
└── README.md
```

## Local preview

Just open `index.html` in a browser, or run a tiny static server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deploy on GitHub Pages with a custom domain

1. **Create a public GitHub repo** and push the contents of this folder to the
   `main` branch (the files should be at the repo root, including `index.html`
   and `CNAME`).

2. **Enable Pages.** In the repo: `Settings → Pages`.
   - Source: `Deploy from a branch`
   - Branch: `main`, folder `/ (root)`
   - Save.

3. **Set the custom domain.** In `Settings → Pages → Custom domain`:
   - Enter `shotandcut.net` (this matches the `CNAME` file already in the repo).
   - Tick **Enforce HTTPS** once the certificate has provisioned.

4. **Configure DNS at your registrar** for `shotandcut.net`:

   Apex (`shotandcut.net`) — add four A records pointing at GitHub Pages:

   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   And/or AAAA records (IPv6):

   ```
   2606:50c0:8000::153
   2606:50c0:8001::153
   2606:50c0:8002::153
   2606:50c0:8003::153
   ```

   `www.shotandcut.net` — add a CNAME record:

   ```
   www  CNAME  <your-github-username>.github.io.
   ```

5. **Wait for DNS + cert.** It can take a few minutes to a few hours. GitHub
   will issue a Let's Encrypt certificate automatically once it sees the
   correct DNS.

## Editing

- Showreel link: `index.html` → search for `livid.com/watch/T2FL54Derqdy`.
- Contact email: `index.html` → search for `felix@shotandcut.net`.
- Big headline: search for `SHOTANDCUT` inside `.bigtype-line` to swap to
  `SHOWREEL` or anything else.
- Brand mark: replace `assets/shotandcut-stencil.jpg` (keep the same filename)
  to update the logo everywhere.

## Notes on design

- Black outer frame, pale bone canvas (`#e9e7e2`), oversized condensed black
  display type (Archivo Black, scaled vertically). Inter for UI.
- Reel hero embeds the Livid player at `https://livid.com/embed/T2FL54Derqdy?transparent=0&playsinline=1`.
  A direct fallback link to the standard `/watch/` page sits underneath.
- Monochrome. No gradients, no decorative imagery, no stock photography.
