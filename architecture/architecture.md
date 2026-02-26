# Architecture Overview

The Notification Prioritization Engine evaluates every incoming notification
event and classifies it as:

- NOW
- LATER
- NEVER

The system is designed for:
- High throughput
- Low latency
- Explainability
- Reliability
- Human-configurable rules

---

## High-Level Flow

Incoming Event  
→ API Gateway  
→ Preprocessor  
→ Deduplication Engine  
→ Rule Engine  
→ AI Scoring Service  
→ Decision Engine  
→ Audit Logger  
→ Output (NOW / LATER / NEVER)

---

## Components

### 1. API Gateway
- Accepts incoming notification events
- Performs authentication and rate limiting
- Routes traffic to evaluation service

### 2. Preprocessor
- Validates required fields
- Normalizes event structure
- Adds missing dedupe hash if needed

### 3. Deduplication Engine
- Prevents exact duplicate notifications
- Detects near-duplicate messages
- Uses time-window comparison

### 4. Rule Engine
- Applies configurable business rules
- Stored in database or config file
- Allows rule updates without deployment

### 5. AI Scoring Service
- Assigns importance score (0–100)
- Considers:
  - event type
  - priority hint
  - user history
  - time sensitivity
- Optional but improves decision quality

### 6. Decision Engine
- Combines:
  - Hard rules
  - AI score
  - User fatigue state
- Produces final classification:
  NOW / LATER / NEVER

### 7. Audit Logger
- Logs:
  - Input event
  - Decision
  - Explanation
  - Score
- Ensures explainability and auditability
