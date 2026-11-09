# SUPERDORO — Complete Product & Design Overview
**Version:** 1.0 design specification • **Date:** 2026-11-09 • **Repository status:** documentation only; no verified mobile implementation or Paper connection in this ChatGPT session.

## 1. What this document is
This document is the **product design bible** for SUPERDORO. It explains the product's reason to exist, intended audience, mental model, information architecture, visual identity, motion grammar, media workflow, key data relationships, privacy/permission boundaries, and the definition of a complete user experience. The companion [DETAILED-SCREEN-MOTION-UX.md](DETAILED-SCREEN-MOTION-UX.md) is the interaction-by-interaction build and design brief for 43 screens in five requested systems. [SCREEN-INVENTORY.md](SCREEN-INVENTORY.md) is the canonical 80-screen catalog.

**What it is not:** a functioning codebase, an assertion that 80 screens have been developed, an approved pixel-perfect Figma/Paper file, actual MP3/GIF media, or a guarantee that all external APIs and OS affordances work. Every generated UI concept is a creative reference until inspected and implemented.

## 2. Product premise and operating model
**Product:** SUPERDORO. **Brand promise:** "Voice to focus. Dump thoughts, get a clear plan, and stay in the work." The product is a calm, premium focus workspace that transforms unstructured voice, text and shared content into explicit, source-linked items that people can review, schedule and execute. Its differentiator is not simply voice transcription or a beautiful timer. It is the **closed loop from capture through action and recovery**, without context loss.

### 2.1 Core user job
1. Capture a thought before it disappears, even offline, without deciding how to file it.
2. Understand what was said and preserve the exact original. AI extracts Task, Idea, or Calendar candidate records with evidence and a review option.
3. Review and correct rather than trust a hidden parser. Later, independently inspect original audio, transcript, AI structure and accepted changes.
4. Attach context: searched web pages, clips, PDFs, images, people, related projects and relevant previous notes.
5. Convert a thought into action: move it to Today, schedule a block, create a reminder or start a timer attached to the original item.
6. Complete focused work, retain actual time spent, optionally reset with a breath/stretch/meditation experience, then return to the original task.
7. Learn from daily/weekly summaries based on recorded activity, not invented gamification or unverified sources.

### 2.2 The three categories are views, not storage silos
**Task** = actionable obligation; may have due date, priority, estimated Pomodoros, subtasks, scheduled focus blocks. **Idea** = exploratory thought, potential project or unresolved question; not automatically a task. **Calendar** = scheduled event/commitment or time block with an actual time context, timezone and duration. A date in a task ("finish Friday") is not automatically an event; "meet Friday 3 PM" may be. Items can be related or converted through explicit action while preserving provenance.

Each item can own many **source references**, including audio, transcript revisions, highlights, web captures and linked files, and many **relations** to projects and other items. The same underlying task may appear in Tasks, Today and Calendar without being duplicated.

### 2.3 Progressive disclosure
The top-level lists are deliberately light; the detail screen can be rich. Suggestions are contextual, user-triggered, and dismissible. The in-app browser and research results should feel attached to the note, not like separate searches that sever context. Do not force every blank metadata field into a note. A one-line note remains one line until the user gives it more meaning.

## 3. Complete primary screen taxonomy
| System | Stable IDs | Planned primary screens |
|---|---|---:|
| Account & onboarding | ONB-01...12 | 12 |
| Voice & AI capture | CAP-01...08 | 8 |
| Today & planning | DAY-01...07 | 7 |
| Tasks & projects | TASK-01...10 | 10 |
| Notes & ideas | NOTE-01...08 | 8 |
| Calendar & reminders | CAL-01...07 | 7 |
| Web research | WEB-01...08 | 8 |
| Focus & recovery | FOCUS-01...11 | 11 |
| Insights & settings | INS-01...09 | 9 |
| **TOTAL** | | **80** |

