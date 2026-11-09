# SUPERDORO — Focus & Recovery: native motion, precision clock and custom meditation media
**Scope:** FOCUS-01…11, eleven canonical screens. **Status:** design specification, user MP3/GIF assets not yet supplied/approved. The user-requested “immersive motion” is the full-screen player mode of FOCUS-11; FOCUS-03 remains essential minimized persistent timer.

## Focus engine invariants
- Time must be derived from persisted timestamps and pause intervals, and reconciled after app background/kill/restart. Animations follow state; they never determine elapsed time.
- The user's preferred **white analog timer with interior tick marks** anchors setup and active focus. Dark mode preserves the same track/tick geometry.
- One active focus session links to an exact task/note ID and has a lifecycle: idle → active → paused/minimized/interrupted → resumed or completed/ended early.
- End of focus never automatically completes the task. Break/meditation minutes are separately recorded.
- React Native animation approach is proposed, not installed: Reanimated for timing/gesture, Skia/vector for ring, native audio service for MP3, an approved GIF or optimized loop/poster for meditation.
- Audio previews are silent until explicitly requested. No unlicensed content, invented track duration or fictitious personalized recommendation.
- No effect hides Pause, Exit, Save thought or real timer status. Reduced Motion favors static visual state with readable time, and can disable all decorative photo/scene movement.

### FOCUS-01 · Timer setup

**Human outcome.** Choose 25-minute classic, 50-minute deep work, free-flow or custom; see linked source task, estimated effort and optional sound; user explicitly taps Start.

**Screen architecture and appearance.** White tactile clock with tick marks INSIDE the circular track, dark dial counterpart, segmented presets and one big thumb-reachable Start. Timer should fit without cropping on 360dp screens.

**Motion, loops, timing and specific triggers.** Dial stroke draws once M25 when visible, preset selection smoothly morphs ring and rolling digits M26/M27; button haptic bounce M12; no continuous attention-pulse loop.

**Scroll physics / sticky controls.** Setup may scroll modestly if keyboard/custom duration settings expand. Clock remains within responsive top region, Start CTA anchored above bottom safe area; tap duration does not scroll page unexpectedly.

**Actions, gestures, destination and return continuity.** Start creates persisted session with id/start monotonic+wallclock markers then navigates FOCUS-02; task change chooser opens short sheet; presets keep current state unless user confirms reset.

**Failure, offline, accessibility and actual source behavior.** Clamping custom duration, paused/resume contract, OS background accuracy, 200% text and reduced motion; active session never accidentally overwritten by preset tapping.

**One-shot image/Paper keyframe.** Light white dial with fine inner minute ticks, 25/50/free/custom controls, linked task and bold Start Focus.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-02 · Active focus session

**Human outcome.** Show accurate elapsed/remaining time, the originating task, pause/end/minimize, with optional capture distraction control. This is the signature work instrument.

**Screen architecture and appearance.** Dark and light theme, single huge precision analog ring with interior ticks and central time, tiny linked task text, obvious Pause and small End/Minimize. No bouncing neon ticker.

**Motion, loops, timing and specific triggers.** M25 real-time radial sweep/inner tick emphasis, M26 digit update, no spring on every second; subtle fixed ring glow only as active-state feedback. Breathing or particle effects are OFF during work.

**Scroll physics / sticky controls.** Nearly no vertical scrolling in the default phone height; on smaller screens content scrolls below stable compact timer. Header safe area; ring never under notch; short swipe-down only if clearly labeled minimize and no conflict with system gesture.

**Actions, gestures, destination and return continuity.** Pause→FOCUS-04, end→FOCUS-05 confirmation, minimize→FOCUS-03, capture distraction→FOCUS-06; tap linked task shows detail overlay not session termination.

**Failure, offline, accessibility and actual source behavior.** Timer persists timestamps and paused intervals, not animation-frame count; when app backgrounded/reopened recompute accurately; no forced audio or keep-awake; accessibility time announced periodically not every frame.

