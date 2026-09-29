# Book Template

A lightweight, well-documented LaTeX template for **books, course notes and long
reports in portrait A4 format**. It is ready to upload to
[Overleaf](https://www.overleaf.com) or to compile on your own computer.

The template book (`main.pdf`) is its own user guide: every feature is explained
and then demonstrated. Read it first.

## Features

- Portrait A4, one column by default; two columns and a wide margin for notes are optional
- Default LaTeX font (Computer Modern / Latin Modern), English text with full Spanish support
- Free figure placement: `wrapfigure`/`wraptable` (wrapfig2), `[H]` floats and `\FloatBarrier`
- Front matter, numbered chapters, appendices and bibliography
- Callout boxes (`note`, `tip`, `warning`) and numbered `definition`, `example`,
  `exercise` and `theorem` environments
- Code listings, professional tables, vector figures and mathematics
- Clickable cross-references and citations (numeric or author--year)
- Small: only standard packages and no font packages; `microtype` and `multicol`
  are loaded only when requested
- Compiles with pdfLaTeX (default) and LuaLaTeX

## Quick start

### Overleaf

1. Download this project as a `.zip` archive.
2. In Overleaf choose **New Project → Upload Project** and select the archive.
3. Open the **Menu** and check that the compiler is **pdfLaTeX** and the main
   document is `main.tex`.
4. Click **Recompile**. Overleaf runs BibTeX automatically.

### Local build

Install TeX Live or MiKTeX, then run:

```
latexmk main.tex
```

`.latexmkrc` selects pdfLaTeX and runs BibTeX when needed. Without `latexmk`, run
`pdflatex`, `bibtex`, `pdflatex`, `pdflatex` in this order.

## Project structure

```
.
├── main.tex               Metadata and order of the parts (start here)
├── references.bib         Bibliography database (BibTeX)
├── style/
│   └── booktemplate.sty   Layout, fonts, colours and all package settings
├── frontmatter/           Title page, copyright, dedication, preface
├── chapters/              One file per chapter
├── appendices/            One file per appendix
├── figures/               Images; sources of generated figures in figures/src/
├── .latexmkrc             latexmk settings for local builds
├── LICENSE                MIT license of the template
└── CHANGELOG.md           Version history
```

Only `main.tex` and `style/booktemplate.sty` hold configuration; everything else is
content. The style file is divided into numbered, commented sections.

## Customization

| I want to…                        | Where                                              |
| --------------------------------- | -------------------------------------------------- |
| Change title, author, date        | `\title`, `\author`, … in `main.tex`               |
| Redesign the cover                | `frontmatter/titlepage.tex`                        |
| Use two columns                   | Uncomment `, twocolumn` in `main.tex`              |
| Use a wide margin for notes       | `\usepackage[marginnotes]{style/booktemplate}`     |
| Enable microtype                  | `\usepackage[microtype]{style/booktemplate}`       |
| Write in Spanish                  | `\selectlanguage{spanish}`, `\es{…}` or `otherlanguage` |
| Wrap text around a figure         | `wrapfigure` (see chapter 3 of the book)           |
| Use a shorter running-header title| `\renewcommand*{\runningtitle}{…}` in `main.tex`   |
| Number and list `\subsubsection`  | `\setcounter{secnumdepth}{3}` and `{tocdepth}{3}`  |
| Use author--year citations        | `\usepackage[authoryear]{style/booktemplate}`      |
| Change the accent colour          | `accent` in section 4 of the style file            |
| Change fonts                      | Section 2 of the style file                        |
| Change margins                    | `geometry` options in section 3 of the style file  |
| Use US Letter                     | `paper=letter` in `main.tex`                       |
| Compile a single chapter          | Uncomment `\includeonly{…}` in `main.tex`          |

Landscape is still possible: add `paper=landscape` to the class options and adjust
`geometry` in the style file.

### Helper macros

| Macro               | Result                                        |
| ------------------- | --------------------------------------------- |
| `\cmd{section}`     | `\section` (a command name)                   |
| `\file{main.tex}`   | `main.tex` (a file or path, may break lines)  |
| `\pkg{natbib}`      | natbib (a package name)                       |
| `\code\|x = 1\|`    | inline code with syntax colouring             |

## Dependencies

All packages ship with TeX Live, MiKTeX and Overleaf:
`scrbook` (KOMA-Script), `scrhack`, `scrlayer-scrpage`, `babel`, `csquotes`,
`amsmath`, `amssymb`, `amsthm`, `lmodern`, `xcolor`, `enumitem`, `geometry`,
`graphicx`, `wrapfig2` (or `wrapfig`), `float`, `placeins`, `booktabs`, `array`,
`tabularx`, `tcolorbox`, `listings`, `natbib`, `url`, `hyperref`, `cleveref`, plus
`microtype` and `multicol` when enabled. Spanish needs the `babel-spanish` package,
included in full TeX Live and Overleaf.

Tested with TeX Live 2023 (pdfLaTeX and LuaLaTeX).

## Troubleshooting

- **Citations show as `[?]`** – the bibliography has not been processed. Recompile
  on Overleaf, or run `latexmk main.tex`.
- **Cross-references show as `??`** – compile a second time.
- **Stale results on Overleaf** – open the *Logs and output files* menu and choose
  *Clear cached files*, then recompile.
- **`Underfull \vbox … output is active`** – harmless; it means a page or column could
  not be filled completely, which is normal with floats.
- **A `wrapfigure` overlaps the text or the page end** – move the environment a few
  lines, add the optional number of lines, or use `[H]` with a normal figure.

## Starting your own book

Follow the checklist in the appendix of the template book. In short: replace the
metadata, delete the sample chapters, figure and references, choose your colours and
fonts, replace `LICENSE` and the copyright page, and compile from scratch.

## License

The template is released under the [MIT License](LICENSE). The books you write with
it are yours, under whatever license you choose.
