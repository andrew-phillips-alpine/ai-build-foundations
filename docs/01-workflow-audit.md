# Workflow Audit

Use this before building anything. The goal is a short, ranked list of fixes with a success measure for each.

## 1. Watch the work

- Sit with the people who do the work, not only the people who manage it.
- Follow one real item from start to finish: a lead, a case, a document, a request.
- Note where it waits, where it is re-keyed, where someone looks something up and where a decision is made.

## 2. Map every step

Write each step as one line: who does it, what goes in, what comes out, how long it takes and how often it happens.

## 3. Classify each step

| Class | Test | Treatment |
|---|---|---|
| Rule | The same input always gives the same output | Plain code or automation, no model |
| AI | Needs reading, summarising, extracting or drafting, and a wrong answer is caught downstream | A model, with a confidence score or source on the output |
| Prediction | Needs a forecast or score learned from history | A statistical or ML model, measured against outcomes |
| Person | Needs judgement, accountability or a relationship | Stays with a person, with better inputs |

Most steps turn out to be rules. Use a model only where a rule cannot do the job.

## 4. Rank the opportunities

Score each candidate fix from 1 to 5 on:

- **Time saved:** hours per week across the team.
- **Frequency:** how often the work repeats.
- **Cost of error:** what a wrong output costs, which lowers the score.
- **Feasibility:** data available, systems reachable, owner willing.
- **Adoption:** whether the people doing the work want it.

Build the top one or two first.

## 5. Write the success measure

Before building, record the baseline, the target, how it will be measured and the point at which the build stops. Use `templates/build-brief.md`.
