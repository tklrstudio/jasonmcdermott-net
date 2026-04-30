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
