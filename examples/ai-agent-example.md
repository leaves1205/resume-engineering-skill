# Example: AI Agent Project

Demonstrates the full workflow from `SKILL.md`: raw notes → silent extraction → three-layer bullets → quality check.

## Raw input (what the user provides)

> I built an AI agent that helps investigate production incidents. It reads logs, comes up with hypotheses about what went wrong, and tries to find the root cause. I used a main agent that hands off work to a couple of sub-agents. Sometimes the investigations got really long and would run out of context, so I had to compress old stuff. It's used by our on-call team, maybe processes 40-50 incidents a month. I built the whole thing myself.

## Step 1 — Extraction (using `templates/project-extraction-template.md`)

```text
Project: Incident Investigation Agent
Purpose: Manual incident investigation was slow and inconsistent across on-call engineers
Users: Internal on-call/SRE team
Scale: ~40-50 incidents/month
My ownership: Sole designer and implementer, 0→1
Architecture: Coordinator-worker — lead agent delegates to specialized sub-agents
Major components: Coordinator agent, log-retrieval sub-agent, hypothesis-generation sub-agent, shared incident context store
Data flow: Coordinator dispatches investigation tasks to sub-agents, sub-agents write findings back to a shared, isolated incident context
Hardest problem: Long-running investigations exceeded the model's context window
Engineering decisions: Coordinator-worker split to parallelize/specialize investigation steps; context compression to survive long investigations
Reliability mechanisms: [ask user — was there retry/error handling on sub-agent failures?]
Performance mechanisms: Context compression, selective state persistence
Testing: [ask user]
Deployment: Used in production by on-call team
Metrics: 40-50 incidents/month (scale only — no latency/time-saved numbers given)
Business impact: [ask user — did this reduce time-to-resolution vs. manual investigation?]
Technologies: [ask user for actual stack]
```

Missing fields (reliability mechanisms, testing, business impact, technologies) should be asked about before finalizing — see below.

## Step 2 — Follow-up questions actually worth asking

- Did sub-agent failures get retried, or did they just fail the whole investigation?
- How was this tested — did you evaluate hypothesis accuracy against known past incidents?
- Do you have a before/after number for time-to-root-cause?
- What model/framework/infra was this built on?

(For this example, assume the user answers: retries existed for failed sub-agent calls with a max of 2 attempts; tested against a set of 15 replayed past incidents; reduced average time-to-root-cause from ~45 minutes to ~12 minutes; built on GPT-4 with a custom Python orchestration layer, no framework.)

## Step 3 — Resume output

### Incident Investigation Agent | Multi-Agent Orchestration + Context Engineering

**My Role:** Project owner; designed and implemented the system from 0→1, deployed to production for the on-call team.

- **Level 1 (what was built):** Built an AI-assisted incident investigation system that coordinates log retrieval, hypothesis generation, and root-cause analysis for the on-call SRE team, replacing ad-hoc manual investigation.
- **Level 2 (how it was engineered):** Implemented a coordinator-worker architecture in which a lead agent dynamically delegates investigation tasks to specialized log-retrieval and hypothesis-generation sub-agents sharing an isolated incident context, with automatic retry (up to 2 attempts) on sub-agent failures to prevent a single tool error from stalling the investigation.
- **Level 3 (hard engineering problem):** Introduced context compression and selective state persistence to prevent long-running investigations from exceeding the model's context window, while preserving the evidence and intermediate conclusions needed for the final root-cause report.
- **Impact:** Validated against 15 replayed historical incidents and deployed to production, reducing average time-to-root-cause from ~45 minutes to ~12 minutes across roughly 40-50 monthly incidents.

## Step 4 — Quality check (§ 26)

| Dimension | Score |
|---|---|
| Ownership | 2 |
| Architecture | 2 |
| Technical depth | 2 |
| Difficult problem | 2 |
| Scale | 1 |
| Quantified impact | 2 |
| Business relevance | 2 |
| Interview defensibility | 2 |

**Total: 15/16** — flagship-quality project.
