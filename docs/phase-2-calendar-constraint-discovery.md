# Phase 2 Calendar Constraint Discovery

**Status:** Accepted discovery specification; sample-only prototype authorized  
**Scope:** Sample events and in-memory interaction only  
**Not authorized by this specification:** live calendar access, credentials, provider selection, persistence, notifications, backend work, or changes to the Phase 1 MVP

## Answer first

The smallest safe Phase 2 experiment is a **mock Calendar Context preview** that lets a user review sample commitments, correct how they are interpreted, and see how the current day's modules would flex. It should prove one product claim before any provider is connected:

> Calendar = external constraints. Mode = internal user state.

Good / Steady / Low remains the user's authoritative capacity signal. Calendar events affect feasibility, available windows, sequence, and suggested buffers, but **calendar density is never evidence of capacity**. The Coach must not silently change mode, diagnose the user from an event, turn every open window into work, or treat a crowded calendar as personal failure.

The prototype should use only hard-coded sample events and in-memory choices. Its useful output is an explainable proposal such as: “You chose Steady. Two fixed commitments narrow the afternoon, so I shortened the Work goal and kept your Indoor Walk available for the evening.” Every proposal is editable and reversible.


## Accepted prototype decisions

1. Event treatment is reviewed per event instance. Recurring-series rules and reusable personal rules are deferred.
2. Preparation, transition, decompression, and travel remain four distinct buffer types in the preview.
3. Private or busy-only events remain neutral and uncertain until the user confirms how they constrain the plan.
4. An event may satisfy Movement, Learning, or Care / Connection only through an explicit, one-time user action.
5. A late fixed event and a protected sleep boundary are shown as an unresolved tension; the Coach must not silently remove either.
6. The preview starts with free/busy-style information. Event titles are not required, and requesting them needs later evidence that the added detail provides clear user value.

## Product contract

### Invariants

1. The user chooses Good, Steady, or Low. Calendar input never selects, upgrades, or downgrades it.
2. The profile is derived from mode plus day type:
   - Good weekday → Standard Workday
   - Steady weekday → Flexible Workday
   - Low weekday → Minimum Workday
   - Good weekend → Active Weekend
   - Steady weekend → Balanced Weekend
   - Low weekend → Recovery Weekend
3. Accepted fixed commitments constrain available time. Flexible commitments are candidates for user-approved movement, not silent rescheduling.
4. The Coach explains which constraints shaped a suggestion and marks uncertainty plainly.
5. Movement and Learning keep the activity selected for that day. Calendar context may change effort, duration, or suggested window, not the activity itself.
6. Care / Connection stays user-defined. Event names never determine a care type or relationship.
7. Weekends do not assume work. Calendar events cannot create a weekend Work default or choose a weekend priority.
8. Week remains descriptive and non-scored. Busyness, free time, and completed events do not create a score.
9. Absence of calendar data means “calendar context unavailable,” not “the day is free.”
10. A user can ignore, correct, hide, or remove calendar context without losing access to the core plan.

### Working definitions

- **Fixed commitment:** The user must attend at a particular time, or explicitly marks it fixed.
- **Flexible commitment:** The timing can change, or the user explicitly marks it movable.
- **Protected commitment:** A fixed commitment the user wants the Coach to preserve without suggesting cancellation or compression.
- **External constraint:** Time or context that changes what is feasible; it says nothing about energy, mood, motivation, health, or recovery need.
- **Buffer:** User-confirmed preparation, transition, decompression, or travel time attached to a commitment.
- **Uncertain constraint:** A tentative, incomplete, stale, or ambiguous event that should be shown but not treated as confirmed.
- **Plan adaptation:** A change to module scope, ordering, suggested window, or optionality while preserving the selected mode and user choices.

## Event model for discovery

Each sample event needs only the fields required to test product behavior:

| Field | Discovery behavior |
| --- | --- |
| Type | Meeting, appointment, therapy, travel, family event, care commitment, blocked time, or all-day event |
| Display label | A sample title or privacy-safe label such as “Appointment” |
| Start and end | Local time, or an all-day flag |
| Status | Confirmed, tentative, canceled, or declined |
| Commitment | Fixed, flexible, or “review needed” |
| Recurrence | None, recurring series, or edited occurrence |
| Buffers | Separate prep, transition/decompression, and travel values |
| Detail quality | Complete, incomplete, or stale |
| User treatment | Include, ignore, protect, mark flexible, or correct details |

