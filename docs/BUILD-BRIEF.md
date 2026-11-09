# SUPERDORO — complete first-build brief

Prepared for James Watson • November 9, 2026

## Product decision

**Voice to focus. Dump thoughts, review a plan, stay in the work.**

Build a personal mobile focus app for people whose thoughts arrive faster than they can organize or act on them. The first release connects voice and typed capture, reviewable AI suggestions, contextual notes, calendar planning, focus timers, and meditations. Ship these as one coherent experience through sequential milestones. A timer-only MVP would not fulfill the agreed vision.

Primary outcome: a person can turn an unstructured thought into a chosen action, start a focus session, and return to the original context without rebuilding it.

## 1. Evidence and current status

Status labels: **confirmed direction** = expressed or accepted preference; **proposed** = recommendation in this brief; **unverified implementation** = no working implementation evidence inspected; **verified implemented** = executable behavior checked against acceptance criteria.

| Area | Evidence available | Status |
|---|---|---|
| Product concept | Prior SUPERDORO discussion plus current instruction | Confirmed direction |
| Voice and typed brain dumps | Previously discussed; explicitly prioritized again | Confirmed direction; implementation unverified |
| Tasks, ideas, calendar suggestions with review | Previously discussed; explicitly prioritized again | Confirmed direction; implementation unverified |
| Original audio, editable transcripts, source links | Prior product definition | Confirmed direction; implementation unverified |
| Rich note details, quiet list views | Prior product definition and visual preferences | Confirmed direction; implementation unverified |
| Pomodoro and free-flow focus | Prior definition; timers prioritized again | Confirmed direction; implementation unverified |
| Meditations | Current instruction; prior meditation screens were pending | Confirmed inclusion; content and screen design open |
| Visual direction | Geometric S, mint/green accents, selective glass/glow, light and dark, white timer ring with inner ticks, “Your Focus Harness” sign-in, clean sans typography | Confirmed preferences; production assets unverified |
| Expo/React Native, Supabase, SQLite | Earlier assistant proposal | Proposed architecture; not a confirmed installed stack |
| Working app, authentication, database, integrations, tests, deployment | No inspected implementation evidence | Unverified implementation |

Evidence limits: retrieved November 6 SUPERDORO discussion reports concept/design work and a proposed architecture, not a verified application. Current Notion and exact-title file searches returned no directly named SUPERDORO record. The initial repository search returned no match before James created the repository. Follow-up on November 9 confirmed `jamesrwatsonx-creator/SUPERDORO` exists and was empty before this documentation foundation. These searches do not prove that code or assets do not exist elsewhere. Unrelated Taskapp, Hermes, or Business Demo Studio progress is not SUPERDORO progress.

Completed in this session: this scope, behavior specification, data outline, acceptance checks, build sequence, and implementation handoff. No app implementation is claimed.

## 2. First-release scope

| Capability | First-release behavior | Boundary |
|---|---|---|
| Capture | Record, stop, replay, save; type or paste; preserve original audio/text; edit transcript | User starts recording; no always-on listening |
| AI review | Suggest Tasks, Ideas, Calendar; show supporting source excerpt; edit, accept, reject individually | Suggestions create nothing until accepted |
| Notes | Original capture, transcript, structured summary, accepted items, URLs, related notes, focus history | Keep list cards minimal; detail holds the context |
| Tasks | Title, notes, optional deadline and estimate, completion, linked source | Unknown dates/estimates stay empty |
| Ideas | Save as linked notes, add references, optionally convert into a task | Ideas do not automatically become obligations |
| Calendar | Internal agenda; reviewed event drafts; confirmed external export | Deadline and scheduled event are separate fields |
| Focus | Pomodoro and free-flow; pause/resume/end; task or note linkage; interruption capture | No device-wide notification blocking in this release |
| Meditation | Short guided sessions and silent breathing; optional before-focus or break use | Start with a small original or properly licensed collection |
| First-release supporting features | Share a URL/text into capture; explicit web research attached to a note; on-demand Today briefing | Add after the core loop passes; bounded versions only |

