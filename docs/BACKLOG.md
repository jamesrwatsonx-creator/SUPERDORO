# Build backlog

**Complete first-product target: 80 screen definitions in nine domains.** Include all requested capabilities in the complete launch build. Individual implementation milestones remain incremental. All implementation tasks begin unchecked. A checkbox means the described acceptance was actually verified; code written without runtime/device proof belongs in STATUS.md as implemented/unverified.

## Milestone 0 — executable foundation

- [ ] Inspect and preserve any newer code/assets; record actual starting state.
- [ ] Initialize Expo + React Native + TypeScript with current mutually compatible packages and lockfile.
- [ ] Add verified install, development-build, type-check, and test commands to README.
- [ ] Establish light/dark tokens and accessible base components following DESIGN.md.
- [ ] Start minimal Today/Library/Focus/Reset navigation with an obvious Capture action. Unimplemented destinations must be honest empty states.
- [ ] Launch on James's Android device and record build/device evidence.

Gate: a runnable mobile foundation, not merely generated files. Device launch may remain explicitly pending if the implementation environment lacks device access.

## Milestone 1 — durable voice and typed capture

- [ ] Implement a local capture repository and schema migrations.
- [ ] Save typed original input separately from edits; support local note detail.
- [ ] Request microphone permission when recording is chosen; preserve typed fallback on denial.
- [ ] Record, stop, persist outside cache, replay, and list a voice capture.
- [ ] Show distinct recording/saving/saved/failed states and actionable recovery.
- [ ] Recover stopped recordings and typed captures after relaunch; offline operation works.
- [ ] Verify first-run, denied mic, offline save, editing, playback, and close/reopen behavior.

Gate: demonstrate typed note + playable recording after relaunch. No AI or cloud credential is necessary. Abruptly interrupted in-progress recording recovery must be characterized honestly rather than assumed.

## Milestone 2 — real processing and review

- [ ] Add authenticated server-side transcription/extraction adapters and the required secret configuration.
- [ ] Introduce durable retryable jobs/outbox; local save succeeds independently of cloud availability.
- [ ] Return validated task/idea/calendar suggestions with stable IDs, source revision, supporting excerpt, and review state.
- [ ] Let users edit, accept, and reject each suggestion.
- [ ] Make acceptance transactional/idempotent and preserve source links.
- [ ] Protect accepted records when transcript edits or regeneration occur.
- [ ] Test missing/relative/ambiguous dates using fixed reference time and timezone.
- [ ] Evaluate a small mixed-input sample for accuracy, latency, and cost; record provider decision.

Gate: real voice capture becomes editable suggestions; rejected event writes nothing; repeated acceptance creates one task.

## Milestone 3 — linked workspace

- [ ] Implement task/idea/note details and reciprocal source navigation.
- [ ] Add manual URL references and related-note links.
- [ ] Add internal agenda/event drafts; separate deadlines from appointments.
- [ ] Keep library lists minimal and add simple search/filters.
- [ ] Verify content/source relationships survive relaunch.

Gate: accepted work retains original context and attached references.

## Milestone 4 — focus and meditation

- [ ] Implement persisted Pomodoro/free-flow sessions with pause/resume/end.
- [ ] Calculate elapsed time from timestamps/paused intervals; restore after backgrounding and relaunch.
- [ ] Schedule/cancel completion alerts correctly; handle denied notification permission.
- [ ] Capture an interruption while preserving the current session.
- [ ] Ask for an explicit task outcome instead of auto-completing tasks.
- [ ] Add the meditation player, silent breathing, and a small original/licensed audio collection.
- [ ] Keep one active timed session and separate meditation/focus totals.
- [ ] Verify screen lock, incoming-call/audio interruptions, resumed audio, and timer recovery on device.

Gate: a person can reset, focus on a source-linked task, and retain an accurate session record.

## Milestone 5 — first-release connections

- [ ] Select and verify calendar export method; confirm all fields before a write; make retries duplicate-safe.
- [ ] Add share capture for URL/text with editable preview.
- [ ] Add explicit source-linked web research and reviewed attachment to a note.
- [ ] Build an on-demand Today briefing from real stored records.

