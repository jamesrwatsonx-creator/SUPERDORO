# Claude Code handoff

Follow AGENTS.md and read the documents linked from README.md. James authorized preparing this repository and intends to build the application in Claude Code. The initial contents are specifications and guidance, not an existing working app.

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

The first implementation slice is capture, but the release also includes editable AI Tasks/Ideas/Calendar review, linked notes/references, Pomodoro/free-flow timers, and meditation. Keep extension points simple. Do not replace the product with a timer demo, a generic chatbot, or an autonomous assistant.

## Immediate success criterion

A user can type a note, record and replay a voice capture, close/reopen the application, and recover both. No transcription, Supabase account, or external AI key is needed to prove this first slice.

After that evidence is recorded, proceed to real transcription and reviewable suggestions following docs/BACKLOG.md; request only configuration that is actually necessary at that point.
