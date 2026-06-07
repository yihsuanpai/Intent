# Intent — Design System

**Version 1.0** · **Date 2026-06-07** · Personal Finance Management + Payments for humans and AI agents
*Your intent becomes the outcome.*

---

## 1. Overview

Intent is an AI-era money app where a stated intent — "save for the trip," "pay rent on the 1st," "show me where July leaked" — resolves into a clear, confident outcome. The interface is built for two kinds of users at once: humans who want calm clarity, and AI agents who act on their behalf. Both deserve a surface that is legible, fast, and trustworthy.

This document is the single source of truth for tokens, components, and behavior. It is mobile-first, designed against a 375×812 phone frame, and ships in two coordinated themes (light and dark) that share one ink-and-electric-blue identity.

---

## 2. Brand Essence & Principles

Intent is premium, forward, and quietly intelligent. It is not a red, alarm-driven banking app — it is a blue-forward, composed system that makes money feel under control. Five principles govern every decision:

1. **Intent → Outcome.** Every screen answers "what did I want, and what happened?" We lead with the result (a number, a status, a confirmation), then offer the detail. Inputs are short; outcomes are vivid.
2. **Calm clarity.** Generous space, restrained color, one accent. We use motion and emphasis to direct attention, never to decorate. Coral appears only when something genuinely needs a human.
3. **Dual / adaptive.** Dark ink surfaces carry the brand and AI moments; light surfaces carry data. The two coexist in a single product without friction (see Theming).
4. **Honest numbers.** Money is always tabular, aligned, and signed. We never round away meaning. Positive is green, spend is neutral ink, alerts are coral — and we are consistent.
5. **Witty where it earns it.** Highlights and the monthly story can be warm and clever. Errors, balances, and confirmations stay plain. Confidence, never cuteness, in the critical path.

---

## 3. Logo Usage

**Construction.** The mark is a forward-motion chevron/arrow rendered in a white→electric-blue gradient, set beside the **INTENT** wordmark — uppercase, wide tracking (~0.14em), with a single accent letter ("N") in electric blue (`--brand`).

**Clear space.** Maintain clear space equal to the chevron's height on all sides. Minimum wordmark height: 16px on screen. The chevron may be used alone as an app icon and as the assistant trigger glyph.