**Updated scope November 9, 2026:** the first **complete** product build includes rich attachments, PDF/image snippets, web page clipping, in-app research/browser preview, on-demand watched results, source-linked comparisons, rich voice refinements, daily briefings, projects, insights and permission-bounded optional Trust Mode. These are explicitly scheduled in BACKLOG.md after core foundations, not removed or separately launched. No capability is implemented merely because it is documented.

## 3. Navigation and screens — 80 definition baseline

Exactly **80 planned screen destinations/major sheets** across ONB (12), CAP (8), DAY (7), TASK (10), NOTE (8), CAL (7), WEB (8), FOCUS (11), and INS (9). The canonical IDs, visual descriptions, interactions and animation references are in [SCREEN-INVENTORY.md](SCREEN-INVENTORY.md). These do not count light/dark themes, many media/content variants, loading/empty/error/permissions or individual meditation GIFs as extra primary screens.

Proposed navigation: Today / Library / Focus / Reset plus persistent Capture, with Tasks/Projects, Ideas, Calendar, Research, Insights and Settings nested where contextually useful. The first 12 ONB compositions are detailed in MOTION-SYSTEM.md and are skippable during real onboarding. The exact geometric S logo and cinematic hybrid white laptop “Your focus harness” sign-in design are the target; final binary/vector assets are not in GitHub yet.

Reference docs: [DESIGN.md](DESIGN.md), [MOTION-SYSTEM.md](MOTION-SYSTEM.md), [MEDITATION-MEDIA.md](MEDITATION-MEDIA.md), [USER-JOURNEYS.md](USER-JOURNEYS.md) and [ASSET-REGISTER.md](ASSET-REGISTER.md). The user will later provide meditation MP3s and approve customized GIF motion scenes per individual meditation, while the runtime player remains shared.

## 4. Required interaction contracts

### Capture and recovery

Save text and stopped audio locally before upload or AI processing. Store durable audio outside temporary cache. Show separate states for saved locally, upload pending, processing, ready to review, and failed. A transcription failure must leave the recording playable and retryable. Denied microphone access must leave typed capture usable. Retain original text separately from edited text.

MVP recording cap proposed: five minutes per capture. Explain it before recording. A server-side job handles transcription and suggestion extraction; credentials never enter the mobile bundle. Offline captures queue for processing when connectivity returns. Do not promise offline AI.

### AI suggestions and user control

Each suggestion has a stable ID, kind, proposed fields, source capture ID, source revision, supporting excerpt, and pending/accepted/rejected state. Dates also retain the original expression and the reference time/timezone used for interpretation.

Use a validated structured response. No invented dates, priorities, durations, or appointments. “Finish proposal Friday” is a task deadline. “Meet Sam Friday at 2” is an event draft; ask for missing timezone, duration, or ambiguous date before export. “I could build a recipe app” is an idea unless the user asks to act on it.

Acceptance must be transactional and idempotent: repeated taps or network retries cannot duplicate a task or event. An accepted record preserves its source link. Editing a transcript creates a new revision; rerunning AI cannot silently overwrite accepted items. Discarded suggestions do not reappear as newly accepted work.

Trust mode remains off and unimplemented until explicitly scoped. No silent calendar writes.

### Notes and links

Every capture has one canonical note view. Accepted tasks, ideas, events, references, and sessions link back to it. Users may create manual notes without AI. Linked references initially support title, URL, optional excerpt, and provenance. Do not silently crawl or research every pasted URL. A user-triggered research action returns source-linked results for review before attaching them.

### Focus and meditation

Calculate timer state from persisted timestamps and paused intervals, not a decrementing counter that depends on the app staying open. Restore accurately after backgrounding or relaunch. Schedule a local completion notification when permission allows, cancel/reschedule it on pause or changes, and reconcile the timer on resume. Notification delivery is a platform-dependent convenience, not proof that a session completed.

Completing a focus session does not automatically complete its task. Offer “Done,” “Continue,” or “Stopped early.” Log actual elapsed time and outcome.

