# CLAUDE.md

This file auto-loads for Claude Code.

Read these files in order for the context-loading sequence, pre-flight checks, and working rules:
1. `.living-systems/GLOBAL_AI_INSTRUCTIONS.md` — universal rules for all LS-governed repos
2. `LOCAL_AI_INSTRUCTIONS.md` — workspace-specific context for this repo

## Universal Behaviours

These apply to every session in every repo/folder:

- **Auto-start MCP session:** If an MCP server is connected with a `start_session` tool, call it automatically on the first message — never wait to be asked.
- **Auto-load instructions:** Read `.living-systems/GLOBAL_AI_INSTRUCTIONS.md` and `LOCAL_AI_INSTRUCTIONS.md` automatically before responding — never wait to be asked.

## Open Brain Memory

At the start of every session:
1. Call `start_session` with the repo name as the workspace
2. Call `search_memory` to retrieve relevant prior context for the current task

During the session:
3. Call `log_message` after every substantive exchange (decisions, observations, conclusions)

This ensures all AI collaboration in this repo is persistent and searchable across sessions.
