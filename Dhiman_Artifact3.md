# Assignment 3

## 1. Analysis of the Brief

### Stakeholders

**Primary (actors):** - Students, Lab assistants, Teaching staff/instructors

**Secondary (non-actors but impacted):** - Dr. Miriam Kasper, University IT department,
Data protection officer, Course coordinators

**Hidden stakeholder:** - Cleaning staff 

**Follow-up question:** Who is responsible for updating the cleaning
status in the system?

------------------------------------------------------------------------

### Three-Bucket Classification

**Functional Requirements (F):** - Book, cancel, view slots - Prevent
double-bookings - Show schedules - Display prep requirements - Track
cleaning status - Block contaminated benches

**Non-Functional Requirements (NFR):** - Mobile-friendly (vague) -
Fast/snappy (vague) - High availability - GDPR compliance - Usability
(no training) - Offline capability

**Constraints (C):** - Kubernetes hosting - No SaaS - Open-source only -
German & English - Hard deadline

------------------------------------------------------------------------

### Four-Colour Markup

**Ambiguity:** "Works offline" - Question: What exact actions must work
offline?

**Hidden Assumption:** Automatic preparation info - Question: Where does
mapping data come from?

**Contradiction:** Offline vs no data loss - Question: How are conflicts
resolved?

------------------------------------------------------------------------

## 2. Requirements Conversation Cheat Sheet

### Stakeholder Mapping

Identify users, beneficiaries, controllers, and hidden roles.

### Requirement Types

-   Functional = does
-   Non-functional = quality
-   Constraint = limitation

### Ambiguity Detection

Look for vague words and missing scope.

### Hidden Assumptions

Check dependencies and ownership.

### Contradictions

Identify conflicting requirements.

### Risk Hotspots

-   Data integrity
-   Concurrency
-   Offline sync
-   Deadlines
-   Dependencies

### Non-Functional Deep Dive

-   Metric
-   Context
-   Validation

### Common Mistakes

-   Accepting vague requirements
-   Missing stakeholders
-   Ignoring integrations
-   Overlooking workflows

### Go-To Questions

-   What happens if it fails?
-   Worst case?
-   Who is responsible?
-   What must never happen?
-   What defines success?

### Key Insight

Simple systems often hide complex logic. Offline + consistency is a
common trap.
