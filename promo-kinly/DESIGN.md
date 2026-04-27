# Design System — Kinly

## Overview

Kinly uses a high-contrast dual-mode layout: an ultra-light lavender hero (`#F8F7FC`) alternates with deep navy feature sections (`#0E0A3C`), creating a dramatic rhythm of "open air" and "serious depth." The signature move is neon lime (`#B8FF00`) used exclusively for emphasis — highlighted words, CTAs, selected states, and large step numbers. Typography is heavy and confident: Manrope 800 for display, DM Sans for everything else. Floating circular pill elements on the hero section give it a tactile, product-UI feel without using actual screenshots.

## Colors

- **Light Surface**: `#F8F7FC` — primary background for hero and light sections
- **Light Surface Dim**: `#F0EFF5` — cards and inset surfaces on light sections
- **Dark Surface**: `#0E0A3C` — feature/CTA sections background
- **Dark Surface Deep**: `#0C0A1A` — deepest backgrounds, also primary text color
- **Primary Text**: `#0C0A1A` — headings on light sections
- **Secondary Text**: `#6B6589` — body copy, subtitles on light
- **Muted Text**: `#4A4568` — descriptions, captions
- **Brand Navy**: `#221080` — nav links, logo type, icon fills
- **Accent Lime**: `#B8FF00` — THE signature color. Word highlights, CTAs, selected tabs, step numbers
- **Accent Lime Bright**: `#CCFF40` — hover / pressed state of lime
- **Bright Purple**: `#7B6FFF` — secondary accent on dark sections
- **White**: `#FFFFFF` — text on dark sections, card backgrounds

## Typography

- **Display**: Manrope (700–800). All major headings. Used at 52–96px. No letter-spacing adjustment needed — weight carries authority.
- **Body**: DM Sans (variable 400–700). Navigation, body copy, labels, badges, descriptions.
- **Sizing hierarchy**: Hero h1: 72px/800 · Section h2: 52px/700 · Sub-heading h3: 18–24px/600 · Body: 16–18px/400 · Label: 12–14px/600 uppercase

## Elevation

White cards on dark navy sections — no shadows, just the inherent contrast between `#FFFFFF` card and `#0E0A3C` background. Light sections use no card elevation — content floats on the surface. Borders are rare; spacing and color do the separation work. Circular pill/badge elements use 1px border at low opacity for definition. The app screenshot inside the feature card has no visible frame — just float with a light shadow to imply dimensionality.

## Components

- **Floating Icon Pills**: Circular elements (48–56px diameter) with dark navy background and icon, positioned absolutely around hero content. Non-interactive UI decoration.
- **Lime Highlight Span**: Inline text wrapped in a `#B8FF00` background-color, using `border-radius: 4px` and slight padding. Used sparingly — one highlighted word per headline.
- **Feature Tab Bar**: Pill-shaped tabs (Record Vault · AI Extraction · Health AI · Reminders) with lime selected state and subtle icon prefix.
- **Contrast Card**: White rounded-corner card (`border-radius: 16–20px`) on dark navy, containing left copy + right product screenshot. The product screenshot floats with slight rotation/tilt.
- **Numbered Step**: Oversized lime step number (01, 02, 03) at ~120px, DM Sans 800, with arrow connecting to description.
- **Trust Pill Row**: Three inline divs (End-to-end encrypted · Your data is never sold · Privacy by design) with small icon prefix and muted text.
- **Testimonial Cards**: Minimal white/light cards with quotation mark, body copy, author name+role. Clean, no decorative borders.
- **CTA Button**: Pill-shaped (`border-radius: 100px`), lime background, dark text, DM Sans 700.

## Do's and Don'ts

### Do's
- Use `#B8FF00` for exactly one emphasis per scene — it loses power if overused
- Alternate light (`#F8F7FC`) and dark (`#0E0A3C`) backgrounds to create visual rhythm
- Let white space do the work — wide margins (160px+), generous line height
- Use Manrope 800 for display text — the weight is the brand's authority signal
- Floating circular icon elements can appear as decorative background elements

### Don'ts
- Do not use serif fonts — the brand is strictly sans-serif
- Do not use gradients on backgrounds — flat color only, with localized radial glows if needed
- Do not use multiple accent colors in the same scene — lime is the single accent
- Do not round corners excessively on text containers — only cards and buttons use `border-radius`
- Do not use drop shadows on text — rely on color contrast
