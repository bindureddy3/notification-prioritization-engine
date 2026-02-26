# Minimal Data Model

---

## 1. Notification Events Table

| Field | Type | Description |
|-------|------|-------------|
| event_id | UUID | Unique event ID |
| user_id | String | User identifier |
| event_type | String | Type of notification |
| message | Text | Notification content |
| score | Integer | AI score |
| decision | Enum | NOW / LATER / NEVER |
| created_at | Timestamp | Event time |

---

## 2. User Notification History

| Field | Type | Description |
|-------|------|-------------|
| user_id | String | User ID |
| sent_count_10min | Integer | Count in last 10 mins |
| sent_count_24hr | Integer | Count in last 24 hrs |
| last_sent_at | Timestamp | Last notification sent |

---

## 3. Suppression Records

Stores:
- dedupe hash
- timestamp
- reason suppressed

---

## 4. Audit Logs

| Field | Type | Description |
|-------|------|-------------|
| event_id | UUID | Linked event |
| decision | String | Final classification |
| explanation | Text | Why decision was made |
| timestamp | Timestamp | Decision time |
