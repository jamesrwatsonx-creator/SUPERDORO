# SUPERDORO — complete screen inventory (design baseline)

**Baseline:** 2026-11-09 | **Status:** planned screens, not implemented. | **Scope:** initial complete product vision.

**Exactly 80 distinct primary screen / full-screen sheet definitions** across nine systems. A screen represents a navigable presentation or significant modal experience; light/dark variants, loading/error/empty states, individual meditation assets, and tiny permission sheets are *not* added to the 80. The number is a design planning estimate, not a promise that the application already has 80 routes. Some may merge as implementation reveals better UX. Expected additional interface and device states: roughly 100–140, to be refined by QA.

The first 12 ONB designs are the agreed **12-frame concept carousel**. They include interactive product demonstrations, which are onboarding previews and are not duplicate counted as CAP or FOCUS screens. The real reusable capture and timer implementations are separate IDs below.

## Counting rules and section totals

| Section | IDs | Count |
|---|---|---:|
| Account & onboarding | ONB-01–12 | 12 |
| Voice & AI capture | CAP-01–08 | 8 |
| Today & planning | DAY-01–07 | 7 |
| Tasks & projects | TASK-01–10 | 10 |
| Notes & ideas | NOTE-01–08 | 8 |
| Calendar & reminders | CAL-01–07 | 7 |
| Web research | WEB-01–08 | 8 |
| Focus & recovery | FOCUS-01–11 | 11 |
| Insights & settings | INS-01–09 | 9 |
| **Total** | | **80** |

**Navigation:** Four recommended tabs — Today, Library, Focus, Reset — with a persistent Capture affordance; Tasks, Ideas, Calendar, Projects, Research, Insights, and Settings remain discoverable via home contexts and library tabs/sheets. This is a proposed information architecture to validate, not a hard dependency on five bottom tabs.

**Universal screen contract:** semantic light/dark themes; stable original-source links; accessible type, contrast and focus order; keyboard avoidance; loading/empty/error/offline/permission-denied states; explicit save and undo when safe; reduced-motion equivalent; navigation returning to prior context. Motion IDs below refer to [MOTION-SYSTEM.md](MOTION-SYSTEM.md). Visual direction is documented in [DESIGN.md](DESIGN.md).

## Account & onboarding — 12 screens

### ONB-01 · Splash / S awakens

- **Look / composition:** Black-to-charcoal canvas, exact geometric S logo, spaced SUPERDORO wordmark, minimal status only.
- **Primary behavior:** Auto-advance or skip after initial reveal; revisit without blocking returning users.
- **Motion references:** M01 M02 M03 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-02 · Welcome / Your Focus Harness

- **Look / composition:** Rounded light photographic desk/laptop hero with floating glass cards representing capture, tasks, calendar and focus; short value statement.
- **Primary behavior:** Start, sign in, or explore; capture a glimpse of the real product.
- **Motion references:** M04 M05 M06 M08 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-03 · Sign-in gateway

- **Look / composition:** Shared photo background with frosted authentication panel, Google, Apple, Microsoft and email options.
- **Primary behavior:** Select provider; show errors without moving controls; preserve auth continuity.
- **Motion references:** M07 M09 M10 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-04 · Account creation / verification

- **Look / composition:** Minimal inputs, email/verification feedback, optional password reveal and secure recovery route.
- **Primary behavior:** Create account, confirm identity or continue existing sign-in; never pretend success.
- **Motion references:** M11 M12 M13 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-05 · Goals and preferred outcome

- **Look / composition:** Up to four choice cards for organize thoughts, finish work, routines and well-being; multiple selections supported.
- **Primary behavior:** Select, edit, skip; personalize later.
- **Motion references:** M07 M14 M15 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-06 · Guided first brain dump

- **Look / composition:** Real demo capture or skippable example with voice/text choices, waveform and live transcript only when actually available.
- **Primary behavior:** Record/stop or type; preserve raw input; demo labelled if sample.
- **Motion references:** M16 M17 M18 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-07 · AI organization demonstration

- **Look / composition:** One source thought branches into Tasks, Ideas and Calendar cards with visible source phrases.
- **Primary behavior:** Show how classifications differ; await real model response or provide clearly labelled preview.
- **Motion references:** M19 M20 M21 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-08 · First review and confirmation

- **Look / composition:** Stacked suggestion cards with source excerpts, editable details, distinct accept/reject and undo affordance.
- **Primary behavior:** Review individually; rejected items never create records.
- **Motion references:** M07 M22 M23 M24 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-09 · Focus style preference

