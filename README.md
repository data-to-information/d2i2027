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

1. On GitHub, create a **public** repo `d2i2027` under the `data-to-information`
   organization, with no README, .gitignore or license (this folder has them).
2. In Terminal, from this folder:
   ```
   git init -b main
   git add .
   git commit -m "D2I 2027 site: first version"
   git remote add origin https://github.com/data-to-information/d2i2027.git
   git push -u origin main
   ```
3. Repo **Settings → Pages → Build and deployment**: Source *Deploy from a branch*,
   branch `main`, folder `/ (root)` → Save. After a minute or two the site is live at
   <https://data-to-information.github.io/d2i2027/>.

## Updating

```
git add .
git commit -m "what changed"
git push
```

## Editing notes

- Home page (`index.html`): hero with the problem figure, "How it works" (three tasks
  and the participation rules), the information theory question, previous editions
  with IEEE BITS articles, and contacts.
- The venue pages share one structure. "To be announced" items are
  `<span class="tba">To be announced</span>`; replace them as details are confirmed.
- When a task is assigned to a venue: update the venue page's *Task* row, the
  "One task per venue" rule on the home page, and optionally add the task name next
  to the venue in the home page's `.stops` list.
- New edition or article: add a row to `.editions` or `.articles` on the home page.
- Naming: always "IEEE ITW 2027" and "IEEE ISIT 2027" in prose; "ESIT 2027".
- Red (`--thread`) is reserved for the thread motif: the active nav tab, the figure's
  thread, the current stop on the venue route. Keep it off ordinary links and buttons.
- The figure (`.probe`) is laid out in em units so the SVG thread lines up with the
  monospaced letters; see the comment in `site.css` before changing row heights or
  column widths.
