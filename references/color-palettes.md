# Color Palettes — Dark-Cream System

All five themes share the same semantic variable names (`C.darkBg`, `C.cream`, `C.orange`, etc.) so that slide code requires **zero changes** when swapping themes. Just replace the `C` object at the top of `slides.js`.

---

## How to Apply a Theme

Copy the chosen `C = { ... }` block verbatim and paste at the top of `slides.js`, replacing any existing palette.

---

## Theme 1 — 暗夜橙光 (Deep Night, Burnt Orange)

**Mood:** Professional, dramatic. Warm tension between cool navy and burnt orange. The original palette for《从Chatbot到Agent》.

```js
const C = {
  darkBg:    "1C1C2E",   // deep navy — cover, section, dark slides
  sectionBg: "252540",   // slightly lighter navy for section dividers
  cream:     "F5F0E8",   // warm cream — all content slides
  white:     "FFFFFF",
  orange:    "D97449",   // burnt orange — primary accent, CTAs, highlights
  blue:      "5B8CDB",   // secondary accent
  teal:      "4ABFBF",   // tertiary accent
  green:     "4CAF7D",   // positive / success
  textDark:  "1C1C2E",   // body text on cream
  textLight: "F5F0E8",   // body text on dark
  muted:     "9090A8",   // secondary text, captions
  divider:   "3A3A5C",   // horizontal rules, shape strokes on dark
  cardBorder:"E0D8CE",   // card borders on cream
};
```

*Accent usage guide: orange → primary headlines/CTAs; blue → tech/data; teal → process/flow; green → positive outcomes.*

---

## Theme 2 — 深蓝碧海 (Deep Sea, Teal)

**Mood:** Calm, trustworthy, slightly clinical. Works well for research, data-heavy, or health/science presentations.

```js
const C = {
  darkBg:    "0D1B2A",   // ocean deep blue
  sectionBg: "162336",   // mid-ocean blue for section dividers
  cream:     "F7F3EC",   // warm ivory content background
  white:     "FFFFFF",
  orange:    "2EBFA5",   // primary accent → teal (replaces orange role)
  blue:      "4A90D9",   // secondary accent — sky blue
  teal:      "1AADA0",   // deeper teal for variety
  green:     "3DB87A",   // positive/success
  textDark:  "0D1B2A",
  textLight: "EEF4F8",
  muted:     "7A92A8",
  divider:   "1E3048",
  cardBorder:"DFD9D0",
};
```

*Note: `C.orange` here is teal — it fills the "primary accent" role across all templates without changing variable names.*

---

## Theme 3 — 墨绿暖沙 (Forest Dark, Coral)

**Mood:** Organic, warm, earthy. Suits branding, consumer insights, lifestyle product research.

```js
const C = {
  darkBg:    "1A2E20",   // deep forest green
  sectionBg: "233B2A",   // slightly lighter forest
  cream:     "F5EDD6",   // warm sand / parchment
  white:     "FFFFFF",
  orange:    "E8734A",   // coral — primary accent (replaces orange role)
  blue:      "5B9E8C",   // sage teal — secondary
  teal:      "3A8C7A",   // deeper sage
  green:     "6AB870",   // lighter forest green for positives
  textDark:  "1A2E20",
  textLight: "F5EDD6",
  muted:     "8A9E90",
  divider:   "2E4E38",
  cardBorder:"E0D4B8",
};
```

---

## Theme 4 — 暗紫金调 (Deep Purple, Gold)

**Mood:** Premium, editorial, slightly mysterious. Good for executive presentations, brand strategy, AI/tech with a luxury feel.

```js
const C = {
  darkBg:    "1E1A2E",   // deep violet-navy
  sectionBg: "29233F",   // lighter violet for section dividers
  cream:     "F5F0E8",   // same warm cream as Theme 1
  white:     "FFFFFF",
  orange:    "D4A853",   // warm gold — primary accent (replaces orange role)
  blue:      "7B6FCC",   // violet — secondary
  teal:      "5B9FBF",   // steel blue — tertiary
  green:     "6AAF7D",   // sage green for positives
  textDark:  "1E1A2E",
  textLight: "F0EBE8",
  muted:     "9488B0",
  divider:   "3D3460",
  cardBorder:"E5DDD0",
};
```

---

## Theme 5 — 铁青暖橙 (Steel Dark, Amber)

**Mood:** Technical yet approachable. High contrast, slightly industrial. Good for engineering/product/AI-focused audiences.

```js
const C = {
  darkBg:    "1A1F2E",   // steel charcoal-navy
  sectionBg: "222840",   // mid-steel
  cream:     "F0EBE1",   // warm linen
  white:     "FFFFFF",
  orange:    "E8952A",   // amber — primary accent
  blue:      "4E8FCC",   // electric blue — secondary
  teal:      "3AAFB8",   // cyan-teal — tertiary
  green:     "56B87A",   // positive
  textDark:  "1A1F2E",
  textLight: "EEF0F5",
  muted:     "8898B8",
  divider:   "2E3850",
  cardBorder:"DDD8CE",
};
```

---

## Accent Color Assignment Guide

All templates use these semantic roles. When switching themes, the accent colors shift but the template code stays the same:

| Variable | Semantic role | Template usage |
|---|---|---|
| `C.orange` | Primary accent | Section numbers, card headers, CTA buttons, highlighted rows, timeline markers |
| `C.blue` | Secondary accent | Tags, subtle badges, secondary highlights |
| `C.teal` | Tertiary accent | Third timeline item, additional variety in multi-card layouts |
| `C.green` | Positive / success | "Good" column in comparisons, achieved milestones, positive data |
| `C.muted` | Captions & secondary text | Subtitles, body copy on dark, speaker notes style |
| `C.divider` | Dark-bg strokes | Card borders, rule lines on dark slides |
| `C.cardBorder` | Cream-bg strokes | Card borders, rule lines on cream slides |

---

## Pairing Notes

- **Text on `cream` backgrounds:** use `C.textDark`
- **Text on `darkBg`/`sectionBg` backgrounds:** use `C.textLight`
- **Dark card on cream slide:** use `C.darkBg` fill + `C.textLight` text (creates contrast pop)
- **Accent on dark slide:** `C.orange` (primary) pops well against all five dark backgrounds
- **Section number watermark:** use `C.divider` (very low contrast, intentional)
