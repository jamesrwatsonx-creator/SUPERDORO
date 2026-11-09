# SUPERDORO — Insights, Settings and Permissions: 9 screen contracts
**Canonical IDs:** INS-01…09. The existing inventory separates `INS-04 Profile and plan` from `INS-09 Privacy/export/security`. The user's “subscription/account” expectation is covered under INS-04, avoiding an untracked 81st primary screen.

## Global settings rules
Settings are not a cinematic scene. Use only readable panel movement, contextual form/focus feedback, real verification and theme preview. No security-score illustration, fake performance metrics or confirmation before an external result. Offline settings persisted locally when appropriate; provider settings clearly mark queued/sync conflict. Every view supports back behavior, accessibility, large text, dark/light, correct safe areas and proper permission timing. Touch and scroll must work while decorative animations are turned off.

### INS-01 · Focus insights dashboard

**User outcome.** Show real total work sessions, completed tasks, time of day distribution and self-selected goals; filter day/week/month.

**Visual structure.** Premium dark chart cards with large verified totals, one restrained mint line/donut visual, segmented date periods, category breakdown and drill-down to source sessions.

**Scroll and sticky behavior.** Header reduces after y≈56, period control sticky until next group; cards scroll vertical; chart drag scrubs only within chart bounds and does not prevent page scroll outside chart.

**Entrance, data, interaction and state motion.** Count-up odometer M36 on first real data render only, line trace M36, tooltip crosshair M33 on drag; date-switch charts crossfade with correct numbers, never ticker.

**Primary actions, confirmation and destination flows.** Tap metric→source sessions, filter period, open weekly review INS-02; back preserves period/y. Export data via privacy page.

**Data/privacy/accessibility/denial/error requirements.** No data means zero-state, not sample numbers; offline insights calculated from local sessions; avoid correlational health/productivity claims; all metrics accessible as text.

**Static image/Paper frame prompt target.** Dark analytics summary with real-looking demo-labeled weekly focus totals, one line chart and readable period tabs.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-02 · Weekly reflection

**User outcome.** Summarize actual planned/completed/deferred tasks, focus sessions, meditation time and optional suggested next-week priorities.

**Visual structure.** Calm editorial narrative with success and friction paragraphs, sourced stats, small week calendar heatmap and proposed actionable chips.

**Scroll and sticky behavior.** Long narrative scroll with 'This week' title compacting y=0–64; insights tiles appear M07 as first seen, no word-by-word reveal on body. Suggested actions anchored near final paragraphs.

**Entrance, data, interaction and state motion.** Section data count-up M36 for verified values only, short highlights M19 for linked work; accepting proposed next-step animates to Today M24.

**Primary actions, confirmation and destination flows.** Tap referenced task/session, accept/reject AI suggestion, share/export. Dismissed advice not reapplied automatically.

**Data/privacy/accessibility/denial/error requirements.** Never claim 'improved focus' without grounded comparisons, distinguish AI inference from activity record, actual week boundaries/timezones.

**Static image/Paper frame prompt target.** Light weekly reflection with two metric cards, a calm progress sparkline and two reviewable suggestions.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-03 · Goals and progress

**User outcome.** Track chosen outcome and habits/targets with real source relationships, avoiding coercive streaks.

**Visual structure.** Goal cards with measured progress ring, target setting and optional milestone/path visualization; maintain clarity about which data counted.

**Scroll and sticky behavior.** Card list vertical, header compact after y=56, one active goal details expand inline; progress ring not fixed over list. Only selected goal chart may scrub with M33.

**Entrance, data, interaction and state motion.** Progress sweep M25, count-up M36 on first data render, optional achievement rays M37 only on true milestone. Goal edit sheet M32.

**Primary actions, confirmation and destination flows.** Tap Adjust goal, inspect underlying tasks/sessions, change targets with explicit save, optionally archive goal.

**Data/privacy/accessibility/denial/error requirements.** Avoid invented XP, penalizing missed work or fake streaks; goals editable; historical denominator shown.

**Static image/Paper frame prompt target.** Warm white goals list with measured progress bars, one green ring and Edit goal.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-04 · Profile and account plan

**User outcome.** Manage identity, plan, account recovery and sign-out without conflating profile with motivational stats.

**Visual structure.** Compact account hero with avatar/initials, email identity, subscription or free status, profile controls, links to privacy/integrations and sign-out.

**Scroll and sticky behavior.** Vertical settings scroll; profile header compresses y≈40; sections stay visible without entrance delay, no excessive floating circles.

**Entrance, data, interaction and state motion.** Simple card navigation M31 and toggle M12; sign-out confirmation M32; completed account update check M13 only after server/local confirmation.

**Primary actions, confirmation and destination flows.** Edit profile, review subscription/account, sign out across devices as supported, recover account; return to previous route.

**Data/privacy/accessibility/denial/error requirements.** Do not invent subscription tiers or plan eligibility; identity never displayed from unverified OAuth record; safe account deletion link.

**Static image/Paper frame prompt target.** Light profile screen with account summary, plan badge and clear links to privacy/settings.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-05 · Appearance and accessibility

**User outcome.** Choose Light / Dark / System, glow intensity, Reduce Motion, contrast, text scale and haptics preferences.

**Visual structure.** Segmented theme selector with two small live preview cards, color/typography token examples, named toggles and accessible status labels.

