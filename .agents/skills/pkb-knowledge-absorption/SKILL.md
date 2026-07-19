---
name: pkb-knowledge-absorption
description: Absorb durable preferences, reusable pitfalls, and PKB operating rules into Personal_Knowledge_Base only after the source project has completed its own documentation and local Git closeout. Deduplicate, abstract, preserve semantics, validate privacy and ownership boundaries, and close the PKB change independently in local Git. Do not use this Skill to modify business-project files, replace project handoff documentation, record one-off project state, synchronize Workspace_Control, publish to cloud services, or merely answer questions about existing preferences or pitfalls.
---

# PKB Knowledge Absorption

## Purpose

Identify durable personal working preferences, reusable verified pitfalls, and PKB-local operating rules; deduplicate them against the current Personal_Knowledge_Base; remove one-off project details; update the single authoritative owner file; validate semantic preservation, privacy, and repository boundaries; and close the PKB change independently in local Git.

This Skill is the second closeout step. It does not replace source-project documentation.

## Core Operating Intent

The source project must first explain its own logic and current state. Typical source-project closeout should make clear:

- what the project is and why it is designed that way;
- the current rules and execution steps;
- what is complete, what is current, and what happens next;
- which code, notebook, script, and document is currently authoritative;
- which old artifacts are superseded and must not be treated as Current;
- project-specific pitfalls and decisions that must not be reopened;
- the validated local Git closeout state.

PKB then absorbs only the cross-project durable lessons. Do not move project handoff duties into PKB.

## Required Inputs

- `TARGET_REPO_PATH`: Personal_Knowledge_Base repository path. If omitted, resolve from the current Git root and block if it is not clearly the PKB.
- `EXPECTED_BRANCH`: expected PKB branch; default `main`.
- `EXPECTED_DIRTY_FILES`: expected pre-existing PKB modifications; default `NONE`.
- `SOURCE_MODE`: `PROJECT_CLOSEOUT_PACKAGE` (default), `CURRENT_CODEX_THREAD`, `USER_PROVIDED_SOURCE_PACKAGE`, `LOCAL_SOURCE_FILE`, or `REPOSITORY_ONLY`.
- `SOURCE_PACKAGE`: required for `PROJECT_CLOSEOUT_PACKAGE` and `USER_PROVIDED_SOURCE_PACKAGE`; block if missing.
- `SOURCE_FILE`: required for `LOCAL_SOURCE_FILE`; block if missing.
- `KNOWLEDGE_FOCUS`: `PERSONAL_CONTEXT`, `PITFALLS`, `PKB_OPERATING_RULES`, or `ALL` (default).
- `EXECUTION_MODE`: `AUDIT_ONLY`, `AUDIT_THEN_CONFIRM` (default), or `DIRECT_EXECUTE_AFTER_SAFE_GATE`.
- `COMMIT_MODE`: `NO_COMMIT` (default) or `COMMIT_AFTER_VALIDATION`.

Read [Source package contract](references/source-package-contract.md) before using any non-repository source.

## Mandatory Closeout Order

Always follow this order:

1. Complete the source project's own documentation closeout.
2. Identify the source project's current authoritative files and current valid code.
3. Resolve or explicitly classify superseded project artifacts.
4. Validate and commit the source project locally.
5. Confirm the source project worktree is clean.
6. Start a separate PKB task.
7. Absorb only durable cross-project knowledge into PKB.
8. Validate and commit the PKB independently.

Do not use the same task to modify both the source project and PKB.

## Repository Gate

Before any write:

1. verify `pwd` and Git root;
2. verify the repository is Personal_Knowledge_Base;
3. verify branch and HEAD;
4. run `git status --short`;
5. compare actual changes with `EXPECTED_DIRTY_FILES`;
6. stop on unexplained modifications, conflicts, or deletions;
7. confirm every source project represented in the source package has already been locally committed or otherwise explicitly closed with a clean worktree.

