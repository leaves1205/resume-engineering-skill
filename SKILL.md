---
name: resume-engineering-skill
description: Transforms raw project, internship, open-source, or work experience into a high-density, architecture-first engineering resume. Use when the user asks to write, rewrite, polish, or "engineer" resume bullets, a project section, or an experience section for a software engineering / AI / technical role, or asks how to make their resume sound more senior, technical, or system-design-oriented.
license: MIT
---

# Resume Engineering Skill

## Purpose

Transform raw project experience, internship experience, open-source work, and technical tasks into a **high-density engineering resume** that demonstrates:

- technical depth
- system-design ability
- engineering ownership
- architecture thinking
- problem-solving complexity
- measurable impact
- production awareness
- business value

The resume must make the candidate look like someone who **designed and owned systems**, not merely someone who completed coding tasks.

---

# 1. Core Principle

Never describe work as a list of technologies or responsibilities.

Bad:

> Built an AI agent using LangChain, OpenAI API and React.

Better:

> Designed and implemented a multi-stage agent workflow that decomposes user requests into research, tool-execution and synthesis stages, with structured state passing and failure recovery between nodes.

Best:

> Owned the design and implementation of a multi-stage agent orchestration layer, separating planning, tool execution and synthesis into independently observable nodes; introduced structured state propagation and retry boundaries to prevent single-tool failures from terminating the entire workflow.

Always move descriptions through this progression:

**Technology → Implementation → Architecture → Engineering Decision → Impact**

---

# 2. Resume Thinking Model

For every experience or project, extract six dimensions.

## A. Background

Why did this system or feature need to exist?

Look for:

- product requirement
- business problem
- user pain point
- scalability problem
- reliability issue
- development bottleneck
- manual workflow
- latency/cost problem

Example:

> Existing workflows required manually coordinating multiple LLM calls and tool executions.

---

## B. Goal

What engineering problem needed to be solved?

Examples:

- reduce inference cost
- improve reliability
- support dynamic tools
- automate a manual workflow
- improve deployment consistency
- increase throughput
- reduce developer effort
- support multiple agents
- improve observability

---

## C. Ownership

Explicitly identify what the candidate personally owned.

Prefer phrases such as:

- Owned end-to-end design and implementation
- Designed and implemented
- Led development of
- Responsible for architecture and delivery
- Built from 0→1
- Independently developed
- Drove the redesign of
- Introduced and implemented

Avoid weak phrases such as:

- Helped with
- Participated in
- Worked on
- Assisted with
- Was involved in

Unless collaboration boundaries require them.

---

# 3. Architecture-First Writing

Whenever possible, describe the **architecture** rather than only the feature.

Extract components such as:

- frontend
- backend
- API layer
- orchestration layer
- queue
- worker
- database
- cache
- model layer
- middleware
- agent
- tool registry
- scheduler
- state store
- evaluator
- retrieval layer
- observability layer

Then explain how information moves through them.

Use structures such as:

> Designed `A → B → C → D` workflow...

> Separated X from Y through...

> Introduced an abstraction layer between...

> Built a pipeline consisting of...

> Implemented a lifecycle of...

Example:

> Designed a `Planner → Researcher → Tool Executor → Synthesizer` workflow with shared structured state, enabling independent retry and observability for each execution stage.

This style makes implementation appear as a system rather than isolated code.

---

# 4. The Engineering Bullet Formula

Use the following formula for technical bullets:

**Action + System + Engineering mechanism + Reason/constraint + Result**

Template:

> **[Strong verb] [system/component]**, using **[technical mechanism]** to solve **[engineering constraint/problem]**, resulting in **[measurable or observable impact]**.

Example:

> Built a reusable middleware chain for agent execution, introducing lifecycle hooks around model calls and tool invocation to centralize logging, context injection and failure handling, reducing duplicated orchestration logic across agents.

---

# 5. Three-Layer Bullet Structure

For important projects, organize bullets into three levels.

## Level 1 — What was built

Explain the system at a high level.

> Built an AI-assisted incident investigation system that coordinates log retrieval, hypothesis generation and root-cause analysis.

## Level 2 — How it was engineered

Explain architecture and mechanisms.

> Implemented a coordinator-worker architecture where the lead agent dynamically delegates investigation tasks to specialized sub-agents sharing an isolated incident context.

## Level 3 — Hard engineering problem

Explain one difficult problem in depth.

> Added context compression and selective state persistence to prevent long-running investigations from exceeding model context limits while preserving critical evidence and intermediate conclusions.

This structure creates visible technical depth.

---

# 6. Prefer Engineering Decisions Over Feature Lists

Do not simply say what features exist.

Explain **why an implementation choice was made**.

Weak:

> Added caching.

Strong:

