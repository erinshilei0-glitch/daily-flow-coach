# AI Planning Logic

This document describes the intended coaching behavior behind the prototype. It is a product specification for prompt and interaction testing, not a production model implementation.

## Inputs

The coach considers:

- User-selected mode: Good, Steady, or Low
- Day type: weekday or weekend
- Core module preferences and minimums
- Care / Connection label and context
- Completed and remaining modules
- User-reported disruptions or priorities
- Future calendar constraints, when integration is added

## Mode selection

Mode represents internal capacity.

- **Good:** Support a fuller plan while preserving breaks and recovery.
- **Steady:** Keep priorities moving with flexible scope and fewer assumptions.
- **Low:** Reduce the plan to essentials, protect recovery, and remove guilt-producing extras.

The coach may explain that a plan looks ambitious or constrained, but it should not override the selected mode. Only the user changes their mode.

## Weekday and weekend behavior

The day type changes the planning profile:

- Good weekday → Standard Workday
- Steady weekday → Flexible Workday
- Low weekday → Minimum Workday
- Good weekend → Active Weekend
- Steady weekend → Balanced Weekend
- Low weekend → Recovery Weekend

Weekday recommendations may prioritize essential work and learning. Weekend recommendations shift weight toward relationships, household needs, movement, recreation, and recovery.

## Care / Connection customization

Care / Connection is supplied as user context, not hard-coded as “Child Time.” Examples include child play and bedtime, couple time, elder care, family check-ins, pet care, personal connection, or a custom label.

The coach should:

- Use the user's chosen label
- Treat genuine care commitments as meaningful plan constraints
- Avoid assuming that every user has children
- Preserve relevant time windows when the user provides them
- Suggest simplification rather than deletion when care is essential

For Erin's personal default, the module is child play and bedtime around 7:15–8:00 PM.

## Coach / Adjust Flow

When the user asks to adjust the flow, the coach should revise the entire remaining day:

1. Acknowledge the current situation without judgment.
2. Identify essential outcomes and fixed commitments.
3. Review all incomplete modules.
4. Reduce, reorder, combine, defer, or drop optional work.
5. Protect Care / Connection, Evening Routine, and Sleep / Recovery where possible.
6. Return a concise revised plan and explain the most important tradeoff.
7. Invite the user to accept or further adjust the result.

The coach should favor realistic completion over preserving the original task volume.

## Future calendar influence

In a future phase, calendar sync will add external constraints such as meetings, appointments, therapy, travel, and family events.

The planning relationship remains:

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

Calendar events can:

- Reserve unavailable time
- Reveal transition or travel needs
- Increase the need to simplify optional modules
- Anchor care or appointment commitments
- Help the coach suggest feasible windows

Calendar events cannot:

- Infer the user's internal capacity with certainty
- Automatically replace the selected mode
- Add unverified obligations
- Remove the user's ability to revise the plan

## Output expectations

A strong AI response is:

- Specific enough to act on
- Brief enough to scan
- Consistent with the selected mode and day type
- Inclusive of the user's Care / Connection context
- Honest about tradeoffs
- Supportive and nonjudgmental
- Explicit about what changed when the flow is adjusted
