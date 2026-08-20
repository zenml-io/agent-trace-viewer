---
name: Agent Trace Viewer
description: Cassette-futurist blackface tape-deck fascia for a zero-network coding-agent trace viewer
colors:
  graphite: "#17191b"
  graphite-highlight: "#1f2226"
  plate-light: "#202427"
  plate-shade: "#1a1e21"
  recess: "#101314"
  black-surround: "#0a0b0c"
  ink: "#e6e9e5"
  engrave: "#d5d9d5"
  muted: "#a2aaa5"
  faint: "#828b86"
  line: "#3a4045"
  line-soft: "#2e3438"
  amber: "#ffb000"
  amber-ink: "#cf8f00"
  matrix: "#0d0c0a"
  matrix-edge: "#332f28"
  led-label: "#a79f8a"
  paper: "#e9e6d8"
  paper-edge: "#a9a390"
  led-message: "#46c46e"
  led-instruction: "#e06a3b"
  led-tool: "#56b6c8"
  led-reasoning: "#e0b23e"
  led-context: "#93a2ac"
  led-error: "#ff5a4e"
  ink-ok: "#6fd88f"
  ink-err: "#ff6b5e"
typography:
  display:
    fontFamily: "Barlow Condensed, ui-sans-serif, system-ui, sans-serif"
    fontSize: "clamp(48px, 7vw, 80px)"
    fontWeight: 600
    lineHeight: 0.96
    letterSpacing: "0.015em"
  headline:
    fontFamily: "Barlow Condensed, ui-sans-serif, system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: "0.1em"
  title:
    fontFamily: "Barlow Condensed, ui-sans-serif, system-ui, sans-serif"
    fontSize: "12.5px"
    fontWeight: 600
    letterSpacing: "0.08em"
  body:
    fontFamily: "ui-monospace, SFMono-Regular, Menlo, Consolas, monospace"
    fontSize: "13.5px"
    lineHeight: 1.65
  matrix:
    fontFamily: "Doto, ui-monospace, monospace"
    fontSize: "19px"
    fontWeight: 700
    letterSpacing: "0.06em"
  label:
    fontFamily: "Barlow Condensed, ui-sans-serif, system-ui, sans-serif"
    fontSize: "11.5px"
    fontWeight: 500
    letterSpacing: "0.1em"
rounded:
  pip: "2px"
  chip: "3px"
  key: "4px"
  plate: "6px"
  panel: "8px"
spacing:
  hairline: "2px"
  xs: "6px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "20px"
  gutter: "24px"
components:
  key:
    backgroundColor: "linear-gradient(180deg, #2b3034, #1e2226)"
    textColor: "{colors.engrave}"
    typography: "{typography.title}"
    rounded: "{rounded.key}"
    padding: "6px 13px"
  key-active:
    backgroundColor: "linear-gradient(180deg, #2b3034, #1e2226)"
    textColor: "{colors.ink}"
    rounded: "{rounded.key}"
  button-primary:
    backgroundColor: "linear-gradient(180deg, #33383d, #22262a)"
    textColor: "{colors.ink}"
    rounded: "{rounded.plate}"
    padding: "13px 26px"
  matrix-window:
    backgroundColor: "{colors.matrix}"
    textColor: "{colors.amber}"
    typography: "{typography.matrix}"
    rounded: "{rounded.key}"
    padding: "10px 12px"
  paper-label:
    backgroundColor: "{colors.paper}"
    textColor: "#3a3a30"
    rounded: "{rounded.chip}"
    padding: "5px 8px"
  panel:
    backgroundColor: "linear-gradient(180deg, #202427, #1a1e21)"
    textColor: "{colors.ink}"
    rounded: "{rounded.panel}"
    padding: "20px"
---

# Design System: Agent Trace Viewer

## Overview

**Creative North Star: "The Blackface Tape Deck"**