Gate: cancelled exports write nothing; references have sources; briefings do not invent work.

## Milestone 6 — complete first-product feature depth and animated onboarding

- [ ] Implement all 12 ONB screens from SCREEN-INVENTORY.md, including cinematic splash, white photographic laptop hero with floating microcards, sign-in and account creation, goals, guided first dump, AI organization, review, focus preferences, recovery preview, granular Trust Mode and personal Today reveal.
- [ ] Complete remaining CAP/DAY/TASK/NOTE/CAL/WEB/FOCUS/INS inventory destinations with contextual action sheets, rich attachments, projects, calendar connections/sync conflicts, web comparisons/source previews, optional opt-in price/news watches, insights, export/restore and full privacy/notification settings.
- [ ] Build the M01–M37 motion library where semantically relevant, with shared transitions, source-to-structure animations, precision inner-tick timer, white/dark theme and reduced-motion variants. Validate thermal/frame budget and fast-scroll content visibility.
- [ ] Integrate actual approved angular S/logo master, branded photo/keyframes and all approved meditation MP3 + custom-motion-GIF pairs once supplied; document licenses, duration/checksum and device playback tests.
- [ ] Enforce Trust Mode as bounded AI organizational automation, independent of security controls and never permitting external booking/purchase/calendar writes without confirmation.
- [ ] Verify feature coverage against the 80 screen IDs; report any blocked or merged UX routes explicitly rather than treating mockups as implemented.

**Gate:** the complete experience and inventory are accounted for in functioning code or transparently tracked with concrete blockers.

## Milestone 7 — private beta

- [ ] Implement/test auth, same-owner relationships, private audio access, and local account isolation.
- [ ] Verify two-user database/storage access, export/deletion, retry safety, and basic account restore.
- [ ] Run the full acceptance journey in BUILD-BRIEF.md.
- [ ] Check accessibility, empty/error states, connectivity changes, and device interruptions.
- [ ] Record known limitations and beta installation instructions.
- [ ] Observe daily use and measure capture-to-focus conversion and repeat use.

No public deployment is part of the repository preparation task.

## Complete scope tracking

Full PDF/image extraction, page clipping, rich attachments, in-app browsing, voice refinements, reviewed Today briefs and bounded opt-in Trust Mode belong to the **complete first build** (Milestones 5–6), not a separately scoped future product. Multi-device conflict-free collaborative editing may require a separately verified depth, but the initial cross-account privacy and basic account recovery remain mandatory. Future meditation packs extend content through the existing player; no additional route is required for each MP3/GIF pair. Treat the 80-screen count as design baseline and log any adjustments.

## Design production workstream — 43 detailed screens and Paper handoff

- [ ] Confirm approved geometric S production asset is actually imported to repo and fonts licensed.
- [ ] Produce the three visual anchors NOTE-02, WEB-02, FOCUS-02 using SCREEN-IMAGE-PROMPTS and separate mobile-design-orchestrator best practices.
- [ ] Review and approve anchor contrast, spacing, safe areas, type hierarchy, glass/glow and light/dark tokens.
- [ ] Produce individual ImageGen reference image for each of the other 40 detailed NOTE/CAL/WEB/FOCUS/INS screens; one clean portrait per screen; do not count documentation prompts as generated art.
- [ ] In user-authorized connected local Paper Desktop MCP session, verify current Paper file via supported read-only API then create tokens and editable frames for each selected/approved design; log real frame refs. Skip/mark pending if MCP absent.
- [ ] Annotate for every screen its scroll owner, pinned controls, offsets, Mxx entrance/loop/gesture transitions, interruption/cancel/undo states and Reduce Motion behavior from DETAILED-SCREEN-MOTION-UX.
- [ ] Validate under 360dp and 430dp widths, enlarged type, keyboard, Android/iOS safe area and all overlays.
- [ ] Convert approved editable designs to native implementation only after working app navigation/data contracts; capture side-by-side screenshot and device evidence.

**Source rules:** external mobile-design-orchestrator is reusable method; Paper MCP is optional design editing bridge; SUPERDORO motion library is the sole motion semantics source. These additions do not imply a live MCP connection or alter the 80-screen count.