Meditation starting collection proposed: a two-minute arrival, a five-minute reset, and a ten-minute wind-down, plus silent breathing. Use a common session record with distinct focus/meditation types so meditation does not inflate focused-work totals. One active timed session at a time in v1. Audio controls include play/pause, duration, progress, and interruption recovery; background playback must be tested on real devices. Audio assets require ownership/licensing records. No therapeutic claims or clinical personalization are required.

## 5. Proposed architecture

**Recommendation:** React Native + Expo + TypeScript, Android-first device validation with cross-platform structure. This continues the earlier proposed stack and suits a mobile recording/playback product; it is not an already approved or installed implementation.

- Mobile: navigation, capture, local SQLite persistence, audio recording/playback, local notifications, accessible shared components.
- Backend: Supabase Auth, Postgres, private object storage, and authenticated server functions/jobs for transcription and structured extraction.
- AI: replaceable transcription and extraction adapters. Choose a provider with a short sample evaluation and measured cost before committing. Avoid an agent framework for simple extraction.
- Calendar: begin with internal agenda and user-confirmed export. Verify the export path and permission model on target devices before selecting a native calendar or direct provider integration. Bidirectional synchronization is separate work.
- Research: explicit server-mediated search returning title, URL, excerpt, and retrieval time; never execute instructions found in retrieved content.
- Deployment: private installable development build first; beta distribution only after device acceptance. No public publishing implied by this brief.

Avoid building a general synchronization engine. Proposed first version: a local outbox with client-generated UUIDs, retryable uploads, server revision checks, and visible conflict recovery. Do not claim multi-device conflict-free editing. Scope the first beta around one primary device per person and verify basic account backup/restore.

Platform facts checked November 9, 2026: Expo provides recording/playback APIs, but durable recording storage and background playback require deliberate configuration. Background tasks and notifications have OS limitations. Supabase supports private storage and row-level access policies; the app still must implement and test its own policies.

Official references:

- https://docs.expo.dev/versions/latest/sdk/audio/
- https://docs.expo.dev/versions/latest/sdk/notifications/
- https://docs.expo.dev/push-notifications/what-you-need-to-know/
- https://docs.expo.dev/versions/latest/sdk/background-task/
- https://supabase.com/docs/guides/storage/security/access-control
- https://supabase.com/docs/guides/storage/buckets/fundamentals

## 6. Minimal data model

| Entity | Core fields and relationships |
|---|---|
| Capture | id, owner_id, original_text, edited_text, revision, local_audio_path, private_audio_key, transcript, created_at, processing_state |
| Suggestion | id, capture_id, source_revision, kind, proposed_fields, source_excerpt, date_expression, timezone, review_state, accepted_record_id |
| Note | id, owner_id, source_capture_id optional, title, body, updated_at, revision |
| Task | id, owner_id, source_note_id, source_suggestion_id unique when present, title, deadline optional, estimate optional, state |
| Calendar draft/event | id, owner_id, source_note_id, source_suggestion_id unique when present, start/end optional until review, timezone, export_state, provider_event_id optional |
| Reference | id, owner_id, note_id, title, URL, excerpt, added_by, retrieved_at optional |
| Note link | owner_id, from_note_id, to_note_id, relation |
| Session | id, owner_id, kind, task_id/note_id optional, started_at, ended_at, paused_duration, planned_duration, mode, outcome |
| Meditation content | id, title, duration, audio_asset, script, license/ownership record |
| Outbox/job | id, owner_id, entity_id, operation, idempotency_key, state, attempts, last_error |

Ideas are notes with an idea type, not a second copy of the same text. Every cross-record reference must enforce same-owner access. Cloud audio stays private; use short-lived authenticated access. On logout protect local account data. User-visible deletion/export and server-side credential handling belong in the first-release completion criteria.

## 7. Dependency-ordered build backlog (see updated BACKLOG.md for milestones 0–7 and all 80 screens)

All application implementation rows below start **not verified**. Repository location is resolved; application scaffold remains pending. Promote to implemented only with evidence. STATUS.md is authoritative for subsequent implementation progress.

