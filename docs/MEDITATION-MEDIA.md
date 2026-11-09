# SUPERDORO — meditation audio and custom motion asset pipeline

**Status:** media slots and workflow specified; user intends to supply owned/appropriately licensed MP3s and later commission/customize motion GIFs for each meditation. **No MP3, GIF, scene pack, or synced player is yet committed or verified.** Do not invent finished audio, licensing or therapeutic effects.

## Experience architecture

The recovery system contains (1) a recommendation/break choice, (2) the meditation catalog, (3) a dedicated meditation/motion player, (4) a stretching sequence player and (5) a silent guided breathing player. The catalog and player are counted as FOCUS-10/11 in the 80-screen inventory. **Each meditation is an individual content item with its own audiovisual identity, not necessarily a new app navigation route.** This enables dozens of customized audio-plus-motion experiences without duplicating application screens.

Meditation starts only by explicit user choice or previously authorized playback preference. It can be offered after a Pomodoro, during a break, as a morning arrival or as a wind-down. **Pomodoro work minutes and meditation minutes remain separate metrics.** Completing meditation does not automatically complete the associated task or focus session.

## Per-meditation asset contract

For each entry define:

- Stable ID/slug, title, objective (e.g. arrival, recovery, grounding), duration and concise, non-clinical description.
- MP3 file name/path, attribution, provenance, owner/license permission, language, narrator, sample rate, channels, bitrate, loudness and total exact duration.
- Custom **motion GIF** ID/path and aspect ratios for portrait player / small square cover, loop point, intended cadence, color palette and any non-looping intro/outro.
- Optional higher-performance runtime motion (Rive/Lottie/Skia) or looping MP4/WebM/animated WebP alternate, and static poster for Reduce Motion, data-saving mode, or decode failure.
- Optional cue map: relative times for breathing, visual transitions, chapter markers, captions and gentle haptics. If no cue sheet, the motion is ambient and never falsely shown as tightly synced to spoken instructions.
- Display and audio behavior: offline availability, download status, play/pause/seek, background/lock-screen policy, interruption/resume, volume preference and whether voice/audio tracks may mix.
- Version number, source, review/approval state, file checksum and accessibility notes.

**Suggested repository paths once assets are supplied:** `assets/meditations/audio/<slug>.mp3`, `assets/meditations/motion/<slug>-portrait.gif`, `assets/meditations/posters/<slug>.webp`, `content/meditations/<slug>.json`, `assets/meditations/README.md`. Store large binaries through an approved size-aware strategy; avoid committing huge MP3/GIF files blindly, and use a source-of-truth asset manifest with checksums. Never use proprietary audio without permission.

## Planned starter catalog (not yet supplied)

| Proposed ID | Meditation | Proposed player scene | Audio state |
|---|---|---|---|
| MED-ARRIVAL-02 | Two-minute arrival | gentle mint horizon emerging from dark, slow atmospheric particles | MP3 pending |
| MED-RESET-05 | Five-minute reset | forest dusk with slowly drifting layered mist and halo | MP3 pending |
| MED-WINDDOWN-10 | Ten-minute wind-down | starfield/soft night landscape with long gradual light movements | MP3 pending |
| BR-SILENT | Silent guided breathing | expanding precision ring and inhale/exhale captions | no MP3 required |
| STR-UPPER-02 | Upper body reset | illustrated movement steps with progressive stroke-draw | custom instruction media pending |
| STR-FULL-02 | Full body stretch | clear sequential stretch demonstration with duration markers | custom instruction media pending |

Durations above are **proposed initial placeholders** and should be replaced by the actual MP3 metadata when supplied. Do not hard-code their lengths or claim these specific scenes are approved.

## Workflow when user supplies MP3s

1. **Ingest and audit:** verify upload opens/decodes; inspect duration, codec and peak level; identify rights/attribution and intended sequence. Never use an unverified guessed duration.
2. **Story map:** transcribe for production references if allowed; mark scene beats, breath cues and chapters; distinguish ambient visual loops from synchronized instructions.
3. **Design one custom motion concept per meditation:** choose a coherent composition in SUPERDORO's white/mint or black/glowing-green visual system; user reviews static keyframes.
4. **Generate original motion sprites or loops:** user specifically wants customized GIFs; export optimized GIFs and static fallback (optionally a more efficient MP4/animated WebP path). Avoid hard cuts at repeat boundaries; do not assume a GIF's playback time can be scrubbed precisely with MP3.
5. **Package with a manifest:** add metadata and versioned assets; mobile player loads by stable ID, not hardcoded route-specific conditions.
6. **Implement player:** explicit start; controls; audio focus/incoming-call recovery; offline buffering; seek; completion; correct elapsed meditation time.
7. **Device QA:** test audio sync perception, loops, battery/memory, background behavior, headphones, interrupted phone call, disabled sound, reduced motion, low-end device and color contrast.

## On-screen treatment

Meditation detail: small title/duration, audio thumbnail, subtle prepared-for-you label only when generated from explicit user preferences. Player: near full-screen artwork or motion loop; very restrained controls and an optional thin progress ring. Distinct visual scene per meditation, but identical controls/gestures. Show captions or transcript when available. No auto-playing previews with audio. Exit returns to the prior task or Pomodoro context; a completed break offers “Resume focus” but never automatically restarts work.

## Motion guidelines specific to media

- Breathing animation timing follows the configured inhale/hold/exhale rhythm. Provide a static text/timed alternative to movement.
- Stretching instructional movement must be clear, safe and appropriately paced; decorative motion must not obscure the actual exercise.
- User-requested GIF loops should be high-quality but mindful of file size; MP3 playback should remain reliable if animation decoding stalls.
- Preserve source audio without transformations unless authorized; never claim a meditation is scientifically therapeutic.
- Distinguish an asset that is **concepted**, **generated**, **approved**, **imported**, **implemented**, and **tested**.

## Acceptance criteria

With one authorized MP3 and matching customized motion asset, a tester can select the meditation, start audio and scene, pause/seek/replay, background/restore where supported, complete the session, see accurate separate meditation metrics, and return to the originating focus task; reduced-motion and silent modes also work. Repeat for each subsequent content item without adding a new application screen.