**One-shot image/Paper keyframe.** Black/charcoal or light precision timer with iconic inner tick marks, accurate 24:12 example clearly illustrative and Pause control.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-03 · Minimized/persistent timer

**Human outcome.** Continue focus while reading/researching without losing time or the source task. Show compact progress in app, OS notification or Live Activity only where supported.

**Screen architecture and appearance.** Floating dark pill with time, active state and pause/return controls, within app safe area; other content remains readable. Provider-specific device UI is not forged inside in-app mockups.

**Motion, loops, timing and specific triggers.** M35 pill shared-element shrinks from FOCUS-02 ring into dock over 350–550ms and expands back; ring arc remains calm, updates from real session clock.

**Scroll physics / sticky controls.** Pill is visually pinned outside scrolling content, not inside virtualized list. On scroll it may tuck toward bottom edge without hiding key CTA; large text may collapse to time-only with accessible label.

**Actions, gestures, destination and return continuity.** Tap pill→FOCUS-02; pause from pill→FOCUS-04; swipe dismissal asks End/Minimize choice, never silently discards time.

**Failure, offline, accessibility and actual source behavior.** OS background restrictions/notification permission checked; when unavailable keep in-app timer and explain limitations; React Native cannot promise universal Android side-button mapping.

**One-shot image/Paper keyframe.** Dark note detail with small anchored 'Focus 12:48' pill and content unobstructed.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-04 · Pause/resume sheet

**Human outcome.** Pause a running session and give explicit Resume, Finish early, Save thought actions without accidental completion.

**Screen architecture and appearance.** Compact bottom glass sheet over frozen timer ring; status Paused, actual time elapsed and optional reason chip; unambiguous Resume top action.

**Motion, loops, timing and specific triggers.** Ring holds fixed angle using M27; sheet M32 slides up 280–360ms; Resume reverses; optional reason chips M12; no fake session complete check.

**Scroll physics / sticky controls.** Sheet internal scroll only at huge type; backdrop ring remains frozen and cannot scroll; swipe down maps to Resume only if clearly communicated and reversible; visible close always present.

**Actions, gestures, destination and return continuity.** Resume persists pause duration; Finish early opens FOCUS-05 outcome; Capture thought opens FOCUS-06 with paused flag.

**Failure, offline, accessibility and actual source behavior.** Screen reader announces paused state; background while paused remains paused; duplicate taps idempotent; app kill recovery displays actual paused status.

**One-shot image/Paper keyframe.** Dark timer behind translucent Pause sheet with Resume and Finish early, no distracting illustrations.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-05 · Session completion and outcome

**Human outcome.** Log work elapsed honestly, then decide Done with task / Continue task / Take break / Return. Distinguish interrupted vs completed focus.

**Screen architecture and appearance.** Completion header, subtle green check arc, real minutes/sessions, linked task snapshot and deliberate next actions; no claim that task is done just because timer ended.

**Motion, loops, timing and specific triggers.** Radial completion closes M25 and M37 light rays once, tiny check draw M23; count-up M26 from actual session duration; particle burst optional, under 0.8 sec and skippable.

**Scroll physics / sticky controls.** Normally one screen view; if long outcome details, vertical scroll below summary with top key time visible. Bottom take-break CTA remains thumb reachable. No infinite confetti.

**Actions, gestures, destination and return continuity.** Tap Mark task done triggers separate task update confirmation; Take break → FOCUS-07; Continue → FOCUS-01 with preserved task link; log notes if interrupted.

**Failure, offline, accessibility and actual source behavior.** Session written exactly once, final duration accurate and persisted; no gamification scores invented; optional completed-task status not automatic.

**One-shot image/Paper keyframe.** Light completion showing true 25-minute session and linked task, with Take a break and Continue buttons.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-06 · Interruption capture

