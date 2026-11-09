# Claude Code handoff

Follow AGENTS.md and read all documents linked from README.md, notably the complete 80-screen inventory, motion master, exhaustive animation reference catalog, meditation media pipeline, journeys and status. James authorized preparing this repository and intends to build the application in Claude Code. The initial contents are specifications and guidance, not an existing working app.

## First implementation task

1. Inspect the repository, STATUS.md, and any new changes before writing.
2. Use the proposed Expo/React Native/TypeScript direction unless actual evidence requires a change; document the selected compatible versions.
3. Initialize a minimal runnable mobile app, reproducible lockfile, type checking, and verified setup/run instructions. Design for Android-first validation and both themes.
4. Implement typed capture and durable local note persistence. Original input survives editing and relaunch.
5. Implement user-started voice recording, stop, durable save, replay, and recovery. Denied microphone access leaves typed capture working. Do not require cloud credentials for this stage.
6. Represent local capture/processing states honestly. AI review is a later milestone; do not pretend transcription is connected or fill the library with unlabeled sample content.
7. Run meaningful available checks. If physical-device execution is unavailable, leave microphone, audio interruption, and relaunch acceptance explicitly unverified with exact test steps.
8. Update STATUS.md, docs/BACKLOG.md, and README setup commands. Report what changed and the next unverified milestone.

## Preserve the complete product

The initial full product build contains **80 planned screen destinations** in nine systems (12 ONB, 8 CAP, 7 DAY, 10 TASK, 8 NOTE, 7 CAL, 8 WEB, 11 FOCUS, 9 INS). The first implementation slice is capture, but the release also includes editable AI Tasks/Ideas/Calendar review, linked notes/references, projects, rich web research, calendar, Today planning, Pomodoro/free-flow timers, meditation MP3 + custom motion GIFs, insights and privacy. Keep extension points simple. Do not replace the product with a timer demo, a generic chatbot, or an autonomous assistant.

## Immediate success criterion

A user can type a note, record and replay a voice capture, close/reopen the application, and recover both. No transcription, Supabase account, or external AI key is needed to prove this first slice.

After that evidence is recorded, proceed to real transcription and reviewable suggestions following docs/BACKLOG.md; request only configuration that is actually necessary at that point.

## Visual and motion implementation protocol

Before building account/onboarding or other screens, read docs/SCREEN-INVENTORY.md (IDs/composition), docs/DESIGN.md (tokens/layout), docs/MOTION-SYSTEM.md (M01–M37), docs/ASSET-REGISTER.md (approved vs missing assets) and docs/MEDITATION-MEDIA.md (audio/GIF contract). User wants cinematic but interruptible animations; preserve a quiet active-focus mode. Treat generated screenshots as design references, not proof of functionality. Use exact approved geometric S asset only after actual import; currently no master image is committed. Build a reusable motion and component system with reduced-motion fallback and real Android performance testing. Meditation tracks and GIFs are pending user supply. Do not invent them, claim them present or mistake separate media content for extra nav screens.

## Mandatory pre-design preflight — external mobile design and Paper MCP

Read docs/COMPLETE-PRODUCT-OVERVIEW.md, docs/MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md, docs/DETAILED-SCREEN-MOTION-UX.md and docs/SCREEN-IMAGE-PROMPTS.md before rendering or implementing any of NOTE/CAL/WEB/FOCUS/INS. The *separate* user repository `jamesrwatsonx-creator/mobile-design-orchestrator` is the mobile layout/inspiration workflow source, pinned at `4d88a488ed78ad7b1bec503e4180abccac338af5`; obey its layout rules without altering that repository. Apply 8dp rhythm, 16–24dp margins, 44–48dp controls, native safe areas, realistic content density and one image per screen.

Paper design MCP is **optional and must be actually connected**: follow official https://paper.design/docs/mcp in Paper Desktop; verify a Paper server/active file using only currently advertised tools. Ask permission to install/connect locally as necessary. If disconnected, produce image prompts/static references and label editable Paper handoff pending; never claim to have created Paper file, frame or link. In an authorized connected local session create semantic tokens and editable 393×852 reference frames, annotating each Mxx trigger/scroll contract and Reduce Motion state. No machine-dependent executable path is guessed/committed.

The newly documented 43 screens are **design specs**, not 43 implemented routes, not 43 finished images and not MP3/GIF assets. Retain 80 total app screen definitions. Test every real interaction, including scroll restoration, child sheet return, calendar write approval, background timer accuracy, recording durability, and provider failure paths.
