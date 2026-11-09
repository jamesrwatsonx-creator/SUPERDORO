# SUPERDORO — Notes & Ideas: screen-level UX, scrolling and animation
**Source:** SCREEN-INVENTORY.md NOTE-01...08 (8 screens). **Status:** design specification, not implemented.
Each screen below is defined against MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md and the 37-primitives MOTION-SYSTEM.md. Native scroll offset `y` is a design coordinate, not a literal promise that device insets are the same everywhere. Motion is reversible unless marked one-shot; no animation may delay data visibility, input or accessibility.

## Shared Notes interaction rules
- Header/list movement: clamp changes to first 40–72dp based on header type, reversible on scroll up; don't use browser-only pinned footer effects.
- Bottom persistent actions: live above home indicator and keyboard, with content padding for unobstructed last paragraph; collapse action rows when text is long.
- Scroll restoration: save per-detail return destination, list query/filter and scroll offset; in-note browser overlays must not create a separate unrelated navigation tree.
- Standard states: no notes, empty search, offline local data, AI queued, processing error, file unavailable, missing mic permission, loading media, 200% dynamic type and Reduce Motion.
- Accessibility: all icons named, 44–48dp/pt practical touch hit areas, long transcript readable in both themes, no glow-only status communication.

### NOTE-01 — Notes library

**User outcome.** Find a thought immediately and launch new voice/text capture without organizing first.

**Composition and visual design.** Quiet list-first composition; top 'Notes' with Search and filter, optional small category segmented control, rows showing title, short preview, date, audio/web badge when present; bottom reachable voice Capture pill. Empty state has one real Create/Record action, not a huge decorative orb.

**Scroll choreography.** Vertical list scrolling: header 'Notes' compresses from large title to compact bar during first 56dp of y; filter row becomes sticky below safe-area header after y≈64dp. Rows do not independently parallax. Infinite pagination or virtualized list must not wait for fade-in. Returning from detail restores exact y and filter.

**Entry and ambient animation.** First content rows fade up 8dp/140ms, 35ms stagger capped at first 4 rows (M07); microphone pill appears via short spring; no repeated loop in list.

**Tap, swipe, navigation and action motion.** Tap row → shared-element lift into NOTE-02 (M31); long-press reveals multi-select/context sheet (M32); swipe optional Archive with Undo and visible overflow alternative. Search opens NOTE-08 without losing filter. New note opens NOTE-03 or CAP-02.

**Data states, safety and accessibility.** Offline list loads local records; restore previous search; 0 results distinct from no notes; large text expands row height; voice permissions only after recording tap; screen reader announces date, source and category.

**Acceptance test.** Create two notes, scroll, open/return and verify offset; record offline; search and archive/undo; no clipped controls at 200% text.

**Static ChatGPT image / Paper anchor frame.** Mid-list populated dark mode with three realistic note rows, compact Search and reachable glowing voice Capture pill; header in large title state.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-02 — Rich note detail

**User outcome.** See source, AI structure and actions in one place, then act without losing note context.

**Composition and visual design.** Editable title/category; original voice play pill if recorded; expandable transcript/typed content; proposed/accepted actions; source-linked web/photo/file preview cards; relevant metadata/related items only when populated; anchored action tray for Search the web, Start focus, Schedule, Add to Today.

**Scroll choreography.** One coherent parent scroll. Header shrinks by up to 28dp over y=0–72; category chip remains visible with title via compact toolbar. Transcript and references scroll naturally; 'Source references' section label may stick only while that section is visible and cannot obscure items. Bottom action tray stays pinned above safe area; content gets extra bottom inset. Selected reference retains scroll offset on return.

**Entry and ambient animation.** Selected note row transforms into header (M31), transcript highlights trace source→proposal once (M19), references stagger as they enter first viewport (M07, 30ms); avoid multi-section glow pulse.

**Tap, swipe, navigation and action motion.** Tap source audio → NOTE-06; tap reference → WEB-03 with origin link; Search → WEB-01 bottom sheet; Schedule → CAL-03 proposal; Start → FOCUS-01; edit → NOTE-03; link/backlinks → NOTE-07. Attach result animates from web sheet into reference slot (M24) only after save success.

**Data states, safety and accessibility.** Original voice/transcript remains accessible even after AI edits; badges clearly mark proposal vs accepted; do not mislabel unsaved sources; offline original content works; graceful long transcript; privacy in screenshots.

