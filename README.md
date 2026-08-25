# resume-engineering-skill

A [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills) that turns raw project, internship, and open-source experience into a high-density, architecture-first engineering resume.

Instead of listing technologies and responsibilities, it drives every rewrite through:

**Technology → Implementation → Architecture → Engineering Decision → Impact**

## What it does

Given raw notes about a project or job ("I built an AI agent with LangChain and React"), the skill:

1. Silently extracts the underlying engineering story (purpose, ownership, architecture, hardest problem, metrics) before writing anything.
2. Asks targeted follow-up questions when ownership, scale, or results are unclear — never invents them.
3. Rewrites bullets using an **Action + System + Mechanism + Constraint + Result** formula, surfacing hidden complexity (retries, concurrency, state management, etc.) behind ordinary-sounding tasks.
4. Scores each flagship project against an 8-dimension rubric (ownership, architecture, technical depth, difficult problem, scale, quantified impact, business relevance, interview defensibility) before finalizing.
5. Refuses to fabricate users, revenue, latency, scale, or ownership — missing data is a follow-up question, not a made-up number.

See [`SKILL.md`](./SKILL.md) for the full rule set (27 sections covering writing formulas, templates, verb selection, quantification, and truthfulness rules).

## Examples & templates

- [`templates/project-extraction-template.md`](./templates/project-extraction-template.md) — fillable version of the § 22 extraction workflow, used before writing any bullets.
- [`examples/frontend-example.md`](./examples/frontend-example.md) — raw notes → resume bullets for a React dashboard, including a race-condition fix.
- [`examples/backend-example.md`](./examples/backend-example.md) — raw notes → resume bullets for a service-aggregation API with caching and retries.
- [`examples/ai-agent-example.md`](./examples/ai-agent-example.md) — raw notes → resume bullets for a coordinator-worker incident investigation agent.

Each example walks through the full pipeline: raw input → silent extraction → follow-up questions → three-layer bullets → § 26 quality score.

## Installation

### Claude Code (personal skill)

Copy this directory into your personal skills folder:

```bash
git clone https://github.com/<your-username>/resume-engineering-skill.git ~/.claude/skills/resume-engineering-skill
```

Or as a project-local skill, clone it into `.claude/skills/` inside your repo.

### Claude Code (plugin)

Reference this repo as a plugin marketplace entry, or copy `SKILL.md` into `<plugin>/skills/resume-engineering-skill/SKILL.md`.

### claude.ai (Projects)

Upload `SKILL.md` as a project file, or paste its contents into the project's custom instructions.

## Usage

Once installed, invoke it directly:

```
/resume-engineering-skill
```

or simply ask naturally — the skill's `description` frontmatter triggers it automatically:

> "Help me rewrite this project description for my resume: ..."
>
> "Make this experience bullet sound more senior/technical."
>
> "I built a Slack bot that summarizes PRs — turn this into a resume bullet."

## Structure

```
resume-engineering-skill/
│
├── README.md
├── SKILL.md
│
├── examples/
│   ├── frontend-example.md
│   ├── backend-example.md
│   └── ai-agent-example.md
│
├── templates/
│   └── project-extraction-template.md
│
└── LICENSE
```

## License

MIT — see [LICENSE](./LICENSE).