No attendee list, notes, conference URL, location history, contact graph, or event-description body is required for this discovery.

## Event-handling decision table

| Input | Default interpretation | Effect on feasibility | Allowed Coach response | Prohibited response |
| --- | --- | --- | --- | --- |
| Meeting | Fixed when confirmed and time-bound; user can correct | Reserve event and confirmed buffers | Move or reduce optional module effort; suggest a user-approved flexible window | Infer importance from attendees or title; call meetings productive; change mode |
| Appointment | Fixed by default | Reserve event and confirmed buffers | Protect surrounding transition; offer a lighter sequence | Infer health, urgency, or emotional impact |
| Therapy | Private fixed appointment by default | Reserve event plus user-selected transition/decompression | Use a neutral private label; offer gentler sequencing if the user has chosen a buffer | Diagnose, infer mental health state, expose the title, or lower mode |
| Travel | Fixed when dates/times are known; otherwise uncertain | Reserve explicit travel period and confirmed buffers | Reduce fragmentation; surface timezone or incomplete-time uncertainty | Infer route, commute, purpose, safety, or fatigue without user input |
| Family event | Review needed unless explicitly fixed | Reserve only after user confirmation | Ask “Is this time fixed or flexible?”; preserve chosen Care / Connection treatment | Infer relationship, caregiving role, obligation, or emotional meaning |
| Care commitment | Fixed or protected only when the user says so | Reserve accepted time and buffers | Protect it and flex optional modules around it | Infer the care recipient or map it to a Care / Connection subtype automatically |
| Blocked time | Busy by default, with private details hidden | Reserve the block | Say “You have blocked time”; allow include/ignore | Guess what the block contains or convert it into a task |
| All-day event | Context only until blocking intent is known | Does not consume the full day by default | Ask whether it blocks time, changes location, or is informational | Treat birthdays, holidays, reminders, or banners as full-day unavailability |
| Confirmed fixed event | Hard constraint for this proposal | Reserve event plus confirmed buffers | Adapt module scope and sequence; name the constraint neutrally | Suggest overlap or silent cancellation |
| Confirmed flexible event | Movable only with user approval | Mark as a candidate, not free time | Offer one or more possible windows and ask before applying | Move, shorten, or delete it automatically |
| Tentative event | Uncertain constraint | Show a possible hold; do not treat as settled | Provide “if it happens / if it does not” options | Present the day as definitely unavailable |
| Canceled event | Excluded | Release its reserved time | Note that the time opened up without filling it automatically | Preserve old pressure or add replacement tasks |
| Declined event | Excluded by default | No reserved time | Hide it or show a muted “declined” trace in review | Treat it as an obligation |
| Recurring event | Evaluate the occurrence, not only the series | Reserve the current instance when confirmed | Respect skipped, moved, or edited occurrences | Apply one exception to every occurrence |
| Overlapping fixed events | Unresolved conflict | Count the union of occupied time; flag conflict | Ask the user to review; build a plan that does not assume both are feasible | Double-count duration, choose which event wins, or blame the user |
| Fixed event overlapping flexible event | Fixed event takes scheduling precedence | Preserve fixed time; flexible item remains unresolved | Offer to move the flexible item with confirmation | Move it silently |
| Incomplete event | Uncertain constraint | Reserve only the known interval; label missing information | Ask for the minimum correction needed | Invent an end time, location, buffer, or commitment type |
| Stale event/calendar | Unverified context | Do not claim current availability | Show last-updated state and let the user continue without it | Present stale data as current or punish the plan for uncertainty |

## Fixed, flexible, and protected commitments

The Coach may:

- place module suggestions before or after fixed commitments;
- reduce the scope of optional goals within the selected profile;
- suggest combining compatible intentions when the user already allows it, such as an outing satisfying Movement;
- show alternative windows for a flexible commitment;
- ask the user to mark an ambiguous commitment fixed or flexible;
- protect sleep, Care / Connection, or another user-marked commitment;
- leave open time open.

The Coach may not:

- move, cancel, shorten, accept, decline, or edit a calendar event;
- decide a flexible commitment is unimportant;
- use the number or duration of events to infer Good, Steady, or Low;
- recommend a mode change solely because the calendar is dense or sparse;
- pack every gap with a module;
- make an optional module mandatory to “make up” for lost time;
- describe overlap, lateness, or overload as failure.

