# Decisions and open questions

## Confirmed product priorities

As of November 9, 2026: voice and typed capture; reviewable AI tasks/ideas/calendar suggestions; linked notes; focus timers; meditations. Preserve original input and context. Keep the full core experience in the release while implementing it in dependency order.

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
