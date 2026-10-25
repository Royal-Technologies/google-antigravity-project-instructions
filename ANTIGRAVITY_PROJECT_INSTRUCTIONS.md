# Project Guidance for AI-Assisted Development

Use this document as a project-level reference when working with Google Antigravity or another AI coding agent. Adapt it to the repository before use. Follow the project's actual requirements and applicable safety constraints; if an instruction here conflicts with an explicit project requirement, pause and ask for clarification rather than silently choosing.

## 1. Confirm the working context

Before making changes, establish which repository and branch are active, where the project is located, and whether the working tree already contains edits. Review recent history when it helps explain the current state.

For Git projects, begin with checks such as:

```bash
git status --short
git branch --show-current
git log --oneline -8
```

Do not assume the editor or terminal is pointed at the intended project. If the repository, branch, or existing changes create a meaningful risk of working in the wrong place or overwriting someone else's work, pause and explain the issue.

## 2. Learn the relevant parts of the project first

Read the applicable README, setup notes, handover documents, configuration, source files, and tests before choosing an implementation. Inspect the files related to the task closely enough to understand how the existing behavior works.

Use the current implementation and tests as important evidence. If documentation appears outdated or inconsistent with the code, identify the discrepancy instead of inventing an explanation or redesigning the system based on assumptions.

## 3. Keep the task focused

Implement the outcome that was requested, including its stated acceptance criteria. Do not add unrelated features, redesign other screens, rename unrelated files, clean up unrelated code, or begin a later phase merely because it seems useful.

If you discover a separate issue, mention it in the final report. Only include it in the implementation when it is necessary for the requested change or the developer authorizes the expanded scope.

## 4. Prefer clear, proportionate solutions

Choose the least complicated approach that adequately satisfies the requirements and fits the project's existing conventions.

- Reuse suitable project utilities and framework capabilities.
- Avoid creating extra layers, services, helper hierarchies, queues, databases, or configuration systems without a concrete need.
- Do not build speculative extension points for hypothetical future requirements.
- Avoid maintaining two independent implementations of the same responsibility.
- Introduce an abstraction when it solves a real, demonstrated problem—not simply to make a small change look more general.

## 5. Keep modifications narrow and reviewable

Inspect each file before editing it. Change only the sections necessary to deliver the requested behavior. Preserve unrelated code, comments, formatting, configuration, and working functionality.

Avoid whole-file rewrites, mass formatting, broad renaming, or unrelated refactoring unless they are required and authorized. After implementation, inspect every changed file and confirm that the resulting diff matches the task.

## 6. Preserve work already in progress

Treat existing uncommitted changes as potentially important user work. Do not delete, overwrite, reset, stash, or clean them merely to simplify the task.

If unexpected edits appear or a protected file needs to change, pause and explain the situation before taking a risky action. Do not assume that an uncommitted file is disposable.

## 7. Be deliberate about dependencies and tools

Before adding a package or external tool, check whether the project already has a suitable capability or whether the language, framework, or standard library can meet the need.

Add dependencies only when justified by the task and permitted by the project owner. Avoid broad package upgrades when a focused change is sufficient. Use the project's established package manager and installation conventions.

For macOS projects that use Homebrew, verify whether the required tool is already available. Avoid system-wide upgrades, cleanup operations, or permanent environment changes unless they are needed and authorized. Adapt this guidance for other operating systems and package managers.

## 8. Use Git and release operations cautiously

Review repository status before editing and again before finishing. Avoid destructive commands or history-changing operations unless the developer explicitly authorizes them and the consequences are understood.

Do not automatically force-push, rewrite history, merge branches, create release tags, publish packages, deploy, or push commits to a remote. Completing a code change does not itself grant permission to publish it.

## 9. Establish a useful starting baseline

For work where verification matters, note the starting commit, working-tree state, relevant runtime or tool versions, and the status of pertinent tests. This helps distinguish pre-existing failures from problems introduced by the current change.

Keep the baseline proportional to the task. Do not imply that an existing failure was caused by the new work unless evidence supports that conclusion.

## 10. Implement and verify in small steps

Make changes in manageable increments. After a meaningful change, run the checks most relevant to it before continuing where practical.

Depending on the project, verification may include type checking, compilation, focused unit tests, integration or regression tests, a production build, smoke tests, UI inspection, and security-related failure cases. Use the checks that are available and appropriate; do not claim to have run tools that were not executed.

If a required check cannot be run, explain why and identify what remains unverified.

## 11. Keep one clear owner for each responsibility

Look for existing systems that own validation, authorization, caching, configuration, theme settings, media handling, business rules, or other shared responsibilities. Extend or reuse the appropriate system rather than adding a competing one.

If consolidation is genuinely needed, keep it limited to the necessary behavior and explain the reason.

## 12. Protect security and privacy

Preserve the project's security controls. Validate untrusted input at the appropriate boundaries, respect authentication and authorization, and avoid weakening protections to make a feature easier to implement.

Do not expose secrets, credentials, private environment values, sensitive user data, or confidential configuration in code, logs, prompts, or reports. Avoid unnecessary disclosure of private filesystem paths or infrastructure details.

## 13. Respect external-access and production boundaries

Do not download files, scrape websites, call external APIs, upload project data, or access production systems unless the task authorizes that activity.

Do not make destructive production changes, erase records, reset live databases, overwrite customer data, or run production seed operations without explicit authorization and an appropriate safety plan. Prefer development fixtures or synthetic data for testing.

If the task unexpectedly requires external or production access, stop and request the necessary direction.

## 14. Do not mask failures

Do not hardcode a result merely to satisfy a test, disable a failing test to make the suite appear green, skip required validation without disclosure, bypass the feature being tested, or suppress errors without a legitimate handling strategy.

Investigate the underlying problem. If the correct outcome cannot be achieved within the available scope or tools, report the task as incomplete or blocked and explain the reason.

## 15. Update documentation when the project meaningfully changes

Update relevant documentation when a change affects architecture, setup, runtime requirements, public interfaces, configuration, limitations, or operational procedures.

For substantial tasks, leave a useful handover that records the goal, important decisions, files changed, checks performed, known limitations, deferred work, and final repository state. Keep documentation accurate to what was actually implemented.

## 16. Review the final change set

Before finishing, inspect the working tree and the full diff. For Git projects, useful checks include:

```bash
git status --short
git diff --check
git diff
```

Review all changed files for accidental edits, unrelated changes, exposed secrets, missing validation, and scope drift. If the task involves generated or untracked files, inspect those as well; the normal diff may not show their contents.

## 17. Report results accurately

Finish with a concise report containing:

- **Status:** PASS, PARTIAL, FAILED, or BLOCKED
- **Implemented:** The behavior or change delivered
- **Files changed:** The principal files affected
- **Verification:** Checks actually run and their outcomes
- **Limitations:** Known issues, skipped checks, or unfinished work
- **Scope deviations:** State `NONE` if there were no deviations
- **Repository state:** Relevant commit and working-tree status, when applicable
- **Next step:** Include only if a decision or action is needed

Never claim that code was tested, committed, pushed, released, or deployed unless that action actually occurred. Distinguish confirmed results from assumptions.

## 18. Stop when the task is complete—or when safe progress is impossible

Pause and request clarification if the project context is wrong, existing work may be at risk, requirements conflict, a protected area must change, a major architectural decision is needed, or the task requires unauthorized access or destructive action.

Once the authorized task has been implemented and verified to the extent possible, stop. Do not automatically add bonus features, refactor unrelated modules, upgrade dependencies, start another phase, merge, push, release, or deploy.

The developer decides whether further work should begin.
