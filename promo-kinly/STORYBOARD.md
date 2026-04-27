# Storyboard — Kinly 30s Launch Video

**Format:** 1920×1080 landscape
**Duration:** 30 seconds
**Audio:** Kokoro TTS voiceover (`af_nova`) + minimal electronic underscore
**VO direction:** Warm female voice, measured delivery, mid-pace. Conversational — not corporate. Pauses are intentional. The quiet between sentences is breathing room, not dead air.
**Style basis:** DESIGN.md — Kinly brand (DM Sans + Manrope, lime accent, dual light/dark rhythm)
**Music direction:** Minimal electronic underscore. Warm sustained pad, slow arpeggiated pulse. Sits well under the VO, never competing. Gentle swell at Beat 4 (product reveal), drops back for testimonial stat, resolves on a warm chord at the final CTA.

---

## Asset Audit

| Asset | Type | Beat | Role |
|-------|------|------|------|
| `capture/assets/image.jpg` | Product screenshot (Reminders) | Beat 4–5 | Feature card visual |
| `capture/assets/svgs/icon-1.svg` through `icon-20.svg` | UI icons | All beats | Floating decorative pill elements |
| `capture/assets/svgs/pointer-events-none.svg` | Decorative shape | Beat 1 | Background texture |
| `capture/assets/svgs/mb-4.svg` | Decorative shape | Beat 1 | Background texture |
| Font files (DM Sans, Manrope) | Typography | All | Embedded via compiler |

*Note: The app screenshot (`image.jpg`) is the primary product visual. Icon SVGs will be used as floating pill decorations on hero beats.*

---

## Global Guardrails

- **Lime (`#B8FF00`) appears exactly once per beat** — on the most important word or element. Never two lime elements simultaneously.
- **Every beat has 3 depth layers** — background texture/glow, midground content, foreground accents.
- **All entrance animations are `from()` only** — no exit animations except final fade to white.
- **Font rule:** Manrope 800 for display headlines. DM Sans 400–700 for everything else. No other fonts.

---

## Beat-by-Beat Direction

---

### BEAT 1 — THE HOOK (0:00–4.0s)

**VO:** *"Your family's medical history lives in a dozen different places."*

**Concept:** We open mid-scene, not with a title card. The viewer is already inside a light, spacious world — but it's fractured. The medical history of one family is scattered across a dozen fragmented boxes drifting apart. This isn't chaos — it's the quiet, mundane frustration of something that should be simple but isn't. The lime word "dozen" lands like a small punch of recognition.

**Visual:**
The canvas is `#F8F7FC` — the Kinly light surface. A gentle radial glow in `#E2E0ED` breathes in from center. Six floating rectangular cards drift slowly outward from a central point — each labeled with a chaos source: "WhatsApp", "Gallery", "Email", "Paper", "Clinic App", "Memory". Cards are white (`#FFFFFF`), 200×80px, 12px radius, with a small icon on the left. They drift apart with subtle rotation (±4°) over the 4-second beat — a slow visual centrifuge. The headline types on word by word in center: "Your family's medical history lives in a" — then **"dozen"** appears with a `#B8FF00` background highlight (inline span, 4px radius). "different places." types on to complete it. Below, a secondary line fades up: DM Sans 400, 28px, `#6B6589`.

**Mood:** Clean morning light. The kind of quiet frustration that's entirely relatable before you've had your coffee. Apple Health app meets a thoughtful editorial magazine.

**Techniques:**
1. **Per-word typing effect** — headline reveals word-by-word, 0.08s stagger, y:16→0, opacity:0→1, power2.out
2. **Inline lime highlight span** — `#B8FF00` background on "dozen", appears at the same time as the word with `scaleX:0→1, transformOrigin:left, 0.25s expo.out`
3. **Floating cards** — GSAP tween each card `x:±(20+i*15), y:±(10+i*8), rotation:±4, duration:4.5, ease:sine.inOut`

**Depth layers:**
- BG: `#F8F7FC` + centered radial glow `rgba(226,224,237,0.6)`, 800px, slow scale 1→1.05 over 4s
- MG: Headline text block, centered, z-index 2
- FG: 6 drifting chaos cards, z-index 3, scatter outward

**Transition to Beat 2:** Velocity-matched upward — entire scene exits `y:-80, blur:16px, opacity:0, 0.30s power2.in`. Beat 2 enters `y:80→0, blur:16px→0, 0.35s power2.out`.

---

### BEAT 2 — THE PROBLEM (4.0–7.5s)