The entire interface is one machined fascia: brushed graphite (#17191b) set into a
black plastic surround (#0a0b0c), covered in pale silk-screened condensed-caps
labels, beveled snap keys, light paper cassette-label insets, and recessed
near-black display windows where the data glows amber. The trace is a tape;
reading it is a playback. Though dark, this is not the dev-console dashboard the
category always ships: every pixel is hardware-literal — the darkness is molded
plastic and brushed metal, never a void, and the page is `color-scheme: dark` with
a fine brushed texture (repeating 1px `#ffffff07` lines over a #1b1e21 → #141719
gradient) across the whole body.

Every surface states its material. Raised plates catch a faint white top bevel;
recesses fall into shadow; matrix windows sink deepest with a hairline lit lip;
labels are silk-screened (pale ink with a dark 1px drop shadow that seats them
into the surface). Nothing floats free of the fascia except the fixed transport
cluster at the bottom of the screen, which is itself a piece of the same hardware.

**Key Characteristics:**
- One dark graphite fascia in a black surround; the only light surfaces are paper
  cassette-label insets and the amber-lit displays
- Amber (#ffb000) strictly means active/lit — never decoration
- Physical depth grammar: bevel up, recess in, matrix deep — no soft ambient shadows
- Silk-screened uppercase Barlow Condensed labels; ui-monospace body; Doto
  dot-matrix digits
- Interactions snap (1–2px translateY press), nothing glides — zero transitions
- Event kinds are coded by small square LED chips, never by colored borders or
  tinted cards

## Colors

A graphite-and-black hardware range (fascia, plates, recesses, matrix wells) with
pale silkscreen inks, warm paper insets as the light accents, amber as the single
lit color, and six bright LED hues that code event kinds.

### Primary
- **Signal Amber** (#ffb000): the lit-display color. Doto digits in matrix
  windows, the active-tab and active-filter indicator groove (`inset 0 3px 0`),
  text selection (with near-black text), the jump-flash outline, dashed meter
  fills. It appears only where something is ON.
- **Amber Ink** (#cf8f00): the toned form of amber for the fascia — every
  `:focus-visible` outline and the input caret. Use it whenever amber marks focus
  rather than lit content.

### Neutral
- **Fascia Graphite** (#17191b): the page body, under the fine brushed-metal
  texture.
- **Plate** (#202427 → #1a1e21): raised component plates (event cards, source
  bays, privacy plate, panels) — always as a top-lit vertical gradient, never flat.
- **Recess** (#101314): sunken wells that hold controls (tab tray, import row,
  ghost/hidden events), always with the inset recess shadow.
- **Black Surround** (#0a0b0c): the plastic housing — the fixed 12px viewport
  frame (`body::after`, with a hairline `#ffffff12` inner ring) and the page
  background behind the fascia.
- **Silkscreen Ink** (#e6e9e5): primary text and the hero headline.
- **Engrave** (#d5d9d5): silk-screened labels and headings (paired with the dark
  drop shadow); **Muted** (#a2aaa5) and **Faint** (#828b86) step body text down;
  **Line** (#3a4045) and **Line Soft** (#2e3438) are borders and hairline rules —
  hover raises borders to #6a7278.
- **Matrix Black** (#0d0c0a) with **Matrix Edge** (#332f28): the recessed display
  windows (stats, KPIs, meters, `pre` output, status pills, density strip) — a
  warmer black than the fascia, so the wells read as a different material.
- **LED Label** (#a79f8a): the only non-amber text allowed inside a matrix
  window — small printed captions under the digits.
- **Paper** (#e9e6d8) with **Paper Edge** (#a9a390): glued-on light cassette-label
  insets carrying dark text (#3a3a30 hints, #1b1b1b input text) — file paths, the
  search input, collapsed-content notes. On the blackface deck these are the
  brightest surfaces on screen.

### Tertiary — kind LEDs
Six bright lit hues that code event kinds everywhere (timeline chips, filter
swatches, mix bar, density strip, flow-graph pips, moment tags):
- **Message Green** (#46c46e), **Instruction Orange** (#e06a3b), **Tool Blue**
  (#56b6c8), **Reasoning Gold** (#e0b23e), **Context Grey** (#93a2ac), and
  **Error Red** (#ff5a4e). Pass/fail text uses **Ink OK** (#6fd88f) / **Ink Err**
  (#ff6b5e); matrix-window status pills reuse the same lit set (#6fd88f
  captured/clean, #ff6b5e high/not-observed, #9fb8c8 low). Unlit swatches rest at
  #4a5257.

### Named Rules
**The Amber Means Active Rule.** Amber appears only where something is switched
on: lit digits, the active key's indicator groove, the focus outline (as
amber-ink), selection, and the jump flash. It is never a decorative accent,
background, or brand color.

**The LED Chip Rule.** Event kinds are coded by an 8px square chip (2px radius,
`0 0 0 1px #00000038` rim, white inner top-light) — never by colored card
borders, tinted backgrounds, or colored text.

**The Paper Is Light Rule.** Paper insets keep their warm light fill and dark
text on the dark fascia — they are printed cassette labels, not theme-inverted
UI. Never darken paper to match the deck.

## Typography

**Display Font:** Barlow Condensed 500/600 (embedded data: woff2; fallback
ui-sans-serif, system-ui) — always uppercase with tracking
**Body Font:** ui-monospace (SFMono-Regular, Menlo, Consolas) — the system's
voice for prose, data values, and hints
**Matrix Font:** Doto 700 (embedded data: woff2; fallback ui-monospace) —
dot-matrix digits, used *only* lit amber inside matrix windows

**Character:** Industrial and printed. Condensed caps read as pale silkscreen on
dark hardware; the mono body reads as technical documentation; Doto reads as a
dot-matrix readout. All display text on the fascia carries the silkscreen
treatment: `text-shadow: 0 1px 1px #000000a0`, which seats the pale ink into the
surface.

### Hierarchy
- **Display** (600, clamp(48px, 7vw, 80px), 0.96, uppercase): the landing
  headline only — panel-scale silkscreen.
- **Headline** (600, 26px loaded-trace title / 16px panel h2 / 13.5px panel h3,
  uppercase, .04–.1em tracking): silk-screened section headings; panel headings
  sit on a 1px line-soft rule (`padding-bottom: 8px`).
- **Title/Key** (600, 12–15px, uppercase, .06–.12em tracking): every button
  label, tab, filter, pill, and component name.
- **Body** (400, 13.5px/1.65 mono): paragraphs, hints (12–12.5px), event payloads
  (`pre` at 12.5px/1.55 in cream #ddd6c2 on #131210).
- **Matrix** (Doto 700, 13–21px): stat and KPI values, the transport view
  readout, the topbar path window — amber with the phosphor glow.
- **Label** (500, 11.5px, .1em, uppercase): printed captions under matrix digits,
  in LED Label #a79f8a.

### Named Rules
**The Silkscreen Rule.** Barlow Condensed is always uppercase, weight 500 or 600,
letter-spaced, and — on the fascia — printed pale with the dark 1px drop shadow.
It never sets body copy.

**The Doto Discipline Rule.** Doto appears only as lit amber content inside a
matrix window. Never on the fascia, never in silkscreen ink, never for prose.

## Layout

One fascia, one column. The shell is `max-width: 1180px`, centered, with 24px
gutters and 120px bottom padding to clear the transport cluster. A fixed 12px
black plastic frame (`body::after`, 8px under 760px) surrounds the whole
viewport; the sticky topbar sits 12px down so it slides beneath the frame edge.

Internal grids are dense and mechanical: a 3-column source-bay grid (16px gap), a
2fr/1fr hero split, and `auto-fit minmax` grids for meter banks (stats 104px,
KPIs 150px, schema windows 250px). Vertical rhythm runs on small steps —
6/8/10/12/14/16px gaps, 20px panel padding, 14–22px between sections. The
timeline is a flat 8px-gap stack of plates, not a line-and-node diagram.

At ≤760px everything drops to one column, the tab tray becomes a full-width
horizontal scroller, the primary key goes full-width, and the transport cluster
stretches to `calc(100vw - 28px)`.

## Elevation & Depth

Depth is machined into the fascia, not cast onto it. There are no soft ambient
drop shadows; every shadow describes fabrication — a bevel, a recess, or a deep
display well. Raised things catch a faint white line at the top (inset
highlight); sunken things fall into black. The single floating shadow in the
system belongs to the fixed transport cluster (`0 8px 22px #000000b0`), which
hovers over the fascia as separate hardware.

### Shadow Vocabulary
- **Bevel up** (`0 1px 0 #ffffff12 inset, 0 1px 2px #00000090`): raised plates —
  event cards, source bays, panels, privacy plate.
- **Bevel key** (`inset 0 1px 0 #ffffff17, 0 1px 1px #000000a0`): pressable
  keys — tabs, filters, toggles, sample buttons, flow nodes.
- **Recess** (`inset 0 2px 4px #000000a0`): sunken trays and wells — tab tray,
  import row, ghost events.
- **Matrix window** (`inset 0 2px 8px #000000d0, 0 1px 0 #ffffff10`): deep
  display wells — the near-black windows get a heavy inner shadow plus a hairline
  lit lip on the fascia below them.
- **Phosphor glow** (`text-shadow: 0 0 6px #ffb00044`): the one glow in the
  system — amber Doto digits inside matrix windows only. It is lit-display
  material, not a UI effect.

### Named Rules
**The Machined Depth Rule.** Every shadow is a fabrication cue (bevel, recess,
well). No blur-heavy ambient shadows, no glassmorphism, no glow outside matrix
windows.

## Shapes

Small radii throughout — this is molded hardware, not soft UI. The scale is 2px
(LED chips and pips), 3px (paper labels, status pills), 4px (keys, matrix
windows, event payload wells), 6px (event plates, primary key, caution plate),
8px (panels, source bays, trays, the transport cluster). Nothing is pill-shaped
or circular except the 9px power dot in the brand (a radial-gradient amber LED).
Borders are 1px solid everywhere; the only dashed border is the paper
collapsed-note inset. The caution plate is a dim amber-lit warning
(#26200f fill, #6b5a1e border, #e0c878 text) carrying an 8px hazard stripe on
its left edge (`repeating-linear-gradient(135deg, reasoning-gold, #2a2a24)`).
Meter fills are dashed amber segments (`repeating-linear-gradient(90deg, amber
0 6px, transparent 6px 9px)`) so bars read as LED segments, not paint.

## Components

### Keys (buttons)
The universal control: a beveled snap key.
- **Shape:** 4px radius, 1px line border, top-lit gradient (#2b3034 → #1e2226)
- **Label:** Barlow Condensed 600 uppercase, engrave color, 11.5–12.5px
- **Hover:** border lifts to #6a7278 — no background or color animation
- **Active (pressed):** `transform: translateY(1px)` — the key physically snaps
  down
- **Selected state** (tabs, filters): an amber indicator groove — `inset 0 3px 0
  var(--amber)` under the top edge — plus full-ink label; the key itself stays
  graphite
- **Primary key** ("Import a trace"): larger (13px 26px padding, 6px radius, 15px
  label), lighter gradient (#33383d → #22262a), with a visible 3px key wall
  (`0 3px 0 #0b0c0d`); pressing travels 2px and shortens the wall to 1px
- **Focus:** `outline: 2px solid var(--amber-ink); outline-offset: 2px` on every
  interactive element

### Matrix windows (stats, KPIs, readouts, pills)
The signature component: a recessed near-black display.
- **Style:** matrix #0d0c0a fill, 1px matrix-edge border, 4px radius (3px for
  pills), matrix-window shadow
- **Content:** Doto 700 amber digits with the phosphor glow; captions in LED
  Label #a79f8a (Barlow Condensed 500, 11.5px, uppercase); status pills use the
  lit green/amber/red/blue set
- **Variants:** stat cell, KPI cell, mix bar and density strip (LED chips inside
  a window, 2–3px internal padding), bar-track meters with dashed amber fill,
  `pre` payload wells (cream #ddd6c2 mono text on #131210, dark scrollbar, amber
  selection), the transport readout, and the topbar path window

### Event plates (cards)
- **Style:** top-lit plate gradient (#202427 → #1a1e21), 1px line border, 6px
  radius, bevel up, `12px 16px` padding with a 34px left inset for the kind chip
- **Kind chip:** 8px square LED at left, colored by event kind (see The LED Chip
  Rule)
- **Hover:** border lifts to #6a7278 only
- **Ghost (hidden/filtered):** recessed instead of raised — recess fill #101314,
  recess shadow, 40%-opacity chip, "· hidden" / "· no match" suffix; clicking
  pops it back
- **Jump flash:** 2px amber outline fading over 1.6s (`flashfade`), the only
  keyframe animation in the system

### Paper labels (inputs and insets)
- **Style:** paper #e9e6d8 fill, 1px paper-edge border, 3–4px radius, slight
  inner shadow, dark text — a glued-on printed cassette label, the brightest
  surface on the deck
- **Search input:** paper style with #6b6553 border, near-black text #1b1b1b,
  warm placeholder #6b6553, amber-ink caret; focus swaps the border to amber-ink
  under the standard outline
- **Collapsed-content note:** dashed paper-edge border variant with #5a5546 text

### Caution plate
- **Style:** dim amber-lit warning — #26200f fill, 1px #6b5a1e border, #e0c878
  text, with the 8px hazard stripe on the left edge — used for the loaded-trace
  privacy warning

### Transport cluster (view switcher)
- **Style:** fixed, bottom-centered raised housing (gradient #22262a → #191d20,
  1px #4a5257 border, 8px radius, floating shadow, faint top bevel) holding two
  34×34px snap keys with chevron transport glyphs around a Doto amber readout
  window naming the current view

### Navigation (topbar)
- **Style:** sticky graphite strip (gradient #22262a → #191d20, 1px line
  border-bottom, faint bevel highlight) carrying the silk-screened brand with
  its amber power dot, an optional lit path window, the tab tray (a recessed
  well of keys, proper `role="tablist"` semantics), and the "New trace" key.
  Links are lit blue (#6faed4 body, #7cb3d6 footer).

## Do's and Don'ts

### Do:
- **Do** give every surface a material: bevel-up for raised plates,
  recess-shadow for wells, matrix-shadow for displays. A flat unshadowed
  rectangle is foreign here.
- **Do** silkscreen all Barlow Condensed text on the fascia with `text-shadow:
  0 1px 1px #000000a0`, uppercase, letter-spaced, in pale engrave ink.
- **Do** express pressing as `translateY(1px)` (2px for the primary key) with
  zero transition, and hover as a border lifting to #6a7278.
- **Do** put any new numeric readout in a matrix window as amber Doto with the
  `0 0 6px #ffb00044` glow and an LED-Label caption.
- **Do** keep focus visible everywhere: `2px solid var(--amber-ink)` (#cf8f00)
  outline, 2px offset — including on focusable non-buttons like flashed events.
- **Do** preserve the accessibility scaffolding: the `sr-only` polite live
  region for state announcements, tablist semantics on the view tabs, and the
  `prefers-reduced-motion` kill switch.
- **Do** keep the page self-contained under CSP `default-src 'none'`: fonts and
  images as `data:` URIs only, all CSS and JS inline, zero network requests.

### Don't:
- **Don't** use amber for anything that is not active or lit — no amber
  branding, amber fills at rest, or amber hover states.
- **Don't** add transitions or easing. Nothing glides: state changes are
  instantaneous snaps. The jump flash is the only animation, and reduced-motion
  disables it.
- **Don't** add light surfaces outside the paper insets. The deck is dark
  graphite; a white panel or light card breaks the world — paper cassette labels
  and lit displays are the only bright material.
- **Don't** let the dark fascia read as a dev console: no pure-black flat
  panels, no terminal-green accents, no borderless dark-on-dark rectangles —
  every dark surface carries its machined bevel, recess, or well.
- **Don't** color-code events with tinted card backgrounds, colored borders, or
  colored titles — the square LED chip carries the kind.
- **Don't** apply glow to anything outside a matrix window, and never to
  non-Doto text.
- **Don't** use radii above 8px, pill shapes, circles (the brand power dot is
  the sole exception), or borderless surfaces.
- **Don't** introduce a second display face or a webfont loaded over the
  network; the three-voice system (Barlow Condensed / ui-monospace / Doto) is
  complete.
