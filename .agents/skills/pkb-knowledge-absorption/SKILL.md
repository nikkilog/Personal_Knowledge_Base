---
name: pkb-knowledge-absorption
description: Absorb durable preferences, reusable pitfalls, and PKB operating rules into Personal_Knowledge_Base after project closeout or from user-provided web, Codex-thread, or local sources, with deduplication, abstraction, validation, and an independent local Git closeout. Use only when updating Personal_Knowledge_Base; do not use while a source project has uncommitted changes, to modify business-project files, record one-off project state, synchronize Workspace_Control, publish to cloud services, or merely answer questions about existing preferences or pitfalls.
---

# PKB Knowledge Absorption

## Purpose

Identify durable preferences and reusable pitfalls, deduplicate them against the current PKB, remove project-specific incident details, update the one authoritative file, validate privacy and ownership boundaries, and close out the PKB change independently in local Git.

## Required Inputs

- `SOURCE_MODE`: `CURRENT_CODEX_THREAD` (default), `USER_PROVIDED_SOURCE_PACKAGE`, `LOCAL_SOURCE_FILE`, or `REPOSITORY_ONLY`.
- `SOURCE_PACKAGE`: use only with `USER_PROVIDED_SOURCE_PACKAGE`; block if missing.
- `SOURCE_FILE`: use only with `LOCAL_SOURCE_FILE`; block if missing.
- `KNOWLEDGE_FOCUS`: `PERSONAL_CONTEXT`, `PITFALLS`, `PKB_OPERATING_RULES`, or `ALL` (default).
- `EXECUTION_MODE`: `AUDIT_ONLY`, `AUDIT_THEN_CONFIRM` (default), or `DIRECT_EXECUTE_AFTER_SAFE_GATE`.
- `COMMIT_MODE`: `NO_COMMIT` (default) or `COMMIT_AFTER_VALIDATION`.

## Repository Gate

Before writing, verify the correct PKB repository, branch and HEAD, a clean worktree, no unexplained changes, and that every source project involved has already been committed or otherwise closed out with a clean worktree. Stop all writes on gate failure. Never stash, overwrite, or absorb knowledge while another repository remains unclosed.

## Sources to Read

Always read `AGENTS.md`, `PROJECT.md`, `PERSONAL_CONTEXT.md`, and `PITFALL_LOG.md`. Read the user-provided Source Package, specified local Source File, current Codex thread, and relevant Git history only as required by `SOURCE_MODE` and the audit. Avoid `archive/` unless traceability is necessary.

Read the references before classifying or executing:

- [Knowledge routing](references/knowledge-routing.md)
- [Privacy and deduplication](references/privacy-and-dedup.md)
- [Pitfall quality](references/pitfall-quality.md)
- [Report contract](references/report-contract.md)

## Two-phase Default

For `AUDIT_THEN_CONFIRM`, first perform only read-only identification, deduplication, ownership classification, and preparation of one recommended execution package. Do not modify files. After explicit user confirmation, modify only approved files, validate them, show the diff, and commit only when `COMMIT_MODE` is `COMMIT_AFTER_VALIDATION`.

For `AUDIT_ONLY`, never write or commit. For `DIRECT_EXECUTE_AFTER_SAFE_GATE`, write only after every repository, privacy, source, and scope gate passes and the request clearly authorizes direct execution.

## Result States

Return exactly one execution state:

- `ACTION_COMPLETED_NOW`: approved updates were made and validated.
- `ALREADY_IN_DESIRED_STATE`: existing knowledge already covers every eligible candidate; do not modify files or create an empty commit.
- `BLOCKED`: a required input or safe gate is missing; state only the minimum unblock requirement.

Keep candidate identification, file modification, validation, and Git commit status distinct.

## Cross-repo Boundary

Never modify CAH, Workspace_Control, another project repository, or any cloud resource. Classify cross-project engineering governance as `WORKSPACE_RULE` and report only:

`WORKSPACE_RULE_FOLLOW_UP_REQUIRED: YES` or `NO`.

Do not update Workspace_Control directly.

## Validation Scenarios

Use these static cases to verify behavior:

1. `USER_PROVIDED_SOURCE_PACKAGE` + `ALL` + `AUDIT_THEN_CONFIRM`: read and deduplicate the supplied web knowledge package; phase one makes no changes.
2. `REPOSITORY_ONLY` + `PITFALLS` + `AUDIT_ONLY`: inspect current Pitfall structure and duplication only; make no changes.
3. `USER_PROVIDED_SOURCE_PACKAGE` without `SOURCE_PACKAGE`: return `BLOCKED` and request only the missing package.
4. A package containing only project versions, commits, hashes, and one-off state: classify as `PROJECT_ONLY`; do not update or commit the PKB.
5. Unconfirmed inferred health, political, religious, or other sensitive attributes: exclude them or return `BLOCKED`; never write them.
6. Fully covered candidate knowledge: return `ALREADY_IN_DESIRED_STATE`; do not modify or create an empty commit.
