---
name: atre-premium-ui-design
description: Use when creating, reviewing, or refining premium UI/UX for ATrinca/Atrinca Real Estate landing pages, Elementor HTML blocks, Figma layouts, lead-capture pages, or any request asking for sophisticated, elegant, conversion-oriented visual design in the user's current Codex profile. Applies especially when the user references white/beige/champagne layouts, rounded cards, Montserrat, 1920px canvases, 1260px containers, Figma replication, mobile-first responsiveness, or wants Codex to be critically proactive rather than passive.
---

# ATRE Premium UI Design

## Core Stance

Act as a design-critical collaborator, not a passive executor.

- Be about 30% proactive in design judgment: point out when something looks generic, loud, cramped, misaligned, overdesigned, or weak for conversion.
- Prefer precise, objective critique over vague praise.
- When the user provides references, extract the design language before implementing.
- Avoid inventing decorative elements only to “look designed”; use proportion, spacing, hierarchy, image quality, and restraint first.
- Respond in Portuguese by default for this user.

## Current Visual Direction

The correct direction for the ATrinca Real Estate Partner landing page is:

- Clean premium editorial.
- Light base, not dark-club dominant.
- White, beige, champagne, and soft warm neutrals.
- Strong rounded panels and large cards.
- Calm luxury, not infoproduct launch page.
- Black or deep blue/green only as contrast blocks.
- Spacious, polished, almost “premium agency / portfolio / private business club”.

Avoid:

- Heavy dark gradients as the main identity.
- Generic glassmorphism overload.
- Excessive glow, bokeh, fake wireframe labels, or visible placeholder copy.
- Giant black typography that feels aggressive.
- Cards touching each other.
- Overlapping sections unless intentionally elegant and verified.
- Purple/blue SaaS gradients.
- Cheap sales-page visuals.

## Brand Tokens

Use these as the default palette:

```css
:root {
  --atre-primary: #172E36;
  --atre-blue: #01214A;
  --atre-highlight: #FFB600;
  --atre-cream: #F4EFE6;
  --atre-cream-2: #EBE1D3;
  --atre-white: #FFFDF8;
  --atre-ink: #11110F;
  --atre-muted: rgba(17, 17, 15, 0.62);
  --atre-champagne: #D9C29B;
}
```

Rules:

- Use `#172E36` as the main institutional dark.
- Use `#01214A` as a secondary deep contrast, usually in gradients or dark panels.
- Use `#FFB600` only for highlights: numbers, small markers, active states, key metrics, subtle accents.
- Keep the base mostly white/beige/champagne.
- Do not let yellow dominate the page.

## Typography

Use Montserrat and its weights.

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800;900&display=swap");
```

Guidelines:

- Use Montserrat for all UI and landing page typography.
- Titles should be uppercase.
- Use bold weights selectively; not every title should be Black/900.
- Prefer elegant title scales:
  - Hero title: `clamp(42px, 5.8vw, 78px)`
  - Section title: `clamp(30px, 3.8vw, 52px)`
  - Card title: `clamp(18px, 1.5vw, 24px)`
- Use line-height around `1.03` to `1.10` for titles.
- Use light letter spacing for uppercase titles, around `0.01em` to `0.02em`.
- Avoid aggressive oversized headings that crop, wrap badly, or dominate the entire viewport.

## Layout System

Default desktop canvas and container:

- Full design canvas/frame: `1920px` wide.
- Main content container: `1260px` wide.
- Horizontal page margin around centered container: `(1920 - 1260) / 2 = 330px`.
- Spacing between major cards/sections: exactly `20px`.
- Spacing between cards in grids: exactly `20px` on X and Y.

Recommended structure:

- Use a `.lp-page` or wrapper that is a vertical grid/flex stack with `gap: 20px`.
- Each major section should be a separate rounded panel, not glued to the previous one.
- Do not use negative margins/translate to overlap metric cards unless there is a strong visual reason and it is verified.
- If a card appears cramped, increase section height before reducing content quality.

Reference CSS pattern:

```css
.lp-page {
  width: min(1260px, calc(100% - 40px));
  margin: 0 auto;
  display: grid;
  gap: 20px;
}

.lp-panel {
  border-radius: 44px;
  overflow: hidden;
}

