---
name: new-build
description: Start a new app, agent or workflow build using the build protocol, inventory and guardrails
disable-model-invocation: true
---

# New Build

## Step 1: Load context

Read before anything else:
- The project's inventory of existing components, connectors and engines.
- `docs/02-build-protocol.md`
- `docs/03-ai-guardrails.md`
- `docs/04-multi-tenant-security.md`

## Step 2: Confirm the request

Ask:
1. What is it called?
2. What problem does it solve, and for whom?
3. What are the core features? Keep the list short.
4. How will we know it worked? Fill in `templates/build-brief.md`.

## Step 3: Check the inventory

Never build custom when a part exists. Select existing components, connectors and engines first. Create a new part only when nothing fits, and add it to the inventory.

## Step 4: Build

Schema migration, then routes with tests, then pages, then docs. Follow the guardrails throughout.

## Step 5: Verify

Run the definition of done in `docs/02-build-protocol.md`. Show the proof: test output, build output or a screenshot.

## Step 6: Hand over

Write the docs, open a pull request and record the success measure to check at 30 days.
