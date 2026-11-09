# Decisions and open questions

## Confirmed product priorities

As of November 9, 2026: complete first-product build includes all **80 planned screens** across nine functional systems, from account/onboarding through research, advanced Today/planning, tasks/projects, notes/ideas, calendar/reminders, focus/meditations and insights/settings. Preserve rich original context, user control and source links. Implement in dependency order; do not release a timer-only MVP as the complete SUPERDORO product.

James created the public `jamesrwatsonx-creator/SUPERDORO` repository and authorized adding the necessary foundation there, with application implementation to continue in Claude Code.

## Proposed technical defaults

| Decision | Proposed default | Becomes confirmed when |
|---|---|---|
| Mobile stack | Expo / React Native / TypeScript | Scaffold and compatibility are verified and recorded |
| Local persistence | SQLite and durable app file storage | Migrations and persistence/recovery checks pass |
| Backend | Supabase Auth / Postgres / private storage | Configured implementation and ownership tests pass |
| First device | Android first, cross-platform structure | Actual build/device result recorded |
| Navigation | Today / Library / Focus / Reset plus Capture | Implemented flow reviewed in use |
| Capture cap | Five-minute initial cap | Deliberately implemented and surfaced before recording |
| Sync depth | Local outbox; one primary device per beta user | Retry/recovery behavior demonstrated |
| Meditation collection | Two-minute arrival, five-minute reset, ten-minute wind-down, silent breathing | Scripts/audio reviewed and rights recorded |

These proposals are not completed integrations or final user approvals. Routine reversible implementation choices can proceed within the authorized build; record the resulting decision and evidence.

## Open when needed

- Locate and import exact approved design source assets.
- Select transcription/extraction providers using measured samples and a stated cost budget.
- Select calendar export method after device permission/integration checks.
- Supply backend/service configuration securely when those milestones require it.
- Finalize meditation scripts, voice/audio, ownership, and playback behavior.
- Confirm distribution/pricing after a working private beta demonstrates repeat use.

## Record future decisions

For a material change record date, decision, reason, evidence, alternatives that mattered, and what would reverse it. Keep this short. Do not confuse the existence of a document, mock, or API adapter with a working user journey.

## New design/media decisions — November 9, 2026

- Baseline screen count is exactly **80**, documented in SCREEN-INVENTORY.md; sketches/states and individual meditation content do not count as extra routes.
- Confirmed identity direction: user-favored angular geometric S, white rounded “Your focus harness” laptop photography paired with modern floating UI widgets, luminous green restrained glassmorphism, contemporary bold sans, light + dark themes and the white timer with interior ticks.
- Motion creative direction: approximately 60–80 motion behaviors throughout 12 onboarding design concepts, using M01–M37 reusable primitives with reduced-motion/performance gates; not a license for continuous loops on every screen.
- User intends to provide meditation MP3s and request **individually customized motion GIFs**; all such binaries remain pending. Never misrepresent provenance/rights or generated content as implemented.
- **Trust Mode** means low-risk optional AI organization, not enabling/disabling privacy or security. Do not display made-up privacy strength percentages.
- AI search/research, richer web clips, calendar provider sync, projects, insights and other detailed experiences are included in the **first complete build**; their late dependency milestones should not be described as a permanent scope exclusion.
