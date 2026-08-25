# Project Extraction Template

Fill this out **before** writing any resume bullets. This is the "silent extraction" step from `SKILL.md` § 22 — do it first, then write the resume from the filled-in answers, not from the raw notes directly.

Leave a field blank (don't guess) if the information isn't known yet — blank fields become follow-up questions.

```text
Project:
Purpose:
Users:
Scale:
My ownership:
Architecture:
Major components:
Data flow:
Hardest problem:
Engineering decisions:
Reliability mechanisms:
Performance mechanisms:
Testing:
Deployment:
Metrics:
Business impact:
Technologies:
```

## Field guide

| Field | What to capture |
|---|---|
| **Project** | Name, or a working name if unnamed. |
| **Purpose** | The business/product/user problem it solves — see § "A. Background". |
| **Users** | Who used it: end users, internal team, other developers, none (personal project). |
| **Scale** | Requests/day, users, data volume, GitHub stars, number of services/agents/tools — anything numeric or verifiable. |
| **My ownership** | What you personally designed/built vs. what was inherited, templated, or built by teammates. Be exact — this determines which verbs you're allowed to use (§ C). |
| **Architecture** | The system's shape: `A → B → C` pipeline, coordinator-worker, event-driven, layered, etc. |
| **Major components** | Frontend, backend, API layer, queue, worker, database, cache, model layer, agent, tool registry, etc. — see § 3. |
| **Data flow** | How information moves between components; where state lives and how it's shared. |
| **Hardest problem** | The one thing that was genuinely non-trivial to solve — this is usually the best bullet (§ 7, § 25). |
| **Engineering decisions** | Choices made and *why* (not just what was used) — see § 6. |
| **Reliability mechanisms** | Retry, timeout, failure recovery, idempotency, error handling, validation. |
| **Performance mechanisms** | Caching, batching, concurrency, streaming, async execution. |
| **Testing** | Unit/integration/e2e tests, eval pipelines, manual QA — whatever actually happened. |
| **Deployment** | Local only, staging, production, CI/CD, containerization. |
| **Metrics** | Any real numbers: latency, throughput, cost, time saved, error rate, adoption — never fabricated (§ 8, § 21). |
| **Business impact** | What changed for the team/company/users as a result. |
| **Technologies** | Concrete stack — used to support claims, not as a buzzword list (§ 9). |

## If fields are missing

Ask targeted questions instead of guessing — see `SKILL.md` § 23 for the question bank. Examples:

- Which parts did you personally implement?
- Was this deployed or only local?
- How many users/requests/jobs did it handle?
- What was the hardest technical problem?
- Did you implement retry/error handling?
- Did you measure latency, cost, or time saved?

## Final check

Before writing bullets from this template, score the project against `SKILL.md` § 26:

| Dimension | Score (0–2) |
|---|---|
| Ownership | |
| Architecture | |
| Technical depth | |
| Difficult problem | |
| Scale | |
| Quantified impact | |
| Business relevance | |
| Interview defensibility | |

A flagship project should score **12+ / 16**. If it scores lower, go back and fill in missing fields rather than inflating the wording.
