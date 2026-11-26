# Instructions for AI assistants

This repository is a Beamer theme (`beamerthemeUBCDSlidesTemplate.sty`) plus a
demo deck. When asked to make or edit a presentation:

1. Start from `starter/main.tex` (new deck) or `example/main.tex` (all components).
2. Use only the components listed in `docs/components.md`; do not redefine theme
   colours or fonts in the deck.
3. Compile with `latexmk main.tex` (XeLaTeX is forced by `latexmkrc`). Fix any
   `Overfull \hbox`/`\vbox` warnings before finishing; check the PDF visually.
4. One idea per slide, 3–5 cards or rows, text sized by the theme (never shrink it
   with `\tiny`). Put speaker notes in `\note{...}` with an approximate duration.
5. Write numbers and claims exactly as the user gave them; do not invent data,
   citations, or funder text.
6. Do not add funder/institution logos unless the user supplies the files.

## Posters

* Start from `poster/main.tex`; package `ubcdposter` (options `a0|a1|a2`, `landscape`).
* Content goes in `ubcdblock`s inside `ubcdcolumn`s; keep columns balanced in height.
* The poster must stay on ONE page (check `pdfinfo main.pdf`); trim text or figure
  heights rather than reducing font sizes.