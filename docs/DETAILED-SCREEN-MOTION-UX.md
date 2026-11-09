# SUPERDORO — Detailed screen-by-screen UX, scroll and animation index
**Design spec, not application code.** This index is the single entry point to **43 extensively documented screens** in the five user-selected sections, each with independent visual hierarchy, scroll/sticky rules, animation/gesture triggers, edge conditions, acceptance and one-frame image specification.

## Canonical rules
Read [COMPLETE-PRODUCT-OVERVIEW.md](COMPLETE-PRODUCT-OVERVIEW.md) first for goals/mental models. Then [MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md) for the separate mobile-design-orchestrator rules and Paper MCP setup (not connected in this chat). Native motion IDs are defined in [MOTION-SYSTEM.md](MOTION-SYSTEM.md), with 105 provided/reference effects preserved in [REFERENCE-MOTION-LIBRARY.md](REFERENCE-MOTION-LIBRARY.md). The canonical complete app remains [80 screens](SCREEN-INVENTORY.md).

**Count reconciliation:** the user listed seven Notes surfaces, but the existing repository had NOTE-01...08 with an original-audio/transcript timeline; all eight are included. The 11 Focus IDs include a minimized timer (FOCUS-03); the user's immersive motion is an explicit full-screen state of meditation player FOCUS-11. Therefore **43** detailed screens here, **80** total product screens, with no renumbering.

**Shared scroll contract:** use native scrolling instead of web scroll libraries. Header collapses only in designated y range (typically 40–72 dp) and restores on scroll up; persistent bottom controls stay above safe area and never obstruct content; parent state and scroll y persist across linked child sheets. Use scroll-linked transforms for section/hero treatment only when semantically useful. Trigger M07 appear effects no more than once per content set, never creating empty blank cards for fast scrollers. All gestures have visible tap alternatives, accessibility, Reduce Motion and interruption paths.

## Section-by-section design documents

### Notes and ideas — 8 screens

[Open full interaction and motion choreography](SCREEN-MOTION-NOTES.md)

- **NOTE-01 — Notes library**: Mid-list populated dark mode with three realistic note rows, compact Search and reachable glowing voice Capture pill; header in large title state.
- **NOTE-02 — Rich note detail**: Dark Q4 Landing Page Brief-inspired detail: clear header, short transcript with green highlights, two image-linked references, compact action row and readable focus CTA.
- **NOTE-03 — Rich editor**: Light mode clean editorial rich editor, body paragraph, highlighted selection toolstrip, compact attach chip and keyboard-safe bottom controls.
- **NOTE-04 — Ideas collection**: Warm white library Ideas list, graceful sparse rows, small project tags, floating New Idea action with just one mint accent.
- **NOTE-05 — Idea detail**: Dark elegant idea detail, editorial large title, hypotheses card, two linked sources, and small Convert to Task / Research pills.
- **NOTE-06 — Source and transcript timeline**: Dark readable waveform with interior tick scrubber above timestamped transcript and a compact Original/Edited/Structured segmented control.
- **NOTE-07 — Related items and backlinks**: Premium light related-items view with grouped task/project/reference rows and a tiny restrained graph preview; no tangled full-screen network.
- **NOTE-08 — Global workspace search**: Warm white global search with query 'landing page', grouped results with type chips and highlighted exact match; realistic compact mobile density.

### Calendar and reminders — 7 screens

[Open full interaction and motion choreography](SCREEN-MOTION-CALENDAR.md)

- **CAL-01 — Calendar overview**: Light week grid with event blocks, differently marked task due dates and clear Today button.
- **CAL-02 — Day agenda**: Dark day timeline with event, task-linked Pomodoro, open time and compact dated header.
- **CAL-03 — Event draft/detail**: Light proposed meeting detail with editable time and source quote.
- **CAL-04 — Event editor**: Dark event creation screen with readable date/time, recurrence and Save.
- **CAL-05 — Reminder composer**: Light reminder sheet above a dimmed note with action presets.
- **CAL-06 — Provider synchronization settings**: Dark provider cards with clearly labeled actual vs sample sync statuses.
- **CAL-07 — Conflict resolution**: Dark side-by-side local/external changed-time conflict card and Resolve CTA.

### Web research — 8 screens

[Open full interaction and motion choreography](SCREEN-MOTION-WEB.md)

- **WEB-01 — AI web search**: Dark detail note visible below glass 'Search the web' sheet, editable query and compact Source context card.
- **WEB-02 — Search results sheet**: Dark floating glass results sheet anchored on research note; three realistic cited results with attach buttons and no unverified prices.
- **WEB-03 — In-app browser/reader**: Light reader with trusted-source domain bar, highlighted excerpt and pinned Clip this button.
- **WEB-04 — Web clip/highlight**: Dark half-sheet showing two highlighted sentences, source URL, preview thumbnail, Attach and Create Idea actions.
- **WEB-05 — Saved references gallery**: Warm white two-column compact source gallery with website, PDF and photo cards, stable domain labels and search.
- **WEB-06 — Comparison workspace**: Dark comparison with two product/source columns, concise highlighted differences and fixed Save comparison action.
- **WEB-07 — Research synthesis**: Light Research Summary with evidence chips, Key Findings and two proposed action items.
- **WEB-08 — Requested watches/alerts**: Dark Watchlist showing opted-in stock and price watches, last checked timestamps and quiet green active indicators.