.grid {
  display: grid;
  gap: 20px;
}
```

## Mobile-First Expectations

Mobile must feel designed, not squeezed.

- Container: `width: min(100% - 40px, 430px)`.
- Keep `20px` side breathing room.
- Convert grids to one column on small screens.
- Maintain rounded cards, but reduce radius slightly if needed: `28px` to `32px`.
- Avoid long uppercase titles that wrap into awkward fragments.
- Use smaller mobile title scales:
  - Hero: `clamp(34px, 10.5vw, 48px)`
  - Sections: `clamp(28px, 8.8vw, 40px)`
- Sticky CTA is acceptable on mobile, but it must not cover form fields or footer content.
- Test text fit inside buttons and cards.

## Section Design Rules

Hero:

- Use a large light panel with a dark rounded navigation pill.
- Keep the title powerful but not oversized.
- Reserve a strong hero image area; the final page needs a real image.
- Do not write visible labels such as “image placeholder” in production HTML.
- Metrics can live inside a dark rounded bar, but the bar must not overlap or collide with the next section.

MLS / Ecosystem:

- Use a split layout: large title on left, logo/copy card on right.
- Keep it clean; do not overload with icons.
- Logo should sit in a compact dark card.

Benefits:

- Use large image slots/cards with rounded corners.
- Prefer two-column visual blocks on desktop, one column on mobile.
- Image areas must feel intentional even before final images arrive.

Dark contrast section:

- Use `#172E36` and/or `#01214A`, not pure black unless needed.
- Keep dark sections limited and purposeful.
- Highlight benefit numbers with `#FFB600`.

Process / How it works:

- Use cards with ample vertical height.
- Avoid cropped text by making cards taller instead of shrinking line-height.
- Number labels should be subtle but visible.

Mentors:

- Use real mentor photos whenever available.
- Use optimized web images, not original 20MB+ files.
- Cards should use vertical portrait crops, rounded corners, and a readable light overlay.
- The mentor section is a major authority driver; do not bury it.

Application / Form:

- A dark form card is acceptable for contrast and conversion.
- Use a clear progress indicator if included.
- Inputs should be rounded, spacious, and high contrast.
- Keep copy concise and selective.

Footer:

- Keep it simple, dark, and low-noise.

## Figma Workflow

When creating or fixing Figma layouts:

- Prefer a `1920px` frame with a centered `1260px` content area.
- Use `20px` vertical spacing between section panels.
- Build sections as independent frames, not top-level loose objects.
- Avoid text boxes with fixed heights that crop content; use auto-height text where possible.
- Load Montserrat before text creation. If unavailable, use Inter only as fallback.
- Do not rely on JSON to recreate complex landing pages.
- If exact HTML replication is needed, prefer `html.to.design` importing a public URL.
- If drawing manually with Figma API, validate with screenshots after major sections.

## HTML / Elementor Workflow

When generating Elementor-ready HTML:

- Deliver one self-contained block with `<style>` and `<script>` inside one root wrapper.
- Use `index.html` for public hosting/GitHub Pages.
- Keep assets relative, e.g. `assets/images/mentores/joel-web.jpg`.
- Do not upload huge PDFs or original images to GitHub Pages.
- Use optimized mentor images for web.
- Keep webhook configuration explicit:

```js
const WEBHOOK_URL = "";
```

- If empty, local test storage is acceptable, but tell the user how to configure the webhook.

## Image Guidance

The design only becomes truly premium with real images.

Prioritize:

- Real mentor photos.
- Premium business/event/networking imagery.
- Clean, bright, beige/champagne scenes.
- Editorial hero image with people, setting, or business atmosphere.

Avoid:

- Abstract fake placeholders.
- Overly dark cinematic images when the reference direction is light/champagne.
- Stock images that feel generic or corporate cheap.
- Low-resolution or unoptimized images.

## Critical Review Checklist

Before finalizing any design, check:

- Are cards and sections separated by real `20px` spacing?
- Is the content container `1260px` on desktop?
- Is the outer frame/page compatible with `1920px` desktop presentation?
- Does mobile look intentional?
- Are titles uppercase but not oversized?
- Are weights varied, not all 900?
- Are highlights `#FFB600` used sparingly?
- Are `#172E36` and `#01214A` present without overpowering the beige/white base?
- Are images real or at least reserved in a polished way?
- Are any boxes, text, or cards cropped?
- Is the result closer to premium editorial/agency references than a generic launch page?

If any answer is no, fix before presenting.