> Introduced Redis caching for repeated retrieval queries to avoid redundant upstream calls and reduce end-to-end response latency.

Weak:

> Used middleware.

Strong:

> Introduced a middleware abstraction around model and tool execution so cross-cutting concerns such as logging, retry, telemetry and context injection could be added without modifying individual agents.

The second version demonstrates engineering judgment.

---

# 7. Surface Hidden Complexity

Whenever raw project notes contain ordinary-looking tasks, search for hidden engineering complexity.

Examples:

### "Called an API"

Rewrite around:

- rate limiting
- retry
- timeout
- concurrency
- batching
- caching
- validation
- schema normalization
- error handling

### "Built an AI agent"

Rewrite around:

- orchestration
- state management
- tool selection
- context lifecycle
- memory
- failure recovery
- evaluation
- observability
- prompt versioning
- cost
- latency

### "Built frontend"

Rewrite around:

- component architecture
- state ownership
- asynchronous state
- rendering lifecycle
- reusable abstractions
- routing
- API boundaries
- accessibility
- performance

### "Built backend"

Rewrite around:

- service boundaries
- data model
- API contract
- concurrency
- transactions
- authorization
- caching
- queueing
- observability
- deployment

Always ask:

> What made this non-trivial?

That answer is often the best resume bullet.

---

# 8. Quantification

Every project should be inspected for possible numbers.

Look for:

- users
- requests
- API calls
- latency
- throughput
- cost
- token usage
- model calls
- test coverage
- deployment frequency
- number of services
- number of agents
- number of tools
- number of supported workflows
- time saved
- manual steps removed
- dataset size
- file count
- concurrency
- success rate
- failure rate
- accuracy
- uptime

Prefer:

> processed 600+ monthly requests

over:

> processed many requests

Prefer:

> reduced workflow construction time from 1–2 hours to 5–15 minutes

over:

> significantly improved efficiency

Never fabricate metrics.

If exact data is unavailable, use verifiable scale:

> supported 8 workflow types

> coordinated 3 specialized agents

> integrated 6 external tools

> handled multi-step workflows spanning API, retrieval and LLM execution

---

# 9. Technical Specificity

Use concrete implementation terminology when it demonstrates real understanding.

Good examples:

- middleware lifecycle
- structured outputs
- schema validation
- state propagation
- retry boundary
- tool registry
- dependency injection
- context isolation
- checkpointing
- async execution
- queue-based processing
- idempotency
- caching
- concurrency control
- streaming
- event-driven architecture
- evaluation pipeline
- observability
- CI/CD
- containerization

Avoid meaningless buzzword chains.

Bad:

> Used AI, LLM, RAG, agents, cloud and microservices to build an intelligent platform.

Every technical noun should correspond to something actually implemented.

---

# 10. Naming Systems

Give substantial systems or mechanisms short technical names.

Examples:

- Agent Harness
- Middleware Chain
- Context Engine
- Evaluation Pipeline
- Tool Registry
- Agent Runtime
- Workflow Engine
- Retrieval Layer
- State Manager
- Failure Recovery Layer
- Skill System

Then explain them.

Example:

> **Context Engine:** introduced selective context loading, compression and isolation policies to prevent unrelated agent state from polluting downstream prompts.

Named abstractions make engineering contributions easier to understand.

Do not invent impressive names for trivial functions.

---

# 11. Use Micro-Headings for Dense Projects

For technically deep projects, group sub-bullets using short component headings.

Example:

- **Agent Harness:** ...
- **Middleware Chain:** ...
- **Skill System:** ...
- **Context Engineering:** ...
- **Evaluation Pipeline:** ...

This is especially useful when one project contains multiple architectural innovations.

---

# 12. Show Scale Before Detail

When a project has impressive scale, surface it early.

Examples:

> Open-source agent framework with 7k+ GitHub stars.

> Production workflow handling 600+ monthly requests.

> Platform supporting 10+ agent tools.

> Evaluation pipeline processing 180k-token trajectories.

Scale establishes credibility before implementation details.

---

# 13. Business + Engineering Together

Professional experience should connect technology to business outcomes.

Use:

**Business problem → Technical system → Operational result**

Example:

> Built an automated report-generation agent for internal operations, combining intent classification, structured tool execution and template-constrained generation; reduced individual report preparation from 1–2 hours to 5–15 minutes.

Do not separate engineering impact from business impact when they are related.

---

# 14. Project Section Template

For every substantial project, produce:

## Project Name | Technical Positioning

One-line positioning:

> Multi-Agent Orchestration + Context Engineering + Tool Runtime

### Background / Goal

1–2 concise bullets explaining why the project exists.

### My Role

Explicit ownership:

> Project owner; designed and implemented the system from 0→1.

### Architecture / Core Contributions

3–5 bullets.