### Focus and recovery — 11 screens

[Open full interaction and motion choreography](SCREEN-MOTION-FOCUS.md)

- **FOCUS-01 — Timer setup**: Light white dial with fine inner minute ticks, 25/50/free/custom controls, linked task and bold Start Focus.
- **FOCUS-02 — Active focus session**: Black/charcoal or light precision timer with iconic inner tick marks, accurate 24:12 example clearly illustrative and Pause control.
- **FOCUS-03 — Minimized/persistent timer**: Dark note detail with small anchored 'Focus 12:48' pill and content unobstructed.
- **FOCUS-04 — Pause/resume sheet**: Dark timer behind translucent Pause sheet with Resume and Finish early, no distracting illustrations.
- **FOCUS-05 — Session completion and outcome**: Light completion showing true 25-minute session and linked task, with Take a break and Continue buttons.
- **FOCUS-06 — Interruption capture**: Dark low-profile interruption capture overlay on faint running timer with voice waveform, single text field and Save Thought.
- **FOCUS-07 — Break recommendation hub**: Glass over forest dusk break selector with Breathe, Stretch and Meditate, calm green accents.
- **FOCUS-08 — Guided stretching player**: Light stretching experience with clear two-step sequence, user-readable pose graphic and controls.
- **FOCUS-09 — Guided breathing player**: Dark breathing screen with gentle mint orb, clear 'Inhale · 4s' phase and Pause.
- **FOCUS-10 — Meditation library**: Light meditation library with three cinematic still scene cards, durations and clear Play icons; no invented MP3 titles advertised as released.
- **FOCUS-11 — Meditation + immersive motion player**: Cinematic dark meditation visual, minimal translucent controls and exact supplied media art; when unavailable display a labeled placeholder rather than pretend finished animation.

### Insights and settings — 9 screens

[Open full interaction and motion choreography](SCREEN-MOTION-INSIGHTS.md)

- **INS-01 — Focus insights dashboard**: Dark analytics summary with real-looking demo-labeled weekly focus totals, one line chart and readable period tabs.
- **INS-02 — Weekly reflection**: Light weekly reflection with two metric cards, a calm progress sparkline and two reviewable suggestions.
- **INS-03 — Goals and progress**: Warm white goals list with measured progress bars, one green ring and Edit goal.
- **INS-04 — Profile and account plan**: Light profile screen with account summary, plan badge and clear links to privacy/settings.
- **INS-05 — Appearance and accessibility**: Light settings showing light/dark card previews, Reduce Motion switch and color intensity slider.
- **INS-06 — Notifications and focus filtering**: Dark settings list with Daily briefing, Session complete, Quiet hours and an honest OS capability note.
- **INS-07 — Trust Mode and AI permissions center**: Premium dark Trust Mode permission sheet with clear safety boundary, no invented '87% protected' gauge.
- **INS-08 — Integrations and connected sources**: Light integration dashboard with Google Calendar and share-sheet cards labeled connected/available as demo state.
- **INS-09 — Privacy, export and security**: Light privacy center with clear Data export and Original recording retention panels, separate Danger zone.

## Required audit for every screen
- **Goal:** essential interaction, actual data and explicit outcome visible before animation.
- **Appearance:** exact S/logo asset when imported; light/dark semantic tokens; readable modern typography, 8dp rhythm, 16–24dp margins and 44–48dp practical target size.
- **Scroll:** who owns vertical y, any horizontal scroll, what sticks, what hides/reverses, how keyboard/large text affects layout.
- **Motion:** Mxx primitive, trigger and state source, approx timing, interrupt/cancel behavior, first-mount vs every scroll, performance and accessibility.
- **Transition:** destination route, originating context ID and preserved source y; no broken return path.
- **Truth:** original audio/provenance, time/date ambiguity, actual web citations and provider status, no fabricated success.
- **Review:** loading/empty/error/offline/permission denied, screen reader, Reduce Motion, low-end phone and small/large geometry.
- **Design evidence:** one-image-per-screen prompt and separately approved Paper editable frame (if connected) with identifiers, not flat PNG masquerading as native implementation.

## Design prompt pack and visual review
The [SCREEN-IMAGE-PROMPTS.md](SCREEN-IMAGE-PROMPTS.md) contains 43 ready-to-use unique portrait-screen prompts based on the approved SUPERDORO visual system. Generate each image separately and apply the three anchors NOTE-02, WEB-02, FOCUS-02 before expanding to the full set. Preserve motion as annotations/representative keyframes, not invented functioning behavior.

## Current evidence
Written specifications exist in GitHub. No 43 generated screen images, editable Paper frames, verified user MP3/GIF files, local Paper MCP connection or tested native interactions are established by this documentation. Design approvals and implementation must be tracked independently in STATUS.md.
