# Prompt Tests

These scenarios test mode, day type, flexible activities, care context, weekend priorities, external constraints, and supportive tone.

## Evaluation criteria

Every response should preserve mode, apply the correct day profile, adjust the whole plan, protect genuine commitments and recovery, use selected activities and care labels, avoid unsupported assumptions, and remain concise and actionable.

## 1. Good weekday with selected activities

**Prompt:** It is Tuesday and I feel Good. My Learning choice is Reading and my Movement choice is Baduanjin. I have one main work task and Care / Connection at 7:15 PM.

**Expected:**

- Standard Workday
- One main work outcome
- Reading and Baduanjin remain the selected activities
- Meaningful but bounded goals
- Care / Connection and wind-down protected

## 2. Low weekday with a busy calendar

**Prompt:** It is Thursday and I am Low after poor sleep. Meetings run from 9:00 AM to 3:30 PM. My selected Movement is Indoor Walk.

**Expected:**

- Minimum Workday
- Meetings treated as external constraints
- Indoor Walk remains selected but becomes gentle or optional
- Learning reduced or optional
- Recovery protected
- Mode not changed without consent

## 3. Balanced Weekend with Outing

**Prompt:** It is Saturday, I feel Steady, and today's priority is Outing. Plan a family outing from 11:00 AM to 3:00 PM.

**Expected:**

- Balanced Weekend
- Outing counts toward Movement
- No separate exercise requirement
- Learning remains small and optional
- Buffers and calm evening preserved

## 4. Recovery Weekend with no focus

**Prompt:** It is Sunday, I feel Low, and I choose No focus today.

**Expected:**

- Recovery Weekend
- No replacement work or focus task
- Essentials, care, and recovery define success
- Learning and Movement optional
- No guilt or pressure

## 5. Couple Time

**Prompt:** My Care / Connection type is Couple Time from 6:30–8:00 PM. It is a Good weekday.

**Expected:**

- Uses Couple Time wording
- Never shows childcare-specific steps
- Protects the time window
- Universal Evening Routine remains present

## 6. Elder Care

**Prompt:** It is Wednesday and I feel Low. I need to call my mother's care team and visit her from 5:30–7:30 PM.

**Expected:**

- Minimum Workday
- Treats call and visit as Care / Connection
- Does not invent medical tasks
- Includes travel, food, decompression, and sleep protection

## 7. Per-day weekly choices

**Prompt:** Wednesday is Baduanjin and Reading. Thursday is Indoor Walk and Studying. Summarize my week.

**Expected:**

- Preserves different selections by day
- Does not replace activities based on mode
- Describes the weekly rhythm without scoring it
- Future days remain flexible

## 8. Optional weekend work

**Prompt:** It is Saturday and I have a required two-hour work commitment.

**Expected:**

- Treats work as an added commitment, not a weekend default
- Protects Care / Connection and recovery around it
- Does not create a permanent Work module for weekends

## Failure signals

A response fails if it changes mode without consent, applies weekday work expectations to a weekend, duplicates exercise after an outing, replaces the user's selected activity, assumes Care / Connection means childcare, treats future days as commitments, preserves full task volume after disruption, removes recovery from a Low plan, or uses guilt and productivity pressure.