Each bullet should focus on one major technical subsystem.

### Impact

Include measurable results when available.

---

# 15. Experience Section Template

Use:

**Company | Team | Time**

**Role / Project**

Then:

### Background

What business workflow/problem existed?

### Impact

Give measurable result early if impressive.

### My Contributions

Describe:

1. architecture
2. core implementation
3. difficult technical problem
4. reliability/performance improvement
5. business outcome

Professional experience should normally emphasize results more heavily than personal projects.

---

# 16. Open-Source Work

Do not write only:

> Contributor to X.

Instead identify:

- project scale
- role
- module contributed
- PRs/issues
- architecture contribution
- maintenance responsibility

Example:

> Apache project committer contributing to the agent runtime and workflow orchestration modules; reviewed community PRs and maintained core execution paths.

If numbers exist, include them.

---

# 17. Project Ordering

Order projects by **signal strength**, not chronology.

Priority:

1. production/commercial systems
2. technically deep systems
3. open-source projects with real adoption
4. projects with measurable users/revenue
5. strong architecture projects
6. coursework/tutorial projects

For engineering roles, the first project should immediately communicate the candidate's target specialization.

---

# 18. Verb Selection

Prefer:

- architected
- designed
- implemented
- built
- introduced
- developed
- optimized
- automated
- orchestrated
- integrated
- refactored
- migrated
- reduced
- improved
- scaled
- standardized
- isolated
- instrumented

Use "architected" only when actual architecture decisions were made.

---

# 19. Compression

The resume should be dense but not verbose.

For every sentence ask:

1. Does this reveal technical ability?
2. Does this reveal ownership?
3. Does this reveal scale?
4. Does this reveal a difficult engineering decision?
5. Does this reveal impact?

If the answer to all five is no, remove or rewrite it.

Avoid filler:

- successfully
- various
- many
- responsible for
- participated in
- familiar with
- learned
- gained experience in

---

# 20. Do Not Write Tutorial Resumes

If a project comes from a course/tutorial, never pretend the candidate invented the original product.

Instead extract personal engineering work such as:

- architecture understanding
- refactoring
- extensions
- independent implementation
- bug fixing
- additional features
- testing
- deployment
- design decisions

Do not exaggerate ownership.

---

# 21. Truthfulness Rule

Never fabricate:

- users
- revenue
- latency
- scale
- architecture
- ownership
- production usage
- team leadership
- open-source contributions
- performance gains

When information is missing, ask the user.

Use technical reframing, not fictional enhancement.

---

# 22. Information Extraction Workflow

When given raw project information, first silently extract:

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

Do not immediately write resume bullets.

First reconstruct the engineering story.

---

# 23. Follow-Up Questions

If important information is missing, ask targeted questions such as:

- Which parts did you personally implement?
- Was this deployed or only local?
- How many users/requests/jobs did it handle?
- What was the hardest technical problem?
- Did you implement retry/error handling?
- How was state stored?
- How did components communicate?
- Was execution synchronous or asynchronous?
- How did you test it?
- What changed after your implementation?
- Did you measure latency, cost or time saved?
- Did other developers use this system?

Avoid generic questions such as:

> Tell me more about the project.

---

# 24. Output Style

Resume bullets should:

- begin with a strong action or subsystem name
- contain concrete technical nouns
- describe architecture where relevant
- explain difficult mechanisms
- include metrics when available
- avoid first-person pronouns
- avoid vague adjectives
- remain technically defensible in interviews

Target bullet length:

**25–55 words**

Allow longer bullets only when technical context requires it.

---

# 25. Technical Interview Defensibility

Every resume statement must survive:

> "How exactly did you implement that?"

Before keeping a bullet, verify that the candidate could explain:

- architecture
- trade-offs
- implementation
- failure cases
- alternatives considered
- testing
- results

If they cannot, weaken the wording.

The resume should maximize perceived technical depth **without exceeding actual technical depth**.

---

# 26. Final Quality Check

Before returning the resume, score each major project from 0–2 on:

| Dimension | Score |
|---|---|
| Ownership | 0–2 |
| Architecture | 0–2 |
| Technical depth | 0–2 |
| Difficult problem | 0–2 |
| Scale | 0–2 |
| Quantified impact | 0–2 |
| Business relevance | 0–2 |
| Interview defensibility | 0–2 |

A flagship project should ideally score **12+ / 16**.

If it scores lower, identify missing information rather than artificially inflating the writing.

---

# 27. Final Transformation Rule

The final resume should make this transformation:

```text
"I made a project."
        ↓
"I built a system."
        ↓
"I designed how the system works."
        ↓
"I solved non-trivial engineering problems."
        ↓
"I owned an engineering outcome."
```

That transformation is the primary objective of this skill.
