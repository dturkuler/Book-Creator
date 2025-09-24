# Book-Creator

Repository to host prompts, templates, checklists, and orchestration assets for the Book Creator project.

## Repo layout
See `/agents/` for agent templates, `/checklists/` for editorial checklists, `orchestrator_prompt.md` for the project-level system instructions, and `manifest.json` for run state tracking.

## Usage
- Copy the agent `.md` files into the ChatGPT Project Docs or keep them in the repo as the canonical source of truth.
- Use GitHub PRs as HITL gates: create a branch per run and open PRs for Editor approval.
- Keep secrets out of the repo. Use GitHub Actions secrets or your automation tool for API keys.

Placeholders to replace before runs:
- `{{BOOK_TITLE}}`, `{{AUTHOR_NAME}}`, `{{TARGET_READERS}}`, `{{GITHUB_ORG}}`, `{{REPO_NAME}}`, `{{TIMESTAMP}}`, `{{RUN_ID}}`.