- **Look / composition:** Precision white timer face with internal tick marks, 25-min, 50-min, custom, free-flow options.
- **Primary behavior:** Choose duration; skip; safe default; don't launch session without explicit tap.
- **Motion references:** M25 M26 M27 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-10 · Recovery and meditation preview

- **Look / composition:** Layered landscape/glass panel preview of breathing, stretching, meditation and animated recovery scenes.
- **Primary behavior:** Preview, skip, choose preference; media previews never auto-play loud audio.
- **Motion references:** M04 M28 M29 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-11 · Trust Mode, theme and permissions

- **Look / composition:** Trust Mode is AI-organization autonomy only; separate privacy controls, theme preview and granular optional integrations.
- **Primary behavior:** Trust off by default; preview automation scope; don't ask OS permissions until feature use.
- **Motion references:** M12 M30 M31 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### ONB-12 · Personal workspace reveal

- **Look / composition:** First Today dashboard preview with linked note, pending review, calendar, timer CTA and branded S.
- **Primary behavior:** Enter workspace; begin first focus session or finish setup later.
- **Motion references:** M01 M02 M07 M23 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Voice & AI capture — 8 screens

### CAP-01 · Capture hub

- **Look / composition:** Sticky voice and text inputs; recent drafts and processing queue; capture available globally.
- **Primary behavior:** Choose voice/text/share; preserve previous work.
- **Motion references:** M07 M15 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-02 · Live recording

- **Look / composition:** Audio-responsive central orb, visible timer, pause/stop, explicit recording state.
- **Primary behavior:** Permission request on action; offline recording; interrupted-audio recovery.
- **Motion references:** M16 M17 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-03 · Text brain dump composer

- **Look / composition:** Fast rich-text composer with autosave, attach/share and keyboard-safe actions.
- **Primary behavior:** Type/paste; offline first; original saved separately from edits.
- **Motion references:** M11 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-04 · Audio playback and original

- **Look / composition:** Original recording player, waveform timeline, replay speed and timestamp marks.
- **Primary behavior:** Seek, replay, never silently overwrite original audio.
- **Motion references:** M17 M33 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-05 · Transcript and structured output

- **Look / composition:** Editable transcript, source and cleaned version alongside AI structure, highlighted spans.
- **Primary behavior:** Edit; rerun extraction against revision; original remains immutable.
- **Motion references:** M18 M20 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-06 · Processing / retries

- **Look / composition:** States: saved locally, queued, transcribing, extracting, review ready, failed; no fabricated progress.
- **Primary behavior:** Retry and back out safely; preserve evidence of error.
- **Motion references:** M26 M34 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-07 · Suggestion review queue

- **Look / composition:** Tasks/Ideas/Calendar suggestions with editable date/priority and supporting excerpt.
- **Primary behavior:** Accept/reject/edit; stable IDs and idempotent writes.
- **Motion references:** M22 M23 M24 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAP-08 · Voice refinement sheet

- **Look / composition:** Conversational correction tied to a particular note or proposed item.
- **Primary behavior:** E.g. make second point Friday task; review resulting diff; undo.
- **Motion references:** M18 M31 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Today & planning — 7 screens

### DAY-01 · Today dashboard

- **Look / composition:** Three suggested priorities, agenda preview, pending review, resume focus, persistent capture.
- **Primary behavior:** Start linked focus or open detail; optional briefing.
- **Motion references:** M07 M35 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-02 · Morning briefing

- **Look / composition:** Tasks/events grounded in stored records plus accepted watch alerts and deferred items.
- **Primary behavior:** Dismiss, accept suggestions, jump to task; no fabricated updates.
- **Motion references:** M07 M36 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-03 · AI priority planner

- **Look / composition:** Candidate priorities ranked with reasoning, time/effort and available schedule.
- **Primary behavior:** Reorder, reject, schedule proposed blocks.
- **Motion references:** M21 M22 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-04 · Today agenda

- **Look / composition:** Chronological event blocks beside undated tasks; distinction between deadline and appointment.
- **Primary behavior:** Drag/attach task to time block with confirmation.
- **Motion references:** M14 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-05 · Task inbox and triage

- **Look / composition:** Compact uncategorized tasks and pending decisions without heavyweight detail cards.
- **Primary behavior:** Add to Today, defer, convert, archive.
- **Motion references:** M23 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-06 · End-of-day review

- **Look / composition:** Completed vs deferred work; optional actual session outcomes and follow-up.
- **Primary behavior:** Close day, carry unfinished to tomorrow with explicit choice.
- **Motion references:** M23 M36 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### DAY-07 · Tomorrow preparation

