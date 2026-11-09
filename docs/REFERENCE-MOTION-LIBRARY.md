# SUPERDORO — supplied animation reference catalog

**Purpose:** preserve **every motion idea and named family from the supplied reference notes**, not just effects selected for immediate implementation. Cross-reference [MOTION-SYSTEM.md](MOTION-SYSTEM.md) for the 37 reusable in-app primitives and [SCREEN-INVENTORY.md](SCREEN-INVENTORY.md) for 80 screen mappings.

**Status:** concept/reference only. The user supplied textual descriptions of multiple Framer templates and mobile demo clips. No third-party implementation or exact footage is included here. A label of CORE means part of proposed SUPERDORO interaction language, **not** implemented code. CONTEXT means selectively appropriate; REFERENCE means saved as inspiration but not required for this productivity app. The named tool examples in those descriptions (Framer/GSAP/Lenis/Flutter/SwiftUI/Rive/Lottie/Reanimated) are *possible implementations*, not installed stack dependencies.

**105 named animation/interaction references** across 7 source families. Closely related entries intentionally remain separately searchable so the user's original vocabulary is not lost. The 37 Mxx identifiers consolidate these concepts into reusable primitives and the animation *behavior count* is not a screen count.

## Spartan AI / Framer reference

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-001 | Fixed footer / curtain reveal | ONB-02→ONB-03 | M08 | ADAPT | Rounded hero uncovers auth; do not literally pin a web footer in native app |
| REF-002 | Floating pill navigation | timer mini-pill, optional shell | M35 | CORE | Pinned compact controls with clear hit area |
| REF-003 | Progressive blur band | top bar/sheets | M35 | CONTEXT | Only if contrast and GPU budget pass |
| REF-004 | Scroll-linked letter fill | editorial onboarding headline | M03 | CONTEXT | Short title, not reading paragraphs |
| REF-005 | Oversized drifting headline | onboarding hero | M03 | CONTEXT | Do not crop controls or accessibly relevant text |
| REF-006 | Hero image parallax | laptop and recovery photo | M04 | CORE | Light tilt/scroll depth |
| REF-007 | Appear fade-up | general UI | M07 | CORE | Initial list animation never hides actual content during fast scroll |
| REF-008 | Staggered fade/cascade | cards, options, logos | M07 | CORE | Small delays; input immediately works |
| REF-009 | Number count-up with easing | real focus insights | M26/M36 | CONTEXT | Never invent metrics |
| REF-010 | Continuous logo marquee/ticker | marketing illustration | M15 | REFERENCE | Not on work surfaces |
| REF-011 | Announcement/news ticker | optional marketing screen | M15 | REFERENCE | Avoid always-moving critical information |
| REF-012 | Cycling pixel arrow chip | primary CTA | M10 | CONTEXT | Stops once tapped or deactivated |
| REF-013 | Rotating glass digital brain engine | AI-organize hero | M01/M20 | REFERENCE | Could be optional intro illustration; expensive 3D |
| REF-014 | Glitch / scan-line overlay | logo cinematic only | M06 | REFERENCE | Exclude from transcription and accessibility text |
| REF-015 | Inference tick dial sweep | focus ring and processing | M25/M34 | CORE | Real timer/processing states |
| REF-016 | Oscillating magnifying glass | search affordance | M15 | CONTEXT | Low amplitude only |
| REF-017 | Orbiting dot on a target | goals/AI illustration | M15 | CONTEXT | Not ongoing distraction |
| REF-018 | Animated mixer sliders | preferences example | M12 | CONTEXT | Only on interactive preview |
| REF-019 | Cycling language-code window | AI multilingual preview | M18 | REFERENCE | Only for implemented language support |
| REF-020 | 3D wireframe star orientation | splash decorative idea | M01 | REFERENCE | Not required |
| REF-021 | Static isometric logo tiles | visual reference only | none | REFERENCE | Do not label a static tile as motion |
| REF-022 | Lightbox overlay / fade close | reader and reference preview | M32 | CORE | Native modal fades with reliable back and z-order |
| REF-023 | Browser chrome collapse | native behavior reference | none | REFERENCE | Do not implement fake browser chrome |

