# SUPERDORO — Web Research: 8 complete interaction and scroll specs
**Canonical IDs:** WEB-01…08. **Status:** product design, not a live research/search service. Source: [SCREEN-INVENTORY.md](SCREEN-INVENTORY.md), [MOTION-SYSTEM.md](MOTION-SYSTEM.md), [mobile-layout/Paper](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md).

**Shared rule:** Search is optional and user-triggered. The note or project is always the parent; result sheets and webviews never destroy origin scroll position. Metadata (URL, title, provenance, retrieval time) stays attached to source. Most web motion should be a single sheet entrance M32, selected card expansion M31, accepted attach M24 and quiet loading M34. No constant price ticker, spurious 3D object or untrusted page reading as a security claim.

### WEB-01 · AI web search

**Outcome and required visual information.** Search launched from the exact note, task or project; editable interpreted query, constraints, category and short source-context preview.

**Entrance, state transition, and motion primitive triggers.** Entry M32 bottom-sheet rise from source action; sheet header anchored with original item title. Search field focus M11. On short query, show suggested intent chips only if actually extracted.

**Exact scroll ownership, sticky elements and reversed effects.** Search history/results scroll within sheet, original note remains fixed beneath. Drag down closes, preserving note's previous y. When sheet expands to full height, internal header condenses after 50dp.

**Buttons, gestures, child routes and back-stack.** Tap suggested query or type; start search explicitly; cancel network request; on success navigate within sheet to WEB-02; on failure keep query and source context.

**Source truth, error, offline, privacy and accessibility states.** Airplane/no search provider returns retry/draft, no invented search; consent to search source text; redacted private fragments.

**One-screen image/Paper representative keyframe.** Dark detail note visible below glass 'Search the web' sheet, editable query and compact Source context card.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-02 · Search results sheet

**Outcome and required visual information.** Three–five sourced search result cards with domain, title, retrieved timestamp, short relevance and explicit Attach/Open/Extract. No fake current price or review counts.

**Entrance, state transition, and motion primitive triggers.** Result cards stagger M07 after results actually arrive; miniature source-to-note attach motion M24 after confirmed save; 150–300ms selected-card lift M31 opens reader. Search state via bounded M34.

**Exact scroll ownership, sticky elements and reversed effects.** Results area is the only vertical scroller until expanded; query/search controls sticky and collapse 40dp after y=48; underlying note must not scroll. Card images lazy load with stable placeholders, no blank cards from delayed fade.

**Buttons, gestures, child routes and back-stack.** Attach current result directly, Open→WEB-03, Extract→review queue, Refine→WEB-01; repeated Attach idempotent; Back returns to same note with references now linked.

**Source truth, error, offline, privacy and accessibility states.** Show exact source, URL and retrieval time; no guaranteed availability. Missing thumbnails do not remove card or actions; summarize only what was retrieved.

**One-screen image/Paper representative keyframe.** Dark floating glass results sheet anchored on research note; three realistic cited results with attach buttons and no unverified prices.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-03 · In-app browser/reader

**Outcome and required visual information.** Safely read original source with domain and URL visible, reliable Back to originating note, Highlight/Clip action, and external-open fallback.

**Entrance, state transition, and motion primitive triggers.** Reader slides above note M32; subtle crossfade from selected result M31; top URL security indicator is static and honest.

**Exact scroll ownership, sticky elements and reversed effects.** Reader content owns scroll. Compact domain toolbar stays visible or collapses to one-line URL after 56dp. Selection handles never fight scroll; full page remains scrollable while preview cards/clip controls hide as needed.

**Buttons, gestures, child routes and back-stack.** Tap highlight, select text, Clip→WEB-04, Attach full page, Back→WEB-02/NOTE-02 at preserved y. An external-site flow may open outside app if sign-in/booking/payment blocks embedded view.

**Source truth, error, offline, privacy and accessibility states.** CORS/site access and anti-embedding restrictions acknowledged; never spoof browser verification padlock or read unshared tabs; retain exact source link even if extraction fails.

**One-screen image/Paper representative keyframe.** Light reader with trusted-source domain bar, highlighted excerpt and pinned Clip this button.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-04 · Web clip/highlight

**Outcome and required visual information.** Review selected excerpt with exact URL, optional screenshot/thumbnail, title, originating item and attach vs new idea/task choice.

**Entrance, state transition, and motion primitive triggers.** Clip tray M32 rises with source quote M19 highlight continuity; selecting Attach produces small check M23 only after persistent save.

**Exact scroll ownership, sticky elements and reversed effects.** Clipped preview scrolls internally for long excerpts, action bar sticky, source page behind stays at exact selection offset; closing tray restores selection without duplicate clip.

**Buttons, gestures, child routes and back-stack.** Edit selection, choose Attach to this item, New Idea, New Task draft or Cancel; after Attach optional Extract facts suggestion remains in review.