**On-dark (preferred).** The signature lockup lives on `--ink` (#0A0E1A). The chevron gradient and the accent letter read brightest here; this is the hero treatment for splash, onboarding, and the assistant.

**On-light.** On `--surface` / `--bg`, use the solid `--brand` chevron (or the gradient if contrast against white holds) with `--text` (#0C1222) wordmark and the accent letter in `--brand`.

**Don'ts.** Don't recolor the chevron outside the brand gradient/solid blue. Don't add a second accent letter. Don't place the lockup on busy imagery without an ink scrim. Don't compress tracking or outline the wordmark. Don't apply shadows to the mark itself.

---

## 4. Theming Model — Dual / Adaptive

Intent runs two full themes that share one identity. The choice between them is *semantic*, not just user preference.

**Ink surfaces** (`--ink` family) are for **hero and agent moments**: the summary hero card, onboarding, the Intent assistant overlay, AI insight panels, and the shareable story card. Ink signals "this is Intent thinking / Intent's voice." It makes the brand gradient and electric blue sing.

**Light surfaces** (`--surface` family) are for **data and tasks**: transaction lists, category breakdowns, filters, search, settings. Light maximizes legibility for dense numeric content and long scrolls.

In **light theme**, ink surfaces appear as dark inset cards within a light app — the hero card and assistant are ink islands on a `--bg` page. In **full dark theme**, the whole app shifts to the dark token overrides, and ink surfaces deepen further to stay distinct (hero/assistant sit slightly above the page using `--ink-2`/`--ink-3`). The rule: **ink is always the brand/agent layer; light is always the data layer.** Electric blue is the one constant accent in both.

---

## 5. Color Tokens

All UI color resolves through tokens. Two themes; ink + brand + semantic are shared.

### Light theme

| Token | Hex | Usage |
|---|---|---|
| `--bg` | `#F4F6FB` | App background |
| `--surface` | `#FFFFFF` | Cards, sheets, rows |
| `--surface-2` | `#F7F9FE` | Inset / secondary fills, search field |
| `--border` | `#E6EAF2` | Hairlines, dividers |
| `--border-strong` | `#CDD4E3` | Inputs, emphasized edges |
| `--text` | `#0C1222` | Primary text, money |
| `--text-2` | `#5B6478` | Secondary, labels |
| `--text-3` | `#9AA3B2` | Tertiary, timestamps, placeholders |

### Ink (hero & agent surfaces — both themes)

| Token | Hex | Usage |
|---|---|---|
| `--ink` | `#0A0E1A` | Hero card base, assistant overlay, splash |
| `--ink-2` | `#121A2C` | Raised ink panels, nested AI cards |
| `--ink-3` | `#1B2438` | Ink dividers, chips on ink, hairlines |

### Brand (electric blue)

| Token | Value | Usage |
|---|---|---|
| `--brand` | `#2D6BFF` | Primary action, accent letter, active states |
| `--brand-bright` | `#4F9BFF` | Hover/active highlight, AI shimmer top |
| `--brand-deep` | `#1746C9` | Pressed, gradient end, deep accents |
| `--brand-grad` | `linear-gradient(135deg,#5AA0FF 0%,#2D6BFF 52%,#1746C9 100%)` | Hero card, primary CTA, chevron |
| `--brand-subtle` | `#EAF1FF` (light) / `rgba(45,107,255,.16)` (dark) | Selected chips, info tints, focus halo |

### Semantic

| Token | Hex | Usage |
|---|---|---|
| `--positive` | `#12B76A` (bg `#E7F7EF`) | Income, gains, positive deltas |
| `--alert` | `#F0556B` | Errors, overspend, destructive — sparingly |
| `--points` | `#E5A93B` | Intent Points, rewards |

### Full dark theme overrides

`--bg:#0A0E1A; --surface:#121A2C; --surface-2:#0F1626; --border:#222C42; --text:#EAF0FB; --text-2:#93A0B8; --text-3:#5A6580.`

**Accessibility notes.** `--text` on `--surface` clears WCAG AAA in both themes. `--text-2` on its surface meets AA for body. `--text-3` is reserved for ≥12px non-essential metadata only. White on `--brand` meets AA (≥4.5:1) at body sizes; on `--brand-bright`, reserve white for large/bold text and prefer `--ink` text for small. Never encode meaning in color alone — pair income/alert color with a sign (+/−) or icon.

---

## 6. Typography

**Stack.** `-apple-system, "SF Pro", "Inter", system-ui, sans-serif`. Inter is the cross-platform fallback. Money and any aligned numerics use `font-variant-numeric: tabular-nums`.

**Type scale.**

| Role | Size / Line | Weight | Notes |
|---|---|---|---|
| Hero numeric | 38 / 42 | 600 | Balance on hero card; tabular, tight tracking −0.02em |
| Display | 30 / 36 | 600 | Story card headline figure |
| Title | 22 / 28 | 600 | Screen titles, sheet titles |
| Section | 17 / 24 | 600 | Card headers, group labels |
| Body | 15 / 22 | 400/500 | Transaction names, paragraph |
| Amount (row) | 15 / 22 | 600 | Tabular, right-aligned |
| Secondary | 13 / 18 | 400 | Metadata, captions |
| Micro | 11 / 14 | 500 | Chip text, badges |
| Label | 9 / 12 | 600 | Uppercase, 0.08em tracking, axis/legend labels |

Weights used: 400 (body), 500 (emphasis/UI), 600 (numbers, titles). Avoid 700+ except inside the ink hero where a bolder figure earns presence. Uppercase tracking increases as size shrinks.

---

## 7. Spacing, Radius & Grid

**Rhythm.** 8px base scale: `4, 8, 12, 16, 20, 24, 32, 40`. Screen gutters are 20px. Card inner padding is 16–20px. Vertical gap between sections is 24px; between rows in a list, 0 with a 1px `--border` divider inset to content.

**Radius.** `--r-sm:6` (chips, badges, inputs), `--r-md:10` (buttons, small cards), `--r-lg:14` (cards, rows, list containers), `--r-xl:22` (hero card, bottom sheets, assistant overlay). Corners are consistently soft; the hero and sheets are the roundest surfaces.

**Grid.** Single-column mobile layout, content width = 375 − 40 = 335px. Components align to the 20px gutter. Two-up stat tiles split the content width with a 12px gap.

---

## 8. Elevation & Shadows

Shadows are layered, low-opacity, and cool-tinted — never heavy. Four levels:

- **e0 — Flat:** dividers only (`--border`). Lists, inline rows.
- **e1 — Resting card:** `0 1px 2px rgba(12,18,34,.06), 0 1px 1px rgba(12,18,34,.04)`. Standard cards, chips.
- **e2 — Raised:** `0 6px 16px rgba(12,18,34,.10)`. Hero card, floating assistant button, sticky header on scroll.
- **e3 — Overlay:** `0 20px 48px rgba(10,14,26,.30)`. Bottom sheets, assistant overlay, story preview.

On ink surfaces, replace shadow with a 1px `--ink-3` top inner highlight for depth. In full dark theme, soften shadow opacity by ~40% and lean on borders for separation.

---

## 9. Iconography

Line icons, **1.8px stroke**, **24px** box, round caps and joins, `currentColor`. Visual weight matches text-2 by default; active/nav-selected icons take `--brand`. Optical sizing: 20px in chips and rows, 24px in nav and headers, 16px inline with secondary text. Avoid filled icons except the active bottom-nav state and the chevron mark. Keep metaphors literal and calm; no novelty glyphs in the critical path.

---

## 10. Component Specs

### Status bar
Native iOS status bar, 44px. Content color adapts: dark glyphs on light screens, light glyphs on ink screens (hero, assistant, onboarding). Never overlap interactive content.

### App header
56px tall, screen gutters. Left: screen title (Title, 22) or back chevron (24px). Right: up to two 44px icon actions (search, profile). On light surfaces the header is `--surface`/transparent over `--bg`; on scroll it gains a 1px `--border` bottom and e2 shadow. Title may collapse from large to inline on scroll.

### Summary hero card (brand-gradient on ink)
The signature element. Full content-width, `--r-xl`, `--ink` base with a `--brand-grad` wash anchored top-left fading into ink, plus a faint chevron watermark. Contents: small uppercase label ("Total balance" — Label, `--text-3`-on-ink), the **38px hero numeric** (white, tabular, count-up on load), a delta chip (+▲ `--positive` / −▼ `--alert`), and a one-line AI summary in `--brand-bright` ("You're ~$240 ahead of last month"). e2 shadow in light theme; sits on `--ink-2` in dark. Tapping expands to balance detail.

### Transaction row
64px min height, `--surface`, divider below. Left: 36px circular category glyph on a tinted fill. Center: merchant name (Body 15/500, `--text`) over category + time (Secondary 13, `--text-2`). Right: **amount** (Amount, tabular, right-aligned) — spend in `--text`, income in `--positive` with a leading "+". Pending shows a `--text-3` dot. Whole row is tappable (≥44px target) and reveals detail sheet.

### Category stacked-bar + rows
A single horizontal stacked bar (`--r-sm`, 12px tall) shows the month's spend mix, each segment a desaturated category color. Below, category rows: glyph, name, bar-share %, and amount. Selecting a segment or row highlights the pair and dims the rest (0.4 opacity). Legend uses 9px Labels.

### Filter chips
Pill, `--r-sm`, 32px tall, horizontally scrollable row. Default: `--surface-2` fill, `--text-2` text, `--border` edge. Selected: `--brand-subtle` fill, `--brand` text, `--brand` 1px edge. Optional leading 16px icon. Active count badge in `--brand`. 8px gap between chips.

### Search bar
`--surface-2` fill, `--r-md`, 40px tall, 1px `--border`. Leading 20px search icon (`--text-3`), placeholder in `--text-3`, trailing clear (×) when populated. Focus: `--border-strong` edge + 3px `--brand-subtle` halo. Supports natural-language queries that route to the assistant.

### Bottom navigation
Fixed, 56px + safe area, `--surface`, 1px `--border` top, e2 shadow. Four items: Home, Activity, Cards/Pay, Insights — 24px line icons + 9px Labels. Active item: `--brand` filled icon + `--brand` label. The center **Intent assistant** trigger floats above the bar (see below). Each target ≥48px.

### Bottom sheets
`--r-xl` top corners, `--surface` (or `--ink` for AI/agent sheets), e3 shadow, 36×4px `--border-strong` grab handle, 20px padding. Springs up over a `rgba(10,14,26,.45)` scrim. Drag-to-dismiss; content scrolls within. Title (Title 22) + optional close.

### Buttons
**Primary:** `--brand-grad` fill, white text (Body 15/600), `--r-md`, 48px tall, full-width in sheets. Pressed → `--brand-deep`, scale 0.98. **Outline:** transparent fill, 1px `--border-strong`, `--text` label; on ink, `--ink-3` border + white label. **Text/link:** `--brand` label, no fill. Disabled: 0.4 opacity, no shadow. All buttons ≥44px.

### Shareable monthly story card
A vertical, ink-themed card (story 9:16 ratio, `--r-xl`) for social sharing. Top: Intent lockup. Center: a big Display figure with a witty, true highlight ("You saved 18% more than April — calm, collected, $312 richer"). Mid: a compact category bar and top-3 merchants. Bottom: Intent Points earned in `--points`, with chevron watermark. Brand-gradient accent edge. Export as image; numbers render with tabular alignment and count-up in the in-app preview.

### Intent assistant (NEW — floating button + slide-up overlay)
The product's namesake pattern, kept subtle.

**Trigger.** A 56px circular floating button centered above the bottom nav, `--brand-grad` fill with the white chevron glyph, e2 shadow and a slow AI shimmer. It does not obstruct content (sits in the safe gutter) and hides on scroll-down, returns on scroll-up.

**Overlay.** Tapping springs up an **ink** sheet (`--ink`, `--r-xl`, e3) covering ~70% height. Header: "What's your intent?" (Title, white). A single input field (`--ink-3` fill, white text, `--brand` caret) accepts natural language: "Move $200 to savings," "Why was June higher?," "Pay the electric bill." Below, 2–3 suggestion chips (ink chips with `--brand` text).

**Outcome.** On submit, the input collapses into a calm AI-thinking shimmer (1–2s), then the **outcome** renders: a confirmation line, the affected number with count-up, and any action as a Primary button ("Confirm transfer") plus an Outline "Adjust." For agent-initiated intents, the same overlay shows the agent's proposed action with an audit line (who/what/when) and an approve/deny pair. Every intent resolves to a visible, reversible outcome — the literal expression of "your intent becomes the outcome." Dismiss via drag-down or backdrop tap.

---

## 11. Motion

Motion is purposeful and quick. Tokens: **fast 140ms**, **base 220ms**, **slow 360ms**; easing `cubic-bezier(.2,.8,.2,1)` (standard) and `cubic-bezier(.4,0,1,1)` (exit).

- **Fade-up:** content enters +8px and fades in over base; staggered 40ms per list item (cap at ~6).
- **Count-up:** all hero/outcome numerics animate from a near value to final over slow, easing out, tabular so digits don't jump.
- **AI / neon shimmer:** a slow (2.4s) `--brand-bright`→transparent diagonal sweep across AI insight surfaces, the assistant button, and the thinking state. Low contrast, respectful — signals "Intent is reasoning."
- **Sheets:** spring up base with slight overshoot; scrim fades in parallel. Buttons press to 0.98 scale at fast.
- **Reduced motion:** honor `prefers-reduced-motion` — replace count-up and shimmer with instant values and a simple opacity fade.

---

## 12. Voice & Tone

Confident, clear, and concise. We state outcomes plainly and explain the "why" in one line when it helps. We are witty only in highlights and the monthly story, where a little warmth rewards attention ("$312 richer — nicely done"). The critical path — balances, confirmations, errors, agent actions — stays plain and exact. Prefer verbs and outcomes ("Transfer sent") over jargon ("Transaction processed"). Never alarmist: surface problems calmly with a clear next step. We address the user directly ("you," "your") and treat AI agents as transparent actors, always shown, never hidden.

---

## 13. Accessibility

- **Contrast:** Meet WCAG 2.1 **AA** minimum across both themes — 4.5:1 for text under 18px, 3:1 for large text and meaningful UI/graphic boundaries. `--text-3` is restricted to non-essential metadata ≥12px.
- **Color independence:** Never rely on color alone. Income/spend/alert always carry a sign or icon; selected states carry a border or fill change, not just hue.
- **Tap targets:** All interactive elements ≥**44×44px** (nav and primary actions 48px). Maintain ≥8px spacing between adjacent targets.
- **Focus & states:** Visible focus uses a 3px `--brand-subtle` halo plus a `--brand` 1px edge — applied for keyboard, switch, and external-keyboard users. Every control has distinct rest / hover / pressed / disabled states.
- **Type & zoom:** Respect Dynamic Type; layouts reflow without truncating money. Minimum body 15px; never set essential text below 12px.
- **Motion & assistive tech:** Honor `prefers-reduced-motion`. Provide labels for icons, live-region announcements for outcomes and the assistant's results, and clear, spoken-friendly confirmation copy for agent actions.

---

*Intent Design System v1.0 — the source of truth for tokens, components, and behavior. Maintained by Design. Your intent becomes the outcome.*
