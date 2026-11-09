# SUPERDORO — Calendar & Reminders: full screen, scroll and animation contract
**Scope:** CAL-01…CAL-07 • Seven planned primary screens • Unimplemented design specification.

For every screen, implement real mobile safe areas, 8dp spacing, ≥44–48dp practical touch targets, dynamic text and light/dark themes. Use the source-of-truth M01–M37 [motion library](MOTION-SYSTEM.md) and [mobile-design + Paper workflow](MOBILE-DESIGN-PAPER-MCP-WORKFLOW.md). Scroll transitions are reversible at the described y offsets; mount animations play once and never delay live content. Maintain the date/time and scroll position when returning from a child screen. Every external calendar write has explicit user consent and error handling.

### CAL-01 · Calendar overview

**User and layout objective.** Show week/month events, task deadlines and time blocks with clearly different visual semantics; thumb-reachable Add and Today.

**Scroll/gesture map.** Calendar week strip docks below compact header while agenda scrolls; header compresses y=0–56dp, scrolling reverses; only week strip handles horizontal week swipe, not the entire page.

**Animation and navigation choreography.** Date underline strokes M14 on selection; event cards fade 8dp M07; tapping event expands shared-element to CAL-03 M31; dragging previews moved block M24 and requires confirmation.

**Safety, offline, edge and accessibility states.** Offline uses last synced state with timestamp; daylight-saving, overlap and timezone clear; deadlines not automatically exported.

**Required still-frame design for ImageGen/Paper.** Light week grid with event blocks, differently marked task due dates and clear Today button.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-02 · Day agenda

**User and layout objective.** Chronological time slots, all-day events separated from due-date badges, visible free-time areas and linked focus blocks.

**Scroll/gesture map.** Day timeline vertical scroll; date bar sticky; current-time line moves with actual clock, not a loop; scroll y restored after returning from event; explicit date arrows prevent gesture conflict.

**Animation and navigation choreography.** Incoming task into free slot snaps with M24 200–350ms; tap event M31, long press drag preview; sheet alternative accessible.

**Safety, offline, edge and accessibility states.** Timezones and recurring instances correct; overlapping blocks readable; no silent event changes.

**Required still-frame design for ImageGen/Paper.** Dark day timeline with event, task-linked Pomodoro, open time and compact dated header.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-03 · Event draft/detail

**User and layout objective.** Show title, parsed date/time/timezone, status draft vs confirmed, duration, location, original source quote, linked tasks and provider.

**Scroll/gesture map.** Detail vertical scroll with title compress y=0–64, metadata top; pinned Confirm/Edit/Cancel CTA with bottom content padding; attendees/history overflow scroll.

**Animation and navigation choreography.** Proposal expands from suggestion card M31, parsed field highlight M11, source quote M19; Save success M13 only after durable store/provider acknowledgment.

**Safety, offline, edge and accessibility states.** Ambiguous relative date gets editable confirmation, recurring event edit scope explicit, no fake 'scheduled' on draft.

**Required still-frame design for ImageGen/Paper.** Light proposed meeting detail with editable time and source quote.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-04 · Event editor

**User and layout objective.** Create or edit real event or scheduled focus block with start/end, timezone, recurrence, calendar/provider and linked task.

**Scroll/gesture map.** Form body scrolls with keyboard avoidance; title compact; Save sticky above insets/keyboard; date picker as nested sheet; on close restore caret and y.

**Animation and navigation choreography.** Sheet open M32, input focus M11, selected date M12; Save M13 upon success and reversible card-to-day move M24.

**Safety, offline, edge and accessibility states.** DST gap/duplicate hour validation, end-before-start, offline internal draft, external write confirmation and duplicate prevention.

**Required still-frame design for ImageGen/Paper.** Dark event creation screen with readable date/time, recurrence and Save.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-05 · Reminder composer

**User and layout objective.** Set linked one-time/recurring reminder with time, before-event offset, preview message and alert permission state.

**Scroll/gesture map.** Usually a half sheet: internal scroll only under large text or keyboard, title and Confirm visible; drag-to-dismiss complemented by Close.

**Animation and navigation choreography.** Sheet spring M32, preset check M12, real scheduled acknowledgement M13; Cancel reverses without side effect.

**Safety, offline, edge and accessibility states.** Permission requested just in time; denied path offers in-app schedule not false notification promise; quiet hours respected.

**Required still-frame design for ImageGen/Paper.** Light reminder sheet above a dimmed note with action presets.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-06 · Provider synchronization settings

**User and layout objective.** Connect and manage Google/Apple where platform supported, calendars selected, direction/scope, status, last sync and disconnect.

**Scroll/gesture map.** Vertical settings cards, collapsible scopes, compact title after y=40; return from OAuth maintains y; failure banner fixed until dismissed.

**Animation and navigation choreography.** Provider cards cascade M07; connect bounded M34; authenticated success M13, never unverified progress percent.

**Safety, offline, edge and accessibility states.** OAuth secret protection, expired token, offline stale status, revoke and cross-account isolation; Apple provider behavior OS-specific.

**Required still-frame design for ImageGen/Paper.** Dark provider cards with clearly labeled actual vs sample sync statuses.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

### CAL-07 · Conflict resolution

**User and layout objective.** Compare SUPERDORO and external versions of title, time, recurrence and source timestamp; choose resolve per event.

**Scroll/gesture map.** Conflict cards expand within scrollable list; chosen resolution preserved while scrolling; bottom Apply sticky if decisions valid; no parallax/animation-driven hiding.

**Animation and navigation choreography.** Cards M07, option check M12, card moves to resolved group M24 after sync actually succeeds; failure stays visible.

**Safety, offline, edge and accessibility states.** Audit log, retry, preview resulting record, destructive edit confirmation; never 'all changes safe' by default.

**Required still-frame design for ImageGen/Paper.** Dark side-by-side local/external changed-time conflict card and Resolve CTA.

**Interaction test:** tap, cancel, navigate back, retry offline/error and verify correct selected date, related task, unchanged provider records until confirmation, large-type layout, Reduce Motion state and screen-reader text. Use actual source data/clearly labeled demonstration values, never fabricated availability.

---

