# Specful brand

The identity is a square two-part symbol, a wordmark cut from Lora, and a small
set of colour and type tokens. It is built for a repository first: a GitHub
masthead, a social preview and a project icon. The same tokens carry a
documentation site without further design work.

The symbol is drawn to a fixed grid, the wordmark is fixed outline artwork, and
the relationship between them is a rule rather than a judgement. Reproduce them;
do not redraw them.

---

## 1. Assets

The default lockup is a vermilion Step with an ink wordmark. Monochrome versions
are part of the identity, not a degraded fallback: use them wherever colour is
unavailable, unsuitable, or simply quieter.

| File | Use |
|---|---|
| `assets/lockup/specful-lockup-colour.svg` | **Default lockup.** Vermilion Step, ink wordmark. |
| `assets/lockup/specful-lockup-colour-reversed.svg` | Default lockup for dark surfaces. |
| `assets/lockup/specful-lockup-ink.svg` | Monochrome alternate, all ink. |
| `assets/lockup/specful-lockup-reversed.svg` | Monochrome alternate, all paper. |
| `assets/lockup/specful-lockup.svg` | Single-colour master for inlining. Inherits `currentColor`. |
| `assets/lockup/specful-wordmark.svg` | Wordmark alone, outlined. For lockups you compose yourself. |
| `assets/symbol/specful-mark-colour.svg` | Symbol in vermilion, 32 px and above. |
| `assets/symbol/specful-mark-colour-small.svg` | Symbol in vermilion, 24 px and below. |
| `assets/symbol/specful-mark-colour-reversed.svg` | Symbol for dark surfaces. |
| `assets/symbol/specful-mark.svg` | Single-colour master for inlining. |
| `assets/github/specful-masthead-light.svg` | README masthead. Clear space already applied. |
| `assets/github/specful-masthead-dark.svg` | README masthead, dark. |
| `assets/github/specful-masthead-mono-light.svg` | Monochrome masthead, light and dark variants. |
| `assets/github/specful-social-preview-light.png` | Repository social preview, 1280 × 640. |
| `assets/github/specful-social-preview-dark.png` | Social preview for dark contexts. |
| `assets/github/specful-icon-ink.svg` | Square project icon, vermilion mark on an ink tile. |
| `assets/github/specful-icon-paper.svg` | Square project icon, vermilion mark on a paper tile. |
| `assets/github/specful-icon-mono-ink.svg` | Monochrome icon, ink and paper variants. |
| `assets/github/specful-icon-mark.svg` | Icon artwork with no tile, for favicons. |
| `tokens.css` | Colour, type, space, corner, divider and focus tokens. |

PNG derivatives sit beside each master at the sizes named in their filenames.

**An external SVG does not inherit the host page's `currentColor`.** A file
loaded through `<img>` or `background-image` resolves `currentColor` to plain
black. Use the `-ink` and `-reversed` files there, and reserve the
`currentColor` masters for SVG pasted directly into a page.

**GitHub repositories have no avatar setting.** The square icon is for the
documentation favicon, social cards, package registries and any future
organisation or application use. It is not a repository avatar.

---

## 2. Symbol

An 18-unit square on a 32-unit grid, cut once by a step that displaces the
division across a ledge set above centre.

| Property | Value |
|---|---|
| Grid | 32 units, artwork drawn edge to edge |
| Void | 2.5 units vertical, 2.2 units at the ledge |
| Outer radius | 1.4 units |
| Inner radius | 0.8 units at the step |
| Small cut | Void opened to 3.2 units, corners square |

The step reads as alignment: two parts of one square, held in register. It is
not a diagram of the information model, which supports many-to-many
relationships the symbol does not attempt to show.

**Clear space** is one quarter of the symbol's height on all four sides. Nothing
enters it, including the wordmark when they are used apart.

**Minimum size** is 16 px. Use `specful-mark-small.svg` at 24 px and below; at
smaller sizes the primary cut's void closes to grey.

Do not stretch the symbol, outline it, rotate it, place it in a circle, or set
its two parts in different colours. Colour the whole Step or none of it: a
two-tone symbol gives one piece more visual weight than the other, and at small
sizes that competes with the stepped gap.

---

## 3. Wordmark and lockup

The wordmark is **fixed outline artwork**. It is never live text, and it is
never re-set in a font at display time. This is what makes it independent of
whatever fonts a reader has installed.

The primary lockup is horizontal: symbol left, wordmark right.

| Property | Value |
|---|---|
| Symbol height | 1.24 × the wordmark's cap height |
| Gap | 0.40 × the symbol's width |
| Vertical alignment | Symbol centred on the cap-to-baseline block |
| Tracking | −6 / 1000 em, applied evenly, no pair kerning |
| Aspect ratio | 4.45 : 1, fixed |

Vertical alignment ignores the ascenders of *f* and *l* and the descender of
*p*. Centring on the full bounding box drops the symbol visibly low.