**Human outcome.** Rapidly park a thought while work timer remains correct; return to exact work state with minimal context loss.

**Screen architecture and appearance.** Tiny voice-or-text jot sheet with current timer capsule in header, 1-field composer, mic record button and Save to Notes/Task option.

**Motion, loops, timing and specific triggers.** Bottom sheet M32 rises from timer without changing ring progress; audio waveform M16 only if actually recording; save check M13 only once local persistence succeeds.

**Scroll physics / sticky controls.** Sheet itself scrolls at large font/keyboard; timer visible in compact header. Dismiss returns to FOCUS-02/03 and maintains pre-existing paused/running state; no dragging near microphone gesture.

**Actions, gestures, destination and return continuity.** Record or type, select Park as idea/task suggestion, Save; AI processing can happen after focus ends; discard confirmation if unsaved content.

**Failure, offline, accessibility and actual source behavior.** Raw thought stored offline, mic permissions just-in-time, interruptions can be saved even while network unavailable; no implicit pause unless user setting explicitly says so.

**One-shot image/Paper keyframe.** Dark low-profile interruption capture overlay on faint running timer with voice waveform, single text field and Save Thought.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-07 · Break recommendation hub

**Human outcome.** Offer optional breathing, stretching, meditation or Skip, with suggested duration based on real work session and user preference.

**Screen architecture and appearance.** Nature-tinted charcoal scene with three consistent glass cards, each with icon, duration and benefit; small session summary; no moralizing or full-screen coercion.

**Motion, loops, timing and specific triggers.** Nature background very light M04 parallax, cards stagger M07 once; selectable card lifts M12; breathe circle preview M28 optionally one quiet cycle, no autoplay sound.

**Scroll physics / sticky controls.** Vertical scroll only if cards exceed screen; sticky Skip/Back after bottom inset, no scroll trap. Preview scene stays behind and remains nonessential to legibility.

**Actions, gestures, destination and return continuity.** Breathing→FOCUS-09, Stretch→FOCUS-08, Meditate→FOCUS-10; Skip returns to original task/Today; Learn more opens short explanation sheet.

**Failure, offline, accessibility and actual source behavior.** User can disable break prompts; no medical claims; auto suggestion never starts audio or motion; reduced motion uses still nature poster.

**One-shot image/Paper keyframe.** Glass over forest dusk break selector with Breathe, Stretch and Meditate, calm green accents.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-08 · Guided stretching player

**Human outcome.** Run safe short stretch sequence (e.g. upper body or full-body) with motion demonstrating proper positions and time per step.

**Screen architecture and appearance.** Full-height instructional animation/poster with step title, remaining time, pause, skip and Next; clear iconographic body poses; easy return-to-focus option.

**Motion, loops, timing and specific triggers.** Animation M29 is per-step instructional (not random decorative motion); step progress draws M19; transition to next illustration crossfades <350ms; haptics optional on step transition.

**Scroll physics / sticky controls.** Primary view mostly non-scroll; movement details accessible in expandable scroll sheet (M32), retaining visible paused animation. Gestures not needed to control exercise; visible Next/Skip.

**Actions, gestures, destination and return continuity.** Choose sequence, play/pause, Next/back, end early, complete; resume task. Optional audio track if approved, disabled by default when no assets.

**Failure, offline, accessibility and actual source behavior.** Movement accuracy and captions reviewed, breaks can be skipped, seizure/motion sensitivity settings respected, duration honest and activity logged separately.

**One-shot image/Paper keyframe.** Light stretching experience with clear two-step sequence, user-readable pose graphic and controls.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-09 · Guided breathing player

**Human outcome.** Visual inhale/hold/exhale rhythm with adjustable pace, timer and mute; distraction-free focus reset, not a medical intervention.

**Screen architecture and appearance.** Large central orb/ring with explicit textual phase 'Inhale' and seconds, small phase progression, Play/Pause and exit. No essential information encoded only in color/scale.

