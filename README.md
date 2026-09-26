# Mehraz Hossain Rumman — Portfolio

Personal portfolio site for Mehraz Hossain Rumman, software engineer in Dhaka, Bangladesh.
Plain HTML, CSS and JavaScript. No build step, no dependencies.

## Structure

```
index.html                  # the whole site (single page)
styles.css                  # theme tokens, layout, responsive rules
script.js                   # analytics config, theme toggle, nav, card tilt, GitHub fetch, clock
404.html                    # GitHub Pages "not found" page
favicon.svg
assets/                     # resume PDF
.github/workflows/deploy.yml  # deploys to GitHub Pages on push to main
```

## Run locally

Open `index.html` directly in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Live at **https://mehrazrumman.github.io/rumman-portfolio/**. The workflow in
`.github/workflows/deploy.yml` deploys every push to `main` (Pages source: GitHub Actions).

## Maintenance notes

- **Resume PDF:** the "Résumé" button downloads `assets/Mehraz_Hossain_Rumman_Resume.pdf`.
  Replace that file (same name) to update it.
- **KachaMorich link:** the card points at the GitHub profile. Set its `href` to the org URL.
- **DSP with FFT:** the card has no link. Add the Google Drive link if you want it public.
- **Renaming the repo:** the canonical/og URLs in `index.html` and the home link in `404.html`
  assume the `/rumman-portfolio/` path. Update them if the repo name changes.

## Analytics

GoatCounter is enabled via the `ANALYTICS` object at the top of `script.js` (code
`mehrazrumman`, dashboard at https://mehrazrumman.goatcounter.com). Nothing loads on localhost
or `file://`. A GA4 Measurement ID can be added in the same object instead.

The strip above the footer shows today's and all-time visits from GoatCounter's public counter
endpoint. Counts are cached by GoatCounter for up to four hours, so new visits lag a little.

## Customising

Colors are CSS custom properties at the top of `styles.css`: `--bg`, `--text`, `--accent` and
`--accent-2` (the gradient pair). Dark is the default; the `[data-theme="light"]` block holds the
light palette. Fonts (Geist and Geist Mono) load from Google Fonts in the `<head>` of `index.html`.

The hero card and the "Popular on GitHub" tile pull live numbers (repos, followers, stars, most
starred repos) from the public GitHub API in the visitor's browser. No token is needed.
If the API is unavailable the static values in `index.html` stay in place.
