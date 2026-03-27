# CLAUDE.md

This file auto-loads for Claude Code.

Read these files in order for the context-loading sequence, pre-flight checks, and working rules:
1. `.living-systems/GLOBAL_AI_INSTRUCTIONS.md` — universal rules for all LS-governed repos
2. `LOCAL_AI_INSTRUCTIONS.md` — workspace-specific context for this repo

## Universal Behaviours

- **Auto-start MCP session:** If an MCP server is connected with a `start_session` tool, call it automatically on the first message.
- **Auto-load instructions:** Read the files above automatically before responding.
- **Open Brain:** Follow the MCP server's injected instructions for session management and logging.
