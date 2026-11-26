# Component reference

All commands are provided by `beamerthemeUBCDSlidesTemplate.sty`. Sizes are in
pt; `example/main.tex` shows each one in use.

## Deck configuration (preamble)

| Command | Purpose |
|---|---|
| `\ubcdkicker{TEXT}` | Mono label next to the logo on the title page |
| `\ubcdfootertext{TEXT}` | Footer text on every slide (page number is automatic) |
| `\ubcdtitlemeta{...}` + `\ubcdmetarow{KEY}{value}` | Metadata rows on the title page |
| `\ubcdtoplogos{...}` | Logo row at the top of the title page (date moves top-right) |
| `\titlegraphic{...}` | Bottom-left block of the title page (funding notice, logos) |
| `\ubcdlogo{file}` / `\ubcdlogodark{file}` | Logo for light / maroon backgrounds |
| `\ubcdsectionlabel{TEXT}` | Divider label (default `SECCIÓN`) |

## Structure

| Command | Purpose |
|---|---|
| `\begin{frame}[plain]\titlepage\end{frame}` | Title page |
| `\ubcdsection{Title}{Description}` | Maroon divider slide (generated automatically) |
| `\begin{frame}{Title}{EYEBROW}` | Normal slide; eyebrow is optional |
| `{\ubcdpaper \begin{frame}...\end{frame}}` | Slide on the lighter "paper" canvas |
| `\ubcdclosing{Big}{Sub}{contact line}` | Closing slide |

## Content components

| Command / environment | Purpose |
|---|---|
| `\begin{ubcdcard}[opts]` … `\ubcdtag{LABEL}` `\ubcdcardtitle{Title}` | White card. `equal height group=name` equalises heights across columns; option `ubcdnuevo` gives a dashed crimson border ("new") |
| `\ubcdband{KEY}{text}` | Maroon banner with a key message |
| `\ubcdlead{text}` / `\ubcdbody{text}` | Grey lead paragraph / body paragraph |
| `\ubcdeyebrow{TEXT}` | Stand-alone mono eyebrow |
| `\ubcdstat[colour]{value}{LABEL}` | Large figure with caption |
| `\begin{ubcdrows}` + `\ubcdrow{01}{Title}{Text}` | Numbered rows separated by hairlines |
| `\ubcdtoolrow{Title}{Text}{\ubcdpill[ok]{TEXT}}` | Row with a status pill on the right |
| `\ubcdstatusrow{\ubcdpill[ok]{TEXT}}{Title}{Text}` | Row with a pill on the left |
| `\ubcdpill[ok\|warn\|bad\|neutral]{TEXT}` | Status pill |
| `\ubcdflow{n}` / `\ubcdflownuevo{n}` + `\ubcdstep{01}{Text}` `\ubcdarrow` `\ubcdstephl{..}{..}` | Horizontal step flow of `n` steps (standard / "new" style; `stephl` highlights a step) |
| `\ubcdshot{w}{h}{file}` + `\ubcdcaption{text}` | Bordered screenshot with caption |
| `\ubcdthead` `\ubcdth{..}` `\ubcdtalt` `\ubcdtablefont` | Table styling (maroon header, alternating rows) with `tabularx` |
| `\ubcdquote{EYEBROW}{quote}{attribution}` | Big quote slide body |

## Typography scale

`\ubcdsizedisplay`, `\ubcdsizedivider`, `\ubcdsizestat`, `\ubcdsizetitle`,
`\ubcdsizesubtitle`, `\ubcdsizehead`, `\ubcdsizelead`, `\ubcdsizebody`,
`\ubcdsizelabel`; helper `\ubcdfs{size}{leading}`.

## Colour tokens

`ubcdVermilion` `ubcdCrimson` `ubcdMaroon` `ubcdMaroonInk` `ubcdLinen`
`ubcdPaper` `ubcdBorderOne` `ubcdBorderTwo` `ubcdInk` `ubcdStoneOne/Two/Three`
`ubcdSuccess` `ubcdWarning` `ubcdDanger`.

## Poster (`ubcdposter.sty`)

Package options: `a0` (default), `a1`, `a2`, `landscape`. Sizes are designed for
A0 and scale with the paper size.

| Command / environment | Purpose |
|---|---|
| `\title` `\subtitle` `\author` | Header text (use `\textsuperscript{n}` for affiliations) |
| `\ubcdaffiliation{...}` `\ubcdkicker{...}` `\ubcdevent{...}` | Affiliations, label next to the logo, event (top right) |
| `\ubcdtoplogos{...}` `\ubcdlogo{file}` | Logos at the right of the header / main logo |
| `\ubcdposterheader` | Paper-coloured header with logo watermark |
| `\begin{ubcdcolumn}{0.31}` … `\end{ubcdcolumn}\hfill` | Column (fraction of text width); separate columns with `\hfill` |
| `\begin{ubcdblock}[opts]{LABEL}{Title}` | Content card with mono label, title and rule. Options: `ubcdnuevo` (dashed crimson border), `ubcdpaper` (paper background), `ubcdplain` (no box) |
| `\ubcdfigure[max height]{file}{caption}` | Full-width bordered figure with caption |
| `\ubcdqr[height]{url}` | QR code on a white tile (needs `qrcode`) |
| `\begin{ubcdrefs}\item …\end{ubcdrefs}` | Numbered reference list `[1]`, small grey type |
| `\ubcdposterfooter{left}{right}` | Maroon footer with binary-digit field, pushed to the bottom |
| `\ubcdposterfunders{...}` | Optional white strip under the footer for funder logos |
| `\ubcdband` `\ubcdstat` `\ubcdrows` `\ubcdrow` `\ubcdtoolrow` `\ubcdpill` `\ubcdflow` `\ubcdstep` `\ubcdstephl` `\ubcdarrow` `\ubcdshot` `\ubcdcaption` `\ubcdlead` `\ubcdtag`, table macros | Same as in the slides, scaled to poster size (`\ubcdtalt` rows are linen instead of white) |

## Tips

* Keep one idea per slide; the theme is dense by design (small type), so prefer
  3–5 cards/rows over long bullet lists.
* Alternate `\ubcdpaper` slides with linen slides to give rhythm.
* Use at most one vermilion/crimson highlight per slide.
* Text is set ragged-right on purpose (`\ubcdragged`); do not justify.