Never stash, reset, restore, checkout, overwrite, or silently absorb around a failed gate.

## Source Completeness Gate

Do not assume a new Codex task can access an earlier Codex thread.

For `PROJECT_CLOSEOUT_PACKAGE`, require enough evidence to understand:

- the source project or workstream;
- what changed and why;
- the project closeout result;
- current branch and clean-worktree evidence;
- candidate durable preferences or reusable pitfalls;
- unresolved items that must remain project-only.

If the source is incomplete, return `BLOCKED` and request only the missing package or closeout evidence.

`CURRENT_CODEX_THREAD` is allowed only when the current task actually contains the relevant source work. Do not use it merely because it is the easiest default.

## Sources to Read

Always read:

- `AGENTS.md`
- `PROJECT.md`
- `PERSONAL_CONTEXT.md`
- `PITFALL_LOG.md`

Read the source package, source file, current Codex thread, and relevant Git history only as required by `SOURCE_MODE` and the audit. Avoid `archive/` unless traceability is necessary.

Read all references before classifying or executing:

- [Source package contract](references/source-package-contract.md)
- [Knowledge routing](references/knowledge-routing.md)
- [Privacy and deduplication](references/privacy-and-dedup.md)
- [Pitfall quality](references/pitfall-quality.md)
- [Report contract](references/report-contract.md)

## Authoritative File Responsibilities

### `PERSONAL_CONTEXT.md`

Store durable working, communication, output, acceptance, Codex-collaboration, project-management, and cross-project work preferences.

Do not store one-off project state, current branch, commit, run ID, resource ID, project version, or project next step.

### `PITFALL_LOG.md`

Store verified reusable incidents with an observable symptom, root cause, wrong handling, correct handling, verification, prevention, and applicability.

Do not store unverified worries or vague reminders.

### `AGENTS.md`

Store only PKB-local operating rules: privacy, local-only boundaries, deduplication, file responsibility, Git, archive handling, and safe execution.

Do not store ordinary personal preferences.

### `PROJECT.md`

Store only the PKB's own purpose, Current files, status, Current Focus, maintenance workflow, and local-only boundary.

Do not store business-project state.

### `archive/`

Use only for a fully retired knowledge asset with independent traceability value that Git history alone cannot express. Routine edits, merges, and deduplication must not create Archive copies.

## Knowledge Classification

Each detailed candidate must have exactly one type:

- `PERSONAL_CONTEXT`
- `PITFALL`
- `PKB_OPERATING_RULE`
- `PROJECT_ONLY`
- `WORKSPACE_RULE`
- `NO_ACTION`

Each candidate must have exactly one recommended action:

- `MERGE_INTO_EXISTING_ENTRY`
- `UPDATE_EXISTING`
- `CREATE_NEW_ENTRY`
- `ALREADY_COVERED`
- `KEEP_IN_PROJECT_ONLY`
- `UPDATE_WORKSPACE_CONTROL_SEPARATELY`
- `NO_ACTION`

Prefer existing authoritative entries. Do not write the same detailed knowledge into multiple files.

## Durable Collaboration Preference Check

When supported by the source, evaluate whether the PKB already captures these durable collaboration preferences:

- Codex is used primarily to preserve local project maintainability, not merely to generate code.
- Project documentation should explain project purpose, design logic, rules, steps, current progress, current valid artifacts, pitfalls, and the next action.
- New people or AI should not need to reread long chat history or guess which file is current.
- Current authoritative code and documents must be unique and explicit.
- Superseded code and outputs without continuing value should not remain as Current execution entry points.
- Candidate deletions should be listed for user confirmation; when useful, the user may provide screenshots or a file list before deletion is authorized.
- Project-specific knowledge remains in the project; only cross-project durable knowledge enters PKB.

Merge these into existing entries when already partially covered. Do not recreate them on every run.

## Two-phase Default

