# Changelog

All notable changes to this template are documented here. The format follows
[Keep a Changelog](https://keepachangelog.com/) and the project uses
[Semantic Versioning](https://semver.org/).

## [1.1.0] - 2026-09-29

### Changed
- Page format is now portrait A4 with a single column; two columns remain
  available as the optional `twocolumn` class option.
- All text now uses the default LaTeX font (Latin Modern when available);
  Palatino, Helvetica and scaled Courier were removed.
- `main=english` with Spanish available through `babel`; callout titles and the
  bibliography heading follow the active language; accents work in listings.
- `multicol` is loaded only in two-column mode, `microtype` became the optional
  `microtype` style option.

### Added
- `wrapfig2` (falling back to `wrapfig`), `float` and `placeins` for free
  figure placement, with a demonstration in chapter 3.
- `marginnotes` style option (wide outer margin for `\marginline`).
- Chapter section on writing in Spanish.

## [1.0.0] - 2026-09-28

### Added
- Landscape A4 book template based on KOMA-Script `scrbook`, in two-column or
  one-column layout.
- Documented style file `style/booktemplate.sty` with `numeric` and `authoryear`
  citation options.
- Editable front matter: title page, copyright page, dedication and preface.
- Callout boxes, theorem-like environments, code listings and helper macros.
- Four guide chapters and two appendices that document the template.
- Sample bibliography and one vector figure with its source.
- README, MIT license and `latexmk` configuration.