**VO:** *"WhatsApp threads. Old photos. Prescriptions no one can find."*

**Concept:** Three rapid-fire truth bombs. Each one is its own moment — a fragment of a familiar frustrating experience. The background is the same light surface, but now we're in a tighter, more urgent register. Text comes in fast, not slow. Short sentences. Short breath.

**Visual:**
Same `#F8F7FC` surface. Three lines enter sequentially, left-aligned, x: 0-800 zone, vertically stacked with 48px gap. Each line is Manrope 700, 64px, `#0C0A1A`. They don't fade in gently — they SLAM in from x:−60 to x:0 in 0.22s, power3.out. Stagger: 0.28s between each line. As each line arrives, a thin underline draws left-to-right beneath it (SVG path, `#B8FF00`, 3px, 0.3s). On the right side (x: 1000–1920), a blurred ghost version of the chaos cards from Beat 1 floats at low opacity (0.08) — a visual echo of the mess.

**Mood:** Staccato. Percussive. Each line hits like a beat drop. The viewer nods along — yes, yes, yes.

**Techniques:**
1. **SVG underline path drawing** — each line gets a `#B8FF00` underline that draws left-to-right on arrival, `strokeDashoffset:width→0, 0.3s, power2.out`
2. **Slam entrance** — `x:-60→0, 0.22s, power3.out` per line, 0.28s stagger
3. **Ghost echo** — right-side blurred echoes of Beat 1 cards at `opacity:0.06, filter:blur(8px)`, GSAP `from({opacity:0}, 0.6s)`

**Depth layers:**
- BG: `#F8F7FC` — same surface, no glow (starkness signals urgency)
- MG: Three stacked problem lines, left-anchored
- FG: SVG underlines drawing on, lime accent

**Transition to Beat 3:** Hard cut — 0s. Smash directly into the dark reveal. The contrast is the effect.

---

### BEAT 3 — THE REVEAL (7.5–10.5s)

**VO:** *"Meet Kinly."*

**Concept:** The camera smash-cuts into darkness. From `#F8F7FC` to `#0E0A3C` — instantaneous. Two words. That's it. "Kinly" lands big, centered, with absolute authority. The lime underline traces itself beneath the brand name as if signing a signature. This is the product's entrance — earned, confident, unhurried.

**Visual:**
Dark navy canvas `#0E0A3C`. A large radial glow in `#221080` (200px radius → 1000px, scale animation) blooms from center as the scene opens, reaching full size in 0.8s. "Meet" appears first — DM Sans 400, 32px, `#9490AB`, letter-spacing 0.2em, uppercase, fades up from y:12 in 0.3s. Then "Kinly" STAMPS down — Manrope 800, 148px, `#FFFFFF`, `scale:0.92→1, y:0, opacity:0→1, 0.4s power4.out`. One beat of silence. Then the lime underline draws itself beneath "Kinly" left-to-right over 0.6s (SVG path, `#B8FF00`, 6px, rounded). Floating decorative icon pills appear — 4 circular dark elements with SVG icons from `capture/assets/svgs/`, positioned at corners, fading in at 0.3 opacity.

**Mood:** Stage lights coming up on the performer. The confidence of a product that knows what it is. Apple event energy — calm, certain, monumental.

**Techniques:**
1. **SVG signature underline** — lime path draws beneath brand name, `strokeDashoffset` animation, `#B8FF00`, 6px stroke, 0.6s power2.out
2. **Radial bloom** — Canvas 2D or CSS radial-gradient animation, `#221080` glow scales from 200→1000px, 0.8s power1.out
3. **Scale stamp** — "Kinly" enters `scale:0.92→1, 0.4s power4.out`, subtle overshoot

**Depth layers:**
- BG: `#0E0A3C` + centered radial bloom `#221080`
- MG: "Kinly" wordmark, 148px, centered
- FG: 4 floating circular icon pills at corners, `opacity:0.35`

**Transition to Beat 4:** Zoom through — `scale:1→1.08, blur:0→20px, 0.25s power3.in` out; `scale:0.92→1, blur:20px→0, 0.4s expo.out` in.

---

### BEAT 4 — THE PRODUCT (10.5–16.0s)

**VO:** *"One app for your entire family's health — and an AI that actually knows them."*

**Concept:** We're still in the dark feature section. The product screenshot floats into frame on the right as a white card — the Kinly app, alive and elegant against the deep navy. On the left, the copy arrives in layers. The phrase "actually knows them" hits with lime emphasis — this isn't just storage, it's intelligence.

