# Decision Log

This log records product decisions that define the Daily Flow Coach MVP and guide future work.

## 1. Use flexible modules instead of strict scheduling

**Decision:** Organize the day around flexible modules rather than minute-by-minute time blocks.

**Rationale:** Capacity and responsibilities change. Modules provide structure while allowing the plan to adapt without making the user feel that the entire day has failed.

**Status:** Accepted

## 2. Use Good / Steady / Low mode logic

**Decision:** Ask users to select Good, Steady, or Low based on their current internal capacity.

**Rationale:** Three simple modes make adaptation understandable and actionable without requiring a clinical or overly detailed self-assessment.

**Status:** Accepted

## 3. Use different mode logic for weekdays and weekends

**Decision:** Map the same three modes to different weekday and weekend profiles.

**Rationale:** A Good weekday and a Good weekend should not produce the same expectations. Separate profiles prevent work-centric assumptions from dominating personal time.

**Status:** Accepted

## 4. Rename Child Time to a customizable Care / Connection Module

**Decision:** Use Care / Connection as the product module and allow the user to customize its meaning.

**Rationale:** A fixed child-focused label excludes people with other relationship and care responsibilities. The customizable module can support child play and bedtime, couple time, elder care, family check-ins, pet care, personal connection, or custom needs.

**Status:** Accepted

## 5. Keep user-selected mode after future calendar sync

**Decision:** Calendar data may inform planning but must not silently change the user's selected mode.

**Rationale:** Calendar events describe external constraints; mode describes internal state. A full calendar does not reveal the user's energy, mood, sleep quality, or capacity.

**Status:** Accepted

## 6. Put real calendar sync in Phase 2, not MVP

**Decision:** Exclude live calendar integration from MVP core and introduce it only after the core planning experience is validated.

**Rationale:** The MVP can test the central value proposition without permissions, provider APIs, synchronization errors, or production data handling. Future calendar data will improve constraint awareness while mode remains the user's internal-state input.

**Status:** Accepted
