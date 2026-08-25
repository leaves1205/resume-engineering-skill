# Example: Frontend Project

Demonstrates rewriting "built frontend" into architecture-level bullets (`SKILL.md` § 7).

## Raw input (what the user provides)

> I built a dashboard for our team to monitor deployments. It shows live status of deployments across a few environments. Data updates automatically without refreshing the page. I used React. There was a bug where the UI would show stale data if you switched environments quickly, so I had to fix the state management. Whole team uses it now, maybe 15 people.

## Step 1 — Extraction

```text
Project: Deployment Monitoring Dashboard
Purpose: Team needed live visibility into deployment status across environments; previously checked manually via CLI/logs
Users: ~15 internal team members
Scale: Multiple environments monitored simultaneously
My ownership: Built the dashboard (confirm sole implementer with user)
Architecture: React frontend with real-time data updates (likely polling or websockets — confirm)
Major components: Dashboard UI, environment-switching state, live-update mechanism
Data flow: Backend/API pushes or is polled for deployment status → UI renders per-environment state
Hardest problem: Stale data shown when switching environments quickly — a state/race-condition bug
Engineering decisions: Fixed by redesigning state ownership around environment switches
Reliability mechanisms: [ask user — was there a fix beyond the immediate bug, e.g. request cancellation?]
Performance mechanisms: Live updates without full page refresh
Testing: [ask user]
Deployment: Used by whole team, ~15 people
Metrics: 15 users, multiple environments (no latency/adoption numbers given)
Business impact: [ask user — did this replace manual status-checking? how much time did that take?]
Technologies: React, [ask user for data-fetching approach: polling, websockets, SWR/React Query, etc.]
```

## Step 2 — Follow-up questions worth asking

- What caused the stale-data bug technically — was it a race condition between in-flight requests for different environments?
- How did you fix it — request cancellation, request IDs, key-based re-fetching?
- Was data pushed (websockets/SSE) or polled?
- What did people do before this dashboard existed, and how long did it take?

(Assume the user answers: it was a race condition — switching environments fired a new fetch before the old one resolved, and the old response could land after the new one and overwrite it; fixed using request cancellation with AbortController keyed by environment; data is polled every 5 seconds; before this, engineers checked deployment status via CLI/logs per environment, taking a few minutes per check.)

## Step 3 — Resume output

### Deployment Monitoring Dashboard | Real-Time Frontend + State Management

**My Role:** Sole frontend engineer; designed and implemented the dashboard end-to-end.

- **Level 1 (what was built):** Built a React dashboard giving the team live visibility into deployment status across multiple environments, replacing manual per-environment CLI/log checks.
- **Level 2 (how it was engineered):** Implemented a polling-based live-update layer (5-second interval) that refreshes deployment state without full-page reloads, with environment-scoped state so each environment's view updates independently.
- **Level 3 (hard engineering problem):** Diagnosed and fixed a race condition where rapidly switching environments could let a stale in-flight request resolve after a newer one and overwrite current state; resolved it with AbortController-based request cancellation keyed by environment, eliminating stale-data display.
- **Impact:** Adopted by the full team (~15 engineers), replacing manual per-environment status checks that previously took a few minutes each.

## Step 4 — Quality check (§ 26)

| Dimension | Score |
|---|---|
| Ownership | 2 |
| Architecture | 1 |
| Technical depth | 2 |
| Difficult problem | 2 |
| Scale | 1 |
| Quantified impact | 1 |
| Business relevance | 1 |
| Interview defensibility | 2 |

**Total: 12/16** — resume-ready. The race-condition fix is a genuinely strong, interview-defensible bullet (§ 25); quantified/business-impact scores are capped because no hard time-saved number was given — worth asking for one if this project needs to carry more weight on the resume.