**Motion, loops, timing and specific triggers.** M28 expands/contracts during actual configured breathing phases. Optional ring tick M25 shows phase time. No arbitrary cosmetic pulse; phase transitions calm, no strobe.

**Scroll physics / sticky controls.** No vertical scrolling on standard phones; dynamic text shifts controls below orb in scrollable safe content. No hidden swipe-to-leave. Full view can minimize controls but tap restores them.

**Actions, gestures, destination and return continuity.** Tap pace selector via sheet, pause, skip, sound toggle, complete; returns to prior task/break flow.

**Failure, offline, accessibility and actual source behavior.** Silent option works; Reduce Motion uses static phase text with progress timer; never sync to bodily sensors without permission/provider evidence.

**One-shot image/Paper keyframe.** Dark breathing screen with gentle mint orb, clear 'Inhale · 4s' phase and Pause.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-10 · Meditation library

**Human outcome.** Choose a user-approved track with duration, purpose and preview of custom motion art; selected meditation launches its own MP3/visual pair.

**Screen architecture and appearance.** Grid/list of meditation cards with cinematic still posters, short duration, download/offline status and honest audio availability. No generic impossible preloaded tracks.

**Motion, loops, timing and specific triggers.** Card posters may have micro parallax M04 on browse but full motion loops should NOT run in list; selected tile expands shared M31 to FOCUS-11; first rows appear M07.

**Scroll physics / sticky controls.** List scroll vertical, category chips sticky after y=48, no auto-play audio. On return from player restore category/y. Horizontal featured carousel optional if accessible arrows.

**Actions, gestures, destination and return continuity.** Select, Preview silent poster, Download where allowed, Play. Track IDs resolve through media manifest, not hardcoded screen variants.

**Failure, offline, accessibility and actual source behavior.** No audio/media assets are currently committed; show pending/demo when not supplied, permissions/licensing verified; large list virtualization and accessible card labels.

**One-shot image/Paper keyframe.** Light meditation library with three cinematic still scene cards, durations and clear Play icons; no invented MP3 titles advertised as released.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

### FOCUS-11 · Meditation + immersive motion player

**Human outcome.** Play exactly the selected MP3 alongside its own approved custom motion GIF/optimized video and poster; immersive mode is this screen's full-screen state, not screen #81.

**Screen architecture and appearance.** Artwork fills portrait canvas under legible overlay controls: track title, time, audio seek, play/pause, background/exit, caption toggle, subtle ambient frame. Match the user-supplied brand palette and media, no forced neon.

**Motion, loops, timing and specific triggers.** Unique motion art M29 loops seamlessly at lower intensity; audio seek bar M33 advances from real track timestamps; on pause freeze or dim animation based on user setting; cover→immersive crossfade M31.

**Scroll physics / sticky controls.** Immersive artwork itself should not scroll. Tap toggles controls, swipe down reveals compact player/close only if accessible visible controls also available; optional transcript/captions panel scrolls independently in a bottom sheet; no gesture that conflicts with OS back.

**Actions, gestures, destination and return continuity.** Play/pause/seek/mute, choose subtitles, minimize where OS supports, complete, return to origin, resume focus by explicit tap. Releasing player stops/unloads assets based on chosen background behavior.

**Failure, offline, accessibility and actual source behavior.** Per-meditation manifest must map real MP3/license/verified duration to distinct motion asset + reduced-motion still; GIF cannot be assumed frame-accurately synchronized to audio; interruption and background/media focus handled; focus vs meditation minutes separate.

**One-shot image/Paper keyframe.** Cinematic dark meditation visual, minimal translucent controls and exact supplied media art; when unavailable display a labeled placeholder rather than pretend finished animation.

**Verification:** test pause/resume/foreground/background and interrupted interactions, true data state, timer accuracy and battery/animation frames on low-end Android plus iOS where supported. Reduced-motion and large text retain all controls.

---

