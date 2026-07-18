# Prompt Tests

These scenarios test whether the AI coach respects mode, day type, external constraints, Care / Connection customization, and the product's supportive tone.

## Evaluation criteria

For every scenario, verify that the response:

- Preserves the user's selected mode
- Applies the correct weekday or weekend profile
- Adjusts the full plan rather than one isolated task
- Protects fixed commitments and realistic recovery
- Uses the user's Care / Connection label
- Avoids judgment, pressure, or unsupported assumptions
- Produces a concise, actionable plan

## Test 1: Good weekday with a normal workday

**Prompt**

> It is Tuesday and I feel Good. I have a normal workday, want to finish one main task, spend 30 minutes on AI learning, move my body, handle child play and bedtime at 7:15 PM, and wind down before bed. Build my day.

**Expected response**

- Uses the Standard Workday profile
- Identifies one main work outcome
- Keeps AI Learning and Movement meaningful but bounded
- Protects child play and bedtime around 7:15–8:00 PM
- Includes a clear evening wind-down and sleep target
- Maintains a sustainable pace instead of filling every minute

## Test 2: Low weekday with a busy calendar

**Prompt**

> It is Thursday and I am Low after poor sleep. My calendar is full of meetings from 9:00 AM to 3:30 PM. Adjust my flow.

**Expected response**

- Keeps Low mode and uses the Minimum Workday profile
- Treats meetings as external constraints, not evidence that the user is Good or Steady
- Reduces work to one essential outcome or meeting-only success
- Minimizes or makes AI Learning optional
- Suggests gentle movement, food, transition time, and earlier recovery
- Clearly names what is deferred

## Test 3: Steady weekend with a family outing

**Prompt**

> It is Saturday and I feel Steady. We have a family outing from 11:00 AM to 3:00 PM. I would also like light movement, a little learning, and a calm evening.

**Expected response**

- Uses the Balanced Weekend profile
- Anchors the outing without treating the day like a workday
- Suggests a small, optional learning block
- Counts appropriate outing activity toward Movement when relevant
- Leaves buffer before or after the outing
- Preserves a calm evening and recovery

## Test 4: Sunday therapy day

**Prompt**

> It is Sunday. I feel Steady and have therapy from 2:00 to 3:00 PM with 30 minutes of travel each way. Help me plan a supportive day.

**Expected response**

- Uses the Balanced Weekend profile
- Reserves travel and transition time around therapy
- Avoids overloading the periods immediately before and after
- Suggests gentle modules and space for reflection or recovery
- Does not make assumptions about therapy content
- Keeps the tone practical and respectful

## Test 5: User with no child but couple time

**Prompt**

> I do not have children. My Care / Connection module is dinner and couple time from 6:30 to 8:00 PM. It is a Good weekday. Plan the rest of my day around that.

**Expected response**

- Uses the user's couple-time label and never refers to “Child Time”
- Applies the Standard Workday profile
- Treats 6:30–8:00 PM as a meaningful commitment
- Places work, learning, and movement in feasible earlier windows
- Provides an evening transition after the connection block

## Test 6: User with elder care responsibility

**Prompt**

> It is Wednesday and I feel Low. I need to call my mother's care team at lunch and visit her from 5:30 to 7:30 PM. Adjust my plan so I can manage the essentials.

**Expected response**

- Uses the Minimum Workday profile
- Treats the call and visit as Care / Connection commitments
- Reduces work and learning expectations
- Includes travel, food, and decompression where appropriate
- Protects sleep and avoids suggesting the care commitments be dropped
- Offers a clear, compassionate definition of success for the day

## Failure signals

A response fails testing if it:

- Changes the user's mode without consent
- Applies weekday work expectations to a weekend
- Assumes Care / Connection always means childcare
- Ignores a fixed calendar or care commitment
- Preserves the original task volume after a major disruption
- Removes recovery from a Low plan
- Uses guilt, shame, or productivity pressure
