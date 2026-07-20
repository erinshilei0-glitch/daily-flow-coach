# Decision Log

This log records accepted product decisions that define the Daily Flow Coach MVP.

## 1. Use flexible modules instead of strict scheduling

**Decision:** Organize the day around flexible modules rather than minute-by-minute time blocks.

**Status:** Accepted

## 2. Use Good / Steady / Low mode logic

**Decision:** Ask users to select Good, Steady, or Low based on current internal capacity.

**Status:** Accepted

## 3. Use different profiles for weekdays and weekends

**Decision:** Map the three modes to Standard, Flexible, and Minimum Workday or Active, Balanced, and Recovery Weekend.

**Status:** Accepted

## 4. Use customizable Care / Connection

**Decision:** Replace fixed Child Time with configurable Child Care, Couple Time, Elder Care, Family Check-in, Pet Care, Personal Connection, or Custom context.

**Status:** Accepted

## 5. Keep user-selected mode authoritative

**Decision:** AI and future calendar data may inform planning but must not silently change the user's selected mode.

**Status:** Accepted

## 6. Put calendar sync in Phase 2

**Decision:** Exclude live calendar integration from the MVP and begin calendar constraint work after the core experience is validated.

**Status:** Accepted

## 7. Do not require work or a replacement focus module on weekends

**Decision:** Weekends retain six genuine modules and use a separate optional priority. Recovery Weekend may use No focus today.

**Rationale:** Weekend Focus duplicated existing modules and risked recreating work pressure.

**Status:** Accepted

## 8. Let weekend priorities reweight existing modules

**Decision:** Outing, Care / Connection, Movement, Learning, Recovery, Optional Work, and No focus today adjust emphasis without adding completion requirements.

**Status:** Accepted

## 9. Make Movement and Learning customizable per day

**Decision:** Users may choose different Movement and Learning activities for each day. Mode changes effort, not activity.

**Status:** Accepted

## 10. Make Week a descriptive rhythm view

**Decision:** Past days show outcomes or not reviewed, today shows the active plan, and future days remain flexible. Weekly insight is descriptive and non-scored.

**Status:** Accepted

## 11. Separate dynamic care guidance from the universal Evening Routine

**Decision:** Care / Connection guidance changes with the selected type, while tomorrow preparation, reduced stimulation, wind-down, and sleep protection remain universal.

**Status:** Accepted

## 12. Keep reminders mock-only in the MVP

**Decision:** Settings reminder switches demonstrate future preferences but do not schedule notifications or persist.

**Status:** Accepted

## 13. Start with a sample-only Calendar Context Preview

**Decision:** Validate calendar interaction with hard-coded sample events and in-memory choices before selecting or connecting a provider.

**Status:** Accepted

## 14. Review event treatment per instance

**Decision:** The preview lets users classify or correct each event instance. Recurring-series rules and reusable personal rules are deferred.

**Status:** Accepted

## 15. Keep four buffer types distinct

**Decision:** Preparation, transition, decompression, and travel remain separate so the preview can test which distinctions are useful.

**Status:** Accepted

## 16. Treat private busy blocks as uncertain

**Decision:** A private or busy-only event does not become fixed automatically. The user confirms how it constrains the plan.

**Status:** Accepted

## 17. Require explicit one-time module fulfillment

**Decision:** An event may satisfy Movement, Learning, or Care / Connection only when the user explicitly marks it for that plan.

**Status:** Accepted

## 18. Show sleep conflicts as unresolved tensions

**Decision:** When a late fixed event conflicts with a protected sleep boundary, show both and explain the tension. The Coach must not silently remove either.

**Status:** Accepted

## 19. Begin with free/busy-style information

**Decision:** Event titles are not required for the sample preview. Later access to titles requires evidence that the additional detail creates clear user value.

**Status:** Accepted

## 20. Require separate provider authorization

**Decision:** Google Calendar or Outlook evaluation begins only after sample-preview validation. No live connection is authorized by the discovery decision.

**Status:** Accepted
