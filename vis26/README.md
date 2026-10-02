# Tutorial website

Single-page site for the IEEE VIS 2026 half-day tutorial *Lossy Compression for
Scientific Data: Principles, Tools, and Implications for Visualization*
(Thursday, November 12, 2026, 08:00–11:30, Hall St. George A–B, Boston).

`index.html` is self-contained: no build step, no dependencies. The only
external request is the Google Fonts stylesheet for IBM Plex.

## Preview locally

    python3 -m http.server -d website 8000
    # then open http://localhost:8000

## Publish on GitHub Pages

1. Push this `website/` directory to a public GitHub repo (this repo's `origin`
   is Overleaf, so use a separate GitHub remote for the site).
2. Repo → Settings → Pages → Source: *Deploy from a branch*.
3. Branch `main`, folder `/docs` — rename `website/` to `docs/` — or move
   `index.html` to the repo root and select `/ (root)`.
4. Send the resulting URL to the VIS web chairs (web@ieeevis.org) so it appears
   as the "Tutorial website" link next to the tutorial on
   <https://ieeevis.org/year/2026/info/program/tutorials>.

## Still to fill in

- **Slides.** The Materials section (`#materials`) is a placeholder. Once the
  slide repository exists, replace the notice text with links per talk.
- **Per-talk times.** The VIS program gives two 90-minute blocks
  (08:00–09:30, 10:00–11:30). The per-talk breakdown in the proposal added up to
  75 minutes per session, so the extra 15 minutes per session were distributed
  across the longer talks. Adjust the `<span class="slot-t">` times if the
  presenters want a different split.

## Keeping in sync with the proposal

The page content tracks `template.tex` and `template.bib` as of commit `d0365fa`.
The reading list mirrors the bibliography one-for-one (20 entries, same
groupings). After an Overleaf pull that touches either file, diff it and check
the abstract, the six topic blurbs, the speaker bios, and the reading list.

One deliberate difference: the bibliography drops the page range from
Lindstrom14 to fit the proposal's page limit. The site keeps it, since it has no
such limit.

## Editing

Everything is in `index.html`: design tokens in the `:root` block at the top
(light theme), with the dark theme redefined in the two blocks below it. Sections
are in document order — masthead, about, schedule, pipeline, topics, materials,
presenters, software, reading list, footer.
