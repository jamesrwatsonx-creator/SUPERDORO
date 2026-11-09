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

Meditation screens remain to be designed. Start with a calm collection/player supporting proposed two-, five-, and ten-minute sessions plus silent breathing. Do not invent an approved visual reference for these screens.

## Quality checks during implementation

- Use semantic theme tokens for background, surface, text, muted text, accent, borders, and state colors.
- Check text contrast, screen-reader labels, dynamic text, touch targets, keyboard behavior, and reduced motion.
- Distinguish recording, saved locally, processing, awaiting review, and failure without color alone.
- Keep important save/review actions visible; do not obscure controls with glow.
- Validate on a real mobile viewport and device, including long transcripts and empty states.

Exact token values, fonts, motion timings, and final assets are implementation/design decisions still open.
