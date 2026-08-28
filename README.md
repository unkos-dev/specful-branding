# specful-branding

Brand identity for [Specful](https://github.com/unkos-dev/specful), including
the symbol, lockups, repository artwork and the canonical identity reference.

This repository is the source of truth for Specful's visual identity. The
Specful product repository carries only the files it needs for presentation;
the complete asset catalogue and usage rules live here.

## Start here

- [`identity.md`](identity.md) defines the identity, typography, colour,
  spacing, voice and asset usage rules.
- [`index.html`](index.html) is a self-contained visual reference. Open it
  locally to inspect the identity in light and dark themes.
- [`tokens.css`](tokens.css) contains the design tokens for a future website or
  documentation interface.

## Contents

```text
.
├── identity.md
├── index.html
├── tokens.css
└── assets
    ├── github
    │   ├── specful-masthead-{light,dark}.svg
    │   ├── specful-social-preview-{light,dark}.png
    │   └── specful-icon-*.{svg,png}
    ├── lockup
    │   ├── specful-lockup-*.svg
    │   └── PNG derivatives at 240, 480 and 960 px
    └── symbol
        ├── specful-mark-*.svg
        └── PNG derivatives from 16 to 256 px
```

The SVG files are the masters. PNG derivatives sit beside them at the sizes
named in their filenames.

## Product repository subset

The Specful README uses these files:

- `assets/github/specful-masthead-light.svg`
- `assets/github/specful-masthead-dark.svg`

The social preview is uploaded through the GitHub repository settings rather
than served by the product. Icons, tokens and the remaining lockups stay here
until a product surface needs them.

## Using these assets

See [`LICENSE`](LICENSE) for the complete terms. The identity documentation,
visual reference and design tokens are licensed under CC BY 4.0. The symbol,
wordmark, lockups, icons and raster artwork identify Specful and remain
reserved brand assets.

## Editing

Brand changes are made and reviewed in this repository. Once a change lands,
the required files are copied into the Specful product repository in a
separate pull request. Do not redraw the symbol or wordmark, and do not link a
product surface to a mutable file in this repository.
