# API Contracts

## 1. POST /evaluate-notification

Input:
{
  "user_id": "123",
  "event_type": "message",
  "message": "New message",
  "priority_hint": "high"
}

Output:
{
  "decision": "NOW",
  "score": 88,
  "explanation": "High priority and no recent fatigue"
}

---

## 2. GET /user-stats/{user_id}

Returns user notification counts.

---

## 3. POST /update-rules

Updates business rules dynamically.
