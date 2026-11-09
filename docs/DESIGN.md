# Design direction

## Confirmed preferences

- Premium, modern, sophisticated presentation.
- Angular geometric S logo and SUPERDORO wordmark direction.
- Light and dark modes with restrained mint/green accents.
- Selective glassmorphism and luminous accents; clear readable content.
- White/light timer ring with inner tick marks.
- Clean sans-serif typography.
- Minimal lists; rich note details with reference cards, metadata, and contextual actions.
- “Your Focus Harness” sign-in direction and detailed onboarding, with optional questions skippable.

These are preferences recorded from earlier discussions, not proof of implemented screens. The exact selected image assets and production logo files have not been added to this repository. Do not claim an approximation is the approved original.

## Proposed composition

Today / Library / Focus / Reset with a persistent Capture action. Capture supports voice and typing equally clearly. Review distinguishes Tasks, Ideas, and Calendar, with editable content and explicit decisions. Note detail holds original audio/text, transcript, references, linked work, and session history.

Meditation catalog/player screens FOCUS-10/11 are specified; each meditation will have its own user-supplied MP3 and customized motion GIF or approved efficient alternate, with an accessible static poster. The user has not yet supplied or approved the final meditation-specific visuals. Do not invent an approved final scene.

## Quality checks during implementation

- Use semantic theme tokens for background, surface, text, muted text, accent, borders, and state colors.
- Check text contrast, screen-reader labels, dynamic text, touch targets, keyboard behavior, and reduced motion.
- Distinguish recording, saved locally, processing, awaiting review, and failure without color alone.
- Keep important save/review actions visible; do not obscure controls with glow.
- Validate on a real mobile viewport and device, including long transcripts and empty states.

Exact token values, fonts, motion timings, and final assets are implementation/design decisions still open.

## Unified detailed visual/motion direction — November 9, 2026

**Premium calm-tech:** quiet off-white photographic light mode, atmospheric charcoal dark mode, selective luminous mint, thin transparent glass surfaces, bright legible content and refined typography. The default is NOT neon glow on every card. User likes modern bold editorial sans used in “Let AI organize notes automatically?”; Geist/Inter are candidates only, with optional italic accent words. Keep one exact angular interlocking S/wordmark geometry for all 80 designs.

**Authentication reference combination:** a rounded photographic bright desk/laptop hero with the “Your focus harness” copy and floating glass microcards showing real app concepts (captured thought, planned event, focus completion). Build both themes from one layout. Make sign-in buttons clear and accessible, not decorative image controls.

**Precision focus instrument:** white circular timer with fine ticks INSIDE the dial and smooth emerald radial progress sweep; preserve dial anatomy in dark mode. Timer is visually immersive, but elapsed time comes from persisted timestamps, not animated frames. The user specifically prefers this white inner-tick reference.

**Note detail:** use the dark Q4 Landing Page Brief hierarchy: title/category, audio/transcript, linked web references with source preview, extracted actionable chips and conditional specs. Minimal calm list view, progressively rich note detail. Empty sections are hidden when unhelpful. Research opens in a return-to-note sheet.

**12-screen account/onboarding storyboard:** S assembles; hybrid hero floats; glass auth; account form; goals; first brain dump; source-to-AI-structure animation; review; focus duration/ticks; recovery preview; Trust/appearance; personal workspace reveal. The animation guide specifies M01–M37 and animation/performance budgets. Actual onboarding is skippable and returns quickly to capture.

**Recovery visuals:** glass break selector, slow nature parallax, optional breath pulse, unique user-approved per-meditation motion GIF, MP3 controls, reduced-motion still. Motion becomes quieter during active work. See MOTION-SYSTEM.md, MEDITATION-MEDIA.md and ASSET-REGISTER.md for source/rights/status.

**Delivery:** Use 15–20 adaptable component families and semantic theme tokens. No generated concept proves that an app animation, provider, permission or data rule works. Test large font, contrast, touch, fast scroll, battery and reduced motion on devices.

## Canonical mobile layout source and Paper design handoff

Designers/agents must apply the independent [mobile-design-orchestrator repo](https://github.com/jamesrwatsonx-creator/mobile-design-orchestrator/tree/4d88a488ed78ad7b1bec503e4180abccac338af5) — 8dp spacing rhythm, usually 16–24dp horizontal margins, approximately 44–48dp practical touch areas, true mobile safe areas, keyboard support, native ergonomics, plausible row/header/card proportions, one portrait image per screen. This is a reusable external standard, not a product-specific separate SUPERDORO repo. See [Mobile Design + Paper MCP](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md) for preflight and generator→editable layer→app workflow.

For detailed UI designs, follow [43-screen index](DETAILED-SCREEN-MOTION-UX.md), five SCREEN-MOTION section files and [43-screen prompt pack](SCREEN-IMAGE-PROMPTS.md). Keep consistent NOTE-02, WEB-02 and FOCUS-02 anchors; preserve geometric S identity and both themes. Paper MCP is local via Paper Desktop and may read/write only after actually connected and authorized. It has not been used in the current ChatGPT environment, so screenshots are reference images and not Paper designs or functioning native screens. The motion system's M01–M37 IDs define scroll/gesture/timer/meditation choreography; reference-only effects must not be forced into all views.
