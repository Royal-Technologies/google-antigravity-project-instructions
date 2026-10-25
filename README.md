# Google Antigravity Project Instructions

A practical, reusable instruction template for more disciplined AI-assisted software development with Google Antigravity.

The goal of this repository is to help an AI coding agent understand the existing project before changing it, stay within the requested scope, protect developer work, avoid unnecessary complexity, and report verification results honestly.

## Repository contents

- [`ANTIGRAVITY_PROJECT_INSTRUCTIONS.md`](./ANTIGRAVITY_PROJECT_INSTRUCTIONS.md) — the project-level guidance to adapt and use with your development workflow.
- [`LICENSE`](./LICENSE) — the license terms for this repository.

## What the instructions cover

The template addresses:

- Understanding the repository and its current state before editing
- Respecting the requested scope and existing architecture
- Choosing focused, maintainable solutions over unnecessary complexity
- Preserving uncommitted work and protecting data
- Managing dependencies and Git operations carefully
- Maintaining security and respecting external-access boundaries
- Testing changes and reviewing the final diff
- Documenting significant changes and providing a truthful handover
- Stopping when a task requires clarification or authorization

## Quick start

1. Open this repository and review `ANTIGRAVITY_PROJECT_INSTRUCTIONS.md`.
2. Copy the file into the root directory of the project you want to work on.
3. Adjust environment-specific guidance so it matches your language, framework, operating system, tools, and team practices.
4. Configure your Antigravity workflow to read and follow the file. Do not assume that a Markdown file is automatically loaded just because it exists in the repository.
5. For each task, provide a separate prompt that describes the requested outcome, relevant constraints, and acceptance criteria.
6. Review the agent's changes and test results before accepting or publishing them.

## Example task prompt

> Please implement [describe the requested change]. First inspect the relevant project code and follow the repository's project instructions. Keep the change limited to this task, reuse established patterns, and avoid unrelated refactoring or unnecessary dependencies. Run the appropriate checks, review the final diff, and report what changed, what was tested, and any remaining limitations. Do not publish, deploy, or perform destructive operations unless explicitly authorized.

Replace the bracketed text with your actual task and add any project-specific requirements.

## Important notes

- This is a starting template, not a guarantee that generated code will be correct or secure.
- Tailor the instructions to your project and review them periodically.
- Only claim that a test passed if it was actually run and passed.
- Keep secrets, credentials, private configuration, and sensitive production data out of prompts and public repositories.
- The instructions do not replace code review, testing, security review, backups, or your team's approval process.

## Contributions

If you adapt this template for a particular framework or workflow, consider documenting the assumptions and keeping changes focused. Before sharing a modified version, check that it contains no secrets, private paths, client information, or project-specific credentials.
