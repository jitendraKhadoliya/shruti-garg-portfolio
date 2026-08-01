# Shruti Garg — Portfolio

Performance marketing portfolio. Static site — no build step.

## Files
- `index.html` — the portfolio page
- `support.js` — rendering runtime (required, keep alongside index.html)
- `Shruti-Garg-Resume.pdf` — linked by the résumé download buttons
- `proof/` — ad-account screenshots for the "Proof" gallery, plus `proof/thumbs/` for the rail

## Adding an exhibit to the proof gallery
1. Drop the screenshot in `proof/` using a `NN-slug.jpg` name.
2. Add a matching 360px-wide copy in `proof/thumbs/` under the same filename.
3. Append an entry to the `EXHIBITS` array near the top of the `<script data-dc-script>`
   block in `index.html` — `file`, `w`/`h` (natural pixel size, prevents layout shift),
   `group` (`leads` / `reach` / `sales`), `platform`, `range`, `kind`, `title`, `note`
   and three `stats`. Counts, filters and the thumbnail rail derive from that array.

Keep `loading="lazy"` on the gallery `<img>` tags — it is what stops the browser's
preload scanner from fetching the unresolved `{{ }}` placeholders out of the raw
`<x-dc>` template. Slides are warmed ahead of the user by `evPreload()`.

## Deploy to Vercel
1. Push this folder to GitHub.
2. vercel.com → **Add New… → Project** → import this repo.
3. Framework preset: **Other**. Leave the build command empty; output directory `./`.
4. Deploy.

Every push to `main` redeploys automatically.

## Run locally
Open `index.html` in a browser, or serve the folder:

    npx serve .

## Contact
shrutiapple531@gmail.com
