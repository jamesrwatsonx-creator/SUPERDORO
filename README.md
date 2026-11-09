# SUPERDORO

**Voice to focus. Dump thoughts, review a plan, stay in the work.**

A voice-first mobile focus app connecting voice and typed capture, reviewable AI task/idea/calendar suggestions, linked notes, focus timers, and meditations.

## Current state

This repository contains the product and engineering handoff. It does not yet contain a runnable application, installed dependencies, a configured backend, or completed integrations. See [STATUS.md](STATUS.md) for verified progress.

## Start in Claude Code

Open this repository in Claude Code and use:

> Read CLAUDE.md, AGENTS.md, STATUS.md, and docs/BUILD-BRIEF.md. Implement milestones 0 and 1 from docs/BACKLOG.md: establish the mobile project, then build durable typed and voice capture with replay and local recovery. Preserve all release priorities. Run available checks, state what still requires a physical device, and update STATUS.md with evidence. Do not stop after producing another plan.

The proposed stack is React Native + Expo + TypeScript, SQLite for local persistence, and Supabase for later authenticated backend work. Validate current compatible packages when scaffolding. Start local capture without requiring AI or cloud credentials.

No install or run commands are provided yet because no app scaffold or lockfile exists. Add verified commands when the project is initialized.

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

## Release goal

Capture → review suggestions → choose an action → focus or meditate → record the outcome.

Keep every core capability in the first-release backlog. Implement them in working increments. A finished timer screen alone does not fulfill this product.