## Paywall, onboarding, and motion character reference

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-024 | Sky gradient with parallax clouds | recovery hero | M04 | CONTEXT | Gentle movement, avoid battery drain |
| REF-025 | Mascot spring-overshoot entrance | future mascot, if approved | M07 | REFERENCE | No mascot identity approved yet |
| REF-026 | Mascot idle breathing/blinking | future optional mascot | M28 | REFERENCE | Use Rive state machine only if requested |
| REF-027 | Progressive timeline disclosure | onboarding and task provenance | M19 | CONTEXT | Reveal real steps |
| REF-028 | Self-drawing connector / stroke line | AI categorization | M19 | CORE | Link source to output |
| REF-029 | Pulsing primary CTA | onboarding hero | M09 | CONTEXT | One subtle pulse, not endless attention bait |
| REF-030 | Floating illustrated objects spring-pop | goals/onboarding | M05/M07 | CONTEXT | Physical yet controlled |
| REF-031 | Gravity drop and bounce | optional illustrative reveal | M07 | REFERENCE | No irrelevant physics inside workflow |
| REF-032 | Ambient object float | floating reference cards | M05 | CORE | Suspend during focus |
| REF-033 | Button slide-up and fade | onboarding | M07 | CORE | Fast and cancellable |
| REF-034 | List scroll-linked parallax | onboarding example | M04 | REFERENCE | Avoid parallax in dense task lists |
| REF-035 | Liquid pour / fill simulation | optional breathing metaphor | M28 | REFERENCE | Use only if it clarifies action |
| REF-036 | Sequenced layer-build animation | brain dump -> structure | M20/M21 | CORE | Show source-to-output order |
| REF-037 | Crossfade label ticker | mode/suggestion label | M18 | CONTEXT | Manual/real mode changes; not arbitrary rotation |
| REF-038 | Mascot state-driven mood morph | future optional companion | none | REFERENCE | Requires user-approved character |
| REF-039 | Radial gauge progress sweep | timer and onboarding | M25 | CORE | Data grounded |
| REF-040 | Loading dot morphs to success check | saved/review/processing | M13 | CORE | Only after confirmed completion |
| REF-041 | Checkmark draw-on | accepted suggestion | M23 | CORE | Clear non-color status label |
| REF-042 | Snap-scrolling carousel | meditation catalog/onboarding concepts | M32 | CONTEXT | Snap to items; native accessibility |
| REF-043 | Coverflow focus scale | small carousel preview | M31 | CONTEXT | Do not hide selected label |

## Achievement, cinematic site and editorial reference

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-044 | Achievement unlock slide-up modal | completed focus/milestone | M37 | CONTEXT | Only real milestone, opt-out |
| REF-045 | 3D Y-axis badge turntable flip | achievement icon | M37 | REFERENCE | Respect motion sensitivity |
| REF-046 | Radial light rays | completion moment | M37 | CONTEXT | Short, subtle |
| REF-047 | Particle spark/confetti burst | review confirm/session finish | M23/M37 | CONTEXT | Low frequency |
| REF-048 | Ambient border glow pulse | primary active control | M09 | CORE | Low-amplitude soft halo |
| REF-049 | Skeleton-to-content / placeholder resolve | AI search result waiting | M18 | CORE | No fake completion and no slow blank cards |
| REF-050 | Typewriter headline reveal | onboarding messaging | M18 | CONTEXT | Not long transcripts unless actual streaming |
| REF-051 | Scroll-linked word-by-word reveal | welcome editorial text | M03 | CONTEXT | Readable without motion |
| REF-052 | 3D voxel/isometric icons with parallax | future marketing splash | M15 | REFERENCE | Simplified in native |
| REF-053 | Sticky stacking cards | onboarding value proposition | M07 | CONTEXT | Only controlled, no trapping scroll |
| REF-054 | Rolling odometer stats | verified insights | M26/M36 | CORE | Accessible numeric alternative |
| REF-055 | Background color shift on scroll | light/dark editorial intro | M30 | CONTEXT | No flicker or illegible transitions |
| REF-056 | Infinite logo marquee | external promo only | none | REFERENCE | Avoid arbitrary product logos in app |
| REF-057 | Swipeable horizontal card carousel | meditation and recommendations | M32 | CONTEXT | Accessible previous/next alternative |
| REF-058 | Collapsing browser navigation chrome | OS/browser behavior | none | REFERENCE | Not a custom animation |

