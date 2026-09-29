# Design

## Theme

Night watch: an amber watch light held steady against near-black, opening onto plain white reading sections. One dark band at the top and bottom, light sections between.

## Colour (OKLCH, tokens in `index.html` `:root`)

| Token | Value | Use |
|---|---|---|
| `--ink` | `oklch(0.17 0.012 70)` | Opening band, footer, monograms |
| `--ink-raised` | `oklch(0.22 0.014 70)` | Code panel on the dark band |
| `--on-ink` / `--on-ink-muted` | `oklch(0.96 0.004 70)` / `oklch(0.76 0.01 70)` | Text on dark |
| `--bg` / `--bg-alt` | `oklch(0.99 0 0)` / `oklch(0.955 0 0)` | Light sections (chroma 0 on purpose) |
| `--text` / `--text-muted` | `oklch(0.21 0.01 70)` / `oklch(0.43 0.012 70)` | Text on light |
| `--amber` | `oklch(0.60 0.124 70)` | Brand seed: lines and shapes only |
| `--amber-deep` | `oklch(0.47 0.1 68)` | Amber text on light backgrounds |
| `--amber-glow` | `oklch(0.8 0.135 76)` | Amber on dark, buttons, focus rings |
| `--del-*` / `--add-*` | red and green tints | Diff lines, always with - and + markers |

Strategy: restrained, with amber carrying emphasis only. Never amber text on white below `--amber-deep`.

## Typography

- Schibsted Grotesk (400, 500, 700, 800) for everything; JetBrains Mono (400, 600) only for code and file names.
- Scale: `--step--1` 0.875rem, `--step-0` 1.0625rem (body), `--step-1` 1.375rem, `--step-2` clamp to 2.2rem, `--step-3` clamp to 3.6rem (hero).
- Display letter-spacing -0.028em; body line-height 1.6; measure capped near 60ch.

## Spacing

4pt-based tokens `--space-2xs` (0.25rem) to `--space-2xl` (3rem), plus `--space-3xl` fluid for section padding. Content width `--page`: up to 72rem with fluid side gutters.

## Components

- Code panel ("watch"): file name bar, numbered lines, flagged lines with amber wash and a 3px inset marker, CWE notes below. A scan beam patrols the panel; reduced motion removes it.
- Steps: numbered circles on a connecting line (vertical on phones, horizontal from 60rem). The fifth step, the human, is filled amber. A dashed loop links Verify back to Recommend on wide screens; phones get the same message as text.
- Diff: unified diff with - and + markers and tinted rows.
- Buttons: pill, amber-glow fill, ink text, 48px tall.

## Motion

Ease-out-quint style curve `cubic-bezier(0.22, 1, 0.36, 1)`. Only the scan beam and the flag highlight animate. Everything is visible without animation, and `prefers-reduced-motion: reduce` turns motion off.