A primary "screen" is a named major destination or full-sized sheet. It does **not** count each empty/loading/offline/error state, dark/light theme, visualization frame, or separate meditation item. The user's request names seven Notes surfaces; the existing catalog includes an eighth: **NOTE-06 Source and transcript timeline**. This document therefore covers 43 screens in five systems, without silently changing the established 80-screen total.

## 4. Navigation architecture
**Recommended main navigation to validate:** Today • Library • Focus • Reset, with a globally accessible Capture affordance. Library exposes Notes, Ideas, Tasks and Projects. Calendar can be entered via Today/schedule and a visible contextual action. Research is launched from a note/task/project or global Search. Insights/Profile/Settings are accessible from stable entry points. A user should not need to memorize hidden gestures.

For each screen:
- Top bar has a visible title or contextual back arrow, optional source breadcrumb, and actions with names.
- Bottom safe area respects gesture/navigation insets; persistent CTAs do not cover scrollable content.
- The back action returns to the precise originating note, task, calendar day or current focus session; overlays preserve state.
- Modal/sheet gestures are complemented by visible Close/Apply/Cancel controls, especially for accessibility.
- Nested lists maintain scroll offset if a user visits detail and returns.
- Multi-step edits have clear Save/Cancel and, where feasible, Undo. External consequences get separate final confirmation.

## 5. Brand and aesthetics: one coherent system
**Approved direction:** geometric interlocking angular "S" plus SUPERDORO wordmark (the image generated in chat still needs a verified repository master file); warm premium white and dark near-black variants; mint/emerald accents; readable geometric contemporary sans; high-end rounded glass surfaces with controlled glow; restrained photographic/nature imagery in welcome and recovery, not busy every-screen marketing imagery. User specifically likes a **white precision timer with interior tick marks** and the combination of the white laptop "Your focus harness" sign-in hero with modern, floating glass status cards.