**Acceptance test.** Return from web reader to exact note y and section; action remains reachable with keyboard; source quote matches accepted suggestion; references survive relaunch.

**Static ChatGPT image / Paper anchor frame.** Dark Q4 Landing Page Brief-inspired detail: clear header, short transcript with green highlights, two image-linked references, compact action row and readable focus CTA.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-03 — Rich editor

**User outcome.** Write, edit and attach without accidentally replacing original captured material.

**Composition and visual design.** Text-first white/dark canvas with title, small format tools, rich editable body, inline attachment chips; fixed Save/Done near thumb, back with unsaved warning only when needed. Keyboard-safe editing zone, not a marketing hero.

**Scroll choreography.** Editor body owns scroll; toolbar condenses after y≈44 and formatting strip can collapse on content scroll while editing, but reappears on selection or explicit formatting tap. Cursor insertion scrolls into view; keyboard avoidance must not double-scroll. Inline images retain position.

**Entry and ambient animation.** Editor expands from note card using M31 over ~300ms; text caret and selected field focus are immediate; active field border traces briefly (M11).

**Tap, swipe, navigation and action motion.** Type/paste → debounced local save (no fake success); attach file/image via sheet; selected text gets Turn into task / Quote / Link action menu; Save updates version and returns to NOTE-02; Cancel offers discard current revision while preserving immutable origin.

**Data states, safety and accessibility.** Input can exceed phone height; voice source is never destructively edited; autosave survives app background; undo/redo operate on current revision; offline edits queue cloud sync; accessible rich-text controls.

**Acceptance test.** Paste 10,000 chars, move caret, insert image, background/return, save and compare versions; no hidden Save under keyboard.

**Static ChatGPT image / Paper anchor frame.** Light mode clean editorial rich editor, body paragraph, highlighted selection toolstrip, compact attach chip and keyboard-safe bottom controls.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-04 — Ideas collection

**User outcome.** Browse nascent ideas without treating speculation as a task.

**Composition and visual design.** Library subtab Ideas, compact stacked idea rows with tags/parent project and an optional illustration-free featured idea. Search and 'New idea' prompt. Sorting by recently added, project, tags.

**Scroll choreography.** List vertical virtualization; same compact-header y=0–56 transform as NOTE-01. Filter strip sticky, tag chips horizontally swipe with visible overflow. No marquee or card-by-card perpetual parallax.

**Entry and ambient animation.** Cards appear with M07 at first mount only; subtle selected category line draws (M14), no big reward for adding an idea.

**Tap, swipe, navigation and action motion.** Tap idea → NOTE-05; New idea opens NOTE-03 in idea mode; long-press Move to project/Link task/Archive; idea-to-task conversion demands review and preserves original link.

**Data states, safety and accessibility.** Not all ideas have actions or due dates; no AI auto-promoting vague thoughts to obligations; empty state suggests one voice dump; filters accessible via text labels.

**Acceptance test.** Quick-add idea, link project, convert to task and inspect original provenance; no accidental calendar entry.

**Static ChatGPT image / Paper anchor frame.** Warm white library Ideas list, graceful sparse rows, small project tags, floating New Idea action with just one mint accent.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-05 — Idea detail

**User outcome.** Explore hypotheses and research links, then decide whether to act.

**Composition and visual design.** Large readable idea title, thinking/body block, optional hypotheses and next-step area, linked references/people/projects, related ideas, compact action chips Convert to Task, Research, Link Project.

**Scroll choreography.** Main content single vertical feed; title compresses on y=0–72; sources and proposed steps reveal when entering viewport, but text remains immediately readable. Floating actions can collapse to one 'Actions' pill when screen y>240 to avoid covering long reading.

**Entry and ambient animation.** Chosen idea row expands to detail (M31); supporting relationship connections trace briefly on initial view (M19).

**Tap, swipe, navigation and action motion.** Research → WEB-01 with this idea context; Convert → TASK-03 draft with backlink, not immediate silent conversion; Accept suggestions individually; Link Project → search picker sheet.

**Data states, safety and accessibility.** Hypotheses visibly distinct from facts; source quotes link to original page; no automatic tagging to sensitive topics; offline body remains usable.

**Acceptance test.** Idea → research → attach → return to same section; convert with explicit confirmation and source ID preserved.

