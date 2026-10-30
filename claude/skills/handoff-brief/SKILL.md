---
name: handoff-brief
description: Required format for any handoff or continuation note. Load before writing one.
---

# Handoff Notes Are Self-Contained Cold-Start Briefs

If the project defines its own handoff format, that format wins. Use this as the fallback.

A handoff must let a fresh session with no prior context verify the state and continue with minimal exploration. It is never a bare task list. Always include:

1. A status banner with an absolute date.
2. **START HERE:** read-only verification commands, and a guard: "if this doesn't match, it's a different problem."
3. What was done and why.
4. Environment and access: how to connect, where things run, how deploys work.
5. Schema and system flow: key tables and the end-to-end pipeline.
6. Scope, with a recommended build order and acceptance criteria.
7. Binding rules.
8. Known landmines.
9. An ordered read-first list.

Cite durable anchors: commit SHAs merged to `main`, not just a pull request number. Tell the reader how to confirm they are on current `main`, and that a referenced file they can't find means the wrong branch, not a gap.

Re-read the draft and ask: could a session with no memory act on this after ten minutes of verification? If environment, schema or flow is missing, add it.

See `templates/handoff.md`.
