# SUPERDORO — flows, decision boundaries and verification matrix

**State:** planned, not coded. Refer to SCREEN-INVENTORY.md for 80 screen IDs; MOTION-SYSTEM.md for M-IDs; MEDITATION-MEDIA.md for media.

## End-to-end pathways

### Account and first session

ONB-01 splash → ONB-02 welcome → ONB-03 sign-in → ONB-04 verification (if applicable) → ONB-05 optional goals → ONB-06 sample or first real dump → ONB-07 extraction demonstration → ONB-08 review → ONB-09 duration → ONB-10 recovery preview → ONB-11 Trust/preferences → ONB-12 Today reveal → DAY-01. **Allow skipping optional stages.** If the sample demonstration is used, label it as sample; never create fake calendar events or focus logs. Returning users bypass the cinematic sequence.

### Real capture-to-action

CAP-01/02/03 → durable local save → CAP-06 processing job → CAP-05 editable transcript → CAP-07 accept/reject → NOTE-02 source detail → TASK-02/CAL-03/NOTE-05 → FOCUS-01/02. All accepted items retain source excerpts/IDs; retries are idempotent. Rejecting an event does not write an external calendar entry.

### Note-to-research

NOTE-02 → WEB-01 explicit Search the web → WEB-02 grounded results → WEB-03 open source OR WEB-04 clip → WEB-05 linked preview → NOTE-02. WEB-06 comparisons, WEB-07 synthesis and WEB-08 opt-in monitoring are reachable from a note or project. On return maintain the original note and scroll position. Show retrieval time and link provenance. Any purchase/booking is user-controlled; do not claim external availability without actual provider evidence.

### Deadline/calendar distinction

“Finish Friday” creates a TASK-02 candidate with deadline. “Meet Friday at two” creates CAL-03 event draft. Both can appear in DAY-01 and CAL-01 but share neither automatic provider write nor identity. TASK-05 schedules a focus block separately. CAL-07 resolves provider conflicts. All external writes require explicit confirmation; duplicate writes forbidden.

### Pomodoro to customized meditation

TASK-02 → FOCUS-01 choose 25/50/custom/free-flow → FOCUS-02 active white-tick ring → optional FOCUS-03 minimized or FOCUS-06 interruption dump → FOCUS-04 pause if requested → FOCUS-05 log session outcome → FOCUS-07 choose reset → FOCUS-10 meditation library → FOCUS-11 player with the user-supplied MP3 and its corresponding motion GIF/alternate → completion → offer resume focus or return to source. Work and meditation durations are separate. Never infer finished task merely from completed timer.

### Daily intelligence

DAY-01 → DAY-02 morning brief populated only from verified local/synced records → DAY-03 recommended priorities → DAY-04 agenda and optional task blocks → DAY-06 end-of-day outcome → DAY-07 tomorrow proposal → INS-02 weekly reflection. External content watches are opt-in and evidenced, not always-on by default.

## High-risk guardrails

1. **Original data:** keep immutable original capture and original media alongside versioned transcript and accepted structured records.
2. **Autonomy:** Trust Mode permits bounded low-risk categorizing/tagging only after opt-in; never silent booking, purchase, sending messages, modifying external calendars, permission changes or deletion.
3. **Privacy:** security is always on regardless of Trust Mode; do not display invented security scores or “nothing used for training” unless verified provider policies and implementation warrant it.
4. **Offline-first:** capture and local navigation continue without connectivity; AI extraction/search requiring network remains visibly queued.
5. **Notifications:** OS-dependent reminder/lock screen/side-button support is scoped by platform and verified on devices; optional notification filtering requires explicit user authority and capability checks.
6. **Sources:** web search summaries, prices, dates, availability, file previews, and comparisons always distinguish source evidence, retrieval time and inference.
7. **Accessibility:** text scales, contrast stays high, touch targets usable, controls not concealed by effects and all animations have reduced-motion behavior.

## Verification checklist

| Journey | Acceptance test | Status |
|---|---|---|
| Initial entry | New account, existing account, guest capture/skippable onboarding; real provider errors | Planned |
| Local save | Voice and typed original survive kill/relaunch/offline | Planned |
| Extraction | Real mixed input yields edit/accept/reject without duplicates | Planned |
| Note context | Task/idea/event source and related references navigable in both directions | Planned |
| Research | User-requested result attaches with URL/time; cancels cleanly | Planned |
| Scheduling | Deadline not auto-event; user confirmation needed before export | Planned |
| Focus | Accurate elapsed time after lock/background, pause, interruption, relaunch | Planned |
| Meditation | MP3+motion paired, seek/interrupt/reduce motion, separate time tracking | Planned |
| Trust | Disabled default, permission scopes and undo/history functional | Planned |
| Themes and accessibility | Light/dark and increased text plus Reduce Motion tested | Planned |

No rows are implemented by documentation alone. Device QA is required before claiming completion.
