# Task Execution & Git Workflow Protocol

To maintain high code quality, system stability, and transparent version control history across all projects:

## 1. Task Decomposition & Planning
- For complex, large, or multi-phase tasks, the agent MUST decompose the work into logical, manageable, and independently verifiable sub-tasks.
- Avoid large monolithic edits across unrelated modules without intermediate validation checkpoints.
- **Interactive Plan Synchronization**: During the planning and discussion phase, whenever the user proposes an idea, adjustment, or design modification that is agreed upon, the agent MUST immediately update the implementation plan (`implementation_plan.md` or active planning artifact). Do not wait for the entire conversation to conclude—keep the plan continuously synchronized so the user can read, review, and build upon it in real time.

## 2. Empirical Verification Before Commits
- Always test and verify changes empirically before committing (run tests, check syntax, or verify endpoints).
- Never assume code or configuration works without validation.

## 3. Atomic Git Commits After Tasks / Sub-Tasks
- After completing a task—or after each distinct, working sub-task of a larger task—the agent MUST execute `git add` and `git commit` with an appropriate, descriptive message.
- **Commit Message Format**: Follow conventional commit conventions:
  - `feat(<scope>): description`
  - `fix(<scope>): description`
  - `docs(<scope>): description`
  - `refactor(<scope>): description`
  - `test(<scope>): description`
- Ensure the commit message details what changed and the rationale behind the change.
- Never leave untracked temporary files or unstaged completed work lingering in the working tree.
- Inform the user when local commits are ready to push to the remote repository.
