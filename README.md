# SUPERDORO

**Voice to focus. Dump thoughts, review a plan, stay in the work.**

A voice-first mobile focus app connecting voice and typed capture, reviewable AI task/idea/calendar suggestions, linked notes, focus timers, and meditations.

## Current state

This repository contains the product and engineering handoff. It does not yet contain a runnable application, installed dependencies, a configured backend, or completed integrations. See [STATUS.md](STATUS.md) for verified progress.

## Start in Claude Code

Open this repository in Claude Code and use:

> Read CLAUDE.md, AGENTS.md, STATUS.md, docs/BUILD-BRIEF.md, docs/SCREEN-INVENTORY.md, docs/MOTION-SYSTEM.md, docs/MEDITATION-MEDIA.md, and docs/BACKLOG.md. Implement milestones 0 and 1 from docs/BACKLOG.md: establish the mobile project, then build durable typed and voice capture with replay and local recovery. Preserve all release priorities. Run available checks, state what still requires a physical device, and update STATUS.md with evidence. Do not stop after producing another plan.

The proposed stack is React Native + Expo + TypeScript, SQLite for local persistence, and Supabase for later authenticated backend work. Validate current compatible packages when scaffolding. Start local capture without requiring AI or cloud credentials.

No install or run commands are provided yet because no app scaffold or lockfile exists. Add verified commands when the project is initialized.

## Complete first-build screen scope

| Area | Screens |
|---|---:|
| Account & onboarding | 12 |
| Voice & AI capture | 8 |
| Today & planning | 7 |
| Tasks & projects | 10 |
| Notes & ideas | 8 |
| Calendar & reminders | 7 |
| Web research | 8 |
| Focus & recovery | 11 |
| Insights & settings | 9 |
| **Total planned** | **80** |

All are included in the complete first-product build. A runnable app is **not yet implemented**; these are design and implementation specifications. Screens are not the same as every UI state or individual meditation asset. See [80-screen inventory](docs/SCREEN-INVENTORY.md) and [complete journeys](docs/USER-JOURNEYS.md).

## Documents

| File | Purpose |
|---|---|
| [CLAUDE.md](CLAUDE.md) | Claude Code entry point and first task |
| [AGENTS.md](AGENTS.md) | Shared engineering rules and product invariants |
| [STATUS.md](STATUS.md) | Evidence-based completed/planned work |
| [Build brief](docs/BUILD-BRIEF.md) | Product behavior, data relationships, architecture, acceptance journey |
| [Backlog](docs/BACKLOG.md) | Dependency-ordered implementation tasks and completion gates |
| [Design direction](docs/DESIGN.md) | Confirmed visual preferences and missing assets |
| [Decisions](docs/DECISIONS.md) | Confirmed priorities, proposed defaults, open decisions |
| [Screen inventory](docs/SCREEN-INVENTORY.md) | All 80 screens, behaviors and motion references |
| [Motion system](docs/MOTION-SYSTEM.md) | 37 reusable motion primitives, 12 animated onboarding concepts |
| [Meditation media](docs/MEDITATION-MEDIA.md) | MP3-to-custom-motion-GIF pipeline, content manifest and playback QA |
| [User journeys](docs/USER-JOURNEYS.md) | End-to-end UX, safety and real-device acceptance tests |
| [Asset register](docs/ASSET-REGISTER.md) | Logo/visual sources and unimported media status |
| [Motion reference catalog](docs/REFERENCE-MOTION-LIBRARY.md) | Complete supplied animation vocabulary, including selectively deferred effects |

## Release goal

Capture → review suggestions → choose an action → focus or meditate → record the outcome.

Keep all 80 defined screen destinations and every complete product capability in the first-release backlog. Implement them in working increments. A finished timer screen alone does not fulfill this product.
