# Decision Logic Design

The system uses a layered decision strategy.

---

## Step 1: Hard Rules (Highest Priority)

These rules override all others.

- If event is expired → NEVER
- If exact duplicate → NEVER
- If critical system alert → NOW
- If user disabled channel → NEVER

---

## Step 2: Alert Fatigue Check

The engine evaluates recent user activity:

- If >5 notifications in last 10 minutes:
  - Only high-priority events allowed NOW
  - Others → LATER

- If >20 notifications in 24 hours:
  - Promotions → NEVER
  - Medium priority → LATER

---

## Step 3: AI-Based Scoring

Each event receives a score between 0 and 100.

Score factors:
- Event type weight
- Priority hint
- Time sensitivity
- User engagement history
- Recency of similar notifications

---

## Final Classification

| Score Range | Decision |
|-------------|----------|
| 80–100      | NOW      |
| 40–79       | LATER    |
| <40         | NEVER    |

---

## Example Explanation Log

Decision: LATER  
Score: 62  
Reason:
- User received 4 notifications in last 5 minutes
- Event not time-sensitive
- Medium priority category