**Visual:**
`#0E0A3C` background (same dark surface, but now it has a subtle dot-pattern texture at 3% opacity for depth). Left zone (x:0–800): feature copy stacks in. Top: "YOUR FAMILY'S HEALTH" — DM Sans 700, 16px, letter-spacing 0.2em, `#7B6FFF`. Then the headline: Manrope 800, 72px, `#FFFFFF`, "One app for your entire family's health." on two lines. Then "— and an AI that <span style='color:#B8FF00'>actually knows them</span>." — the lime phrase appears last, sliding up from y:20. Right zone: the product card enters from x:120→0, `opacity:0→1, 0.45s power3.out`. Card is white, 280×580px, 20px radius, box-shadow, containing `capture/assets/image.jpg` (Reminders screenshot). Card floats subtly up/down, ±10px, 2.5s sine.inOut yoyo loop.

**Mood:** A product you trust. The dark background is deliberate authority. The white card says "this is clean." The lime phrase says "this is different."

**Techniques:**
1. **CSS floating card** — product screenshot as a white-bordered phone card, floats ±10px on sine.inOut, 2.5s yoyo
2. **Per-word cascade** — headline words enter staggered, y:28→0, opacity:0→1, 0.08s stagger
3. **Lime inline emphasis** — "actually knows them" has `color:#B8FF00`, enters with a slight x:8→0 offset after the rest of the line

**Depth layers:**
- BG: `#0E0A3C` + dot pattern (CSS radial-gradient at 3% opacity, 20px spacing) + `#221080` radial glow right-side
- MG: Left text block + right product card
- FG: Subtle purple glow ring behind product card (`border-radius:50%`, blur)

**Transition to Beat 5:** Velocity-matched upward — `y:-80, blur:16px, 0.28s power2.in` → `y:80→0, blur:0, 0.35s power2.out`.

---

### BEAT 5 — FEATURE 1: SCAN (16.0–20.0s)

**VO:** *"Upload any report. Kinly reads it instantly."*

**Concept:** Light scene. A document floats in, gets "scanned" — a lime beam sweeps across it. Then structured data values emerge from it, floating outward as labeled pills. AI as transformation: chaos in, clarity out. Fast. Satisfying.

**Visual:**
Back to `#F8F7FC` light surface. A document card (white, 340×200px, 12px radius, subtle border `rgba(34,16,128,0.12)`) drops in from y:−60 to center-right at 0.4s power3.out. It has placeholder text lines (three gray bars, 140px, 100px, 80px wide). A lime horizontal line (`#B8FF00`, 3px) sweeps across the document top-to-bottom in 0.5s — the "scan" moment. After the sweep, four data pills CASCADE out from the right side of the document: white pills with a bold value and a gray label ("HbA1c — 7.2%", "Glucose — 94", "Cholesterol — 180", "Status — Normal"). Pills stagger in with `x:30→0, opacity:0→1, 0.12s stagger`. Left zone: headline "Upload any report." — Manrope 700, 68px, `#12103A`. Second line: "<span style='color:#B8FF00'>Kinly reads it</span> instantly." — lime phrase.

**Mood:** Frictionless. The product makes something that felt tedious feel instant and obvious. Satisfying UI interaction energy.

**Techniques:**
1. **Sweeping scan line** — lime div, `height:3px, width:100%`, animates `top:0%→100%` (or `scaleY` + translate), 0.5s power1.inOut
2. **Cascading data pills** — staggered `x:30→0, opacity:0→1, 0.12s stagger, back.out(1.4)`, 4 pills total
3. **Document drop** — `y:-60→0, opacity:0→1, 0.4s power3.out`

**Depth layers:**
- BG: `#F8F7FC` + left-side radial glow `rgba(108,92,231,0.08)`
- MG: Document card + data pills
- FG: Scan line sweep (lime), headline left

**Transition to Beat 6:** Blur through — `blur:0→18px, opacity:1→0, 0.28s power2.in` → `blur:18px→0, opacity:0→1, 0.30s power2.out`.

---

### BEAT 6 — FEATURE 2: AI (20.0–24.0s)

**VO:** *"Ask anything. Get answers grounded in their real records."*

**Concept:** Dark scene. Three AI query bubbles appear in sequence — each one a question a real family caregiver would ask, pulled directly from the website copy. Each question appears as if being typed. Below each question, a brief answer. This is not a demo — it's empathy. The viewer sees their own questions in the list.

