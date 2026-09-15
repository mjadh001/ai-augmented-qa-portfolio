This repository demonstrates a full-spectrum approach to QA in an AI-Integrated world: 
evaluating AI response quality directly (prompt engineering + LLM evals),
verifying AI-augmented applications work correctly end-to-end (AI-assisted 
test generation + semantic assertions in UI automation), and 
confirming systems hold up under load (performance testing).
Build while transitioning from 15 years of QA experience into AI/LLM-focused quality engineering.

## 1. Prompt Engineering & LLM Evaluation ('response-evals/')
**What's tested:** A media/streaming support chatbot evaluated across 5 scenarios - normal Q&A, 
prompt injection resistance, competitor/off-topic handling, tine under hostility, and context continuity
**What I found:** The buffering question failed because the system prompt scoped the bot to billing-only topics,
revealing a mismatch between prompt design and test design.
**What I would add next:** True multi-turn conversation testing using promptfoo's history feature; a bias/fairness eval slice.

## 2. AI- Augmented UI Automation ('ui-and-performace/')
**What's tested:** A playwright suite covering login (happy path + edge cases), a full checkout flow, AI-generated
edge-case suggestions (human-reviewed) and a semantic LLM-based assertion on dynamic confirmation text.
**What I found:** An AI-suggested test case revealed the login field doesn't trim whitespace on username input - 
a real, previously unverified behavior.
**What I would add next:** Visual regression testing via screenshot comparison; CI/CD integration via GitHub Actions.

## 3. Performance Testing ('ui-and-performance/load_test.js')
**What's tested:**  K6 load test simulating 10 concurrent users against a test API over 30 seconds.
**What I found:** All requests returned successfully within acceptable response time thresholds.
**What I would add next:** Load testing against an actual AI-backed endpoint to measure how LLM API latency affects performance
under concurrent load - directly relevant to my current work building a performance framework at my job.