**Static ChatGPT image / Paper anchor frame.** Dark elegant idea detail, editorial large title, hypotheses card, two linked sources, and small Convert to Task / Research pills.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-06 — Source and transcript timeline

**User outcome.** Replay original recording and understand exactly how transcript and AI versions evolved.

**Composition and visual design.** Original audio waveform/player at top with real elapsed-time marks, transcript paragraphs synchronized to audio positions, tabs/compare controls for Original, Edited and Structured, compact provenance/version history.

**Scroll choreography.** Audio transport may pin below compact top bar while transcript scrolls; scrubbing waveform never scrolls page. Tap transcript timestamp scrolls to relevant text and cues playback. Header compresses after 40dp; no hidden audio controls on scroll.

**Entry and ambient animation.** Waveform traces only from actual audio shape (M17); active word highlight follows real playback, source-to-extracted span line (M19) only when inspected.

**Tap, swipe, navigation and action motion.** Scrub with finger, +/- seek, speed picker, transcript revision compare; Re-transcribe generates a new proposal and does not erase previous output; tap related accepted task opens TASK-02.

**Data states, safety and accessibility.** If transcript timestamps unavailable, show honest paragraph transcript without fake karaoke timing; corrupted media has retry/export option; playback interruption and offline support; screen reader can seek via buttons.

**Acceptance test.** Seek, pause, background/resume, compare versions, restart; original audio checksum stable and no fabricated timestamps.

**Static ChatGPT image / Paper anchor frame.** Dark readable waveform with interior tick scrubber above timestamped transcript and a compact Original/Edited/Structured segmented control.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-07 — Related items and backlinks

**User outcome.** Trace how a note connects to work, projects, events and references.

**Composition and visual design.** Linked graph expressed primarily as accessible grouped rows: Tasks, Projects, Calendar, Related Notes, References; optional small interactive relationship map behind an explicit View graph toggle.

**Scroll choreography.** Parent grouped list scrolls; category labels may be sticky when a group is tall, but should unstick at group end. Any graph canvas handles gestures only when explicitly opened and offers list alternative. No scroll-hijacking orbit animation.

**Entry and ambient animation.** Connected lines draw once across displayed relation chips (M19); newly accepted link moves into its group (M24).

**Tap, swipe, navigation and action motion.** Tap related item → its detail and preserve backlink; Add existing link opens filterable bottom sheet; unlink confirmation for destructive changes; show reason/anchor phrase for AI suggested association.

**Data states, safety and accessibility.** Relationships are proposals until user-accepted where AI-generated; no fake graph nodes; duplicate edges prevented; small-screen accessible list fallback.

**Acceptance test.** Add, inspect reciprocal backlinks, unlink/undo, verify no orphan provenance; large text readability.

**Static ChatGPT image / Paper anchor frame.** Premium light related-items view with grouped task/project/reference rows and a tiny restrained graph preview; no tangled full-screen network.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

### NOTE-08 — Global workspace search

**User outcome.** Locate content by phrase, type, project, person or reference origin.

**Composition and visual design.** Search field at top with keyboard focus; tabs All/Notes/Tasks/Ideas/Calendar/Files; recent searches (optional) and highlighted source-aware result cards; secure private scope marker.

**Scroll choreography.** Results list owns scroll; search field remains pinned. Filter chips horizontally scroll with obvious affordance. Results are already visible when loaded; reveal first few with M07 optional but never delay fast-scroll rows. Tapping result then Back restores query, filters and y.

**Entry and ambient animation.** Search overlay slides from toolbar (M32) with focused caret (M11); text result highlighting fades in only after actual search response (M18).

**Tap, swipe, navigation and action motion.** Type query, tap filter, select result, clear, attach result to current originating note if launched in context; optionally voice query with permission.

**Data states, safety and accessibility.** Local/offline indexed results before cloud; prevent cross-user leakage; no search telemetry displayed as private if unverified; display empty/no-results separately.

**Acceptance test.** Find text in a transcript and file, open/back with query preserved, offline query, keyboard and 200% font.

**Static ChatGPT image / Paper anchor frame.** Warm white global search with query 'landing page', grouped results with type chips and highlighted exact match; realistic compact mobile density.

**Engineering motion contract.** Reuse `Mxx` identifiers named above; preserve native scroll/gesture response and reduce-motion equivalence. Never animate unsaved data as saved or invented result states.

---

