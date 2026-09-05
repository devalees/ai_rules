---
trigger: always_on
---

# Mandatory LLM Wiki & Knowledge Maintenance Protocol

To ensure continuous project memory and architectural integrity across sessions, agents must strictly follow and maintain the project's LLM Wiki system.

## 1. Auto-Initialization
Whenever the agent operates in any repository or workspace:
- Check if the documentation wiki directory `docs/ai_wiki/` exists.
- If `docs/ai_wiki/` does not exist, the agent MUST automatically initialize it with the following core files:
  1. `docs/ai_wiki/index.md` – Project master index, system overview, and current state summary.
  2. `docs/ai_wiki/architecture.md` – Technical stack, database models, directory structure, and business logic.
  3. `docs/ai_wiki/agent_log.md` – Chronological activity log of all AI agent interactions and system changes.

## 2. Pre-Execution Protocol (Read First)
Before inspecting arbitrary files, executing modifying commands, or proposing architectural changes, the agent MUST read:
1. `docs/ai_wiki/index.md` – Master index, active plan link, and current project status.
2. `docs/ai_wiki/architecture.md` – Core tech stack, architectural decisions, and models.
3. `docs/ai_wiki/agent_log.md` – Chronological history of recent changes, fixes, and developments.
4. **Active Implementation Plan**: Follow the active plan link specified in `index.md` / `agent_log.md` to identify exact completed, in-progress, and pending sub-tasks before taking action.

## 3. Post-Execution Protocol (Update Before Concluding)
Before concluding any task or turn that modified code, configuration, or documentation:
1. **Append a timestamped entry** to `docs/ai_wiki/agent_log.md` formatted as:
   ```markdown
   ### YYYY-MM-DD HH:MM:SS+TZ - [Brief Title]
   - **Agent:** Antigravity (Gemini [Model Version])
   - **Active Plan:** [Plan Title](file:///path/to/docs/plans/active_plan.md) — (e.g., Sub-task 1 of 5 completed)
   - **Status:** [Brief Summary of Status]
   - **Details:**
     - [Bullet points of exact changes, files modified, and rationale]
   - **Current State:** [Summary of current system state and next pending step]
   ```
2. **Update Wiki Indexes & Active Plan**:
   - If changes introduce new architectural patterns, models, endpoints, or features, synchronize `docs/ai_wiki/index.md` and `docs/ai_wiki/architecture.md`.
   - Update the active plan's checkbox (`- [x]`) and commit hash upon completing sub-tasks.
