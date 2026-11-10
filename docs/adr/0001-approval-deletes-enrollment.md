# Approving a refund deletes the enrollment

When an admin approves a refund, we delete the student's enrollment row for that course and keep everything else (the purchase, lesson progress, video watch events, rating, comments). Access to a course is decided by the existence of an enrollment in 18 queries across the app, including the "already enrolled" guard on purchase, so deleting the row removes access everywhere and lets the student buy again with no other change. Progress is stored per student and lesson, so it comes back if they re-buy.

## Considered Options

- **Delete the enrollment (chosen).** One write; every existing access check, list and guard stays correct.
- **Mark the enrollment as revoked** (e.g. a `revoked_at` column). Keeps the enrollment's history, but every one of the 18 enrollment queries must learn to skip revoked rows, and missing one leaks access to a refunded student.

## Consequences

- The enrollment's `enrolled_at` and `completed_at` are lost for approved refunds and cannot be recovered.
- Instructor views built on enrollments (student lists, enrollment counts in analytics) drop the student, including for past date ranges — historical enrollment numbers shrink after a refund.
- Reversing this later means adding a revoked marker, updating every enrollment query, and accepting that rows already deleted are gone. Acceptable because a resolved refund is final.