**Clear space** is one quarter of the symbol's height on all four sides of the
lockup.

**Minimum size** is 90 px wide, which puts the wordmark at roughly 13 px cap
height. Below that, use the symbol alone.

Never set the two elements independently, never recolour one and not the other,
and never substitute a font for the outlined wordmark.

The product name is **Specful** in title case. The binary, the command and every
literal CLI reference is lowercase `specful`.

---

## 4. Typefaces

| Role | Face | Weight | Source | Licence |
|---|---|---|---|---|
| Wordmark | Lora | 600 | [google/fonts `ofl/lora`](https://github.com/google/fonts/tree/main/ofl/lora) | SIL OFL 1.1 |
| Body, navigation, controls, documentation headings | Source Sans 3 | 400 / 600 | [adobe-fonts/source-sans](https://github.com/adobe-fonts/source-sans) | SIL OFL 1.1 |
| Code, commands, paths, identifiers | JetBrains Mono | 400 / 700 | [JetBrains/JetBrainsMono](https://github.com/JetBrains/JetBrainsMono) | SIL OFL 1.1 |

Lora is a brand face. It appears in the wordmark, and may be used for a
top-level brand headline on a marketing surface. Routine documentation headings
are Source Sans 3, which keeps a documentation site from turning serif-heavy and
keeps Lora scarce enough to still mean something.

Lora ships from Google Fonts as a variable font. The wordmark was cut from an
instance at `wght=600`; record that if the artwork is ever re-generated.

The identity asks nothing of the CLI. Plain-text output is appropriate terminal
presentation, and nothing in this guide depends on the binary printing a mark.

Whether `specful` ever prints one is a product decision and remains open. If it
does, the constraints are practical rather than aesthetic: suppress it when
stdout is not a TTY, when `--json` is set, and in CI, so it never reaches a log,
a pipe or a parser.

### Reproducing the wordmark

Cap height 100 units, `wght=600`, tracking −6/1000 em, no kerning, glyphs
converted to outlines and normalised so the artwork's top-left is the origin.
The resulting path is 486.57 × 144.52 units with the baseline 108.10 units from
the top. The SVG masters are plain single-path artwork and can be edited in any
vector tool.

---

## 5. Colour

`tokens.css` is the source. It separates three layers, and the separation is the
whole point:

- **Brand** (`--sf-brand-*`): fixed identity values. Artwork only. Never
  referenced from interface code.
- **Accent** (`--sf-accent-*`): the brand colour doing interface work: links,
  focus rings, identifying details.
- **Action** (`--sf-action-*`): routine primary controls. Neutral by design.

**Vermilion is the identity. It is not the button colour.** A solid warm-red
control reads as destructive whatever the token is called, so routine primary
actions use an ink fill with light text, and the reverse in dark mode. That is
not a workaround for a difficult brand colour; it is the correct division. The
brand marks the product, it does not operate the interface. The same logic keeps
prose and code surfaces neutral.

| Token | Light | Dark | Role |
|---|---|---|---|
| `--sf-accent` | `#C54A3B` | `#CD6555` | Links, focus, identifying details |
| `--sf-accent-hover` | `#AD3326` | `#E67A6A` | Link hover |
| `--sf-accent-strong` | `#BD4334` | `#D66D5D` | Accent text on the accent tint |
| `--sf-accent-surface` | `#FFEAE5` | `#3B1D19` | Tinted accent background |
| `--sf-action` | `#191D24` | `#EAEDF0` | Routine primary control fill |
| `--sf-action-fg` | `#FFFFFF` | `#0F1318` | Label on that fill |
| `--sf-success` | `#1B6734` | `#76C788` | Status only, never brand |
| `--sf-warning` | `#864F00` | `#E8B966` | Status only, never brand |
| `--sf-danger` | `#9B0034` | `#F37986` | Status only, never brand |

### Rules that came out of testing rather than taste

**Links carry the accent and an underline.** Colour alone never distinguishes a
link, in either theme.

**Code surfaces are neutral.** Accent text on the accent tint measures 4.11:1,
below the 4.5:1 floor for normal text. Inline code is therefore ink on the neutral
sunken surface. `--sf-accent-strong` exists for the cases that genuinely need
accent text on an accent tint, and it is the only value that clears the floor
there.

**Status never means anything by colour alone.** Pair every status with a label,
an icon, or both. This holds regardless of which accent the identity uses; no
hue makes meaning unambiguous on its own.

**Danger sits at a deeper crimson than a conventional red.** Beside a vermilion
accent that separation is easier to read, and it costs nothing. This is a design
choice, not a threshold that had to be met: perceptual distance between two
colours is a useful diagnostic, not a pass/fail gate, and it says nothing about
whether someone will read a control as destructive.

**The accent doubles as the GitHub badge fill.** At `#C54A3B` it clears 3:1 against
both the light and dark GitHub backgrounds and carries a white label at 4.75:1,
so no separate badge colour is needed. Where a badge label is neutral, use
`#5F646A`, which also survives both GitHub themes.

### Contrast record

Twenty-one text and boundary pairs were computed against WCAG 2.1 minima in both
themes: 4.5:1 for normal text, 3:1 for large text, component boundaries and focus
rings. **No pair fails.** The narrowest margins are the accent as link text on the
page at 4.51:1, `--sf-accent-strong` on the accent tint at 4.52:1, and
`--sf-border-strong` against the page at 3.09:1 light and 3.04:1 dark.
`--sf-fg-subtle` clears 3:1 but not 4.5:1, so it is for large or non-essential
text only.

Hover moves lightness and never reduces contrast: the accent darkens in light
mode and lightens in dark, so a label gains contrast on hover in both.

## 6. Space, corners, dividers, focus

Space is a 4 px base scale, `--sf-space-1` through `--sf-space-9`
(4, 8, 12, 16, 24, 32, 48, 64, 96 px). Use scale steps rather than arbitrary
values.

Corners are `--sf-radius-sm` 6 px for inputs and small controls,
`--sf-radius-md` 10 px for buttons, `--sf-radius-lg` 16 px for cards and
panels, `--sf-radius-full` for pills.

Dividers are one pixel. Prefer a rule above a group over a box around it;
borders on all four sides make a document look like a brochure. Use
`--sf-border` for separation and `--sf-border-strong` for the boundary of
something a person can interact with.

Every focusable element carries a visible ring: `--sf-focus-ring` at
`--sf-focus-offset`. The ring is the accent in both themes and never depends on
colour alone to be perceivable: it changes the element's outline, not its fill.

---

## 7. Voice

Two registers, and the difference is the audience's question.

**Specification documents**: MSRS, MSDD, ADRs. Present tense, current state
only, written as though the system has always worked this way. Requirements use
BCP 14 keywords. History lives in Git, rationale lives in an ADR, and neither
belongs in a current-state document. These rules come from the project charter,
not from this guide.

**Project communication**: the README, release notes, adoption guidance, the
website. Plain, specific and mechanism-focused, but not bound by
specification-document rules. It is correct here to describe what changed, what
a reader gains, and what is planned, provided every claim is accurate.

Across both:

| Prefer | Over |
|---|---|
| Naming the mechanism: "Indexes are generated views; rebuild them." | Naming a feeling: "Documentation that just stays in sync." |
| A stated fact: "Requires Rust 1.97.1 or newer." | An unsourced number: "Ten times faster." |
| Plain description: "Re-spec your repository." | Reach: "Reimagine your engineering knowledge layer." |
| An honest limit: "Traceability views are planned." | Implying it exists. |

Never invent a metric, a compatibility claim, a release date or a capability.
Where a real value is unavailable, say so.

---

## 8. README integration

```html
<picture>
  <source media="(prefers-color-scheme: dark)"
          srcset="docs/assets/brand/specful-masthead-dark.svg">
  <img src="docs/assets/brand/specful-masthead-light.svg" alt="Specful" height="44">
</picture>
```

Notes:

- `alt="Specful"` is the whole accessible name. The masthead is the wordmark, so
  the alt text is the word it shows: not "Specful logo", which reads the word
  "logo" aloud to no purpose.
- `height="44"` keeps the masthead from crowding the content beneath it. The
  clear space is already inside the file; do not add more.
- The `-light` file is the `<img>` fallback, so anything that ignores
  `<picture>` still gets readable artwork.
- PNG derivatives are available at the same paths if you prefer to avoid SVG in
  the README.
- Do not put a release number in the masthead. Version information belongs in a
  badge or in prose, where it can be updated without re-cutting artwork.

### Badges

Badges are third-party artwork with their own type and geometry. You cannot make
them match Lora and Source Sans, and trying looks worse than not trying. The job
is to stop them shouting.

| Setting | Value | Why |
|---|---|---|
| Style | `flat-square` | Square corners, no gloss |
| Label colour | `5F646A` | Survives GitHub light and dark; the default grey does not |
| Value colour | `C54A3B` | The accent; clears 3:1 on both GitHub themes |

Place them after the tagline, not between the masthead and it: the first human
sentence should come before the machine strip.

Which badges to carry is a judgement about what a visitor needs before they read
anything. A badge that answers a question they already have earns its place; one
that reports internal process belongs in `CONTRIBUTING.md`.

```markdown
[![build](https://img.shields.io/github/actions/workflow/status/unkos-dev/specful/ci.yml?branch=main&style=flat-square&label=build&labelColor=5F646A&color=C54A3B)](https://github.com/unkos-dev/specful/actions/workflows/ci.yml)
```

One accuracy note: a `licence` badge reading `Apache-2.0` would be inaccurate by
omission, because templates and schemas are CC0-1.0. Either label it fully or
leave licensing to the prose, which already covers it.
