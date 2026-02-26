# Metrics and Monitoring Plan

To ensure reliability, performance, and correctness, the following metrics will be monitored.

---

## 1. Performance Metrics

- Average decision latency (target <100ms)
- P95 and P99 latency
- Throughput (events per minute)

---

## 2. Decision Distribution Metrics

- % NOW decisions
- % LATER decisions
- % NEVER decisions
- Suppression rate

This helps detect over-suppression or over-sending.

---

## 3. Duplicate Metrics

- Exact duplicate rate
- Near-duplicate suppression rate

High duplicate rate may indicate upstream issues.

---

## 4. Alert Fatigue Indicators

- Notifications per user per hour
- Users hitting cap limits
- Night-time send rate

---

## 5. AI Service Health

- AI scoring latency
- AI timeout rate
- Fallback activation rate

---

## 6. Error Monitoring

- Failed evaluations
- DB write failures
- Queue backlog size

---

## Alerts

System should trigger alerts if:
- Latency > 200ms
- AI failure rate > 5%
- Suppression rate suddenly spikes