## Orbit onboarding / spatial navigation reference

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-059 | Pulsing swipe-up cue bubble | optional introduction | M09 | CONTEXT | Can dismiss; never required to discover gesture |
| REF-060 | Iris/circular mask portal | S-to-app transition | M02 | CORE | Signature brand reveal |
| REF-061 | Continuous macro-to-micro zoom fly-through | optional onboarding transition | M02 | REFERENCE | Only if story and frame rate justify |
| REF-062 | Map-to-globe projection morph | not a core product need | none | REFERENCE | Do not force map metaphor onto productivity |
| REF-063 | Orbiting avatar/pin radial layout | not a core product need | none | REFERENCE | No multiplayer map in this product |
| REF-064 | Tap avatar shared-element zoom | note/item detail analogy | M31 | CONTEXT | Use shared element for actual note card |

## Welcome, quest and game microinteractions

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-065 | Tinder-style swipeable card stack | review queue | M22 | CORE | Reject/accept with explicit buttons alternative |
| REF-066 | Directional swipe stamp | review card | M22 | CONTEXT | Show ACCEPT/REJECT briefly, with undo |
| REF-067 | Spring-in logo scale-pop | splash and auth | M01 | CORE | No endless breathing on logos |
| REF-068 | Checkbox completion tap bounce | tasks/subtasks | M23 | CORE | Haptic if enabled |
| REF-069 | Sparkle/check confetti feedback | completed tasks | M23 | CONTEXT | One shot |
| REF-070 | Animated list reorder | task priority and suggested cards | M24 | CORE | Preserve accessibility focus |
| REF-071 | Winding Duolingo-like journey map | future optional goal view | none | REFERENCE | Do not gamify primary productivity navigation |
| REF-072 | Node tap bounce | goal/path preview | M12 | CONTEXT | Only if pathway view implemented |
| REF-073 | Slide-up decorative cloud-edge sheet | recovery/sleep mood | M32 | REFERENCE | Can conflict with consistent glass sheet geometry |

## Four-phone motion examples

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-074 | Pixel sprite animated character | future optional easter egg | none | REFERENCE | No approved pixel-art style |
| REF-075 | Text pop / punch scale | success feedback | M23 | CONTEXT | Very brief |
| REF-076 | Hidden interaction / easter egg game state | not central | none | REFERENCE | Do not implement ahead of core product |
| REF-077 | Rolling calculator digits | timer/verified metrics | M26 | CORE | No fake precision |
| REF-078 | Swipe-to-confirm slider | high-stakes action | M22 | CONTEXT | Prefer simple buttons for routine actions |
| REF-079 | Live ticking value counter | real timer only | M26 | CORE | No simulated market or price ticks |
| REF-080 | Animated line-chart path trace | insights | M36 | CORE | Real stored data |
| REF-081 | Drag scrub crosshair and tooltip | audio and charts | M33 | CORE | Expose exact values |
| REF-082 | Balance count-up and mascot idle | inspiration only | M36 | REFERENCE | Apply count-up to focus metrics; no finance mascot |
| REF-083 | Spotlight search slide-in | global search | M32 | CORE | Return to previous context |

## General motion vocabulary and original SUPERDORO ideas

