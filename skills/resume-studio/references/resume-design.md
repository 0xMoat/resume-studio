# Resume Design Reference

> Design guidance adapted from Anthropic's frontend-design skill (Apache 2.0).

Visual design decisions for single-page A4 resume HTML → PDF export.
Not a general web design guide — everything here is scoped to print-oriented resume layout.

## Design Direction

Commit to a clear aesthetic direction before writing CSS:

- What visual tone fits this candidate's field? (editorial for marketing, refined technical for engineering, minimal professional for finance, portfolio-adjacent for creative)
- Should the layout feel restrained or expressive?
- What's the one design choice that makes this resume feel intentional, not templated?

Bold maximalism and refined minimalism both work — the key is intentionality, not intensity.

### The AI Slop Test

If someone saw this resume and immediately thought "AI made this," redesign it. Avoid:

- Overused fonts (Inter, Roboto, Arial, Open Sans)
- Cyan-on-dark, purple-to-blue gradients, neon accents
- Glassmorphism, blur effects, excessive shadows
- Gradient text on headings
- Identical card grids with icon + heading + text

## Typography

### Hierarchy & Scale

Use fewer sizes with more contrast. A resume needs 4–5 sizes:

| Role | Use Case |
|------|----------|
| xs (0.75rem) | Dates, metadata, secondary labels |
| sm (0.875rem) | Skills, project details |
| base (1rem) | Body text, bullet points |
| lg (1.25–1.5rem) | Section headings |
| xl (1.5–2rem) | Name / title |

Pick a consistent ratio (1.25 major third or 1.333 perfect fourth) and commit. Combine size, weight, and color for hierarchy — don't rely on size alone.

### Font Selection

Avoid invisible defaults: Inter, Roboto, Open Sans, Lato, Montserrat.

Better Google Fonts alternatives:

- Sans-serif: **Instrument Sans**, **Plus Jakarta Sans**, **Outfit**, **Onest**, **Figtree**, **DM Sans**
- Editorial / premium: **Fraunces**, **Newsreader**, **Lora**
- System fonts (`-apple-system, BlinkMacSystemFont, "Segoe UI", system-ui`) load instantly and are highly readable — consider when performance matters more than personality.

### Pairing

One well-chosen font family in multiple weights often creates cleaner hierarchy than two competing typefaces. Only add a second font when you need genuine contrast (e.g., serif display + sans body).

When pairing, contrast on multiple axes: serif + sans, geometric + humanist, condensed display + wide body. Never pair fonts that are similar but not identical.

### Vertical Rhythm

Line-height should be the base unit for vertical spacing. If body text has `line-height: 1.5` on 16px (= 24px), spacing values should be multiples of 24px.

### Readability

- Use `rem` / `em` for font sizes, never `px` for body text
- Minimum 16px body text
- Use `font-variant-numeric: tabular-nums` for aligned numbers (dates, metrics)
- Use `font-variant-caps: all-small-caps` for abbreviations when the font supports it

## Color

### Use OKLCH

OKLCH is perceptually uniform — equal steps in lightness look equal, unlike HSL.

```css
--color-primary: oklch(60% 0.15 250);
--color-primary-light: oklch(85% 0.08 250);
--color-primary-dark: oklch(35% 0.12 250);
```

As you move toward white or black, reduce chroma. High chroma at extreme lightness looks garish.

### Tinted Neutrals

Pure gray has no personality. Add a subtle hint of your accent hue:

```css
/* Cool-tinted (tech, professional) */
--gray-100: oklch(95% 0.01 250);
--gray-900: oklch(15% 0.01 250);

/* Warm-tinted (creative, approachable) */
--gray-100: oklch(95% 0.01 60);
--gray-900: oklch(15% 0.01 60);
```

Chroma is tiny (0.01) but perceptible — it creates subconscious cohesion between your accent color and your neutrals.

### The 60-30-10 Rule

- **60%**: Neutral backgrounds, white space
- **30%**: Text, borders, secondary elements
- **10%**: Accent — section markers, name highlight, key visual anchors

Accent colors work because they're rare. Overuse kills their power.

### Contrast

| Content Type | WCAG AA Minimum |
|--------------|-----------------|
| Body text | 4.5:1 |
| Large text (18px+ or 14px bold) | 3:1 |

Avoid: light gray text on white, gray text on colored backgrounds, pure black (`#000`) or pure white (`#fff`) — always tint slightly.

## Spatial Design

### Spacing System

Use 4pt base: 4, 8, 12, 16, 24, 32, 48, 64px. Name tokens semantically (`--space-sm`, `--space-lg`), not by value.

### Visual Hierarchy

The squint test: blur your eyes at the resume. Can you identify the name, section headings, and content groupings? If everything looks the same weight, you have a hierarchy problem.

Combine multiple dimensions for strong hierarchy:

| Tool | Strong | Weak |
|------|--------|------|
| Size | 3:1 ratio+ | <2:1 ratio |
| Weight | Bold vs Regular | Medium vs Regular |
| Color | High contrast | Similar tones |
| Space | Generous separation | Crowded |

The best hierarchy uses 2–3 dimensions at once.

### Layout Rhythm

Create visual rhythm through varied spacing — not the same padding everywhere. Tight groupings within sections, generous separations between sections. The resume should feel intentionally composed, not uniformly spaced.

### Optical Adjustments

- Text at `margin-left: 0` looks indented due to letterform whitespace — use negative margin (`-0.05em`) to optically align
- Geometric centering often looks off-center visually — adjust by eye
