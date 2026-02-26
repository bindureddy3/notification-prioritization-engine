# Fallback Strategy

## If AI Service Fails
- Use rule-based scoring only
- Default to priority_hint
- Log fallback mode activated

## If Database Unavailable
- Queue event in message broker
- Retry processing

## If High Latency
- Use cached user frequency stats
- Return decision under 100ms target
