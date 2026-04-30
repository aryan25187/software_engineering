# Assignment S7 -- Architecture Decision Record

## Decision Scenario

**Authentication Session Management**

### Option A: Server-side Sessions

User logs in and server stores session state.

**Pros** - Easy session invalidation/logout\
- Strong security control\
- Simple for internal systems

**Cons** - Requires session storage\
- Lower horizontal scalability

### Option B: Stateless JWT

User logs in and token is stored client-side.

**Pros** - Highly scalable\
- No server session storage

**Cons** - Harder token revocation\
- More security pitfalls

------------------------------------------------------------------------

## Architecture Decision Record

### Title

Use Server-Side Sessions for Campus Lab Booking Authentication

### Status

Accepted

### Context

Campus Lab Booking requires: - secure authentication\
- GDPR compliance\
- internal university hosting\
- low budget\
- moderate traffic

Scalability is less critical than security and simplicity.

### Decision

Use **server-side session lookup** instead of JWT authentication.

### Consequences

**Positive** - Easier logout/session revocation\
- Lower security complexity\
- Simpler implementation

**Negative** - Session storage required\
- Slightly lower scalability

------------------------------------------------------------------------

## Trade-off Card

  Criterion         Server Sessions   JWT   Why it mattered
  ----------------- ----------------- ----- --------------------------------------
  Cost              4                 4     Low budget project
  Complexity        5                 3     Small team benefits from simplicity
  Security          5                 3     Student data + GDPR
  Scalability       3                 5     Internal system, not internet-scale
  Maintainability   5                 3     Easier debugging and session control

Score: 1 = poor, 5 = strong

------------------------------------------------------------------------

## Personal ADR Method

### Questions

-   What problem are we deciding?\
-   What options exist?\
-   Which criteria matter?\
-   What trade-off is accepted?

### Criteria to Check

-   Cost\
-   Complexity\
-   Security\
-   Maintainability\
-   Scalability\
-   Reversibility

### Common Mistakes

-   Following trends over context\
-   Ignoring team skill\
-   Ignoring operational costs


