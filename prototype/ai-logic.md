# AI Planning Logic

This is the intended coaching specification for prompt and interaction testing, not a production AI implementation.

## Inputs

- User-selected mode: Good, Steady, or Low
- Day type: weekday or weekend
- Completed and remaining modules
- Per-day Movement and Learning selections
- Care / Connection type, label, and time
- Optional weekend priority
- User-reported disruption or priority
- Future calendar constraints, when Phase 2 is added

## Core rules

1. Mode represents internal capacity and remains user-controlled.
2. Day type selects the weekday or weekend profile.
3. Mode changes the size or optionality of goals, not the user's chosen activity.
4. Replanning adjusts the entire remaining day.
5. Genuine care commitments and recovery are protected.
6. Language remains specific, concise, and nonjudgmental.

## Day profiles

- Good weekday → Standard Workday
- Steady weekday → Flexible Workday
- Low weekday → Minimum Workday
- Good weekend → Active Weekend
- Steady weekend → Balanced Weekend
- Low weekend → Recovery Weekend

Weekends do not assume work. A separate optional priority may reweight existing modules. No focus today is valid on Recovery Weekend.

## Weekend priority effects

- **Outing:** counts toward Movement; no duplicate exercise
- **Care / Connection:** protects or expands connection time
- **Movement:** receives a modest mode-aware increase
- **Learning:** receives more space while competing optional goals soften
- **Recovery:** makes Learning and Movement optional or gentle
- **Optional Work:** treated as an added constraint around which connection and recovery are protected
- **No focus today:** adds no expectations

## Movement and Learning

Movement may be Baduanjin, Indoor Walk, Outdoor Walk, Stretching, Mobility, Strength, Yoga, Recreation, or Custom.

Learning may be Reading, Studying, Online Course, AI Learning, Research, Skill Practice, Creative Learning, or Custom.

Coach must use the selected activity and adjust effort by mode rather than replacing it.

## Care / Connection and Evening

Coach uses the selected Care / Connection label and time without assuming children or a specific household. Evening guidance may change by care type, but universal wind-down remains separate.

## Adjust Flow sequence

1. Acknowledge the current situation.
2. Identify fixed commitments and essential outcomes.
3. Review incomplete modules and shared daily activity choices.
4. Reduce, reorder, combine, defer, or drop optional work.
5. Protect Care / Connection, Evening Routine, and recovery.
6. Explain the most important tradeoff.
7. Invite acceptance or further adjustment.

## Week and Reflection

Past days may remain not reviewed. Future days must not be treated as commitments. Weekly insight is descriptive, not scored. Reflection should use the actual selected activities and context without grading the user.

## Future calendar influence

```text
Calendar = external constraints
Mode = internal user state
AI Coach = adjusts the daily plan using both
```

Calendar may reserve time, reveal travel or transitions, and simplify optional modules. It cannot infer capacity, replace mode, invent obligations, or remove user control.

## Output expectations

A strong response is actionable, brief, mode-appropriate, consistent with day type and selected activities, inclusive of care context, honest about tradeoffs, and explicit about what changed.
