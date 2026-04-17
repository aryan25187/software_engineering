# Assignment S4 - User Story Sheet                              Aryan Dhiman (100001914)


## User Stories

### Story 1 - Student Booking

**User Story:**  
As a chemistry student, I want to book an available lab bench for a specific time slot so that I can complete my practical course.

**Acceptance Criteria:**
1. Given a free bench and time slot  
   When the student confirms booking  
   Then the system assigns the slot and prevents double-booking  

2. Given a booked slot  
   When another student tries to book it  
   Then the system rejects the booking with an error  

3. Given a successful booking  
   When the student views "My Bookings"  
   Then the new booking is listed  

---

# Story 2  Lab Booking Cancellation

**User Story:**
An enrolled student with an existing lab booking can cancel that booking up to a defined cutoff time, 
immediately releasing the slot so it becomes available for other students to book.

**Acceptance Criteria**

1. Given a student is enrolled and has a confirmed booking starting in more than 2 hours  
   When the student cancels the booking  
   Then the booking status becomes "cancelled"  
  

---

2. Given a student has a confirmed booking starting in less than 2 hours  
   When the student attempts to cancel  
   Then the system prevents cancellation  
 

---

3. Given a booking has been successfully cancelled  
   When another enrolled student views the same time slot  
   Then they can select and confirm a new booking for that slot without errors  

---

# S4 cheat sheet

### Failure Mode 1: Vague Role

**Watch for:**
- "As a user"

**Why it"s bad:**
- No clear stakeholder or value  

**Ask:**
- Who exactly is this for?  
- Who benefits?  

**Fix:**
- Use a specific role  
- Add clear value  

---

### Failure Mode 2: Untestable Criteria

**Watch for:**
- fast, user-friendly, intuitive  

**Why it's bad:**
- Cannot verify success  

**Ask:**
- How do we measure this?  
- How would a tester verify it?  

**Fix:**
- Add measurable outcomes  
- Use Given/When/Then  

---

### Failure Mode 3: Too-Big Scope

**Watch for:**
- Multiple features in one story  
- "and" in the sentence  

**Why it's bad:**
- Not estimable  
- Not testable  

**Ask:**
- Can this be built in one iteration?  
- What is the smallest useful part?  

**Fix:**
- Split by action, role, or workflow  

---

## Personal Mistakes

- Wrote "fast" without defining it  
- Combined multiple features into one story  

---

## Go-To Questions

- Who is this for?  
- What value does it provide?  
- How do we test it?  
- What happens if it fails?  
- Can it be built in one iteration?  

---

## Key Insight

A good user story balances:
- Clear role  
- Testable outcome  
- Small scope  

