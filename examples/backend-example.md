# Example: Backend Project

Demonstrates rewriting an ordinary-sounding backend task by surfacing hidden complexity (`SKILL.md` § 7).

## Raw input (what the user provides)

> I built the backend API for our internal reporting tool. It pulls data from a few different services, combines it, and returns reports. Some of the upstream calls were slow so I added caching. Also added retries because one of the services was flaky. It's used by maybe 30 people internally, a few hundred requests a day.

## Step 1 — Extraction

```text
Project: Internal Reporting API
Purpose: Teams needed combined reports from multiple internal services; no existing aggregation layer
Users: ~30 internal users
Scale: A few hundred requests/day
My ownership: Built the backend API (assume sole implementer unless told otherwise — confirm with user)
Architecture: API layer aggregating data from multiple upstream services
Major components: API layer, upstream service clients, cache, retry layer
Data flow: Client request → API layer fans out to upstream services → responses combined → cached → returned
Hardest problem: One upstream service was flaky/unreliable; another was slow
Engineering decisions: Added caching to avoid redundant slow upstream calls; added retry for the flaky service
Reliability mechanisms: Retry logic for the flaky upstream service
Performance mechanisms: Caching for slow upstream calls
Testing: [ask user]
Deployment: [ask user — production/internal only?]
Metrics: ~30 users, a few hundred requests/day (no latency numbers given)
Business impact: [ask user — did this replace a manual process? how long did reports take before?]
Technologies: [ask user for actual stack]
```

## Step 2 — Follow-up questions worth asking

- What did the retry strategy actually look like — fixed attempts, backoff, circuit breaker?
- What was cached, and for how long — was staleness a concern?
- Was there a manual process this replaced, and how long did that take?
- What was the stack (language, framework, cache technology)?

(Assume the user answers: exponential backoff retry with a 3-attempt cap on the flaky service; Redis cache with a 5-minute TTL on aggregated report data; replaced a process where analysts manually pulled data from each service and combined it in spreadsheets, taking ~1 hour per report; built in Python/FastAPI with Redis.)

## Step 3 — Resume output

### Internal Reporting API | Service Aggregation + Reliability Engineering

**My Role:** Sole backend engineer; designed and implemented the aggregation API end-to-end.

- **Level 1 (what was built):** Built a backend API in Python/FastAPI that aggregates data from multiple internal services into unified reports, replacing a manual process where analysts assembled reports by hand from each service.
- **Level 2 (how it was engineered):** Designed a fan-out aggregation layer that queries upstream services in parallel and combines results into a single report response, with Redis caching (5-minute TTL) on aggregated results to avoid redundant calls to slow upstream services.
- **Level 3 (hard engineering problem):** Added exponential-backoff retry (up to 3 attempts) around calls to a flaky upstream service to prevent transient failures from breaking report generation, isolating that instability from the rest of the aggregation pipeline.
- **Impact:** Reduced report preparation from ~1 hour of manual work to a single API call, now used by ~30 internal users generating a few hundred reports daily.

## Step 4 — Quality check (§ 26)

| Dimension | Score |
|---|---|
| Ownership | 2 |
| Architecture | 1 |
| Technical depth | 1 |
| Difficult problem | 1 |
| Scale | 1 |
| Quantified impact | 2 |
| Business relevance | 2 |
| Interview defensibility | 2 |

**Total: 12/16** — solid, resume-ready; not flagship-tier because the architecture and difficult-problem depth are moderate rather than deep. If this were the candidate's top project, it would be worth asking for more detail on the aggregation logic (e.g., partial-failure handling: what happens if one upstream service fails but others succeed?) to push those scores higher.
