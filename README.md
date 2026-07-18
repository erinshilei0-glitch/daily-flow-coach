# Daily Flow Coach

Daily Flow Coach is an AI-assisted, flexible daily planning app that helps people balance work, learning, movement, care responsibilities, evening routines, and recovery without relying on rigid minute-by-minute schedules.

## Problem

Traditional planners often assume that every day has the same capacity. In real life, energy, sleep, mood, care responsibilities, and external commitments change. When a fixed plan no longer fits, users can feel behind instead of supported.

Daily Flow Coach responds by organizing the day into flexible modules and adapting expectations to the user's current capacity.

## Target user

The primary user is a busy adult—especially a working parent, caregiver, learner, or professional—who needs enough structure to make progress without turning the day into an inflexible timetable.

## Core features

- Today dashboard
- Good / Steady / Low mode selection
- Separate weekday and weekend planning logic
- Flexible checklist for core daily modules
- Customizable Care / Connection module
- Coach / Adjust Flow support for replanning the whole day
- Evening routine with wind-down and bedtime support
- End-of-day Reflection Review
- AI Learning module
- Settings mockup

## Daily modules

- Work / Main Tasks
- AI Learning
- Movement
- Care / Connection
- Evening Routine
- Reflection Review
- Sleep / Recovery

Care / Connection is intentionally customizable. It can represent child play and bedtime, couple time, elder care, a family check-in, pet care, personal connection, or another user-defined responsibility. Erin's personal default is child play and bedtime, usually around 7:15–8:00 PM.

## Mode logic

Mode represents the user's internal state: energy, sleep quality, mood, and capacity.

| Selected mode | Weekday plan | Weekend plan |
| --- | --- | --- |
| Good | Standard Workday | Active Weekend |
| Steady | Flexible Workday | Balanced Weekend |
| Low | Minimum Workday | Recovery Weekend |

The user's selected mode remains authoritative. A future calendar connection may add external constraints, but it should not silently replace the user's self-assessment.

## MVP scope

### Included

- Today dashboard and mode selection
- Weekday / weekend logic
- Core module checklist
- Care / Connection customization
- Coach / Adjust Flow
- Evening routine and Reflection Review
- AI Learning module
- Settings mockup

### Excluded from the MVP

- Real calendar sync
- Login or account system
- Backend database
- Push notifications
- Wearable integration
- Payment or subscription
- Multi-user family sharing

## Current status

The working MVP has validated its core experience:

- The Today page works.
- Good / Steady / Low mode logic updates module goals correctly.
- Weekday and weekend recommendations are distinct.
- Coach / Adjust Flow can revise the full daily plan.
- Evening supports wind-down and bedtime.
- Reflection Review captures the end-of-day outcome.

This repository adds the initial documentation and portfolio structure while keeping the working prototype intact.

## Documentation

- [Product vision](docs/vision.md)
- [Product architecture](docs/architecture.md)
- [Roadmap](docs/roadmap.md)
- [Milestones](docs/milestones.md)
- [Decision log](docs/decision-log.md)
- [Phase 1 completion summary](docs/phase-1-completion-summary.md)
- [AI planning logic](prototype/ai-logic.md)
- [Prompt tests](prototype/prompt-tests.md)

## Future roadmap

The next stages focus on prototype polish, structured AI prompt testing, portfolio packaging, and later integrations. Calendar sync is a future integration rather than an MVP dependency. See [the roadmap](docs/roadmap.md) for the phased plan.

## Portfolio purpose

This project demonstrates:

- Product discovery and problem framing
- Human-centered AI product design
- Scope discipline and MVP prioritization
- Adaptive planning logic
- Inclusive design for different household and care contexts
- Prompt design and scenario-based AI testing
- Product documentation, decision tracking, and roadmap planning
