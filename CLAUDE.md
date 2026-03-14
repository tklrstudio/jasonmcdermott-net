# jasonmcdermott.net

Read the project charter before making changes: `_context/CHARTER.md`

## Open Brain Memory

At the start of every session:
1. Call `start_session` with the repo name as the workspace
2. Call `search_memory` to retrieve relevant prior context for the current task

During the session:
3. Call `log_message` after every substantive exchange (decisions, observations, conclusions)

This ensures all AI collaboration in this repo is persistent and searchable across sessions.
