# Cadence

An online course platform. Instructors publish courses; students buy them and work through the lessons.

## Language

### People

**Student**:
A person who buys courses and works through their lessons.
_Avoid_: Learner

**Admin**:
A person who runs the platform. Only admins resolve refunds.

### Refunds

**Refund**:
A student's request to give back a purchase and get the money back. When a refund is approved, the student loses access to the course.
_Avoid_: Cancellation, Reversal, Chargeback, Refund Request

**Requested**:
The state of a refund that waits for a decision.
_Avoid_: Pending, Open, Raised

**Approved**:
The state of a refund that was accepted. The student gets the full refund amount back and loses access to the course; their progress is kept.

**Declined**:
The state of a refund that was not accepted. No money goes back, and the student keeps access. The student may request a new refund while the purchase is still eligible.

**Resolved**:
A refund that is approved or declined. A resolved refund is final.

**Decline Reason**:
The admin's note to the student on why a refund was declined.
_Avoid_: Rejection reason, Note

**Refund Amount**:
The money a student gets back for a refund: exactly what the student paid for the purchase.
_Avoid_: Refundable amount, Amount refunded

**Refund Reason**:
The student's own words on why they want a refund.
_Avoid_: Note

**Refund Window**:
The days after a purchase in which a student can ask for a refund, counted in whole calendar days.
_Avoid_: Cancel window, Deadline

**Eligible**:
A purchase that can get a refund now: it is inside the refund window, under the watch limit and the completion limit, not a claimed team seat, and has no requested refund.
_Avoid_: Cancellable, Refundable

**Watch Limit**:
The most video a student can watch in a course and still be eligible for a refund.

**Completion Limit**:
The share of a course's lessons a student can finish and still be eligible for a refund.

**Chargeback**:
A payment that the buyer's bank takes back after the buyer disputes it with the bank. It is not a refund: we do not start it and we do not approve it.
