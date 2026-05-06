# Assignment S8 -- Test Thinking Reference

## Feature Under Test

**Lab Bench Booking**

A chemistry student books an available lab bench for a selected time
slot.

System validates: - authentication\
- bench availability\
- cleaning status\
- contamination/out-of-service status

------------------------------------------------------------------------

## Test Cases

### Test 1 -- Successful Booking

**Category:** Normal

**Testing:** Student books available bench

**Setup:**\
- authenticated student\
- free bench\
- valid date/time\
- cleaned bench

**Expected Result:**\
- booking saved\
- confirmation shown\
- visible in My Bookings

------------------------------------------------------------------------

### Test 2 -- Double Booking Prevention ⭐

**Category:** Edge

**Testing:** Two students book same slot

**Setup:**\
- Student A books bench\
- Student B attempts same slot

**Expected Result:**\
- Student A succeeds\
- Student B gets availability error

------------------------------------------------------------------------

### Test 3 -- Unclean Bench

**Category:** Invalid

**Testing:** Booking blocked if bench unclean

**Setup:** Bench marked not cleaned

**Expected Result:**\
- booking rejected\
- cleaning error shown

------------------------------------------------------------------------

### Test 4 -- Contaminated Bench

**Category:** Invalid

**Testing:** Unsafe bench blocked

**Setup:** Bench contaminated

**Expected Result:**\
- booking rejected\
- unavailable shown

------------------------------------------------------------------------

### Test 5 -- Missing Authentication

**Category:** Invalid

**Testing:** Unauthorized booking attempt

**Setup:** User not logged in

**Expected Result:**\
- redirect to login\
- booking blocked

------------------------------------------------------------------------

### Test 6 -- Cancellation Frees Slot

**Category:** Edge

**Testing:** Cancelled booking reopens slot

**Setup:** Existing booking cancelled

**Expected Result:** Slot becomes available immediately

------------------------------------------------------------------------

### Test 7 -- Authentication Service Failure

**Category:** Invalid

**Testing:** Campus SSO unavailable

**Setup:** Authentication provider offline

**Expected Result:**\
- login fails gracefully\
- clear error shown

------------------------------------------------------------------------

## Test Classification Summary

  Test                      Category
  ------------------------- ----------
  Successful booking        Normal
  Double booking            Edge ⭐
  Unclean bench             Invalid
  Contaminated bench        Invalid
  Missing authentication    Invalid
  Cancellation frees slot   Edge
  Auth failure              Invalid

------------------------------------------------------------------------

## Specification Gaps

-   Can students hold overlapping bookings?\
-   Offline booking behavior unclear

------------------------------------------------------------------------

## Personal Test Thinking Reference

### Process

1.  Start from feature spec\
2.  Test happy path\
3.  Break assumptions\
4.  Test boundaries\
5.  Test invalid input\
6.  Test dependency failures

### Categories

-   Normal = intended success\
-   Edge = boundaries/concurrency\
-   Invalid = forbidden/wrong behavior

### Common Mistakes

-   Only testing happy path\
-   Testing implementation instead of spec\
-   Ignoring invalid states

### Key Insight

Good testing is about finding where systems break, not proving
perfection.