**Source truth, error, offline, privacy and accessibility states.** Quotes must be attributed; screenshots/files require permissions; offline clip queue stores shared bytes/URL; no silent full-page scraping where site blocks it.

**One-screen image/Paper representative keyframe.** Dark half-sheet showing two highlighted sentences, source URL, preview thumbnail, Attach and Create Idea actions.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-05 · Saved references gallery

**Outcome and required visual information.** Browse all sources attached to note/project, grouped by web/file/image/audio, each with small preview, source date and title.

**Entrance, state transition, and motion primitive triggers.** References enter using M07 low stagger only on initial load; selected tile shared expands to its viewer M31. No continuously orbiting gallery.

**Exact scroll ownership, sticky elements and reversed effects.** Grid or list vertical scroll with compact header after y=56; filter chips horizontal and scroll separately; preserve selection/y after viewer close. Avoid heavy masonry causing layout jumps.

**Buttons, gestures, child routes and back-stack.** Tap tile preview, open domain/browser, remove or unlink with confirmation and Undo, compare selected results (WEB-06), attach to another item via picker.

**Source truth, error, offline, privacy and accessibility states.** Broken link or unavailable file still shows reference metadata and fallback; private attachments scoped to account; no generated thumbnail assumed authentic.

**One-screen image/Paper representative keyframe.** Warm white two-column compact source gallery with website, PDF and photo cards, stable domain labels and search.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-06 · Comparison workspace

**Outcome and required visual information.** Compare 2–3 selected items on clearly sourced fields, meaningful constraints and captured retrieval dates; preserve 'unknown' cells.

**Entrance, state transition, and motion primitive triggers.** Column focus changes via native snap carousel M32, difference highlights animate only when compared data changes M12; any price/counter should not tick without data.

**Exact scroll ownership, sticky elements and reversed effects.** Sticky top product/source labels, vertical synchronized row scroll; optional horizontal columns snap, never independently scroll individual spec rows. On narrow phones use segmented selected item + Compare table rather than illegible 3 columns.

**Buttons, gestures, child routes and back-stack.** Choose comparison dimensions, attach snapshot, request updated source only on explicit search; turn chosen decision into task with provenance.

**Source truth, error, offline, privacy and accessibility states.** Unknown/unverified data labeled; old prices marked observed at date; unit/currency/timezone not silently converted; no fake winner rating.

**One-screen image/Paper representative keyframe.** Dark comparison with two product/source columns, concise highlighted differences and fixed Save comparison action.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-07 · Research synthesis

**Outcome and required visual information.** AI summary with evidence links, claim statuses, implications, suggested tasks and review controls; make observed fact vs inference apparent.

**Entrance, state transition, and motion primitive triggers.** Summary paragraphs reveal without typewriter delay M18; citations/source markers use subtle M19 line when tapped; accepted task chip moves to linked queue M24.

**Exact scroll ownership, sticky elements and reversed effects.** Long source-grounded report scrolls naturally; compact title after 64dp; citation tray sticky only while open and dismissible; no parallax on paragraphs.

**Buttons, gestures, child routes and back-stack.** Tap citation opens exact source location, Accept proposed task via review, edit unsupported claim note, Add summary to originating project or note.

**Source truth, error, offline, privacy and accessibility states.** Must never cite nonexistent web content; retrieval time visible; user can challenge summary; offline cached summary clearly stale.

**One-screen image/Paper representative keyframe.** Light Research Summary with evidence chips, Key Findings and two proposed action items.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

### WEB-08 · Requested watches/alerts

**Outcome and required visual information.** List explicit opt-in watches for price, stock, news or availability, each with trigger, schedule/cadence, last checked and source scope.

**Entrance, state transition, and motion primitive triggers.** Watch cards M07, activation toggle M12, a watch-created success M13 only once monitoring job exists; loading status M34 bounded.

**Exact scroll ownership, sticky elements and reversed effects.** Vertical list with sticky Watch filters after y≈56; inline expand card shows thresholds and sources; restoring y on return from watch edit.

**Buttons, gestures, child routes and back-stack.** Create watch from researched item, set alert threshold, preview estimated frequency, pause/resume/cancel; alert opens actual observation plus source, not a purchase screen.

**Source truth, error, offline, privacy and accessibility states.** No continuous watching without user request; provider limits/failures/staleness surfaced; location permission optional; never claim automatic booking/purchase.

**One-screen image/Paper representative keyframe.** Dark Watchlist showing opted-in stock and price watches, last checked timestamps and quiet green active indicators.

**Acceptance:** launch from existing note, navigate, select/attach, cancel, return to original note and y; verify sources/citation timestamp and no duplicate writes, keyboard/large-type/reduced-motion behavior.

---