| Reference ID | Effect / motion term | SUPERDORO placement | Primitive | Use | Guidance |
|---|---|---|---|---|---|
| REF-084 | Shared-element / hero transition | notes, tasks, card->detail | M31 | CORE | Keep content identity continuity |
| REF-085 | Glow pulse / magnetic hover | active timer/CTA | M09 | CORE | Touch equivalent; hover not assumed on phones |
| REF-086 | Haptic synchronized press bounce | buttons/toggles | M12 | CORE | Respect OS haptic settings |
| REF-087 | Line/shape morph | S, check, ring | M01/M13/M27 | CORE | Prefer vector primitives |
| REF-088 | 3D isometric float | hero cards only | M05 | CONTEXT | No heavy perpetual gyro |
| REF-089 | Gyroscope tilt parallax | photographic intro/illustrations | M04 | CONTEXT | User setting + reduced motion fallback |
| REF-090 | Liquid fill | optional reset metaphor | M28 | REFERENCE | Not needed for app mechanics |
| REF-091 | Spring scale/pop | auth and goals | M07 | CORE | Limited overshoot |
| REF-092 | Swipe-card dismissal | review items | M22 | CORE | Undo and accessible buttons |
| REF-093 | Scroll-linked color word reveal | welcome text | M03 | CONTEXT | No hidden essential information |
| REF-094 | Rotating clock tick-ring sweep | focus | M25 | CORE | Precise real state |
| REF-095 | Waveform synchronized audio | recording/playback | M16/M17 | CORE | Actual audio samples |
| REF-096 | Animated AI source-to-structure graph | AI organization | M19/M20/M21 | CORE | Show semantic provenance |
| REF-097 | Meditation GIF motion loop per MP3 | individual meditation | M29 | CORE | Asset/user supplied; player reusable |
| REF-098 | Breath circle rhythmic expansion | breathing player | M28 | CORE | Timing based on breath guide, not decorative |
| REF-099 | Stretch sequence movement | guided stretch | M29 | CORE | Instructional correctness first |
| REF-100 | Cross-theme surface color morph | appearance settings | M30 | CORE | Text contrast maintained |
| REF-101 | Radial session completion | task-linked timer | M25/M37 | CORE | Never implies task done |
| REF-102 | Curved note-to-reference attach flight | research | M24 | CONTEXT | Data relation preserved |
| REF-103 | Source-linked highlighting | transcript and web clips | M19 | CORE | Evidence and selection clear |
| REF-104 | Soft atmospheric nature motion | recovery | M04/M29 | CONTEXT | Audio optional, high-efficiency assets |
| REF-105 | Staged motion scene per intro (12) | account/onboarding | M01–M37 | CORE | 12 reference compositions, skippable, actual app uses routes sparingly |

## Production gates and platform translations

Framer Motion, GSAP ScrollTrigger and Lenis are web-centric; do not copy DOM/CSS prescriptions like fixed-footer z-index and scroll-linked transforms directly into React Native. Native suggestions: Reanimated + Gesture Handler for screens/gestures, Skia for precise timer ring and custom drawing, Rive state machines for future approved characters or interactive scenes, Lottie for compact decorative motion, and controlled MP3 + GIF/MP4/animated WebP players for meditation scenes. Verify package/runtime compatibility instead of assuming availability.

A rendered screen is not a working motion prototype. For each approved effect specify **trigger, initial/final state, easing, duration, interrupt/reversal behavior, audio/haptic coupling, reduced-motion equivalent, semantic evidence, and battery/frames verification**. Focus work screens should minimize animation even though splash/onboarding showcase many effects. Don't fake security, progress, achievements, source freshness, price or availability.

## Shortlist of brand-defining original interactions

1. **S awaken/portal:** angular logo assembles then expands into the welcome photography.
2. **Your focus harness floating desk:** light rounded photo with glass status microcards, single restrained depth loop.
3. **Thought -> action:** transcript source phrases draw semantic links to Task/Idea/Calendar output and reviewer decisions.
4. **Precision inner-tick clock:** bright physical-instrument-like ring, accurate persisted count, beautiful but silent progress.
5. **Review/undo:** check/stamp/fly-to-destination with source links, no irreversible organizational action.
6. **MP3 + personal motion scene:** user-supplied meditation audio paired to a distinct loop and static reduced-motion poster, returning to the original focus session.

## Design QA

Never play an animation as a substitute for loading data or a promised external action. Keep the app navigable while a sequence runs. In content-heavy screens, render content first and then enhance. Implement a “Reduce Motion / Less Glow” preference, respect OS reduce-motion, test power and memory, and ensure colors/text remain accessible in dark and light modes.