If confirmed commitments plus user-protected buffers make the profile plan infeasible, the Coach should preserve the selected mode label and present a softer version of that profile. Example: “Your mode is still Good. With the fixed afternoon commitments, a smaller Standard Workday plan may fit better today.”

## Preparation, transition, decompression, and travel buffers

Buffers must be visible objects, not hidden arithmetic.

- **Preparation:** Optional time before an event for setup or readiness.
- **Transition:** Optional time to switch context before or after an event.
- **Decompression:** A user-chosen post-event buffer; never inferred from event sensitivity.
- **Travel:** Time explicitly present in sample data or entered by the user. No routing or location inference is in scope.

Discovery defaults should be conservative: no buffer is added unless the sample scenario defines it or the user selects one. The UI may offer sample choices such as None, 10 minutes, 20 minutes, or Custom, but it must show the resulting occupied window before applying it. Overlapping buffers are merged for feasibility so they are not double-counted.

When a buffer creates an overlap, the Coach should say which buffer is involved and ask what to protect. It must not silently remove the buffer.

## Overlap, overload, and uncertainty behavior

### Overlap

An overlap is a constraint conflict, not proof of overload or low capacity. Fixed/fixed overlap is sent to review. Fixed/flexible overlap can produce a move suggestion for the flexible commitment. Two flexible events can produce options, but the user chooses.

### Overload

For discovery, **calendar overload** means there is not enough unreserved time to fit the current profile's proposed module scopes and protected commitments. It is a feasibility condition only. The Coach responds by:

1. preserving mode;
2. keeping fixed and protected commitments visible;
3. softening, shortening, combining, or making optional the remaining module goals;
4. leaving recovery space where possible;
5. explaining the tradeoff without a score or warning color associated with personal performance.

### Cancellation and changes

A canceled event releases a constraint, but the Coach does not automatically fill the opening. A moved occurrence is evaluated at its new time. A series exception affects only that occurrence. If a previously used event changes, the proposal is marked “needs refresh” until the user reviews it.

### Tentative and incomplete details

Tentative events produce two lightweight possibilities only when that distinction changes the plan. Missing end time, unknown all-day meaning, and absent commitment type are shown as uncertainty. The plan must never hide invented assumptions behind confident language.

## Precedence rules

Apply these in order:

1. **Direct user control:** Current mode, manual plan changes, event corrections, and explicit include/ignore choices.
2. **Safety and protected needs:** User-set sleep boundary, Care / Connection commitment, recovery space, and any commitment explicitly marked protected.
3. **Confirmed fixed external constraints:** Accepted event time plus user-confirmed buffers.
4. **Day model:** Weekday or weekend and its profile derived from the selected mode.
5. **User choices:** Per-day Movement and Learning activity, Care / Connection configuration, and optional weekend priority.
6. **Flexible and uncertain constraints:** Candidates for suggestions or branching, never silent actions.
7. **Coach optimization:** Scope, sequence, possible windows, combinations, and optionality.

Rules higher in the list constrain lower rules. A calendar event can make a module goal infeasible at a particular time, but it cannot override mode, select an activity, choose a weekend priority, or redefine Care / Connection.

## Module and surface interactions

| Area | Calendar may affect | Calendar must not do |
| --- | --- | --- |
| Work / Main Tasks | Available work windows, fragmentation, proposed scope, and whether a task is optional | Treat meetings as completed focus work; add weekend work; judge productivity |
| Movement | Suggested window, duration, or effort within the current mode | Replace the day's selected activity or infer that travel counts as Movement without confirmation |
| Learning | Suggested window, duration, or optionality | Replace the selected learning activity, create a lesson, or treat event attendance as Learning automatically |
| Care / Connection | Protect a user-confirmed commitment or show a collision | Infer care type, relationship, recipient, or private meaning from event data |
| Evening | Move preparation earlier, shorten the routine gently, or protect wind-down after a late event | Remove sleep protection, frame a late event as failure, or infer fatigue |
| Weekend priority | Help fit the user-selected priority around constraints; allow an outing to satisfy Movement when already chosen | Select a priority, default to work, or create a seventh required module |
| Week | Show neutral constraint markers, uncertainty, and descriptive rhythm | Score density, rank days, predict mode, or preselect future modes |
| Coach | Explain constraints, offer reversible adaptations, and ask for missing classification | Edit events, infer capacity, expose private content, or use coercive language |
| Reflection | Ask whether the plan fit the real day and whether a constraint was represented accurately | Infer event attendance or module completion; penalize deviation |