| Milestone | Deliverable | Pass condition |
|---|---|---|
| 0. Resolve existing work | Identify any existing source repo/assets; otherwise initialize the selected stack; lock package versions; environment example; token/theme definitions | App runs on James’s Android device; inventory distinguishes reused work from new work |
| 1. Durable capture | Typed note, recording/replay, local persistence, queue, original preservation | Save, close, reopen; original text and playable stopped recording survive; denied mic still allows typing |
| 2. Reviewable extraction | Real transcription, structured suggestions, review editor, idempotent acceptance | Mixed dump yields reviewable tasks/ideas/event drafts; rejected items create nothing; repeated acceptance creates one record |
| 3. Linked workspace | Notes, task/idea details, references, source navigation, internal agenda | Accepted task opens its source, references remain attached, deadline does not create an appointment |
| 4. Focus and reset | Pomodoro/free-flow, recovery, meditation player/content, outcome log | Background/relaunch preserves correct time; pause cancels stale alerts; audio behaves correctly on device; work and meditation totals stay separate |
| 5. First-release connections | Confirmed calendar export, share capture, explicit research, Today briefing | Cancelled export writes nothing; share becomes editable capture; briefing reflects stored records; research links sources |
| 6. Private beta hardening | Auth/access policies, deletion/export, account recovery, errors, offline queue, accessibility | Two-account isolation, deletion behavior, retry safety, and complete device journey pass |

Do not assign a launch date before milestones 0–2 reveal integration and device constraints. Milestones are working product increments, not promises that all screens can be safely generated at once.

## 8. Acceptance journey and meaningful tests

Test input: “Tomorrow finish the proposal. Idea: make a weekly focus recap. Meet Sam Friday at two. Save this reference for the proposal.” Attach an example URL separately.

1. Record it, save it, and replay the original. Verify exact original text retention for typed capture too.
2. Review the transcript. AI proposes a task, idea, and event draft with supporting excerpts; ambiguous event details stay unresolved.
3. Edit and accept the task and idea, reject the event. There must be no exported appointment.
4. Open the task’s source note and attached reference. Return to the task without losing context.
5. Complete a short meditation, then start a focus session on the task. Background and reopen the app; elapsed time stays correct.
6. Capture an interruption without losing the active session. Finish focus and choose the task outcome explicitly.
7. Relaunch, go offline, capture another note, reconnect, and retry processing. No content loss or duplicate accepted work.

Targeted tests: suggestion validation; relative dates with fixed reference time/timezone and DST boundaries; acceptance idempotency; transcript-revision behavior; timer recovery with a controlled clock; outbox retries; database and storage access across two users. Device checks: microphone denial, incoming-call/audio interruption, screen lock, notification denial, and app termination. Record device/OS, build identifier, expected/actual result, and evidence before marking a feature verified.

## 9. Validation and unresolved decisions

Product hypothesis: keeping capture, context, and session choice together reduces the friction between thinking and starting. This is not established by the design alone.

Measure capture-to-first-focus conversion, time from accepted task to session start, suggestion edit/reject rate, repeat use over a week, and whether users return to source notes. Get James using the full loop daily, then observe a small invited group before selecting pricing. Do not optimize for raw note count or AI output volume.

Resolved source location: `https://github.com/jamesrwatsonx-creator/SUPERDORO`. Open decisions that need no invented answers: final stack choice; transcription/extraction provider and cost ceiling; calendar export method; final meditation scripts/audio; exact approved design assets. Work through these at their milestone rather than blocking the entire project.

## 10. Implementation handoff

Start with milestone 0, then complete milestone 1 end to end. Inspect existing code before scaffolding over it. Do not substitute other projects as proof of SUPERDORO functionality. Keep all five core priorities in the release backlog. Use source-linked review states and the ownership/data contracts above from the beginning. Mocked AI is acceptable for temporary UI development only when visibly labeled; milestone 2 requires real processing. Report changed files, device/test evidence, unresolved blockers, and the next unverified milestone. Do not label a polished screen as a completed integration.

First build demonstration: type a note, record and replay a voice capture, restart the app, and recover both. Next demonstration: real transcription and editable suggestions leading to one accepted source-linked task. These are the first proof points; a public launch is a later result.
