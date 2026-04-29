# Assignment S5 -- Feature Specification Cheat Sheet

## Feature: Lab Bench Booking

### Related User Story

As a chemistry student, I want to book an available lab bench for a
specific time slot so that I can complete my practical course.

## Inputs

-   Student login (campus SSO)
-   Selected lab
-   Selected bench
-   Date
-   Time slot
-   Practical course/experiment

## Outputs

**Success** - Booking confirmation - Booking saved - Visible in My
Bookings

**Failure** - Clear error message

## Normal Flow

1.  Student logs in
2.  Opens booking page
3.  Selects lab, bench, date, time, experiment
4.  System validates:
    -   availability
    -   cleaning status
    -   contamination/out-of-service
5.  If valid:
    -   save booking
    -   confirm success

## Error Cases

-   Bench already booked → reject + error
-   Bench not cleaned → reject + error
-   Contaminated/out of service → reject
-   Save/database failure → immediate error

## Edge Cases

-   Two students book same bench simultaneously → first wins
-   Cancellation frees slot immediately
-   Session timeout → re-authenticate
-   Offline attendance confirmation allowed only after sync

## Rules / Constraints

-   Authentication required
-   Data stored in EU
-   No SaaS
-   Hosted on university Kubernetes
-   Unsafe benches cannot be booked

## Gap Hunt

**Missing Case:** Can students book overlapping slots?

**Unclear Rule:** Who updates cleaning status?

------------------------------------------------------------------------

# Personal Feature Specification Cheat Sheet

## Process

1.  Start from user story
2.  Define inputs
3.  Define outputs
4.  Write happy path
5.  Hunt error cases
6.  Hunt edge cases
7.  Extract rules/constraints
8.  Find missing or unclear cases

## Always Check

-   Invalid input
-   Permission issues
-   Resource conflicts
-   Network/database failures
-   Concurrency
-   Timeouts

## Common Mistakes

-   Forgetting edge cases
-   Ignoring contradictions
-   Assuming missing workflows are defined

## Final Check

A feature spec is ready only if: - Developer can build it - Tester can
test it - Stakeholder can validate it

## Key Insight

A feature is complete only when failure cases are as clear as the happy
path.