## Privacy, consent, and permissions

### Consent rules

1. The mock prototype clearly says “Sample events only — no calendar is connected.”
2. Any later provider experiment requires separate, informed opt-in before data is read.
3. Permission must be revocable, and the product must remain usable after decline or disconnect.
4. Event inclusion, private-title display, and Coach use are separate understandable choices where technically possible.
5. A permission screen must state what is read, why it is used, how long it is retained, and what actions the Coach cannot take.

### Data minimization

For the later live-integration decision, start by testing whether free/busy intervals plus status, all-day state, and recurrence metadata are sufficient. Request titles, locations, attendees, descriptions, and attachments only if a validated user benefit cannot be achieved without them. Prefer on-device or short-lived derived constraints when architecture permits. Do not retain raw details merely because a provider returns them.

### Prohibited inferences

The product must not infer:

- capacity, mood, energy, sleep quality, motivation, or recovery need from calendar density;
- diagnoses, medical status, or emotional state from appointments or therapy;
- family structure, caregiving identity, relationship quality, or dependency from titles and attendees;
- religion, politics, union membership, sexuality, finances, legal status, or other sensitive traits;
- work performance, seniority, importance, or productivity from meeting patterns;
- travel purpose, home/work location, routine, or safety from location data;
- social closeness or obligation from invitees;
- attendance or completion from an event's presence on the calendar.

The Coach uses the minimum neutral representation necessary: for example, “fixed appointment, 2:00–3:00 PM,” not an interpretation of why it matters.

## Privacy and fallback decision rules

| State | User-facing behavior | Planning behavior |
| --- | --- | --- |
| User declines access | “That’s completely fine. You can keep planning without calendar context.” | Use mode, day type, and manual changes only |
| Calendar disconnected | Explain that calendar context is off; provide a reconnect action only if requested | Remove calendar-derived claims; keep the core plan intact |
| Permission revoked or insufficient | Name the unavailable capability without pressure | Fall back to manual constraints or no calendar context |
| Data stale | Show “Last updated…” and a neutral stale label | Do not claim current availability; let the user refresh or continue |
| Partial sync | Identify the calendars or interval that could not be read | Use only clearly labeled available data; never imply completeness |
| Service unavailable | “Calendar context isn’t available right now. Your plan still works.” | Continue mode-led planning; offer manual blocked-time entry in a later prototype |
| Event details hidden | Show a private busy block | Respect the interval without asking for the title |
| Event incomplete | Ask only for the missing field that materially changes the proposal | Keep it uncertain until corrected |
| No events returned | Say “No calendar constraints were found,” not “You are free” | Preserve normal plan flexibility |
| Timezone uncertain | Flag the affected event and avoid exact sequencing around it | Do not guess the local time |
| User ignores an event | Confirm it is excluded from this proposal | Do not repeatedly reintroduce it during the same planning cycle |

Fallbacks must be graceful, local to calendar context, and non-blocking. No calendar error should lock Today, Week, Coach, Movement, Evening, Reflection, or Settings.

## Mock prototype flow

The discovery prototype is a separate, clearly labeled preview using hard-coded data. It does not alter the current MVP's persistent structure or imply a live connection.

### 1. Entry from Settings

Card title: **Calendar Context Preview**  
Copy: “See how sample commitments could help shape a gentler, more realistic day. Nothing connects to your calendar.”  
Action: **Try sample day**

### 2. Consent and boundary explainer

Title: **Your mode stays yours**  
Copy: “Calendar events can show when time is constrained. They cannot tell us your energy, mood, or recovery needs, and they will never change Good, Steady, or Low for you.”  
Actions: **Continue with sample events** / **Not now**

### 3. Choose a sample

Offer a small set such as:

- **Meeting day:** two meetings and a flexible admin block
- **Appointment day:** a private appointment with an optional decompression buffer
- **Care day:** a protected care commitment and an incomplete family event
- **Travel day:** confirmed travel, a tentative event, and a timezone warning
- **Weekend plans:** an all-day banner, an outing, and optional Care / Connection
- **Calendar trouble:** stale, partial, disconnected, or unavailable states

