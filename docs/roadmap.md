# Roadmap

The roadmap protects the validated MVP while sequencing product discovery, calendar-aware planning, prototype refinement, AI testing, portfolio work, and future production capabilities.

## Phase 1: Product Discovery and MVP Definition

**Goal:** Define the problem, users, product principles, core planning model, and MVP boundaries.

- Validate flexible modules as an alternative to strict schedules
- Define target users and key planning needs
- Establish Good / Steady / Low modes
- Separate weekday and weekend logic
- Define inclusive Care / Connection customization
- Record MVP boundaries and product decisions
- Validate the core Today, Coach, Evening, Reflection, and Settings experience

Calendar sync is explicitly excluded from the Phase 1 MVP.

## Phase 2: Calendar Constraint Discovery and Prototype Integration

**Goal:** Add calendar awareness as an external planning input while keeping user-selected mode authoritative.

- Define supported calendar constraints, event types, and availability rules
- Document permission, privacy, consent, and failure-state requirements
- Prototype how meetings, appointments, travel, therapy, and family events affect the daily plan
- Test calendar-informed adjustments across Good / Steady / Low modes
- Confirm that calendar data never silently changes the user's selected mode
- Preserve manual planning when calendar access is unavailable or declined
- Evaluate a limited live calendar connection only after the prototype behavior is validated

The planning relationship remains:

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

Calendar sync begins in Phase 2. It is not an MVP dependency and does not replace the user's self-assessment.

## Phase 3: Prototype Polish and AI Validation

**Goal:** Refine and systematically validate the expanded prototype without rebuilding it.

- Improve visual consistency, responsive behavior, and accessibility
- Standardize labels and supportive microcopy
- Confirm Today, Coach, Evening, Reflection, Settings, and calendar-aware flows
- Run structured AI prompt tests
- Evaluate tone, feasibility, user control, privacy, and fallback behavior
- Preserve validated mode, day-type, and Care / Connection behavior

## Phase 4: Portfolio Packaging

**Goal:** Present the project as a clear product and AI design case study.

- Capture polished screenshots and create a project icon
- Explain discovery, tradeoffs, validation, and scope decisions
- Document what the prototype demonstrates
- Show how calendar constraints and user-selected capacity work together
- Prepare a concise case-study narrative

## Phase 5: Future Production Capabilities

**Goal:** Add production capabilities only after the core and calendar-aware experiences are validated.

- Persistent preferences, plan history, and reflection data
- Authentication and privacy controls
- Calendar reliability, provider expansion, and synchronization hardening
- Notifications and wearable integrations
- Payment or subscription
- Multi-user family sharing

These capabilities should extend the validated planning experience rather than redefine it.
