# Niche Directories: design system

Recorded 2026-11-19 from the approved editorial design in
`templates/directory.html.j2` and `templates/index.html.j2`.
This documents the existing implementation, not a redesign or an accessibility certification.
Keep maintenance changes within this visual identity. Reference collections are inspiration,
not permission to change the design or install dependencies.

## Identity

Quiet, dark product editorial. Warm near-black ground, cream display type, restrained orange
signals, fine rules and numbered entries. The information leads. Sections grow with their
content rather than sharing an artificial fixed height. The directory index uses ruled rows,
not rounded cards, even though the existing CSS class is named `card`.

## Palette

| Role | Directory token | Value |
| --- | --- | --- |
| Background | `--bg` | `#121110` |
| Secondary surface | `--panel` | `#171614` |
| Main text | `--ink` | `#ece7de` |
| Body/supporting text | `--mut` | `#9d968c` |
| Quiet metadata | `--faint` | `#6d675f` |
| Rules | `--line` | `#292723` |
| Secondary rules | `--line-soft` | `#201e1b` |
| Accent | `--acc` | `#e0602a` |
| Dim accent | `--acc-dim` | `#a34a22` |

The index uses `--fg` for the same cream main text. Its later CSS declarations override the
older values still present above them. Treat computed styles and the later declarations as
the implemented design. Do not restore the obsolete card treatment by removing those overrides.

Contrast has not been audited. In particular, quiet metadata and small orange labels need
contrast checks before claiming WCAG conformance. Leonardo is a possible evaluation tool,
not a dependency or a guarantee that the current colors pass.

## Typography

- Display: Fraunces, with Georgia/serif fallback. Directory headline weight 400,
  `clamp(44px,6.2vw,84px)`, line height 1.02, tracking -0.015em, optical size 144.
- Secondary headline phrase: Fraunces 300, muted, upright. The `em` element is explicitly
  not italic in this design.
- Index headline: Fraunces 400, `clamp(46px,6vw,80px)`, line height 1.04, tracking -0.025em.
- Body: Inter 400, system sans fallback; 16px/1.6 baseline. Lead: 17px/1.65,
  up to 52ch. Entry notes: 15.5px, up to 62ch.
- Entry titles: Fraunces 400, `clamp(26px,3vw,38px)`/1.1.
- Kicker and section labels: Inter 600, 11px, uppercase with 0.22em tracking.
  Other metadata uses 10-12px and 0.1-0.16em tracking.
- Entry numbers: two digits, Fraunces 400, 20-26px, oldstyle numerals.
- Fonts currently load through Google Fonts. Keep the fallbacks functional.

## Grid and rhythm

- Main directory wrap: maximum 1160px including horizontal padding;
  side padding `clamp(20px,5vw,64px)`.
- Hero with art: columns 1.25fr / 0.75fr, gap `clamp(32px,6vw,96px)`.
  Without art: single column, maximum 820px.
- Hero top space: `clamp(64px,10vh,120px)`; bottom: `clamp(48px,8vh,88px)`.
- Spec strip: fine top/bottom rules, flexible cells, 22px vertical padding,
  uppercase label over a 20px serif value.
- Entry rows: 64px number column plus content, gap `clamp(20px,4vw,56px)`,
  vertical padding `clamp(36px,5vh,56px)`, fine bottom rule.
- Supporting sections: 0.9fr / 1.6fr columns, gap `clamp(24px,5vw,80px)`,
  vertical padding `clamp(44px,7vh,72px)`.
- Index rows: 32px vertical padding, no enclosing border or radius, bottom rule only.
- Do not equalize section heights or pad short sections to imitate long ones.

## Mobile

At 820px and below, directory heroes, entries and supporting sections become single-column.
Hero art moves above the copy and is limited to 260px; the spec strip wraps into two columns.
Directory top padding becomes 52px. The index has its own 640px breakpoint with 28px rows
and a 52px main top inset. Verify at 390px and desktop widths. No horizontal scrolling,
clipped headings or squeezed desktop columns.

## Imagery

The cassette directory has original inline SVG art: a cassette shell, reels and tape path,
using the same palette. Art is decorative and hidden from assistive technology. Desktop
maximum width is 420px. Other directories do not need an invented illustration to fill space.
Optional per-niche `hero.svg` supplies art. Do not substitute unlicensed product imagery,
faux dashboards, stock gradients or unrelated 3D objects.

## Interaction and motion

- Filters are real buttons; selecting a tag changes the visible entry set. The active chip
  uses cream fill and dark text. Pills are for filters, not every piece of metadata.
- Hover changes are brief: 150ms color/border/background transitions, 100ms press transform,
  active scale 0.97. Links use subtle underline/rule changes.
- No scroll-reveal, entrance staggering, autoplay illustration or decorative looping motion.
  The current document enables smooth anchor scrolling; no bespoke scroll animation exists.
- Preserve keyboard operation and visible focus. The index has an explicit accent outline;
  directory controls currently rely on browser focus treatment. This is not an accessibility
  audit. Check focus, contrast and reduced-motion behavior before claiming compliance.

## Content and generation

- Keep maker claims labeled as claims, link each proof source and preserve exclusions.
  Design polish must not upgrade a claim into an independently measured fact.
- A successful URL fetch proves reachability, not the meaning of a warranty or stock status.
  Never advance factual confidence solely because a status code is 200.
- The template supports optional `hero` fields (`kicker`, `html`, `lede`), `spec_strip`,
  and per-niche `hero.svg`. Trusted authored markup only belongs in the HTML fields.
- Evidence may use a quote treatment, but only exact verified wording belongs in quotation
  marks. Paraphrases must remain paraphrases.
- Update templates and content sources rather than hand-editing generated HTML alone.
- Maintenance is for existing directories. This document does not resume paused scaling.

## Avoid

Generic rounded-card grids; nested cards; glass panels; purple-gradient defaults; ornamental
badges; italic-serif accent tricks; excessive pills; forced equal-height sections; multiple
competing accents; unearned superlatives; animation that delays reading; copy changes hidden
inside visual fixes. Do not add React/Tailwind libraries to this static Jinja project just
because a reference list recommends them.

## Check before delivery

Regenerate from source, inspect actual desktop and mobile renders, test filters and back
links, check heading wraps and content counts, and confirm there is no overflow. Verify
claims separately from the layout. A documentation-only change should not edit templates,
content data or generated pages.
