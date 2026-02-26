# Example Decision Scenarios

---

## Scenario 1: Urgent Security Alert

Event:
- event_type: security_alert
- priority_hint: high
- user received 1 notification in last hour

Decision: NOW  
Reason:
- Critical category
- Low recent frequency
- High AI score (92)

---

## Scenario 2: Promotional Offer During Noisy Period

Event:
- event_type: promotion
- user received 6 notifications in last 10 minutes

Decision: LATER  
Reason:
- Fatigue threshold exceeded
- Non-critical category
- Score: 55

---

## Scenario 3: Duplicate Message

Event:
- Same dedupe_key within 2 minutes

Decision: NEVER  
Reason:
- Exact duplicate detected

---

## Scenario 4: Low Priority at Night

Event:
- event_type: product_update
- time: 2:00 AM

Decision: LATER  
Reason:
- Non-urgent
- Night-time deferral policy