The current Good / Steady / Low choice remains visible and editable by the user, not by the calendar preview.

### 4. Review constraints

Each event card shows time, privacy-safe label, status, fixed/flexible/review-needed state, and buffers. Available actions: **Keep fixed**, **Mark flexible**, **Protect**, **Ignore for this plan**, **Add buffer**, and **Correct details**.

Supportive copy:

- “Does this need to happen at this time?”
- “This event is tentative, so we’ll keep the plan flexible around it.”
- “We only know the start time. Add an end time, or leave it uncertain.”
- “This all-day item may be informational. Does it actually block your day?”

### 5. Preview the adapted flow

Show a before/after comparison by module, not an hour-by-hour optimized schedule. Every change includes a reason chip such as **Fixed appointment**, **Travel buffer**, **Tentative hold**, or **Protected care**.

Suggested summary:

> “You chose Low, so Recovery Weekend remains the guide. The afternoon outing is fixed, and you protected Care / Connection. I kept Movement light, left Learning optional, and protected an unfilled recovery window.”

Actions: **Use this sample plan**, **Adjust**, and **Keep my original plan**. In discovery, “Use” changes only preview state and resets on refresh.

### 6. Coach explanation

The Coach can answer “Why did this change?” with a concise trace:

> “Your mode did not change. I used the fixed 2:00 PM appointment and the 20-minute buffer you approved. That made the earlier Learning window less practical, so I moved the suggestion and reduced its scope.”

### 7. Fallback simulator and reset

Let the user switch the sample calendar to stale, partial, disconnected, or unavailable and observe that the core plan remains usable. End with **Reset sample** and the persistent label **Prototype only · sample events · no calendar connected**.

## Scenario matrix

These scenarios validate all six profiles. Each must be run with the named mode already selected; events never select it.

| Profile | Sample constraints | Expected adaptation | Must remain true |
| --- | --- | --- | --- |
| Standard Workday (Good weekday) | 9:00 meeting, 1:00–2:00 fixed appointment, flexible 30-minute admin block | Keep a meaningful Work goal in available windows; offer to move admin; preserve chosen Movement and Learning activities with Good-mode effort where feasible | Good remains selected; meeting density is not praised or used as proof of capacity |
| Flexible Workday (Steady weekday) | Two confirmed meetings, one tentative late meeting, 10-minute transitions | Reduce fragmentation, show “with / without tentative meeting” only if useful, and keep optional modules light | Steady remains selected; no tentative event is presented as certain |
| Minimum Workday (Low weekday) | Fixed therapy label hidden, 20-minute decompression, overlapping flexible task block | Protect appointment and buffer; offer to move the flexible block; retain only essential Work continuity and gentle modules | Low was user-chosen, not inferred; no health or mood inference |
| Active Weekend (Good weekend) | Morning outing, all-day birthday banner, optional Learning priority | Ask whether the banner blocks time; allow outing to satisfy Movement; fit the chosen Learning priority without adding Work | No default Work; Good remains selected; birthday does not consume the full day automatically |
| Balanced Weekend (Steady weekend) | Protected family event, flexible home block, canceled evening plan | Preserve family time, offer a window for the home block, leave canceled time open unless the user chooses otherwise | Weekend priority remains user-selected; open time is not auto-filled |
| Recovery Weekend (Low weekend) | Care commitment, short travel block, incomplete tentative event | Protect care and explicit travel, flag incomplete event, soften optional modules, and allow No focus today | Recovery is not justified by calendar density; no required work or catch-up behavior |

### Cross-profile edge tests

Run the following against at least one weekday and one weekend profile:

| Edge case | Expected result |
| --- | --- |
| Two overlapping fixed events | Conflict review; union of occupied time; no automatic winner |
| Fixed plus flexible overlap | Fixed preserved; flexible move offered with confirmation |
| Recurring series with one canceled occurrence | Only that occurrence is excluded |
| Declined invite | Excluded from constraints |
| All-day travel with unknown timezone | Uncertain context; no exact sequencing |
| Calendar becomes stale after preview | Existing proposal marked as based on stale context; core plan stays available |
| User changes mode after calendar review | Recompute module scope under the new user-selected mode; retain reviewed constraints |
| User changes Movement or Learning activity | Preserve the new activity and adapt effort/window only |
| User ignores a private block | Exclude it for the current proposal without requesting details |
| No event data | Normal mode-led plan; no claim that the day is empty |

