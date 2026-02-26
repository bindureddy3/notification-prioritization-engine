# Notification Prioritization Engine

Round 1 – Cyepro AI Team Hiring

## Problem Statement

Users receive too many notifications across multiple services.
This system intelligently decides whether a notification should be:

- NOW (send immediately)
- LATER (defer/schedule)
- NEVER (suppress)

---

## Key Capabilities

- Duplicate prevention (exact + near-duplicate)
- Alert fatigue reduction
- AI-assisted importance scoring
- Human-configurable rule engine
- Clear explainability & audit logs
- Fail-safe fallback strategy
- High-volume, low-latency design

---

## Architecture Overview

Incoming Event  
→ API Gateway  
→ Preprocessor  
→ Deduplication Engine  
→ Rule Engine  
→ AI Scoring  
→ Decision Engine  
→ Audit Logging  

---

## Design Sections

- Architecture
- Decision Logic
- Data Model
- Duplicate Strategy
- Fatigue Handling
- Fallback Strategy
- API Contracts
- Monitoring Plan
- Example Scenarios

---

## Design Principles

- Reliability first
- Explainable decisions
- Configurable rules
- Safe failure handling
- Important notifications are never silently lost

---

## Tools Used

- ChatGPT (for ideation and structuring)
- Final design refined manually