- **Look / composition:** Suggested next-day priorities and conflict detection.
- **Primary behavior:** Approve tomorrow's shortlist and draft schedule.
- **Motion references:** M21 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Tasks & projects — 10 screens

### TASK-01 · Task list

- **Look / composition:** Minimal checklist, priority/due chips and optional timer shortcut.
- **Primary behavior:** Quick complete, filters, open detail.
- **Motion references:** M23 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-02 · Task detail

- **Look / composition:** Original-source link, notes, subtasks, specs, relevant references, related work and sticky focus CTA.
- **Primary behavior:** Edit, schedule, research, start focus; progressive disclosure.
- **Motion references:** M07 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-03 · Create/edit task

- **Look / composition:** Title, details, due date distinct from block time, estimate, priority and source.
- **Primary behavior:** Manual create and explicit save; resolve ambiguous dates.
- **Motion references:** M11 M12 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-04 · Subtasks and breakdown

- **Look / composition:** Ordered checklist with AI-suggested subtasks visibly distinguished.
- **Primary behavior:** Accept/edit suggestion, reorder and complete.
- **Motion references:** M23 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-05 · Schedule task

- **Look / composition:** Time block composer with date, timezone, duration and conflicts.
- **Primary behavior:** Write internal schedule, export only after review.
- **Motion references:** M14 M25 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-06 · Projects library

- **Look / composition:** Projects with compact progress, recent activity and linked tasks/ideas.
- **Primary behavior:** Create, filter, open.
- **Motion references:** M07 M36 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-07 · Project workspace

- **Look / composition:** Goal, tasks, source notes, references, sessions, decisions and calendar blocks.
- **Primary behavior:** Navigate relationships without losing context.
- **Motion references:** M07 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-08 · Project editor

- **Look / composition:** Project title, outcome, linked items, tags and optional deadline.
- **Primary behavior:** Edit, archive, connect existing records.
- **Motion references:** M11 M23 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-09 · Link or move task

- **Look / composition:** Searchable project/related-note picker; preview of destination.
- **Primary behavior:** Link vs move clearly differentiated; undo.
- **Motion references:** M22 M24 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### TASK-10 · Task activity/history

- **Look / composition:** Chronological creation, accepted AI edits, focus sessions and changes.
- **Primary behavior:** Inspect origin, restore/undo applicable changes.
- **Motion references:** M36 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Notes & ideas — 8 screens

### NOTE-01 · Notes library

- **Look / composition:** Readable quiet list with title, first lines, source badge, search, quick voice capture.
- **Primary behavior:** Search/filter, open, new note.
- **Motion references:** M07 M15 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-02 · Rich note detail

- **Look / composition:** Header, original audio, transcript, structured thoughts, linked reference cards, contextual actions and conditional metadata.
- **Primary behavior:** Start timer, search web, schedule, link; hide empty sections.
- **Motion references:** M07 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-03 · Rich editor

- **Look / composition:** Text and lightweight formatting with autosave; attachments and selected-text actions.
- **Primary behavior:** Edit safely offline; preserve original capture separately.
- **Motion references:** M11 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-04 · Ideas collection

- **Look / composition:** Unscheduled inspiration and exploratory notes distinct from obligations.
- **Primary behavior:** Explore, convert voluntarily, group by project.
- **Motion references:** M07 M15 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-05 · Idea detail

- **Look / composition:** Idea description, supporting research, hypotheses, people, project links and optional next steps.
- **Primary behavior:** Convert to task and retain original idea link.
- **Motion references:** M07 M31 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-06 · Source and transcript timeline

- **Look / composition:** Audio waveform synchronized to original text, transcript revisions and AI-accepted outputs.
- **Primary behavior:** Replay, inspect evidence, compare versions.
- **Motion references:** M17 M33 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-07 · Related items / backlinks

- **Look / composition:** Linked tasks, calendar events, mentions and related dumps with source provenance.
- **Primary behavior:** Accept/reject suggestions to link; reversible.
- **Motion references:** M19 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### NOTE-08 · Global workspace search

- **Look / composition:** Search tasks, notes, ideas, projects, events and attached source titles.
- **Primary behavior:** Search locally first; show filters and safe highlights.
- **Motion references:** M18 M15 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Calendar & reminders — 7 screens

### CAL-01 · Calendar overview

- **Look / composition:** Week/month calendar with scheduled event blocks, due markers and linked task chips.
- **Primary behavior:** Switch weeks; distinguish task due dates from time blocks.
- **Motion references:** M14 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-02 · Day agenda

