# D2I 2027 — Arianna's Thread

Website of the 2027 Data-to-Information competitions (IEEE Information Theory
Society, Student & Outreach Committee). One topic, three venues, one task each.

Published at <https://data-to-information.github.io/d2i2027/>
(GitHub repo `data-to-information/d2i2027`, Pages from `main`, root folder).

## Layout

```
index.html            Challenge (home): the shared topic
itw/index.html        IEEE ITW 2027  · Munich   · Apr 5–8
esit/index.html       ESIT 2027      · Ankara   · Jun 20–25
isit/index.html       IEEE ISIT 2027 · Sorrento · Jun 27 – Jul 2
assets/css/site.css   the only stylesheet (tokens documented at the top)
assets/fonts/         self-hosted Archivo, Newsreader, IBM Plex Mono (OFL)
assets/img/           logo (png + webp), og.png share image
assets/img/partners/  society / sponsor logos
assets/icons/         favicons
files/                PDFs and downloads linked from the site
```

Plain HTML + CSS. No build step, no JavaScript, nothing loaded from third parties.
All links are relative, so the same files work under `/d2i2027/` on GitHub Pages.

## Preview locally

Clean URLs (`itw/`) need a local server rather than double-clicking:

```
cd site/d2i2027
python3 -m http.server 8000
# open http://localhost:8000
```

## Publish (first time)

1. Create the empty repo `d2i2027` under the `data-to-information` organization.
2. From this folder:
   ```
   git init -b main
   git add .
   git commit -m "D2I 2027 site: first version"
   git remote add origin https://github.com/data-to-information/d2i2027.git
   git push -u origin main
   ```
3. Repo Settings → Pages → Deploy from branch → `main` / root.

## Editing notes

- The venue pages share one structure. "To be announced" items are
  `<span class="tba">To be announced</span>`; replace them with content as it is confirmed.
- When a task is assigned to a venue, update three places: the venue page's
  *Task* row, the home page "Three venues, one thread" list, and the venue's
  `.task` text in that list.
- Naming: always "IEEE ITW 2027" and "IEEE ISIT 2027" in prose; "ESIT 2027".
- Red (`--thread`) is reserved for the thread motif: the active nav tab, the figure's thread,
  the current stop on the venue route. Keep it off ordinary links and buttons.
- The figure on the home page (`.probe`) is laid out in em units so the SVG thread
  lines up with the monospaced letters; see the comment in `site.css` before changing
  row heights or column widths.
