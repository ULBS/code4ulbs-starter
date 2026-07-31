---
name: ulbs-brand
description: Apply ULBS official brand guidelines — colors, typography, logos, and visual identity rules. Use when creating materials for "Lucian Blaga" University of Sibiu.
version: 1.0.0
author: ULBS Marketing & DCM
license: Proprietary — ULBS Brand
metadata:
  hermes:
    tags: [ulbs, university, branding, visual-identity, romanian, sibiu]
    related_skills: []
---

# ULBS Brand Guidelines

## Overview

Official brand identity for **"Lucian Blaga" University of Sibiu (ULBS)**. Apply these rules whenever producing visual materials — social media graphics, presentations, documents, web components, print materials, or any other medium carrying the ULBS name.

**Assets in this folder:**
- `SKILL.md` — brand guidelines (this file)
- `logos/` — 4 logo variants (horizontal/vertical × positive/negative) + favicon

### Brand Manual

Full visual identity manual (PDF, Google Drive — may require @ulbsibiu.ro auth):
- [Manual_Identitate_Vizuala_ULBS_2020](https://drive.google.com/file/d/1EjgdVtWc6qRaoLqJIqKoQt7SdgzwkRs_/view?usp=sharing)

### Logos — Complete Packages (Google Drive)
- [Main ULBS logos — all formats](https://drive.google.com/drive/folders/1WuoRIRd3y0GZyhVz2EcYYJa1Oh3DXfHR?usp=sharing)
- [Faculty logos — all formats](https://drive.google.com/drive/folders/1DldiLuIX52RHcF1YgJoerHoY3qabbv3-?usp=sharing)
- [Rectorate logos — all formats](https://drive.google.com/drive/folders/1NrQUVVdnnE9FxfrjnL82pMESJz4w1mCP?usp=sharing)

### Internal Use (@ulbsibiu.ro auth required)
- [Letterhead, PPT templates, Business cards](https://drive.google.com/drive/folders/1zhryplc_EZl7oTrgcO6IEFaP8v-KOgF8?usp=sharing)

## When to Use

- Generating any visual material for ULBS (social posts, flyers, presentations, reports)
- Building web components/pages for ULBS subdomains
- Creating templates for official ULBS communication
- Designing promotional or academic materials bearing the ULBS identity
- Reviewing external materials that use the ULBS name

**Do NOT use for:** non-ULBS projects, personal work unrelated to the university, materials that haven't been approved by the Communications and Marketing Department (`marketing@ulbsibiu.ro`).

## Brand Colors

### Primary Palette

| Color | Hex | Usage |
|---|---|---|
| Dark Navy | `#0B2F63` | Primary brand color — headers, navigation, faculty items, links |
| Very Dark Navy | `#011F5B` | Table headers, cookie banners, high-contrast elements |
| White | `#FFFFFF` | Backgrounds, text on dark |

### Accent Palette

| Color | Hex | Usage |
|---|---|---|
| Purple | `#622483` | Navigation dropdown carets, secondary accents |
| Bright Blue | `#2184FF` | Selection highlight, interactive elements |
| Burgundy | `#900E36` | Banner navigation controls |
| Gold/Orange | `#F7A30F` | Tertiary accents, alerts |
| Red | `#EE1927` | Warnings, critical indicators |
| Green | `#7FCC27` | Positive indicators, success states |
| Teal | `#10ADB6` | Supplementary accent |
| Light Blue | `#1AB7EA` | Social media, light accents |

### Neutral Palette

| Color | Hex | Usage |
|---|---|---|
| Heading Text | `#454B67` | H1–H6 headings |
| Secondary Text | `#414755` | Muted/helper text |
| Light Gray | `#F7F7F7` | Subtle backgrounds |
| Border Gray | `#EDEDED` | Dividers, borders |
| Light Blue-Gray | `#D7E1EB` | Hover states, light accents |
| Accessibility | `#4054B2` | Accessibility toolbar |
| Medium Gray | `#959392` | Secondary icons |
| Dark Text | `#000000` | Body text |

## Typography

### Primary Font

**Open Sans** (Google Font)
- Weights used: 300 (Light), 400 (Regular), 600 (SemiBold), 700 (Bold)
- **Fallback:** `sans-serif`
- **Usage:** Body text (`font-size: 14px`), navigation (`font-weight: 600, font-size: 17px`), headings, all UI text

### Secondary Font

**Agenda-Ro** (custom web font licensed for ULBS)
- Weights: Normal/Regular, Normal/Italic, Medium (500), SemiBold (600), Bold, Bold/Italic
- **Fallback:** Helvetica, Arial, sans-serif
- **Usage:** Banner headings, specialized promotional materials
- **Note:** Hosted locally at `assets/fonts/agend*.woff` — embed from ULBS server or use Open Sans as fallback

### Decorative Font

**Handsome** (custom web font)
- Weight: Regular only
- **Fallback:** serif
- **Usage:** Rarely used, mostly in legacy materials

### Typography Scale

| Element | Size | Weight | Color |
|---|---|---|---|
| H1 | 30px | Bold | `#454B67` |
| H2 | 20px | Bold | `#454B67` |
| H3 | 18px | Bold | `#454B67` |
| Body | 14px | Normal (400) | `#000000` |
| Navigation | 17px | SemiBold (600) | `#FFFFFF` (on dark) |
| Small/Meta | 12px | Normal | `#414755` |

## Logo Specifications

### Logo Variants

All logos are available in **PNG** (raster) and **PDF** (vector) formats.

| Variant | Type | Dimensions (px) |
|---|---|---|
| **LOGO-ULBS_orizontal** | Horizontal — positive (dark text on light bg) | 1182 × 353 |
| **LOGO-ULBS_orizontal_negativ** | Horizontal — negative (white text on dark bg) | 1181 × 352 |
| **LOGO-ULBS_vertical** | Vertical — positive | 860 × 694 |
| **LOGO-ULBS_vertical_negativ** | Vertical — negative | 861 × 694 |

### Logo Rules

1. **Do NOT modify** the logo except for proportional resizing
2. **Do NOT** distort, rotate, recolor, or add effects
3. **Black-and-white** variants only for monochrome print materials
4. Use **positive** variant on light backgrounds, **negative** on dark backgrounds
5. Maintain clear space — minimum margin = 1× logo height from all edges
6. Use **horizontal** variant whenever space allows; **vertical** for constrained spaces

### Logo Approval

All logo use **must be approved** by the Communications and Marketing Department:
- Email: `marketing@ulbsibiu.ro` or `relatii.publice@ulbsibiu.ro`
- Phone: 0269/217779, int. 143 / 147

## Web Implementation Notes

### CSS Variables (recommended)

```css
:root {
  /* Primary */
  --ulbs-dark-navy: #0B2F63;
  --ulbs-very-dark-navy: #011F5B;
  --ulbs-white: #FFFFFF;

  /* Accents */
  --ulbs-purple: #622483;
  --ulbs-bright-blue: #2184FF;
  --ulbs-burgundy: #900E36;
  --ulbs-gold: #F7A30F;
  --ulbs-red: #EE1927;
  --ulbs-green: #7FCC27;
  --ulbs-teal: #10ADB6;

  /* Text */
  --ulbs-heading: #454B67;
  --ulbs-body: #000000;
  --ulbs-secondary: #414755;

  /* Surfaces */
  --ulbs-bg-light: #F7F7F7;
  --ulbs-border: #EDEDED;
  --ulbs-bg-hover: #D7E1EB;

  /* Typography */
  --ulbs-font-body: 'Open Sans', sans-serif;
  --ulbs-font-heading: 'Open Sans', sans-serif;
}
```

### Dark Mode Adaptation

On dark backgrounds:
- Use **negative** logo variant (white text)
- Text: `#FFFFFF` on dark navy backgrounds
- Accent colors stay the same but may need lighter variants
- Adjustable backgrounds should retain `#0B2F63` as primary dark surface

### Navbar (current site pattern)

```
background-color: #0B2F63
text: #FFFFFF, font: Open Sans 600 17px
hover dropdown bg: #0B2F63
dropdown text: #011F5B
```

## Common Pitfalls

1. **Using wrong logo variant** — always match variant to background (positive on light, negative on dark). Never use the colored logo on a busy photographic background without checking with marketing.
2. **Missing font licenses** — Agenda-Ro and Handsome are licensed fonts. Use Open Sans for web unless you have the font files hosted.
3. **Color inaccuracy** — brand navy (`#0B2F63`) is often confused with `#011F5B`. Use `#0B2F63` as the primary brand color; `#011F5B` is for high-contrast table headers only.
4. **Logo modification** — stretching, adding drop shadows, or changing logo colors is strictly forbidden. Only proportional scaling allowed.
5. **Missing approval** — always route new ULBS materials through `marketing@ulbsibiu.ro` before publishing.

## Verification Checklist

- [ ] Logo variant matches background (positive/negative)
- [ ] Logo is proportionally scaled, not distorted
- [ ] Primary brand color is `#0B2F63` (not `#011F5B` unless table header)
- [ ] Typography uses Open Sans (body) or explicit web font fallback
- [ ] Heading color: `#454B67` on light backgrounds
- [ ] Materials approved by Communications and Marketing Department
- [ ] Print materials: CMYK versions used where applicable
- [ ] Digital materials: sRGB color space
