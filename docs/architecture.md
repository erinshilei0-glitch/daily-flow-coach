# Product Architecture

This document describes the current product structure and the intended separation between MVP behavior and future integrations. It is a product architecture, not a claim about a production backend.

## Page structure

- **Today:** mode selection, daily overview, core modules, and completion state
- **Coach / Adjust Flow:** full-day replanning based on mode, context, and user input
- **Evening:** wind-down, bedtime support, and remaining care or connection
- **Reflection Review:** end-of-day outcome, learning, and a gentle reset
- **Settings:** mock configuration for preferences and Care / Connection defaults

## Core modules

The plan is composed from flexible modules rather than fixed time blocks:

1. Work / Main Tasks
2. AI Learning
3. Movement
4. Care / Connection
5. Evening Routine
6. Reflection Review
7. Sleep / Recovery

Each module can receive a different goal, emphasis, or minimum depending on the day type and selected mode.

## Weekday and weekend logic

The planner first identifies the day type, then maps the selected mode to a plan profile.

| Mode | Weekday profile | Weekend profile |
| --- | --- | --- |
| Good | Standard Workday | Active Weekend |
| Steady | Flexible Workday | Balanced Weekend |
| Low | Minimum Workday | Recovery Weekend |

This separation prevents workday assumptions from being applied to weekends and gives recovery and relationships appropriate weight.

## Care / Connection module

Care / Connection is a customizable module rather than a fixed “Child Time” feature. Supported examples include:

- Child play and bedtime
- Couple time
- Elder care
- Family check-in
- Pet care
- Personal connection
- Custom

The module stores or accepts a user-facing label and planning context. Erin's personal default is child play and bedtime, usually around 7:15–8:00 PM, but that default is not universal product behavior.

## Coach / Adjust Flow logic

Coach / Adjust Flow operates across the full daily plan:

1. Read the current day type and user-selected mode.
2. Consider completed, remaining, and disrupted modules.
3. Protect essentials such as care commitments and recovery.
4. Reduce, reorder, or simplify module goals as needed.
5. Return a realistic revised plan with supportive reasoning.
6. Preserve the user's selected mode unless the user changes it.

## Calendar sync: Phase 2

Calendar data represents external constraints such as meetings, appointments, therapy, and family events. Mode represents internal state such as energy, sleep quality, mood, and capacity.

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

Calendar sync is not required for the MVP. In a later phase, calendar events should inform available windows and constraint handling without overriding the user's mode.

## MVP architecture

The MVP is intentionally prototype-oriented:

- Client-side screens and interactions
- Local or in-memory state sufficient to demonstrate the experience
- Deterministic mode and day-type mappings
- Mock settings and AI coaching behavior
- No required identity, database, payments, notifications, or third-party integrations

## Future architecture

Future production work may introduce:

- Calendar provider integration and permission handling
- A service layer for AI planning and prompt orchestration
- Persistent preferences, history, and reflection data
- Authentication and privacy controls
- Notification and wearable integrations
- Subscription or shared-family capabilities

These additions should follow validation, not precede it. The product must continue to function around the core relationship between user-selected mode, external constraints, and adaptive coaching.
