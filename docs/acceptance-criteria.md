# Requirements and Acceptance Cases

## User story

As a student, I enter a future start time, a duration, and the room status, then receive an availability decision with a clear reason. Existing bookings must remain unchanged.

## Acceptance criteria

1. Start time must be in the future.
2. Duration must be a whole number from 1 to 120 minutes.
3. Any overlap with an existing booking makes the slot unavailable.
4. A blocked room is unavailable.
5. Each result includes a readable reason, and booking data is never modified.
6. Invalid inputs receive a clear validation error.
7. Intervals use [start, end), so touching a booking boundary is allowed.

## Fixed data

- Room: Software Engineering Lab, SE-101.
- Test clock: 24 November 2026 at 10:00.
- Bookings on 25 November 2026: 09:00–10:00 and 11:00–12:00.

## Acceptance cases

| ID | Input | Expected result |
| --- | --- | --- |
| T1 | 25 Nov 12:00, 60 min, open | Available |
| T2 | 25 Nov 09:30, 60 min, open | Unavailable due to overlap |
| T3 | 25 Nov 12:30, 60 min, blocked | Unavailable because room is blocked |
| T4 | 25 Nov 12:00, 0 min | Validation error |
| T5 | 25 Nov 12:00, 121 min | Validation error |
| T6 | 24 Nov 09:00, 60 min | Validation error against fixed test clock |
| T7 | 25 Nov 10:00, 60 min, open | Available at adjacent boundaries |
| T8 | Booking data before and after tests | Unchanged |

Both interface views run this same suite and use the same decision function. The low-code page is a labelled workflow simulation, not a build in an external platform.
