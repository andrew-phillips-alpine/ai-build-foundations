# Build Protocol

Binding rules for any session that adds or changes an app, agent or workflow.

## Sequence

1. **Confirm the request:** name, problem, target user and core features. Keep it tight.
2. **Check the inventory.** If a component, connector or engine already exists, use it. Assembly beats custom building.
3. **Write the intent first:** the purpose, data model, routes, external services and who can access what.
4. **Build in order:** schema migration, then routes with tests, then pages, then docs.
5. **Verify against the definition of done.**
6. **Open a pull request.** Nothing reaches production except through review and CI.

## Definition of done

- [ ] Type check is clean, tests pass and the production build succeeds.
- [ ] Every new route follows one of the authorisation patterns in `04-multi-tenant-security.md` and has tests for the 401 and 403 cases.
- [ ] New tables have row-level security with tenant isolation.
- [ ] External calls go through a connector layer with a mock mode, never a vendor SDK called directly from a page.
- [ ] The change is proven working: test output, a query result or a screenshot. "It compiles" is not done.
- [ ] Docs updated: what it does, how to run it and what it depends on.
- [ ] Files are staged by explicit path. Never stage everything at once.

## Architecture rules

- **Shell isolation:** the shared runtime never contains app-specific logic. App code lives in its own folder.
- **Connectors:** every external service sits behind one wrapper that declares its secrets, supports a mock mode and logs usage.
- **Model choice:** pick the cheapest model that passes the evaluation for each step, and escalate per step, not per pipeline.
- **One config place** for model IDs, prices and limits.

## Git rules

- Branch from current `main`, open a pull request and let CI gate the merge.
- Never force-push to `main`.
- Never commit secrets, environment files, client data or large data files.
- A pre-commit hook blocks commits that delete an unusual number of files.
