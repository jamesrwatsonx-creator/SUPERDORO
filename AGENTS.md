# SUPERDORO engineering instructions

## Start here

Read STATUS.md, docs/BUILD-BRIEF.md, docs/BACKLOG.md, docs/DESIGN.md, and docs/DECISIONS.md before implementation. Inspect the actual checkout and preserve newer user work. The brief records product intent; STATUS.md records observed implementation. Resolve conflicts explicitly instead of treating historical plans as completed code.

## Product invariants

- Keep voice capture, typed capture, reviewable AI suggestions, linked context, focus timers, and meditations in the release.
- Save locally before depending on uploads, transcription, or AI. Preserve original text and stopped recordings in durable storage.
- Separate original text, editable transcript, source revision, AI suggestion, and accepted record.
- Suggestions require individual review and editable fields. Rejection creates no task/event. Repeated acceptance must create only one record.
- Every accepted item links to its source note. Rerunning AI cannot silently replace accepted items.
- Task deadlines and calendar appointments are different concepts. Do not invent missing dates, priorities, or durations. Retain date expressions and interpretation context.
- External calendar writes require explicit confirmation. Trust mode is not enabled or implemented by default.
- Calculate timer state from persisted timestamps and pauses. Background execution is not a reliable clock. Completing a session does not automatically complete the task.
- Keep meditation and focused-work session totals separate. Use original or properly licensed audio.
- Use light and dark themes; preserve the confirmed design direction. Keep list views quiet and detail views contextual.

## Implementation approach

The recommended default is React Native + Expo + TypeScript, with SQLite locally and Supabase later. This is not an installed stack. Unless existing code or a concrete compatibility problem changes the choice, initialize that direction and record exact versions/commands. Do not switch to a hosted website builder or timer-only demo.

Build the next unverified milestone end to end. Do not scaffold every integration at once. Avoid a general agent framework, a generic sync engine, and speculative abstractions. Choose a small number of replaceable service adapters where external services are actually needed.

Keep provider/service secrets server-side. Never commit credentials, voice recordings, personal transcripts, local databases, signing keys, or private test data. Do not place server secrets in EXPO_PUBLIC variables. Add only placeholder environment examples when configuration exists.

Configure and test per-user database/storage access before cloud-backed private data is considered complete. Keep local data isolated between accounts. Do not deploy live services, publish an app, purchase services, or request broad account access merely to scaffold local capture.

## Verification and reporting

Run checks appropriate to the change. Add meaningful tests around persistence, review idempotency, source revisions, date interpretation, timers, retries, and ownership as those behaviors are implemented. Avoid tests that only mirror constants or document wording.

Use explicit evidence labels: planned, implemented/unverified, automated-check verified, device verified, blocked. Type checking does not establish device behavior. Mock AI does not establish real transcription/extraction. Do not mark complete without a result that supports the claim.

Update STATUS.md and the relevant backlog checkbox with changed files, checks/results, remaining device checks, and the next task. Update decision records when a proposal becomes an implementation choice. Report blockers precisely; continue independent local work. Stop for missing required account configuration rather than inventing credentials.
