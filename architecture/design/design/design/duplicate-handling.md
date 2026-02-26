# Duplicate Prevention Strategy

## Exact Duplicate Detection

If dedupe_key exists:
- Check recent events for same key
- If found within 5 minutes → NEVER

If missing:
- Generate hash from:
  user_id + event_type + message

---

## Near-Duplicate Detection

- Use text similarity (cosine similarity or fuzzy match)
- If similarity > 90% within short window → suppress

---

## Time Window

Duplicates checked within:
- 5 minutes (default)
- Configurable