- **Look / composition:** Time-ordered events and optional focus blocks with gaps clearly shown.
- **Primary behavior:** Tap or move blocks with edit preview.
- **Motion references:** M14 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-03 · Event draft/detail

- **Look / composition:** Original utterance, interpreted time/timezone/duration, invitees and linked tasks.
- **Primary behavior:** Confirm ambiguous values before creating/exporting.
- **Motion references:** M22 M31 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-04 · Create/edit event

- **Look / composition:** Date/time/duration/recurrence/location fields with timezone preview.
- **Primary behavior:** Save internal draft or explicitly export.
- **Motion references:** M11 M12 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-05 · Reminder composer

- **Look / composition:** One-time/recurring notification and target item preview.
- **Primary behavior:** Preview permission needs; schedule/cancel safely.
- **Motion references:** M12 M25 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-06 · Calendar connection settings

- **Look / composition:** Provider status and import/export scope, permission explanation, reauth.
- **Primary behavior:** Connect Google/Apple where supported, scope access and disconnect.
- **Motion references:** M12 M30 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### CAL-07 · Sync conflicts / review

- **Look / composition:** Side-by-side proposed external/internal edits, origin and timestamps.
- **Primary behavior:** Choose version or keep both, prevent duplicates.
- **Motion references:** M22 M24 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Web research — 8 screens

### WEB-01 · Search from note

- **Look / composition:** Search intent extracted from chosen note, editable query, source/time visibility.
- **Primary behavior:** User-triggered search; cancel; no implied background crawling.
- **Motion references:** M07 M34 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-02 · Results sheet

- **Look / composition:** 3–5 grounded links with title, source, thumbnail and one-line relevance.
- **Primary behavior:** Attach, open, extract; results attach only on consent.
- **Motion references:** M07 M23 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-03 · In-app reader/browser

- **Look / composition:** Reader inside note context with original URL, source domain and trust boundary.
- **Primary behavior:** Open external page safely; back to exact originating note.
- **Motion references:** M04 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-04 · Web clip/highlight

- **Look / composition:** Selected text plus URL and optional image captured as reference preview.
- **Primary behavior:** Attach to existing note or create a new idea/task.
- **Motion references:** M22 M23 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-05 · References gallery

- **Look / composition:** Linked PDFs/images/web excerpts, origin and retrieval/attachment times.
- **Primary behavior:** Open preview, detach, annotate, restore context.
- **Motion references:** M07 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-06 · Comparison workspace

- **Look / composition:** Side-by-side factual specs/prices and citations with dates observed.
- **Primary behavior:** Choose what matters, pin findings, save decision.
- **Motion references:** M36 M33 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-07 · Research synthesis

- **Look / composition:** Concise source-linked summary and decisions with unsupported statements flagged.
- **Primary behavior:** Attach findings or extract reviewable tasks/events.
- **Motion references:** M19 M23 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### WEB-08 · Requested watches/alerts

- **Look / composition:** User-configured price/news/availability watch with trigger and check cadence.
- **Primary behavior:** Opt-in only; cancel; never promise a purchase or booking.
- **Motion references:** M12 M25 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Focus & recovery — 11 screens

### FOCUS-01 · Timer setup

- **Look / composition:** Iconic white circular timer with interior tick ring in light mode; charcoal analog in dark; linked task.
- **Primary behavior:** Choose classic/deep/free-flow/custom and sound; explicitly start.
- **Motion references:** M25 M26 M27 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-02 · Active focus session

- **Look / composition:** Immersive large precision ring, elapsed/remaining display, discreet linked task and capture shortcut.
- **Primary behavior:** Pause, finish, minimize; accurate persisted clock.
- **Motion references:** M25 M27 M35 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-03 · Minimized / persistent timer

- **Look / composition:** Compact control in app and OS-supported notification/Live Activity/widget surfaces.
- **Primary behavior:** Return to same active session; avoid false OS feature promises.
- **Motion references:** M25 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-04 · Pause/resume sheet

- **Look / composition:** Frozen radial arc, resume/end choices and optional pause reason.
- **Primary behavior:** Resume accurately; cancel old alerts.
- **Motion references:** M12 M25 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-05 · Session completion & outcome

- **Look / composition:** Gentle celebratory radial completion, actual duration, done/continue/stopped early.
- **Primary behavior:** Log outcome without auto-finishing task.
- **Motion references:** M23 M26 M37 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-06 · Distraction / interruption capture