### Acceptance assertions

- Every proposal displays the mode the user selected and states that it did not change.
- Every changed module can identify the constraint or user choice that caused the suggestion.
- No scenario assigns a mode from event count, event type, or occupied duration.
- No flexible event moves without an explicit confirmation step.
- No all-day item blocks time until its meaning is reviewed.
- No sensitive event label is needed to generate a feasible proposal.
- All calendar failure states preserve access to the non-calendar plan.
- Week shows context without a score, streak, warning grade, or productivity ranking.
- The six profile scenarios preserve their correct weekday/weekend module model.

## Non-goals

- Connecting Google Calendar, Outlook, or any other provider
- Requesting OAuth credentials or permissions
- Reading real user events or free/busy data
- Creating, editing, moving, accepting, declining, or deleting events
- Persisting event data, derived constraints, or user classifications
- Calendar write-back, notifications, reminders, routing, or live timezone resolution
- Automatic scheduling or a rigid hour-by-hour agenda
- Capacity, health, mood, relationship, or productivity inference
- Provider selection, production infrastructure, backend services, authentication, or database changes
- Rebuilding or modifying the Phase 1 MVP as part of discovery

## Criteria for later provider selection

Google Calendar versus Outlook should be decided only after the mock flow proves useful. Evaluate both with the same weighted criteria:

1. **User fit:** Which provider is actually used by the intended test group, including mixed personal/work calendars?
2. **Least privilege:** Can the product start with free/busy or read-only minimum scopes and clearly explain them?
3. **Data fidelity:** Reliable handling of statuses, all-day events, timezones, recurring exceptions, private events, and partial calendars.
4. **Consent and revocation:** Clear OAuth consent, calendar-level selection, easy disconnect, and dependable token revocation.
5. **Freshness:** Change notifications or safe polling, explicit sync state, and predictable stale-data behavior.
6. **Privacy architecture:** Ability to avoid descriptions, attendees, attachments, locations, and long-lived raw event storage.
7. **Enterprise constraints:** Admin consent, managed-account restrictions, tenant policies, and support for personal accounts.
8. **Reliability and operations:** Rate limits, quota behavior, outages, SDK maturity, auditability, and support burden.
9. **Cross-platform consistency:** Whether the constraint model can stay provider-neutral without provider-specific Coach behavior.
10. **Cost and exit:** Pricing at expected scale, deletion guarantees, portability, and the ability to add or change providers later.

A provider should not be chosen merely because authentication is easiest. The preferred option is the one that supports the validated minimum-data contract for the initial users with the clearest consent and fallback behavior.

## Open questions

The following questions are validation topics rather than blockers for the sample-only prototype:

1. When does an all-day event change day context without reserving time—for example, travel, leave, holidays, or birthdays?
2. What is the gentlest useful representation of a tentative event: a striped block, a short label, or a two-outcome plan?
3. How much explanation is useful before the Coach's reasoning feels like extra work?
4. How should multi-day travel and timezone transitions affect the descriptive Week view without implying capacity?
5. What should “ignore for this plan” mean if an event later changes?
6. Which user-reported outcomes best define success: less manual reshaping, greater plan realism, clearer tradeoffs, lower pressure, or trust in Coach explanations?

## Recommendation: smallest safe Phase 2 prototype

Build a **single-session, sample-only Calendar Context Preview** after this discovery is reviewed. It should contain:

- the six existing mode/profile combinations;
- five to six hard-coded sample event sets plus failure states;
- event review for fixed, flexible, protected, uncertain, and ignored treatment;
- visible prep, transition/decompression, and travel buffers;
- a module-level before/after proposal with an explanation trace;
- one-click return to the original plan and reset-on-refresh behavior;
- no provider picker, OAuth language, network request, persistence, or calendar write action.

The prototype is successful if users can correctly explain that mode represents their internal state, calendar represents external constraints, and the resulting plan feels more feasible without feeling more demanding. It should also reveal whether neutral free/busy-style data is sufficient. Only after those findings should the team choose a provider or define production architecture.

