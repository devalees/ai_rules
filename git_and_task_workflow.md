---
trigger: always_on
---

# Task Execution & Git Workflow Protocol

To maintain high code quality, system stability, and transparent version control history across all projects:

## 1. Task Decomposition & Persistent Implementation Planning
- **Persistent Repository Plans**: Implementation plans MUST NOT exist solely in transient agent memory or temporary scratch directories. Every multi-step task or project must maintain a persistent, tracked Markdown plan located in the repository (e.g., `docs/plans/active_plan.md` or `docs/implementation_plan.md`).
- **Standardized Checkbox Progress Tracking**: Plans must use explicit markdown task lists indicating status, verification, and commits:
  - `- [x] **Sub-task 1: [Name]** - COMPLETED (Commit: `a1b2c3d`)`
  - `- [/] **Sub-task 2: [Name]** - IN PROGRESS`
  - `- [ ] **Sub-task 3: [Name]** - PENDING`
- **Dynamic Real-Time Plan Synchronization**: Whenever an idea, adjustment, or design modification is agreed upon, or when a sub-task is completed and verified, the agent MUST immediately update the plan file in the repository (checking off `- [x]` and recording the commit hash).
- **Verifiable Decomposition**: Decompose large tasks into independently testable and verifiable milestones. Avoid monolithic edits across unrelated modules.

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

## 4. Services, Databases & Containerization (Docker)
- When a project requires backend infrastructure or database services (such as PostgreSQL, Redis, Celery, or background task runners), the agent MUST configure and manage these services using **Docker** and **Docker Compose** (`Dockerfile`, `docker-compose.yml`) rather than installing or running database servers directly on the bare-metal host.
- Always provide clean, production-parity container configurations with sensible defaults, persistent volume mappings, and decoupled environment variables (`.env`).
- Before binding host ports in `docker-compose.yml`, inspect existing running containers (`docker ps`) to prevent port collisions.