- **Look / composition:** Tiny voice/text capture overlay on top of timer.
- **Primary behavior:** Save new thought, dismiss instantly, return to focus.
- **Motion references:** M16 M32 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-07 · Break recommendation hub

- **Look / composition:** Short optional breathe/stretch/meditate choices after working; skip available.
- **Primary behavior:** Choose suitable reset with no coercion.
- **Motion references:** M07 M28 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-08 · Guided stretching player

- **Look / composition:** Motion visual for selected movement, duration, progress, safe skip/pause.
- **Primary behavior:** User controls pace; support per-sequence animations.
- **Motion references:** M28 M29 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-09 · Breathing visual player

- **Look / composition:** Expandable circles/curves synced to inhale/exhale and optional sound.
- **Primary behavior:** Change tempo, no audio, reduced motion.
- **Motion references:** M28 M25 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-10 · Meditation library

- **Look / composition:** Cards for individual meditations with duration, voice/audio and unique motion-art previews.
- **Primary behavior:** Preview/select, download/stream based on state.
- **Motion references:** M04 M07 M29 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### FOCUS-11 · Meditation + motion player

- **Look / composition:** Specific meditation MP3, synchronized custom loop/GIF or video animation, scrub and background controls.
- **Primary behavior:** Play/pause/seek, resume after interruption, separate meditation analytics.
- **Motion references:** M28 M29 M33 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## Insights & settings — 9 screens

### INS-01 · Focus insights dashboard

- **Look / composition:** Actual focus time, sessions, task completions and honest trends.
- **Primary behavior:** Switch period, drill down to real session evidence.
- **Motion references:** M36 M33 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-02 · Weekly reflection

- **Look / composition:** Narrative summary of work completed, deferred, and activity patterns.
- **Primary behavior:** Accept next-week suggestions, no fabricated success.
- **Motion references:** M07 M36 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-03 · Goals and progress

- **Look / composition:** Goal timelines, focus targets and habits based on user-selected outcomes.
- **Primary behavior:** Adjust and inspect source records.
- **Motion references:** M25 M36 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-04 · Profile and plan

- **Look / composition:** Account, subscription state, storage/privacy entry, sign out.
- **Primary behavior:** Manage account with confirmation for destructive actions.
- **Motion references:** M07 M12 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-05 · Appearance and accessibility

- **Look / composition:** Dark/light/system theme, glow intensity, contrast, text scale, reduced motion.
- **Primary behavior:** Live preview, persist preferences.
- **Motion references:** M30 M31 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-06 · Notifications and focus filtering

- **Look / composition:** Local timer/reminder alerts, quiet hours, optional filtering where OS supports.
- **Primary behavior:** Explain platform limitations and ask only necessary permissions.
- **Motion references:** M12 M31 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-07 · Trust Mode permission center

- **Look / composition:** Granular allowed AI organizational actions, review history and kill switch.
- **Primary behavior:** Default off; reversible; external side effects require explicit confirmation.
- **Motion references:** M12 M22 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-08 · Integrations and connected sources

- **Look / composition:** Calendar, browser-share, research providers and later optional connectors.
- **Primary behavior:** Connect/disconnect, permission status, reauth.
- **Motion references:** M12 M30 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

### INS-09 · Privacy, export and security

- **Look / composition:** Data use transparency, original recording retention, encryption claims only when verified, export/delete.
- **Primary behavior:** Review, export, request deletion and confirm irreversible operations.
- **Motion references:** M12 M22 (adapt to reduced motion).
- **Evidence:** design specification only; implementation and device behavior not verified.

## State and overflow inventory (not included in 80)

Each route needs first-run/empty, populated, long-text and overflow, keyboard open, loading, offline, reconnect/retry, permission denied, accessible large type, dark/light, reduced-motion and error handling. Authentication adds provider failure / expired code / recovery; capture adds background microphone interruption; timer adds lock-screen / background / paused / completion recovery; calendar adds DST and timezone ambiguity; media adds no MP3 / corrupted file / resumed playback. These are design states, not additional primary screen IDs.

## Complete acceptance journey

Splash > account or guest capture entry > optional onboarding > voice or text dump > reliable local save > user-visible transcription/extraction > edited approval/rejection > source-linked task > user-initiated web search > attached reference > approved date/event > task-linked focus session > pause/interruption capture > session outcome > suggested break > selected meditation MP3 + its own motion visual > Today briefing > weekly review. Each transition must preserve prior context and be verifiable on a physical device.

The 80-screen scope is included in the product plan for the first full build. Development remains dependency-ordered: do not claim these 80 screens or providers are implemented, or let aesthetic mockups replace working workflows.
