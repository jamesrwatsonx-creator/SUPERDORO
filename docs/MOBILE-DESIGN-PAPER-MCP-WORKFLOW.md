# SUPERDORO — mobile-design-orchestrator + Paper MCP workflow

**Status:** design-operational playbook, 2026-11-09. **External reference repo:** [jamesrwatsonx-creator/mobile-design-orchestrator](https://github.com/jamesrwatsonx-creator/mobile-design-orchestrator), pinned at commit `4d88a488ed78ad7b1bec503e4180abccac338af5`. **Paper source:** [Paper MCP official docs](https://paper.design/docs/mcp). No Paper MCP tool is connected in this ChatGPT conversation; installing anything on the user's computer requires a local connected agent and user permission.

## Why these are separate systems
- **SUPERDORO** is the product: its screens, brand, app behavior, motion grammar and technical delivery live in *this* repository.
- **mobile-design-orchestrator** is a reusable design *method* for any mobile app. It establishes screen planning, layout/ergonomic constraints, and image prompts. It is **not** an alternative source of product requirements and should not be copied wholesale into SUPERDORO or mutated by product-specific changes.
- **Paper MCP** is an optional bridge to an editable design canvas. It gives local AI agents access to the currently open Paper design file; it does not itself make a generated PNG or a real native app. It may be used after or alongside concept images.
- **MOTION-SYSTEM.md** and **REFERENCE-MOTION-LIBRARY.md** specify SUPERDORO's animations and interaction vocabulary. Paper frames must be annotated with these IDs and native implementation behavior.

### Source-of-truth precedence
1. Exact confirmed user requirements and approved images/logo.
2. SUPERDORO `SCREEN-INVENTORY.md`, `DESIGN.md`, `MOTION-SYSTEM.md`, this product overview and finalized accepted screen specs.
3. Mobile design orchestrator's hard layout/ergonomics rules and image creation process.
4. Paper editable frame/layer state **after** explicit user review and approval.
5. Generator interpretation and exploratory visual details (never silently override required mechanics).

If the paper design, generated image and source of truth conflict, resolve with documented approval, not an accidental silent copy.

## Step A — design preflight
Read, in order: `docs/COMPLETE-PRODUCT-OVERVIEW.md`, `docs/DESIGN.md`, `docs/SCREEN-INVENTORY.md`, `docs/MOTION-SYSTEM.md`, `docs/REFERENCE-MOTION-LIBRARY.md`, `docs/DETAILED-SCREEN-MOTION-UX.md`, `docs/SCREEN-IMAGE-PROMPTS.md`, and `docs/ASSET-REGISTER.md`. Check the latest git commit and any user-approved corrections before designing. Read the separate orchestrator's `PROJECT-INSTRUCTIONS.md`, `skills/screen-planning.md`, `skills/mobile-image-generation.md` and `references/mobile-layout-rules.md` at the pinned commit. Do **not** restart "Interview Me" because SUPERDORO already has an established brief, screen inventory and approved general direction.

For each request, record the canonical screen IDs and target user journey, e.g. NOTE-02 → WEB-01/02 → WEB-03 → NOTE-02, or TASK-02 → FOCUS-01/02/05 → FOCUS-07/11.

## Step B — mobile spec defaults and devices
These are design constraints and test targets; exact device profiles may change as implementation tools evolve.

| Constraint | Standard | Acceptance |
|---|---|---|
| Spacing | 8 pt/dp baseline, occasional 4 dp refinements | visible consistent parent-child relationships |
| Screen edges | usually 16–24 dp/pt content inset | no floating controls clipped at edges |
| Safe areas | real status bar/notch/navigation bottom gesture insets | buttons and text remain usable |
| Touch areas | aim for practical 44–48 dp/pt or larger | no icon-only tiny tap regions |
| Native patterns | native scroll, bottom sheets, bottom nav or visible contextual tabs | no desktop web UI squeezed into a phone |
| Controls | labels, segmented controls, readable input heights, realistic icon proportions | easily usable one-handed |
| Responsive | narrow phone, typical phone, large phone; tablet optional | no overflow; keyboard does not block Save |
| Typography | high contrast and dynamic text scaling | large font and localization tested |
| Repetition | consistent nav/header/row/card/button styles | same component means same dimensions |
| Density | compact list, rich progressive detail, restrained hero space | no 1-screen-per-card fake mockup |
| Color | semantic light/dark tokens, selective accent and glow | readable, high-contrast text |
| Motion | review Mxx IDs per screen, Reduce Motion fallback | no interaction blocked waiting for animation |

**Artboard recommendation:** native-portrait phone design targets around 393×852 pt/dp in a common concept artboard, with explicit reference captures for a narrower 360×800 profile and a taller 430×932 profile. These are **design-space targets**, not universal device pixels or exact Android/iOS status-bar specifications. Test actual safe area insets on devices. Generator outputs should prefer clean single-screen composition rather than drawing a fake physical phone.

## Step C — three approved-direction visual anchors
Choose three screens that expose the actual product, rather than only presenting login artwork:

1. **NOTE-02 / Rich Note Detail:** premium dark glass, real density, transcript, source-linked cards, smart actions; establishes 80-screen content hierarchy.
2. **WEB-02 / Research Results Over Note:** bottom sheet on original note, trusted source previews and tap actions; establishes in-context information flow and sheet physics.
3. **FOCUS-02 / Precision Timer:** white circle with interior ticks, quiet dark/light analog balance, minimal persistent actions; establishes signature product visual.

These three are **production anchors**, not exhaustive deliverables. Build light/dark matching variants after concept approval. Once approved, compare remaining 40 detailed screens against these anchors as references, not as direct copies.

## Step D — one-image-per-screen generation
ImageGen is for static high-fidelity reference frames. It cannot output editable layers, native gestures, operational screen state or truly functioning scroll animation. Use exactly one screen ID and one chosen moment/state per output; a set of 12 separate images may be displayed as a carousel, but each image is one screen. Preserve the right caption, label, contrast, controls and geometry. Provide the same app logo/reference to each generation where available; do not ask generator to invent a new S every time.

### Universal image prompt preamble
> Render ONE high-fidelity real native mobile screen for SUPERDORO. Follow the approved geometric S brand, calm premium glass-and-glow design, airy warm white and charcoal dark themes with mint accent, modern legible typography and the canonical three anchors. Apply 8dp spacing rhythm, 16–24dp horizontal insets, 44–48dp targets, safe areas, keyboard and thumb reach, appropriate information density. Do not imitate a desktop website or add unnecessary sci-fi effects. Use the exact screen ID, required labels/controls and information hierarchy from docs/DETAILED-SCREEN-MOTION-UX.md. The image is one representative *still frame* of its specified entry/scroll/interaction storyboard. Do not present fabricated live metrics or unverified external data as factual.

Use `docs/SCREEN-IMAGE-PROMPTS.md` for each screen's unique image prompt, which includes the chosen hero state, route and motion IDs. Record which visual frame (idle, partial scroll, open sheet, accepted item, etc.) the image represents. As a default generate **one portrait screen at a time**, sequentially, to maintain cross-screen consistency and correct typography. Avoid multi-phone mosaics as implementation assets.

### Image quality acceptance
Review for exact screen ID/function, visible unambiguous affordances, lower CTA reachable, legible text at realistic mobile sizes, true safe areas, no cut-off/duplicated elements, realistic status bar, uniform component widths, user-data privacy, approved S mark and accurate light/dark variant. Correct errors with revision prompts, not vague "make it better" instructions.

## Step E — Paper MCP preflight and editable file authoring
Paper MCP is a local agent connection. The official Paper documentation explains that Paper Desktop starts its MCP server and installs a Paper CLI, and the desktop app's MCP panel can connect Claude Code, Codex, Cursor and other tools. The official recommended path for Claude Code is the **Paper Desktop plugin/installer**. Manual CLI examples are only valid once Paper Desktop and its CLI are installed and the executable path is known.

**Official Claude Code plugin option** (from Paper docs, verify live before executing locally):
```bash
claude plugin marketplace add paper-design/agent-plugins
claude plugin install paper-desktop@paper
```
Open or restart Claude Code and check `/mcp` for a real Paper server. Alternatively in Paper Desktop choose **Add to Claude** or **Add to Codex** and follow that installer; Codex CLI documented form is `codex mcp add paper -- /path/to/paper mcp`, replacing the path with the *real* local executable. Do not commit a made-up path. A user's explicit local install and plugin permissions are required. Never claim ChatGPT chat's disconnected tools can write a local Paper file.

**Paper file preflight:** user opens the dedicated SUPERDORO Paper file; connected agent checks currently open design via the server's *advertised* read-only file-info function (the Paper support docs refer to `get_basic_info`, but verify the available live tool name/schema before calling). If no file, connection or write permission is visible, stop and report unavailable; don't silently substitute a Figma/PNG result claiming to be Paper.

**Design file:** `SUPERDORO — Mobile Design System`; pages for `00 Tokens`, `01 Anchors`, `02 Notes`, `03 Calendar`, `04 Research`, `05 Focus & Recovery`, `06 Insights & Settings`, `07 Interaction Frames`, and `08 Review`. Page names are proposed organizational conventions, not guaranteed Paper API page features.

**Authoring protocol:**
1. Create tokens in Paper for colors, spacing, radius, typography and elevation, with dark/light variants; use the official Paper tokens guide: https://paper.design/docs/tokens. Check actual token APIs rather than guessing.
2. Create a named 393×852 portrait frame for each canonical screen ID, layered flex/stack structures, safe-area guides and real text components. Use 360 and 430 widths for responsive validation where available.
3. Implement reusable-looking components with consistent geometry: shell, note row/detail, action chip, glass sheet, reference card, search result, timer, input, toggle, meditation player. Do not assume Paper's component-feature API exists; composition and token reuse can be documented if actual reusable components are unavailable.
4. Add captions/annotations for Mxx motion: trigger, duration/ease, scroll start/end offsets, pinned elements, interrupt/cancel state, haptic/audio relationship, Reduce Motion result. Paper cannot be assumed to simulate every native effect.
5. Validate contrast, touch target bounds, overflow and safe areas by inspecting the actual frames, not merely the generator image.
6. Create additional **interaction-state** frames as needed (sheet open, keyboard active, permission denied, calendar conflict, paused timer, meditation player controls visible). Do not increase 80-screen count for these.
7. Link the current frame's design ID/URL or exported verified artifact in a repo review record, after the connection returns a real identifier; never invent Paper URLs.
8. Implement in React Native only after approval; compare native screenshots to approved Paper frame and test actual device transitions.

## Step F — Motion choreography and scroll behavior
The primitive library M01–M37 is global; `DETAILED-SCREEN-MOTION-UX.md` supplies the 43 individual contracts. The 105-term library remains inspiration and is deliberately filtered to avoid incoherent effects.

**Five technical animation types:**
- **Mount/appear:** grouped content opacity 0→1, translation roughly 8–16dp→0, stagger 30–70ms *without hiding actual data*.
- **Scroll-linked (reversible):** based on native scroll offset `y`, header height/opacity, slight parallax and sticky action constraints; clamp transforms to avoid hidden controls. Never scroll-tie critical text opacity to zero.
- **Event-driven:** task accepted, file attached, filter selected, timer started, date picked, compare column switched; motion is atomic and undoable.
- **Shared-element route change:** selected note, reference card or meditation tile becomes detail, preserving identity and prior scroll state.
- **Ambient/content rhythm:** subtle photographic parallax, breathing guide and meditation scene loop; pause or drop frames in background, stop with Reduce Motion or user opt-out.

**Recommended broad duration bands:** 120–240ms for controls, 200–450ms for cards, 250–500ms sheets and 450–800ms shared-route transitions, all device-dependent and interruptible. Avoid GSAP/Framer scroll libraries for native views; translate intent to Reanimated/native scroll + Skia/vector or content players. Verify the user can reach actions immediately on every scroll.

## Step G — Approval and implementation contract
A screen has reached **Visual Reference** when its unique image exists and matches mobile rules; **Editable Design** when a real Paper file has layered structures and tokens; **Specified Interaction** when state, scroll, motion and error behavior have been annotated; **Implemented** only when real app code and data exist; **Verified** only when usability and device QA are recorded.

Write a small `DESIGN-REVIEW.md` record with screen ID, image asset (actual path), Paper frame URL (actual returned link), motion IDs, reviewed date, known compromises, approved state and next step. If any asset/connection absent, record **blocked** rather than made-up success.

## How we avoid overdesign
- A plain note list is not the place for a 3D rotating brain, parallax per row, or a permanent ticker.
- A running Pomodoro is deliberately quieter than the cinematic timer setup: ticks, accurate numbers and minimal controls only.
- A medal/confetti animation appears on true completed work, not on an AI suggestion that merely exists.
- In-app research moves as a sheet anchored to its source note, not as an unrelated browser app.
- A meditation can be visually immersive, but pause/exit/captions and safe playback always outrank particles and light effects.

## Repository/agent setup prompt
> Before designing any SUPERDORO screen, read SUPERDORO docs/COMPLETE-PRODUCT-OVERVIEW.md, SCREEN-INVENTORY.md, DESIGN.md, MOTION-SYSTEM.md, REFERENCE-MOTION-LIBRARY.md, DETAILED-SCREEN-MOTION-UX.md, SCREEN-IMAGE-PROMPTS.md and this workflow. Read the *separate* mobile-design-orchestrator source at pinned commit 4d88a488ed78ad7b1bec503e4180abccac338af5, especially mobile-layout-rules.md and mobile-image-generation.md. Design one canonical screen ID per image, using the approved logo/theme and three anchor screens. Check Paper Desktop MCP connection with its actual supported read-only tool before any write. If connected, create an editable layered Paper frame with tokens and motion annotations; otherwise save an image/prompt design and label Paper handoff pending. Do not misrepresent a flat generated picture, an unrelated project, or future MP3/GIF as an implemented app feature.

## Verification references
- [Paper MCP setup and local connection](https://paper.design/docs/mcp)
- [Paper token generation and themes](https://paper.design/docs/tokens)
- [Mobile Design Orchestrator at pinned revision](https://github.com/jamesrwatsonx-creator/mobile-design-orchestrator/tree/4d88a488ed78ad7b1bec503e4180abccac338af5)
- [Motion system](MOTION-SYSTEM.md), [All motion references](REFERENCE-MOTION-LIBRARY.md), [Per-screen choreography](DETAILED-SCREEN-MOTION-UX.md), [Per-screen prompts](SCREEN-IMAGE-PROMPTS.md)
