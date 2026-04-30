# Local AI Instructions — jasonmcdermott-net

**Purpose:** Workspace-specific context for the jasonmcdermott-net repo
**Status:** Canonical
**Scope:** This workspace only
**Created:** 2026-03-14
**Last Updated:** 2026-04-28
**Version:** 1.0.0

All global rules are in `.living-systems/GLOBAL_AI_INSTRUCTIONS.md`. Read that file first. This file adds workspace-specific context only.

---

## Scope

Personal landing page for Jason McDermott at jasonmcdermott.net. A single-page static site — no build step, no backend, no JavaScript frameworks.

**Workspace code:** `JM`
**Decision prefix:** `DEC-JM`
branch-strategy: main-only

---

## Key Architectural Rules

- Single HTML file with inline CSS — no build tooling, no dependencies beyond Google Fonts
- Deployable as a static page with zero build step
- Edit `index.html` directly

---

## Enqueueing Blacksmith Tasks

Use the `enqueue_task` MCP tool — never raw SQL INSERTs into `brain.blacksmith_queue`, and never `RemoteTrigger`.

**The brief must be committed and pushed to GitHub before calling `enqueue_task`.** The tool fetches the spec file from GitHub at enqueue time and fails immediately if it isn't found. This is intentional: it eliminates the race condition where Smitty would claim a task before the file was reachable.

If the brief isn't on GitHub yet (e.g. you're working locally), pass `spec_content` inline:
```
enqueue_task(task_name=..., spec_path=..., repo=..., spec_content="<brief text>")
```

---

**End Local AI Instructions — jasonmcdermott-net**

---

## Merge Strategy

**This is a main-only repo. There are no persistent feature branches.**

- **Always commit and push directly to `main`.** Never create a branch unless the brief explicitly instructs it.
- **Never reuse an existing remote branch.** If you find yourself on a branch (e.g. from a previous session or a `git checkout`), switch back to `main` before committing: `git checkout main && git pull`.
- **Do not open a pull request** unless the brief's Scope section explicitly says to and gives a reason.

The only exception: schema changes at Structural or Breaking tier may use a PR as a review gate — but only when the brief says so explicitly.

The default assumption for any brief that does not mention branches or PRs: commit and push directly to `main`.
