# Global Coding, Documentation & Communication Standards

A pragmatic, lightweight standard designed for clarity, efficiency, and zero unnecessary overhead.

---

## 1. Communication & Response Style
- **Language Policy**:
  - The user frequently speaks or writes in Arabic.
  - The agent MUST ALWAYS respond in **English** unless the user explicitly requests Arabic (or another language).
- **Structure & Formatting**:
  - **Bullet Points Preferred**: Use clear, scannable bullet points rather than long narrative paragraphs.
  - **Concise Yet Complete**: Deliver direct answers without conversational filler or pleasantries, while ensuring the full technical meaning and rationale are conveyed.
  - **Terminology & Phrasing**: Use precise, professional technical vocabulary. Keep headings and sections well-defined.
  - **File Links**: Always link referenced files with clickable Markdown links (`file:///path/to/file`).
- **Inquiry vs. Action Protocol (Strict)**:
  - When the user asks a question, raises an issue, brainstorms, or requests advice/opinions (e.g., *"What do you think about X?"*, *"Could we do Y?"*, *"Think with me about Z"*), the user expects an **informative answer, technical analysis, or discussion**, NOT immediate modifying actions.
  - The agent MAY run read-only tools and commands (e.g., `view_file`, `grep_search`, `git status`) to investigate the codebase and provide an accurate answer.
  - The agent MUST NOT modify code, change files, or execute state-changing actions unless the user explicitly directs it to act (e.g., *"Implement this"*, *"Take action"*, *"Apply the fix"*).
  - If the user's intent is ambiguous, provide the analysis and recommended solution first, then wait for explicit confirmation.

---

## 2. Pragmatic Coding Principles
- **Keep It Simple (KISS)**: Write clean, straightforward, readable code. Avoid unnecessary abstractions, premature optimization, or complex design patterns for simple tasks.
- **Descriptive Naming**: Use clear, self-explanatory variable and function names (e.g., `calculate_ending_balance` instead of `calc_eb`).
- **Single Responsibility**: Keep functions focused on doing one thing well. Break oversized functions into smaller, digestible helpers.
- **Defensive & Explicit**: Handle likely edge cases and catch specific exceptions; avoid silent failures or bare `except:`.

---

## 3. Function Comments & Documentation
- **Function / Method Level (Mandatory)**:
  - Every function, method, and class must have a concise docstring or top-level comment.
  - Briefly state **what it does**, its **key inputs/outputs**, and any important assumptions.
- **Inline Comments (Pragmatic & Minimal)**:
  - Do **NOT** comment on obvious, self-explanatory code (e.g., avoid `i += 1  # increment counter`).
  - Use inline comments **only** to explain non-obvious business logic, mathematical formulas, or bug workarounds ("explain *why*, not *what*").
- **Clean Codebase**:
  - Never leave commented-out dead code. Delete unused code and rely on Git history.
