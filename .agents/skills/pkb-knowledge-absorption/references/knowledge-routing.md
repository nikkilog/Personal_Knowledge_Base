# Knowledge Routing

Assign each detailed item to exactly one owner.

## Knowledge Types

- `PERSONAL_CONTEXT`
- `PITFALL`
- `PKB_OPERATING_RULE`
- `PROJECT_ONLY`
- `WORKSPACE_RULE`
- `NO_ACTION`

## Recommended Actions

Use exactly one:

- `MERGE_INTO_EXISTING_ENTRY`
- `UPDATE_EXISTING`
- `CREATE_NEW_ENTRY`
- `ALREADY_COVERED`
- `KEEP_IN_PROJECT_ONLY`
- `UPDATE_WORKSPACE_CONTROL_SEPARATELY`
- `NO_ACTION`

Prefer, in order:

1. `MERGE_INTO_EXISTING_ENTRY`
2. `UPDATE_EXISTING`
3. `CREATE_NEW_ENTRY`
4. `ALREADY_COVERED`
5. `NO_ACTION`

## `PERSONAL_CONTEXT.md`

Store durable working, communication, output, acceptance, Codex-collaboration, project-management, and cross-project work preferences.

Examples of eligible durable collaboration preferences include:

- using Codex to maintain project logic, rules, steps, current progress, next actions, current valid artifacts, pitfalls, and local Git closeout;
- requiring a unique Current code/document entry point so a new person or AI does not guess the latest version;
- listing candidate deletions for explicit user confirmation, optionally supported by screenshots or a concrete file list;
- preferring source-project closeout before PKB absorption.

## `PITFALL_LOG.md`

Store verified incidents with the problem, observable symptom, root cause, wrong handling, correct handling, verification, prevention, and applicability.

## `AGENTS.md`

Store only PKB-local rules for privacy, deduplication, file responsibilities, Git, archive handling, local-only operation, and safe closeout execution.

## `PROJECT.md`

Store only the PKB's purpose, Current files, status, focus, maintenance workflow, and local boundary.

## `PROJECT_ONLY`

Keep project versions, commits, run IDs, resource IDs, Current state, project next steps, schemas, controllers, project-specific code identity, and project-specific pitfalls in their source project. Do not absorb them into PKB.

## `WORKSPACE_RULE`

Classify cross-project engineering governance, including global Git, Skill, repository-isolation, and lifecycle rules, as workspace follow-up. Do not write it to Workspace_Control from this Skill.

When an item touches several categories, choose the single detailed owner and use only a short cross-reference elsewhere if strictly necessary.