**Visual:**
`#0E0A3C` dark surface. Right-side radial glow `#221080`. Three chat bubbles appear left-to-right in sequence, each 0.4s apart:
1. `"Is my mother's cholesterol improving?"` — user bubble (rounded pill, `rgba(34,16,128,0.6)` background, `#E2E0ED` text, right-aligned)
2. `"When was Ahmed's last blood test?"` — user bubble
3. `"What medications is my father on?"` — user bubble

Each bubble enters from x:40→0, opacity:0→1, 0.32s back.out(1.2). After all three are visible, a single AI response bubble fades up at center: `"Based on his records — Metformin 500mg, Lisinopril 10mg."` — DM Sans 400, 18px, `#FFFFFF`, bubble background `rgba(108,92,231,0.18)`, lime left border (4px `#B8FF00`). Left text block: "Ask anything." — Manrope 800, 72px, `#FFFFFF`. Second line: "Get answers grounded in" + lime "real records." inline.

**Mood:** Intimate, useful, human. Not "AI powered" in a cold tech way — in a "it knows my family" way. The questions feel like things Fatima actually asks.

**Techniques:**
1. **Chat bubble cascade** — three user questions stagger in, `x:40→0, 0.32s, back.out(1.2), 0.4s stagger`
2. **AI response reveal** — answer bubble fades up with `y:20→0, opacity:0→1, 0.4s power2.out`
3. **Lime border accent** — 4px left border on AI bubble pulses gently `opacity:0.6→1, 0.6s sine.inOut, yoyo, repeat:2`

**Depth layers:**
- BG: `#0E0A3C` + `#221080` glow right-center
- MG: Left headline + right chat bubbles
- FG: AI response bubble with lime border

**Transition to Beat 7:** Cinematic zoom — `scale:1→1.06, blur:0→16px, 0.3s power2.in` → `scale:0.94→1, blur:16px→0, 0.45s expo.out`.

---

### BEAT 7 — PROOF + CTA (24.0–30.0s)

**VO:** *"One hundred and forty three of two hundred spots are claimed. Kinly. Secure yours today."*

**Concept:** Back to dark. The final beat is a CTA — but it earns it with social proof first. A counter animation counts up to 143, then settles. Below it, the full brand name. Then the lime button. Fade to white on the final word.

**Visual:**
`#0E0A3C` dark surface. Wide centered radial glow `#2E1BA8`, 1200px. At center, a counter: Manrope 800, 120px, `#FFFFFF`. It animates from `0` to `143` over 1.2s (ease: power1.out), then holds. Below the counter: DM Sans 400, 24px, `#6B6589`, "of 200 spots claimed." fades up. Then a spacer. Then "kinly" — DM Sans 700, 40px, `#FFFFFF`, letter-spacing 0.12em, lowercase, slides up from y:20. Then below it, the lime CTA button — pill shape, `background:#B8FF00`, `color:#0C0A1A`, DM Sans 700, 22px, text "Secure Your Spot". Button bounces in `scale:0.85→1.05→1, 0.5s, back.out(2.0)`. Hold for 2s. Then fade entire scene to `#FFFFFF` over 1.5s.

**Mood:** Landing. A product that has real demand, real momentum. The counter is not bragging — it's creating urgency. The CTA is confident, not desperate.

**Techniques:**
1. **Counter animation** — GSAP counter proxy `{val:0}` → `{val:143, duration:1.2, ease:power1.out}`, `Math.round(proxy.val)` on `onUpdate`
2. **Lime CTA button bounce** — `scale:0.85→1.05→1, 0.5s, back.out(2.0)`
3. **Fade to white** — `#FFFFFF` overlay div, `opacity:0→1, 1.5s, power2.in` from 28.5s

**Depth layers:**
- BG: `#0E0A3C` + wide radial glow `#2E1BA8`
- MG: Counter + brand name + CTA button, all centered
- FG: White fade-out overlay

**Transition:** Fade to `#FFFFFF`. End.

---

## Production Architecture

```
apps/promo-kinly/
├── index.html                    Root composition (30s, all beats inline)
├── DESIGN.md                     ✓ Brand reference
├── SCRIPT.md                     ✓ Narration
├── STORYBOARD.md                 ✓ This file
├── narration.wav                 TTS audio (Step 5)
├── transcript.json               Word timestamps (Step 5)
├── capture/
│   ├── screenshots/
│   ├── assets/
│   │   ├── image.jpg             Reminders screenshot → Beat 4
│   │   └── svgs/                 Icon pills → Beats 1, 3
│   └── extracted/
└── renders/
```
