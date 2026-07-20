# Roadmap

## Phase 1: Product Discovery and MVP Definition — Complete

The validated Phase 1 outcome includes:

- Flexible modules instead of strict scheduling
- Good / Steady / Low modes
- Separate weekday and weekend profiles
- Optional weekend priorities that reweight rather than add modules
- Per-day Movement and Learning choices
- A descriptive Week rhythm view
- Customizable Care / Connection
- Dynamic care guidance plus a universal Evening Routine
- Whole-day Coach adjustment
- Non-scored Reflection Review
- A verified, Sites-hosted front-end prototype

Calendar sync remains explicitly excluded from Phase 1.

## Phase 2A: Calendar Constraint Discovery — Complete

**Goal:** Define calendar context as an external feasibility input while keeping user-selected mode authoritative.

- Event types, uncertainty, buffers, privacy, consent, and fallback behavior documented
- Six-profile scenario matrix and acceptance assertions defined
- Sample-only prototype boundaries accepted
- Live providers, credentials, persistence, and calendar write actions remain out of scope

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

## Phase 2B: Sample Calendar Context Preview — Next

**Goal:** Validate the interaction model without connecting a real calendar.

- Build a separate, single-session preview using hard-coded sample events
- Review event instances as fixed, flexible, protected, uncertain, or ignored
- Keep preparation, transition, decompression, and travel buffers distinct
- Treat private busy blocks as uncertain until the user confirms their effect
- Allow explicit one-time event fulfillment for Movement, Learning, or Care / Connection
- Show sleep-versus-late-event conflicts as unresolved tensions
- Start with free/busy-style information without requiring event titles
- Test all six profiles and calendar failure states
- Keep every proposal explainable and reversible without silently changing mode

## Phase 2C: Provider Readiness Decision — Later

- Review evidence from the sample preview
- Decide whether calendar context improves realism without increasing pressure
- Determine whether free/busy information is sufficient
- Compare Google Calendar and Outlook using user fit, privacy, consent, fidelity, failure handling, and implementation cost
- Require a separate authorization before any limited live connection

## Phase 3: AI Validation and Product Hardening

- Run structured prompt tests
- Define production AI boundaries and fallbacks
- Validate accessibility and responsive behavior
- Decide whether device-local or account-based persistence comes first
- Design accessible reminders without pressure

## Phase 4: Portfolio Packaging

- Capture polished screenshots
- Create a project icon and selected illustration direction
- Assemble the product case study
- Present discovery, decisions, validation, limitations, and outcomes

## Phase 5: Future Production Capabilities

- Persistent preferences, plans, and reflections
- Authentication and privacy controls
- Calendar provider expansion and synchronization hardening
- Notifications and wearable integrations
- Payments or subscriptions
- Multi-user family sharing
