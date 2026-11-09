# SUPERDORO — master animation and motion design specification

**Status: design-only master reference (2026-11-09).** Covers all supplied reference-effect vocabulary plus recommended original motion patterns. No animation has yet been implemented or device-verified in the repo.

For the complete term-by-term list of externally supplied effects (including reference-only or not-for-product patterns), see [REFERENCE-MOTION-LIBRARY.md](REFERENCE-MOTION-LIBRARY.md). This ensures no animation reference is lost while keeping the actual 37 primitive system disciplined.

## North star

**Quiet surfaces, luminous interaction.** Motion should express intelligence, progress, state changes and continuity, not compete with focus. The angular geometric S (from the user's approved visual direction) is the repeated identity; preserve its geometry, do not independently regenerate the mark on every screen. Light mode uses off-white and restrained mint; dark mode uses near-black/charcoal with controlled green illumination. Glass surfaces need predictable opacity and real readable content.

The requested experience is exceptionally motion-rich: approximately 60–80 distinct motion *behaviors* across the 12 onboarding design screens, but never 60–80 simultaneous looping effects. Set strict budgets and interruption rules. Preview screenshots are hero frames, not evidence of implemented animation.

## Motion timing and constraints

| Purpose | Suggested range | Behavior |
|---|---|---|
| Tap/haptic feedback, check, toggle | 120–240 ms | immediate response |
| Chip/card/layout transform | 200–450 ms | spring only for purposeful surfaces |
| Bottom sheet / staged group | 250–500 ms | cancellable, no blank placeholders |
| Shared-element route transition | 450–800 ms | navigation must remain responsive |
| One-off splash / cinematic reward | 1–2.5 sec | skip/fast path, no repeated wait |
| Ambient float/light loop | 4–12 sec | low amplitude, pause in background/focus |
| Breathing / meditation pulse | tied to actual inhale/exhale program | not an arbitrary decorative animation |

Only animate opacity and transform by default; use caution with blur, large shadow/glow radius, masks, particles and continuous layout or 3D shader work. A device-verified fallback is required for lower-end phones and reduced-motion settings. 60 Hz stability is a target, not a guarantee. Preserve accessibility, text readability and task completion under disabled animation.

## Motion primitives catalog (stable IDs)

| ID | Animation primitive | Visual behavior, trigger and best use |
|---|---|---|
| M01 | Angular S formation and 3D ribbon turn | Intro once; geometric line draws then faceted S seats with small luminous seam sweep; spinner fallback |
| M02 | Circular iris/portal/shared logo reveal | S inner negative space expands into welcome/Today; route transition, reversible |
| M03 | Letter/word-by-word text fill | Hero headline letters brighten across line; short one-time appear, not long text |
| M04 | Layered parallax and gentle depth | Laptop hero, natural landscape and meditation backdrops; scroll or slight device tilt with permission and reduced-motion fallback |
| M05 | Floating 3D glass microcards | Task/focus/calendar confirmations drift subtly at different depths; relevant to actual product, not fabricated live events |
| M06 | Ambient particles and soft scanning light | Selective splash/hero/complete moments; never on long reading surfaces |
| M07 | Staggered fade-up/cascade | Lists, dashboard modules, cards and connection buttons appear progressively without blocking taps |
| M08 | Curtain/sticky reveal | Native adaptation of website fixed-footer reveal: a rounded welcome sheet uncovers auth; do not port CSS fixed footer literally |
| M09 | Glass surface highlight sweep | Auth CTA and featured tile reflective accent; respect contrast and motion setting |
| M10 | Animated chevron/pixel-arrow glyph | Tiny directional arrow shifts/dot cycles on primary CTAs; stops when button inactive |
| M11 | Focused-input float label / glowing border trace | Form fields, typed capture, task edit; validation stays textual |
| M12 | Toggle spring / haptic confirmation | Trust, theme, permissions and pause switches; do not imply permission granted until OS confirms |
| M13 | Loading-to-success morph/check stroke | Real backend success only; visual check strokes with measured status |
| M14 | Scroll- and selection-linked progress / indicator | Goal selection, calendar and onboarding progress; progress from real state |
| M15 | Isometric icon float / orbit microinteraction | Small illustrative icons and search; low amplitude, no ornamental overload |
| M16 | Audio-reactive recording waveform | Animated from real microphone level when authorized; simulated state clearly labelled in walkthrough |
| M17 | Waveform scrubbing/seek marker | Audio playback and synchronized transcript; stable seeking, accessible controls |
| M18 | Typewriter or skeleton-to-content resolve | Actual transcription streaming/AI result reveal; avoid meaningless fake typing |
| M19 | Semantic source-to-output line draw | Evidence/source phrases connect to tasks, ideas, calendar; data-driven branches |
| M20 | Text/particle clustering and extraction | Raw dump resolves into structured objects; motion mirrors actual extraction result |
| M21 | Spatial three-category reflow | Tasks/Ideas/Calendar stack and reorder with preserve-origin indicators |
| M22 | Review swipe deck / swipe-to-confirm | Swipe left/right with visible accept/reject controls, cancellation and undo |
| M23 | Check draw-on + restrained sparkle burst | Accepted review, completed task, completed focus; never equate a session with task completion |
| M24 | Layout reordering/shared-item flight | Accepted card moves to destination; discarded cards safely slide away |
| M25 | Precision timer radial progress sweep | Smooth ring with **inner tick marks**; correct persisted duration and resumption |
| M26 | Odometer/count-up/count-down digits | Timer, statistics, progress; numbers reflect real records, not fictitious achievements |
| M27 | Dial/ring morph and pause hold | 25/50/custom/free flow; smoothly reconfigure display without resetting active session unexpectedly |
| M28 | Breath-synchronized scale and wave | Guided inhale/hold/exhale and stretching reset cards; medically neutral copy |
| M29 | Landscape/meditation scene ambient loop | Custom scene per meditation with MP3 synchronization; GIF or alternative motion asset per media manifest |
| M30 | Theme crossfade / semantic color shift | Full theme change with color and surface tokens; never hide content during morph |
| M31 | Shared-element overlay/reveal | Item expands into edit/detail or controls slide into sheets; preserves context |
| M32 | Reversible slide-up sheet / collapsible section | Search, research, references, note specs, quick capture, pause; modal accessibility and back behavior |
| M33 | Scrub crosshair / slider and data tooltips | Audio timeline, research comparisons and insights charts; no fake market quote ticks |
| M34 | Bounded loading/scan-ring | Real processing/queue status; no infinite optimistic spinner or implied completion |
| M35 | Persistent pill control / blur strip | Compact timer or quick capture UI; progressive blur only if low-cost and legible |
| M36 | Data count-up, trace-on chart and period shift | Insights and goal progress, sourced from actual data and proper zero state |
| M37 | Milestone badge unlock / radial rays | Optional celebration, single trigger and skip; no manufactured streaks or coercive gamification |

## Supplied inspiration effects and correct adaptation

**Web-template effects:** floating capsule navbar becomes a persistent pill control or compact tab affordance; progressive backdrop blur is allowed only in small overlays; headline drift and per-letter scroll reveal are reserved for intro/editorial sections, not core task lists; slow hero parallax is permitted. Fixed/footer-curtain reveal maps to ONB-02→03 only. Fade-up, stagger, marquee and ticker may be used for demonstrations, but *never* continuously scrolling crucial information. A rotating digital brain/engine, inference ring and animated capability icons are optional illustrations, not core progress truth. A native sheet must never reproduce browser chrome or Safari/Chrome tapping glitches.

**Mascot/physics effects:** spring mascot arrival, idle breathing, mood state machines, drop/bounce props and object physics can support a future optional mascot system. No mascot is currently approved for the SUPERDORO identity, so do not introduce one during onboarding implementation. Liquid fill and sequential-layer assembly can be used for an optional metaphorical breath/wellness scene, not task saving. Badge Y-axis flip, sparkle burst and radial rays should be reserved for real milestones.

**Advanced motion:** orbiting avatars, map-to-globe projection morph, continuous macro-to-micro zoom, voxel icon parallax, rotating glass engine, 3D isometric tiles, background scroll-color shifts, sticky stacking cards, Tinder card swipe, Duolingo-style journey maps, dynamic count-up finance dashboards, scrubbable charts, and hidden easter-egg sprite motion are documented ideas, not mandatory app UI. Use only when semantically appropriate; SUPERDORO is neither a social map nor a trading app. Website GSAP/Lenis and Framer scroll effects do not translate one-to-one to native screens.

**Loading and transition discipline:** avoid placeholder cards that appear blank when scrolled fast. Render content first, then progressively enhance with motion. Avoid screen-wide infinite tickers, constant large glows, auto-playing audio, looping card rearrangements and multiple competing pulsing buttons.

## 12-screen onboarding motion direction

| Screen | Hero motion and secondary feedback | Transition |
|---|---|---|
| ONB-01 | S stroke assembly, green seam sweep, wordmark fill | logo iris expands to hero |
| ONB-02 | laptop depth parallax, four floating linked-work microcards, headline reveal | rounded hero curtain lifts to sign-in |
| ONB-03 | auth panel spring, stagger provider cards, shimmering selected CTA | selected provider expands into next state |
| ONB-04 | field trace, floating labels, checked validation | successful verification compresses into next card |
| ONB-05 | goal cards cascade, isometric float, selected tile lifts/check draws | goals shrink to semantic tokens |
| ONB-06 | real/simulated-labelled waveform, mic orb pulse, transcribed text arrival | audio streams converge into extraction |
| ONB-07 | source phrases connect via animated lines to Tasks/Ideas/Calendar | category stack becomes review |
| ONB-08 | swipeable reviews, check draw, outcome count-up and undo | approved cards fly to destination |
| ONB-09 | analog tick ring draws in, preset changes ring length, digits roll | timer collapses to workspace chip |
| ONB-10 | nature parallax, breathe/stretch mini-previews, glass selector | chosen preview expands as portal |
| ONB-11 | shield stroke, reactive Trust switch, light/dark morph, preview of automation boundaries | settings converge into S |
| ONB-12 | S brightens, Today modules cascade, restrained success sparkle | preview expands into real Today |

These are *creative storyboards*, not mandatory 12-step blocking onboarding. Allow skip/return; test users should reach usable capture quickly.

## Route-level patterns outside onboarding

- **Capture:** audio waveforms synchronized to real audio and transcript; automatic classification should visually preserve traceability between input and outputs.
- **Notes/Tasks:** modest reveal of contextual chips, reference cards with linked provenance, quick bottom sheets, atomic accepted-action feedback; avoid glow around each list item.
- **Calendar:** smooth day/week slide, drag-preview of a time block, explicit confirmation and conflict highlights; time interpretation must not be hidden by transitions.
- **Web:** research results sheet rises over existing note, card attach snaps into references, in-app reader returns to exact scroll position; links never claimed verified unless fetched.
- **Focus:** progress ring + inner ticks are hero; active timer is quieter than onboarding, no forced 3D or distracting animation. On break, sound and animation are optional and user-controlled.
- **Reset:** each meditation has its own themed scene and sourced audio; animation loop must not dictate duration if GIF loops independently.
- **Insights:** count-up and chart trace on entry once, with actual data. When empty, show honest blank state.

## Native engineering implementation

Proposed stack, subject to verified compatibility: React Native + Expo + TypeScript; Reanimated + Gesture Handler for gestures/transforms/shared elements, Skia for precision ring/effects, Rive for optional state-machine artwork, Lottie for compact prebuilt assets. Meditation GIF/animated WebP may be used as content; for long, high-quality looping scenes consider local MP4 with proper licensing/performance and a still-image reduced-motion fallback. Do not assume Framer Motion, GSAP ScrollTrigger, Lenis or DOM CSS translate to React Native. The motion engine must observe app foreground state, device capability, battery settings and Reduce Motion.

Required performance checks: actual Android device first, iOS where possible; dropped-frame inspection, battery/heat on continuous timers, memory during MP3+animation playback, fast-scroll content visibility, text scaling, touch response under animation, screen readers, reduced motion, rotation/resize and app background/resume. For every motion record fallback and verify UI remains fully usable without animation.

## Review gate

A motion is approved when its source state, trigger, destination state, cancellation/interruption, reduced-motion path, visual token, performance budget and device-verification result are documented. Never count a generated mockup or MP4 of an imagined interaction as functioning app code.