**Scroll and sticky behavior.** Settings scroll vertical; small preview area sticky only during theme selector group, not entire screen; no scroll parallax; preserve y when changing font scale.

**Entrance, data, interaction and state motion.** Theme crossfade M30 under 250ms only when allowed; radio selection M12; Reduce Motion immediately stops all ambient loops, glow preview updates without flashing.

**Primary actions, confirmation and destination flows.** Tap theme, preview high contrast, set reduced motion and haptics; revert to System; Save automatically or Confirm if user chooses.

**Data/privacy/accessibility/denial/error requirements.** OS Reduce Motion overrides decorative animation; high-contrast and screen reader text; keep all settings reachable at 200% text.

**Static image/Paper frame prompt target.** Light settings showing light/dark card previews, Reduce Motion switch and color intensity slider.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-06 · Notifications and focus filtering

**User outcome.** Configure focus timer reminders, schedule alerts, optional quiet hours and supported app/contact priority controls.

**Visual structure.** Simple grouped notification switches, time picker, OS capability banner when platform restrictions apply, small live example of sample notification.

**Scroll and sticky behavior.** Long list vertical scroll with compact header; time picker opens native sheet M32; keep save/permission action reachable. No scroll animations in a sensitive control page.

**Entrance, data, interaction and state motion.** Switch spring M12; permission request and bounded status M34; actual test notification indicator M13 only after OS reports success.

**Primary actions, confirmation and destination flows.** Configure daily planning alert, break reminder, quiet hours, high-priority alert exceptions; inspect exact scope; connect OS capabilities only if available.

**Data/privacy/accessibility/denial/error requirements.** Unrestricted phone-wide blocking/filtering not available on every OS; never imply SUPERDORO can silence arbitrary notifications without supported permissions. User can always cancel.

**Static image/Paper frame prompt target.** Dark settings list with Daily briefing, Session complete, Quiet hours and an honest OS capability note.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-07 · Trust Mode and AI permissions center

**User outcome.** Offer granular low-risk AI automatic organization while user retains decision control; separate from privacy/security.

**Visual structure.** Shield line icon, Trust toggle OFF as default, allowed action chips (tag, categorize, link low-risk), review history, always-ask categories (calendar export, sending, purchases).

**Scroll and sticky behavior.** One vertical scroll with title reducing after y≈56; permission group headers may pin while related toggles visible; no security-score meter.

**Entrance, data, interaction and state motion.** Shield stroke M12/M13 upon actual selection, preview card changes when Trust changes, review-change list M07. Any settings toggle effect has clear immediate explanation.

**Primary actions, confirmation and destination flows.** Tap preview example, enable bounded subset, undo individual auto decisions where reversible, view audit trail, disable instantly.

**Data/privacy/accessibility/denial/error requirements.** Trust does not turn encryption on/off; high-confidence classification is probabilistic and can be wrong; no silent external writes or credential access.

**Static image/Paper frame prompt target.** Premium dark Trust Mode permission sheet with clear safety boundary, no invented '87% protected' gauge.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-08 · Integrations and connected sources

**User outcome.** Review calendar, browser/share, files, search provider and future optional connectors, with exact permission scope and health.

**Visual structure.** Provider cards grouped Connected / Available / Unavailable; last authorization and sync time, connection controls, access descriptions and test action.

**Scroll and sticky behavior.** Vertical list with lightweight expand accordion; return from auth restores list/y; chips filter providers within screen without hidden navigation.

**Entrance, data, interaction and state motion.** Connected status check M13 only on verified success, ongoing sync M34 bounded; card expand M32 with readable permission details.

**Primary actions, confirmation and destination flows.** Connect/disconnect/revoke, reauth expired scopes, choose sync, test connection, launch calendar connection detail CAL-06.

**Data/privacy/accessibility/denial/error requirements.** Never display a provider as connected because user merely tapped button; tenant isolation and credentials protected; OS limitations visible.

**Static image/Paper frame prompt target.** Light integration dashboard with Google Calendar and share-sheet cards labeled connected/available as demo state.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

### INS-09 · Privacy, export and security

**User outcome.** Make original capture retention, AI data handling, downloaded media, export, delete account and permissions genuinely transparent.

**Visual structure.** Evidence-first text with clear data categories and storage/retention descriptions, export format choices, session/device overview, irreversible Delete action separated visually.

**Scroll and sticky behavior.** Text-first vertical scroll with semantic sections; header compress y=0–56, destructive actions stay after educational copy and require separate confirmation sheet; no hypnotic glow.

**Entrance, data, interaction and state motion.** Export processing uses real bounded M34, file-ready check M13 after actual artifact exists; delete confirmation M32 with explicit dangerous-action text.

**Primary actions, confirmation and destination flows.** Download Markdown/JSON/media as supported, inspect consents, delete local cache, request deletion of cloud data with verification, revoke permissions.

**Data/privacy/accessibility/denial/error requirements.** No 'nothing used for training' statement unless contract/provider confirms; export only actual files, don't fake encrypted status; follow real retention/compliance design.

**Static image/Paper frame prompt target.** Light privacy center with clear Data export and Original recording retention panels, separate Danger zone.

**Verify:** click, scroll, large text, Reduce Motion, toggle/change/cancel, account and permission boundaries, real backend/OS acknowledgment and preserved navigation state.

---

