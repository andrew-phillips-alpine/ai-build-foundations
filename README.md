# AI Build Foundations

The operating foundations I use to build AI agents, apps and workflows with Claude Code, and to get teams using them.

My production repositories are private because they hold client data. This repository holds the parts that are safe to share: the protocols, guardrails, Claude Code skills and agents, and templates that every build follows.

Andrew Phillips, Founder, Alpine Systems. Portfolio: https://portfolio.thealpinesystem.com

## How a build runs

1. **Audit the workflow.** Sit with the team, map each step and find where time is lost. See [workflow audit](docs/01-workflow-audit.md).
2. **Agree success measures.** Write the baseline, the target and the stop criteria before building. See the [build brief template](templates/build-brief.md).
3. **Build.** Assemble from proven parts, follow the [build protocol](docs/02-build-protocol.md) and stay inside the [guardrails](docs/03-ai-guardrails.md).
4. **Ship.** A working version runs on real data in about a week, behind a human checkpoint where judgement matters.
5. **Adopt.** Train the team on its own work and track usage. See the [adoption playbook](docs/05-adoption-playbook.md).
6. **Measure and cut.** Compare the result with the success measures, and stop tools that don't earn their place.

## What is here

| Path | What it is |
|---|---|
| `docs/01-workflow-audit.md` | How to audit a team workflow and rank AI opportunities |
| `docs/02-build-protocol.md` | Definition of done and the build sequence |
| `docs/03-ai-guardrails.md` | Rules for agents: human sign-off, cost caps, kill switches, untrusted input |
| `docs/04-multi-tenant-security.md` | Tenant isolation and route authorisation patterns |
| `docs/05-adoption-playbook.md` | How a new tool becomes a habit |
| `claude/CLAUDE.md` | A working-agreement template for Claude Code sessions |
| `claude/skills/` | Claude Code skills: new build, handoff brief |
| `claude/agents/` | Claude Code subagents: route auth auditor |
| `templates/` | Build brief, SOP and handoff templates |

## Principles

- Rules go to plain code, judgement stays with a person, and AI handles the steps in between.
- Every output a person relies on carries a source or a confidence score.
- Nothing destructive or outward-facing happens without a person approving it.
- A build is done when it is proven working, not when it compiles.
- Tools nobody uses are removed.

## License

MIT
