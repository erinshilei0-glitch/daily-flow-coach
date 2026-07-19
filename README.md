# Daily Flow Coach

Daily Flow Coach is an AI-assisted, flexible daily planning app for people balancing work, learning, movement, care, connection, evening routines, and recovery without relying on rigid minute-by-minute schedules.

## Problem

Traditional planners often assume that every day has the same capacity. Daily Flow Coach treats changing energy, care responsibilities, and unexpected events as normal planning inputs. It organizes the day into flexible modules and adjusts expectations without framing adaptation as failure.

## Live prototype

[Open the Daily Flow Coach prototype](https://daily-flow-coach-erin.erin-shi-lei0.chatgpt.site)

The live prototype is a private, client-side MVP using mock or in-memory state. Choices reset after refresh. It does not include accounts, persistent storage, real notifications, a production AI service, or live calendar integration.

## Core experience

- Today dashboard with Good / Steady / Low selection
- Separate weekday and weekend plan profiles
- Whole-day Coach / Adjust Flow
- Six genuine weekend modules plus an optional, non-scored priority
- Per-day Movement and Learning choices shared across the prototype
- Selectable Week cards and a descriptive Your Weekly Rhythm insight
- Customizable Care / Connection guidance
- Universal Evening Routine and Reflection Review
- Settings mockup with prototype-only reminder controls

## Planning model

| Selected mode | Weekday plan | Weekend plan |
| --- | --- | --- |
| Good | Standard Workday | Active Weekend |
| Steady | Flexible Workday | Balanced Weekend |
| Low | Minimum Workday | Recovery Weekend |

Mode represents the user's internal state and remains authoritative.

Weekdays include **Work / Main Tasks**. Weekends do not assume work or add a replacement task. Instead, users may choose an optional priority such as Care / Connection, Movement, Recovery, Home, Outing, Learning, Optional Work, Custom, or—on Recovery Weekend—No focus today. The priority reweights existing modules rather than adding work.

## Flexible daily activities

**Movement** can vary by day: Baduanjin, Indoor Walk, Outdoor Walk, Stretching, Mobility, Strength, Yoga, Recreation, or Custom. Mode changes the expected effort, not the chosen activity. An outing may satisfy Movement without requiring separate exercise.

**Learning** replaces AI Learning as the universal module name. Reading, Studying, Online Course, AI Learning, Research, Skill Practice, Creative Learning, and Custom are supported. AI Learning remains one learning type.

## Care, evening, and reflection

Care / Connection can represent child care, couple time, elder care, family check-in, pet care, personal connection, or custom. The prototype's personal default is Child play + bedtime from 7:15–9:00 PM.

Evening separates type-aware Care / Connection guidance from a universal routine: prepare for tomorrow, reduce stimulation, wind down, and protect sleep. Reflection uses the selected mode, activities, weekend priority, and Care / Connection context without scoring the user.

## Calendar: Phase 2

Calendar data will represent external constraints. Mode represents internal state. The AI Coach will use both while preserving user control.

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

## MVP exclusions

- Real calendar sync
- Login or account system
- Backend database or durable state
- Push notifications
- Wearable integration
- Payment or subscription
- Multi-user family sharing

## Current status

Phase 1 product definition and the front-end MVP prototype are complete. Sites version 14 is active, and the final source/build verification passed all five behavior tests. Portfolio screenshots, icon work, and production capabilities remain later work.

## Documentation

- [Product vision](docs/vision.md)
- [Product architecture](docs/architecture.md)
- [Roadmap](docs/roadmap.md)
- [Milestones](docs/milestones.md)
- [Decision log](docs/decision-log.md)
- [Phase 1 completion summary](docs/phase-1-completion-summary.md)
- [AI planning logic](prototype/ai-logic.md)
- [Prompt tests](prototype/prompt-tests.md)

## Portfolio purpose

This project demonstrates product discovery, human-centered AI design, scope discipline, adaptive planning logic, inclusive care design, scenario-based prompt testing, and behavior-preserving prototype refinement.