For `AUDIT_THEN_CONFIRM`, phase one is read-only. Perform identification, deduplication, ownership classification, semantic-preservation planning, and preparation of one unique recommended execution package. Do not modify, delete, stage, or commit.

After explicit user confirmation, modify only approved files and approved entries, validate them, show the diff summary, and commit only when `COMMIT_MODE` is `COMMIT_AFTER_VALIDATION`.

For `AUDIT_ONLY`, never write or commit.

For `DIRECT_EXECUTE_AFTER_SAFE_GATE`, write only after every repository, source, privacy, deletion, and scope gate passes and the request explicitly authorizes direct execution.

## Deletion and Semantic Preservation Gate

Do not delete or substantially rewrite existing PKB knowledge merely because it appears old or verbose.

Before deleting, compressing, merging, or archiving existing content:

1. identify the exact entry or file;
2. state why it is superseded, duplicated, or being merged;
3. identify where the surviving knowledge will live;
4. request explicit confirmation when the change removes or materially rewrites existing knowledge;
5. when practical, let the user confirm from a screenshot or concrete file/entry list;
6. classify every removed block as:
   - `SUPERSEDED_CORRECTLY`
   - `DUPLICATE_REMOVED`
   - `MERGED_INTO_EXISTING`
   - `VALID_CONTENT_LOST`
   - `NEEDS_CONFIRMATION`

If any content is `VALID_CONTENT_LOST`, do not commit. If any content is `NEEDS_CONFIRMATION`, stop and request the single necessary decision.

## Cross-repo Boundary

Never modify a source project, CAH, Workspace_Control, another repository, or any cloud resource.

Classify cross-project engineering governance as `WORKSPACE_RULE` and report only:

`WORKSPACE_RULE_FOLLOW_UP_REQUIRED: YES` or `NO`.

Do not update Workspace_Control directly.

## Validation Before Commit

After approved edits:

1. run `git diff --check`;
2. show `git status --short`;
3. show `git diff --stat`;
4. verify only approved files changed;
5. verify no project-only state entered PKB;
6. verify no ordinary personal preference entered PKB `AGENTS.md`;
7. verify no duplicate detailed knowledge was created;
8. verify no Secret value or inferred sensitive attribute was added;
9. verify semantic preservation classifications contain no `VALID_CONTENT_LOST`;
10. create no empty commit.

## Result States

Return exactly one execution result:

- `ACTION_COMPLETED_NOW`: approved updates were made and validated.
- `ALREADY_IN_DESIRED_STATE`: existing knowledge already covers every eligible candidate; do not modify files or create an empty commit.
- `BLOCKED`: a required input or safe gate is missing; state only the minimum unblock requirement.

Keep candidate identification, file modification, validation, and Git commit status distinct.

## Validation Scenarios

Use these static cases to verify behavior:

1. `PROJECT_CLOSEOUT_PACKAGE` + `ALL` + `AUDIT_THEN_CONFIRM`: read and deduplicate the supplied closeout package; phase one makes no changes.
2. `REPOSITORY_ONLY` + `PITFALLS` + `AUDIT_ONLY`: inspect current Pitfall structure and duplication only; make no changes.
3. `PROJECT_CLOSEOUT_PACKAGE` without `SOURCE_PACKAGE`: return `BLOCKED` and request only the missing package.
4. A new Codex task that lacks the previous project thread: do not infer access; require the project closeout package.
5. A package containing only project versions, commits, hashes, and one-off state: classify as `PROJECT_ONLY`; do not update or commit the PKB.
6. Unconfirmed inferred health, political, religious, or other sensitive attributes: exclude them or return `BLOCKED`; never write them.
7. Fully covered candidate knowledge: return `ALREADY_IN_DESIRED_STATE`; do not modify or create an empty commit.
8. A proposed deletion or large rewrite without explicit approval: return `BLOCKED` and request only the deletion decision.
9. A source project with a dirty worktree: return `BLOCKED`; do not absorb knowledge.
