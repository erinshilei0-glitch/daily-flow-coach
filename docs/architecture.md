# Product Architecture

This document describes the validated front-end MVP and the boundary between current prototype behavior and future production capabilities.

## Page structure

- **Today:** day type, mode selection, daily modules, optional weekend priority, and completion state
- **Week:** selectable day cards, past/today/future context, per-day Movement and Learning, and Your Weekly Rhythm
- **Coach / Adjust Flow:** full-day replanning using mode, day type, disruption, activities, care context, and weekend priority
- **Movement:** per-day activity selection with mode-aware effort
- **Evening:** dynamic Care / Connection guidance plus a universal wind-down routine
- **Reflection Review:** non-scored end-of-day outcome using the active plan context
- **Settings:** mock profile, Care / Connection defaults, rhythm times, prototype reminders, and Phase 2 framing

## Shared planning state

The prototype keeps shared client-side state for:

- Good / Steady / Low mode
- Weekday or weekend day type
- Per-day Movement choice
- Per-day Learning choice
- Care / Connection type, label, and time
- Optional weekend priority
- Completed modules and reflection inputs

The same selections flow through Today, Week, Coach, Movement, Evening, and Reflection. State is intentionally in memory and resets after refresh.

## Weekday and weekend logic

| Mode | Weekday profile | Weekend profile |
| --- | --- | --- |
| Good | Standard Workday | Active Weekend |
| Steady | Flexible Workday | Balanced Weekend |
| Low | Minimum Workday | Recovery Weekend |

Weekdays include Work / Main Tasks. Weekends keep six genuine modules and offer a separate optional priority. Recovery Weekend may use No focus today. Weekend work is never assumed.

Selected weekend priorities reweight existing modules:

- Outing can satisfy Movement
- Care / Connection becomes protected
- Movement or Learning receives gentle additional emphasis
- Recovery makes optional expectations lighter
- Optional Work is treated as an added commitment
- No focus today adds nothing

## Movement and Learning

Movement and Learning are selected per day.

Movement options include Baduanjin, Indoor Walk, Outdoor Walk, Stretching, Mobility, Strength, Yoga, Recreation, and Custom.

Learning options include Reading, Studying, Online Course, AI Learning, Research, Skill Practice, Creative Learning, and Custom.

Mode changes the size or optionality of the expectation, not the selected activity.

## Week model

Week is a descriptive rhythm view rather than a strict weekly schedule.

- Past days show recorded or gently unreviewed states
- Today shows the active plan
- Future days use flexible intentions without requiring a mode in advance
- Your Weekly Rhythm describes patterns without scoring, streaks, or failure language

## Care / Connection and Evening

Care / Connection supports Child Care, Couple Time, Elder Care, Family Check-in, Pet Care, Personal Connection, and Custom.

Evening contains:

1. Type-aware Care / Connection guidance using the selected label and time
2. A universal routine for tomorrow preparation, reduced stimulation, wind-down, and sleep protection

Changing the Care / Connection setting updates the relevant prototype views without retaining childcare-specific wording for other types.

## Coach logic

Coach / Adjust Flow:

1. Reads day type and user-selected mode.
2. Reads shared Movement, Learning, Care / Connection, and weekend-priority context.
3. Considers completed, remaining, and disrupted modules.
4. Protects genuine commitments and recovery.
5. Reduces, reorders, combines, defers, or drops optional work.
6. Returns a concise revised plan without silently changing mode.

## Reminder controls

Settings reminder switches are visual prototype controls only. They do not schedule device notifications or persist after refresh. Learning nudge is off by default and labeled Good-mode days only.

## Calendar sync: Phase 2

Calendar represents external constraints; mode represents internal state. Future calendar input may reserve unavailable time and improve feasibility, but it cannot infer capacity or replace the user's selected mode.

## MVP boundary

The MVP uses deterministic mappings, mock content, and in-memory client state. It has no required identity, database, production AI service, payments, notifications, or third-party integrations.
