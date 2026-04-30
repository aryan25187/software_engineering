# Assignment S6 -- System Decomposition Guide

## System Components

### 1. User Interface

**Responsibility:** Provides web/mobile screens for students and staff.\
**Talks to:** Authentication Service, Booking Service, Schedule Service

### 2. Authentication Service

**Responsibility:** Validates campus login and user identity.\
**Talks to:** Campus SSO, User Interface

### 3. Booking Service

**Responsibility:** Creates, updates, and cancels bookings while
enforcing rules.\
**Talks to:** Booking Database, Cleaning Status Service, Notification
Service

### 4. Cleaning Status Service

**Responsibility:** Tracks cleaning timestamps and bench readiness.\
**Talks to:** Booking Service, Cleaning Database

### 5. Schedule Service

**Responsibility:** Generates daily schedules.\
**Talks to:** Booking Database, User Interface

### 6. Notification Service

**Responsibility:** Sends confirmations and reminders.\
**Talks to:** Booking Service, Email System

### 7. Booking Database

**Responsibility:** Stores bookings, users, labs, benches.\
**Talks to:** Booking Service, Schedule Service

### 8. Cleaning Database

**Responsibility:** Stores cleaning logs and contamination status.\
**Talks to:** Cleaning Status Service

------------------------------------------------------------------------

## Feature Trace: Student Books a Slot

1.  Student enters request via **User Interface**\
2.  Login verified by **Authentication Service**\
3.  Request handled by **Booking Service**\
4.  Cleaning checked by **Cleaning Status Service**\
5.  Booking saved in **Booking Database**\
6.  Confirmation sent via **Notification Service**\
7.  Schedule updated through **Schedule Service**

**End:** Booking stored and visible.

------------------------------------------------------------------------

## Personal System Decomposition Guide

### Questions to Ask

-   Where does interaction begin?\
-   Where is business logic?\
-   Where is data stored?\
-   What external systems exist?\
-   Which responsibilities change independently?

### Patterns

-   Separate UI, logic, storage, integrations\
-   Authentication is usually separate\
-   Notifications often isolated

### Hardest Part

Operational logic (like cleaning workflows) is often hardest to place.

### Common Mistakes

-   Components too broad
-   Mixing UI + logic
-   Forgetting external dependencies

### Gap Rule

If feature trace gets stuck -> decomposition missing a component.

