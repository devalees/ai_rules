# Global Antigravity AI Rules

This repository contains the global rules and operational protocols for **Google Antigravity AI Agents**.
When placed in `~/.gemini/config/rules/`, these rules are automatically loaded into every session, project, and workspace on the machine.

---

## 📁 Included Rules

1. **`coding_and_communication_standards.md`**:
   - **Language Policy**: User communicates in Arabic; Agent strictly responds in English (unless explicitly overridden).
   - **Inquiry vs. Action Protocol**: Inquiries receive technical analysis/discussion without modifying actions; state-changing actions require explicit user direction.
   - **Response Style**: Bullet points preferred, concise yet complete, precise vocabulary, clickable file links.
   - **Pragmatic Coding**: Clean, straightforward code (KISS), descriptive naming, single responsibility.
   - **Commenting & Docstrings**: Mandatory docstrings/comments on functions and classes; minimal and pragmatic inline comments ("why", not "what").

2. **`llm_wiki.md`**:
   - **Auto-Initialization**: Ensures `docs/ai_wiki/` (`index.md`, `architecture.md`, `agent_log.md`) exists in every repository.
   - **Pre-Execution Protocol**: Mandatory inspection of wiki files before making architectural changes or inspecting code.
   - **Post-Execution Protocol**: Mandatory timestamped logging in `agent_log.md` and index synchronization upon completing tasks.

3. **`git_and_task_workflow.md`**:
   - **Task Decomposition**: Breaking large tasks into verifiable sub-tasks.
   - **Empirical Verification**: Testing and verifying before committing.
   - **Atomic Git Commits**: Committing after each task/sub-task with conventional commit format (`feat`, `fix`, `docs`, `refactor`).

---

## 🚀 Setup on a New Machine

To install these rules on a new computer:

```bash
mkdir -p ~/.gemini/config
git clone https://github.com/devalees/ai_rules.git ~/.gemini/config/rules
```

Or to create a desktop shortcut on Linux:
```bash
ln -s ~/.gemini/config/rules ~/Desktop/ai_rules
```