### 5.1 Nonnegotiable layout standard
Integrate [mobile-design-orchestrator](https://github.com/jamesrwatsonx-creator/mobile-design-orchestrator) at pinned source revision `4d88a488ed78ad7b1bec503e4180abccac338af5`, especially `references/mobile-layout-rules.md`, `skills/mobile-image-generation.md`, `skills/screen-planning.md` and `PROJECT-INSTRUCTIONS.md`. Use an **8-point spacing rhythm** (4-point increments only if justified), margins generally 16–24 dp/pt, finger-accessible controls 44–48 dp/pt practical minimum, appropriate font hierarchy, strong contrast and safe areas, realistic content density, consistent proportion and thumb-reachable frequent actions. Build a native mobile composition, never a website shrunk to phone width.

### 5.2 Type and surfaces
- Main header: clear editorial sans, stable typography scale; body text remains practical and high-contrast. Huge hero words only during onboarding and immersive media, not scrollable tasks.
- Glass card: material opacity and border are theme tokens; dark glass remains high-contrast and accessible; layering never makes small text hard to read.
- Glow: status/active affordance, not a decoration on every border. A user may choose less glow or Reduce Motion.
- Tone: quiet, precise, confidence without pretending an AI suggestion or web result is verified.
- Empty states: meaningful next action such as "Record a note" or "Search from this note", never a forced huge illustration that hides the control.
- Iconography: consistent stroke thickness and size, always accompanied by explanatory label where unfamiliar.
- Photos/video/meditation assets: licensed/approved, with accessible static alternatives.

## 6. Motion as a functional language
The motion source of truth is [MOTION-SYSTEM.md](MOTION-SYSTEM.md), a 37-primitive catalog (M01–M37), and [REFERENCE-MOTION-LIBRARY.md](REFERENCE-MOTION-LIBRARY.md), a 105-term inspiration index. The per-screen choreography is in [DETAILED-SCREEN-MOTION-UX.md](DETAILED-SCREEN-MOTION-UX.md). **The rule is high expressiveness in onboarding and transitions, low visual noise during active work.** Each motion exists to signal navigation continuity, extraction, ownership, state change, progress, time or a meaningful reward.

### 6.1 Four classes of motion
**Entrance:** fade-up, slight spring, stagger/cascade, word reveal when first appearing. No blank screen waiting for animation. **Scroll-linked:** reversible header compression, subtle parallax, sticky anchored primary action, data/section disclosure; use native scroll handlers with controlled transforms and no forced web scroll library. **Interaction:** pressed state, focus ring, selection, swipe, drag/reorder, card attach, comparison toggles, check draw-on and undo. **Ambient:** breathing rhythms, soft photo depth or meditation scene loops only where semantically suitable. Continuous ambient effects pause in background and must not compete with reading or the running clock.

### 6.2 Timing and state discipline
Tap feedback about 120–240 ms; card and list transitions 200–450 ms; native sheets 250–500 ms; shared-element navigation around 450–800 ms when device performance allows; one-off cinematic reveals up to about 1–2.5 s and always skippable. Avoid inventing progress. Animated timer visuals derive from persisted clock state, not from an incrementing UI interval. Screen readers and Reduce Motion get equivalent meaning without motion.

### 6.3 Native motion handoff
Proposed implementation candidates: React Native/Reanimated/Gesture Handler for screen and gesture transitions; Skia/vector rendering for dial precision; Rive for future interactive scene state machines; Lottie for localized decorative assets; MP3 plus GIF/animated WebP or efficient video for meditation. Web Framer/GSAP/Lenis vocabulary must be **translated to native equivalents**, never blindly pasted as CSS. Paper designs describe layers/frames and motion annotations; they are not a runtime animation engine.

## 7. Data and provenance architecture
Recommended logical entities (to refine during implementation): User, Device, Project, SourceCapture (type: voice/text/shared), OriginalAudio, TranscriptRevision, Note, Task, Idea, CalendarEvent, Reminder, ScheduleBlock, Relationship, SourceReference (web/file/image/clip), ExtractionProposal, ProposalDecision, FocusSession, RecoverySession, MeditationContent, MediaAsset, WebSearchRun, WatchSubscription, NotificationPreference, IntegrationConnection, AuditChange. Suggested stable object IDs and timestamps are necessary to avoid duplicate actions.

**SourceCapture** is an immutable origin after save (new revisions are separate). AI structured proposals reference exact source spans, with confidence and provenance. The user edits/accepts/rejects; resulting items carry linked source IDs and accepted decision IDs. A proposed web price is evidence with retrieval time and original source, not a universal current price. External calendar providers use provider IDs, tenant/user scope, idempotent write keys and conflict history. Task due date is not the same as ScheduleBlock start time.

### 7.1 Offline and resilience
Persist text locally first. Persist voice recordings to durable app-owned storage before marking saved. AI transcription, search and cloud sync are queued with explicit online dependency and retry/failed states. No fake "completed" spinner. Users can re-open the raw content while offline. Conflict policies need explicit user-facing choices for external calendars and edited notes.

### 7.2 Privacy and permissions
Microphone on active record request; photos/files on user share/attach; location only for a local result and with a denied path; notifications on first relevant reminder/focus trigger; calendar connections with scoped consent. **Trust Mode** means optional bounded low-risk AI organizational automation, not an encryption/security switch. No autonomous purchases, bookings, messages, credentials handling or consequential external writes without separate user confirmation. Never claim specific end-to-end encryption, training-use policy or security score absent verification.

## 8. Five priority screen systems for detailed design
The requested five modules comprise **43 detailed primary screen definitions** within the 80-screen app:
- **NOTE 8:** notes library, rich note detail, rich editor, ideas collection, idea detail, original-audio/transcript timeline, related items/backlinks and global search.
- **CAL 7:** calendar overview, day agenda, event draft/detail, create/edit event, reminder composer, calendar provider connection and sync-conflict review.
- **WEB 8:** user-triggered search, results sheet, in-app reader, clip/highlight, references gallery, comparisons, evidence-based synthesis and watched items.
- **FOCUS 11:** timer setup, active timer, minimized persistent timer, pause, completion, interruption capture, break choice, stretching, breathing, meditation library and meditation + immersive motion player. Immersive motion is a full-screen **mode/state of FOCUS-11**, not an extra screen; FOCUS-03 preserves the existing minimized timer.
- **INS 9:** insights dashboard, weekly review, goal progress, profile/account plan, appearance/accessibility, notification filtering, Trust Mode permissions, integrations and privacy/export/security.

Each gets visual anatomy, scroll semantics, entry transition, touch/gesture behavior, sheets, AI evidence, edge states, reduced-motion alternatives, acceptance test and a one-screen image-generation brief in the companion documents.

## 9. Focus and recovery is a first-class loop, not an appendix
A Pomodoro session is launched from a task, note or Focus tab and records a specific originating item. The analog white clock is the hero: interior minute ticks, radial progress, center digits and simple pause. Options include 25-minute classic, 50-minute deeper focus, custom and free-flow. The user can pause, minimize, capture a distraction and resume. Lock/background/relaunch must not create time drift or duplicate sessions. Session completion opens a genuine logged outcome; task completion remains an independent explicit action.

A break sheet offers breathing, stretching or meditation (skippable). A meditation player has content manifest `meditation-id → user-authorized MP3 → unique customized motion GIF / optimized motion media → static poster → cue map`. The user intends to supply MP3s; matching visual motion is future user-reviewed creative work. Every meditation can have unique art without creating a new app route. Audio playback, loop, pause/seek, interruptions and reduced-motion fallbacks must be verified. **Work minutes and meditation minutes remain separate metrics.** The immersive scene may hide app chrome temporarily but always supports tap-to-reveal controls and an obvious Exit.

## 10. Web research and integrations
Search from a particular note preserves its context: open search sheet, refine intent, show 3–5 genuine sourced results, attach/open/clip, summarize with source links, extract proposed tasks/calendar items and return to same original note/scroll position. User approval precedes attached references and externally consequential actions. Clip from share sheet is a parallel input. In-app webview cannot assume unrestricted access to arbitrary pages, cookie state or cross-site content; failed extraction has a URL/manual text fallback. Background price/news/availability watch is opt-in with a specified check interval and notification constraints, not always-on scraping.

## 11. Image-generation pipeline
Use the **separate** mobile-design-orchestrator repository for mobile geometry (not as a SUPERDORO dependency or code package). Its process: existing product brief → canonical numbered screen map → three visual anchors → establish consistent style → one portrait output **per screen** → inspect typography, spacing and contents → approve revisions → export prompt+image+layer notes. As the user already supplied a visual direction, the recommended three anchor screens for these 43 are NOTE-02 rich detail, FOCUS-02 active precision timer and WEB-02 search results in-context. Preserve the exact S mark only if the approved asset is available; otherwise explicitly label any temporary logo approximation in generated art.

Every prompt must name screen ID, concrete user task, required labels/controls, parent/child route, precise layout hierarchy, visual and motion hero state and reduced-motion fallback. **One image = one screen**; never use twelve miniature mockups on one canvas as implementation references. Build dark and light from the same tokens. Prompt pack: [SCREEN-IMAGE-PROMPTS.md](SCREEN-IMAGE-PROMPTS.md).

## 12. Paper MCP design process
Paper Desktop's official MCP documentation is [paper.design/docs/mcp](https://paper.design/docs/mcp). Paper MCP can read/write the **currently open** Paper file from a connected agent; it is not available as an executable connection in this current chat. Official setup currently uses the local Paper CLI `paper mcp` or the Paper Desktop agent installer. It can create editable frames and design tokens. **Do not commit guessed machine-specific executable paths or assert a connection is installed.**

**In the local Claude Code/Codex environment when connected:**
1. Open Paper Desktop with a dedicated SUPERDORO file; verify the correct open file through an available read-only/basic-info MCP call.
2. Import/create semantic light and dark tokens, type, spacing and component families using the visual spec; avoid hardcoded unrelated surface colors.
3. Create one named portrait artboard per canonical ID with consistent native mobile frame dimensions and linked component rules.
4. Use approved ChatGPT image-generation concept as a **reference**, then build actual editable layers and correct type/hit areas in Paper. Do not assume the PNG becomes editable UI.
5. Annotate transitions, overlay states, scroll/touch physics, fixed/sticky elements, motion primitive IDs, and reduced-motion.
6. Render/capture frames for visual comparison against mobile rules and approved anchors; iterate.
7. Hand off approved frames/tokens to the implementation harness; verify native implementation visually and on-device.

A detailed setup, verification, fallback and design-layer contract is in [MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md). The installed availability of Paper is a **preflight check**, not a presumed fact.

## 13. Definition of a complete design and complete build
**Design-ready screen:** ID, parent/next routes, goal, content and sample data, appearance, scrolling/sticky behavior, all touch states, loading/empty/error/offline/permission paths, notes on AI/source provenance, light/dark references, motion storyboard and reduced-motion alternative, image prompt and approval status.

**Implementation-ready:** editable design frame/verified screenshot, tokens and reusable component mapping, state machine, data contract, performance budget, accessibility labels and acceptance steps.

**Functionally complete:** user workflow operates with real persistence, back-stack state, correctly timed transitions, actual services where claimed, full error handling and physical-device evidence. Generated artwork, spec prose and a Paper file by themselves do not qualify.

## 14. Deliverables and ownership
- **80-screen source inventory:** [SCREEN-INVENTORY.md](SCREEN-INVENTORY.md)
- **43 detailed screen UX and scroll animation specs:** [DETAILED-SCREEN-MOTION-UX.md](DETAILED-SCREEN-MOTION-UX.md)
- **37 reusable motion primitives:** [MOTION-SYSTEM.md](MOTION-SYSTEM.md)
- **105 reference ideas:** [REFERENCE-MOTION-LIBRARY.md](REFERENCE-MOTION-LIBRARY.md)
- **43 image-generation-ready briefs:** [SCREEN-IMAGE-PROMPTS.md](SCREEN-IMAGE-PROMPTS.md)
- **External mobile design + Paper bridge:** [MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md)
- **MP3/GIF media and original recording data:** [MEDITATION-MEDIA.md](MEDITATION-MEDIA.md)
- **Visual identity/assets status:** [DESIGN.md](DESIGN.md), [ASSET-REGISTER.md](ASSET-REGISTER.md)
- **Engineering execution/QA:** [BACKLOG.md](BACKLOG.md), [USER-JOURNEYS.md](USER-JOURNEYS.md), [STATUS.md](../STATUS.md)

## 15. Decisions and risks to protect
- Beautiful animations can cause scroll jank, battery drain, lost accessibility and blocked inputs. Build one meaningful motion idea at a time, cancel correctly and benchmark low-end Android and iOS.
- Generated mockups can be visually persuasive but structurally wrong (fake phone status bars, unsafe area, overlapping keyboard, tiny hit targets). The mobile-design-orchestrator constraints and editable Paper frames correct these shortcomings.
- A more comprehensive first build increases integration risk; keep the *complete scope* but release internally in verified vertical slices. Do not confuse scope with simultaneous implementation.
- Unverified source content can produce fake prices, reviews, times, security claims or AI output; always distinguish actual evidence from presentation samples.
- The full-screen meditation experiences require actual user MP3s, approved visual assets and tested device media lifecycle. Do not declare them ready prematurely.

**Product success criterion:** a user speaks a messy thought, sees exactly what SUPERDORO extracted, approves a linked task, collects trustworthy references without losing their place, schedules and completes a timed focus session, takes an optional audiovisual break, and returns to the work. The entire experience feels like one coherent application in both light and dark modes.
