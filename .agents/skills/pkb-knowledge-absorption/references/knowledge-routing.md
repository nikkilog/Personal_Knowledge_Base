# Knowledge Routing

Route each detailed candidate to exactly one authoritative owner before drafting.

## Knowledge Types

- `PERSONAL_CONTEXT`
- `PITFALL`
- `PKB_OPERATING_RULE`
- `PROJECT_ONLY`
- `WORKSPACE_RULE`
- `GENERAL_INFORMATION_ONLY`
- `NO_ACTION`

## Recommended Actions

Use exactly one:

- `MERGE_INTO_EXISTING_ENTRY`
- `UPDATE_EXISTING`
- `CREATE_NEW_ENTRY`
- `ALREADY_COVERED`
- `KEEP_IN_PROJECT_ONLY`
- `UPDATE_WORKSPACE_CONTROL_SEPARATELY`
- `GENERAL_INFORMATION_NO_PKB_WRITE`
- `NO_ACTION`

Prefer merge, then update, then create. If fully covered, use `ALREADY_COVERED` and make no edit.

## Owner Files

### `PERSONAL_CONTEXT.md`

Store durable personal background, working preferences, communication preferences, output and acceptance habits, and cross-project collaboration preferences.

Do not store temporary project state, branch, commit, run ID, resource ID, project version, or project next step.

### `PITFALL_LOG.md`

Store incidents that actually occurred and have reusable observable symptoms, sufficiently established causes, correct handling, verification, and prevention value.

A personal preference is not automatically a Pitfall. A technical rule is not a Pitfall unless the failure actually occurred.

### `AGENTS.md`

Store only mandatory PKB-local operating, privacy, file-responsibility, deduplication, archive, validation, and Git rules.

Modify it only when those rules change. Do not store ordinary preferences.

### `PROJECT.md`

Store only the PKB repository's own purpose, Current files, status, maintenance entry point, and current maintenance focus.

### `PROJECT_ONLY`

Keep project versions, branches, commits, hashes, run IDs, resource IDs, Current state, project next steps, schemas, controllers, business choices, and readable source-project facts in the source project.

### `WORKSPACE_RULE`

Use for governance that applies across repositories or changes global Git, Skill, repository-isolation, or workspace lifecycle rules. Report it as follow-up; do not update Workspace_Control from this Skill.

### `GENERAL_INFORMATION_ONLY`

Use for ordinary general knowledge that has no durable user-specific, operational, or verified Pitfall value. Use `GENERAL_INFORMATION_NO_PKB_WRITE`; do not store it in PKB.

## Conflict and Authorization Boundary

Interpret repository rules in this order:

1. current explicit user instruction;
2. PKB `AGENTS.md`;
3. active Skill contract;
4. `PROJECT.md`;
5. `PERSONAL_CONTEXT.md`;
6. `PITFALL_LOG.md`.

A durable preference is a default choice, not authorization for deletion, destructive overwrite, cross-repository modification, stage, commit, push, publication, cloud synchronization, or writing unconfirmed personal information.

## Cross-file Movement

When detailed knowledge moves to a better owner:

- classify the change as `MOVED_TO_CORRECT_DOCUMENT`;
- identify the old owner and surviving owner;
- preserve a short cross-reference only when useful;
- remove duplicate detailed text only after semantic preservation is confirmed.
