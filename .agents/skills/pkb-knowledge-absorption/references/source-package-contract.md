# PKB Source Package Contract — Standalone Chat Review

## Schema

Package-based modes require:

```text
PACKAGE_SCHEMA_VERSION:
1
```

Unknown or missing versions must return `BLOCKED`. Do not guess compatibility.

## Purpose

A new PKB task may not have access to the earlier Chat window, Project, or Codex task. The package must be self-contained enough to classify durable knowledge without reopening or reinterpreting the source conversation.

A Source Package is a transport format, not independent evidence.

## `CHAT_WINDOW_REVIEW`

This is the default mode for the PKB Bridge Prompt and can be used after **any Chat window**.

Require:

```text
PKB_ABSORPTION_RECOMMENDED:
YES
```

The package should contain:

- minimum Chat-window background;
- optional project or closeout background, or `NONE`;
- Personal Context candidates;
- Pitfall candidates;
- PKB operating-rule candidates;
- possible existing coverage;
- topic-specific or project-specific details to strip;
- content explicitly excluded from PKB;
- fact levels and uncertainties.

This mode must not require:

- a Project;
- Project Closeout;
- `PKB_SYNC_REQUIRED`;
- source-project branch, commit, Hash, or clean-worktree evidence.

If the Bridge Prompt finds no eligible durable candidate, it must output `NO_PKB_ACTION_REQUIRED` and must not create a package.

## `PROJECT_CLOSEOUT_PACKAGE`

This optional compatibility mode is used when a Project Closeout Skill directly generates the PKB call package.

Require an explicit:

```text
PKB_SYNC_REQUIRED:
YES
```

If `NO`, perform no PKB action. If missing or ambiguous, block only in this source mode.

The package should contain, where applicable:

- minimum source project or workstream background;
- closeout result and why the work changed;
- evidence that the source project preserved its own Current state;
- local branch/commit/clean-worktree evidence;
- Personal Context candidates;
- Pitfall candidates;
- PKB operating-rule candidates;
- possible existing coverage;
- project-specific details that must be stripped;
- items that must remain in the source project;
- fact levels and uncertainties.

Project Closeout is a convenience source, not the universal PKB entry point.

## `USER_PROVIDED_SOURCE_PACKAGE`

Use for user-supplied durable knowledge not necessarily tied to a Chat review or Project Closeout, such as a pasted operating principle, research package, or manually assembled incident set.

Do not require project-closeout evidence unless the package relies on a source repository.

## `CURRENT_CODEX_THREAD`

Use only when the current Codex task actually includes the relevant work and evidence. Never assume access to an earlier task or hidden thread.

## `LOCAL_SOURCE_FILE`

Use only the explicitly supplied local file. Do not browse neighboring project files unless separately authorized and necessary.

## `REPOSITORY_ONLY`

Use only to audit current PKB structure, ownership, duplication, or existing coverage. It does not authorize inventing source evidence.

## Fact Levels

Use:

- `USER_CONFIRMED`
- `USER_PROVIDED`
- `OBSERVED_WORKFLOW`
- `INFERENCE`
- `NEEDS_CONFIRMATION`

Only `USER_CONFIRMED`, `USER_PROVIDED`, or a concretely evidenced `OBSERVED_WORKFLOW` may become formal candidates.

`INFERENCE` and `NEEDS_CONFIRMATION` may be reported but must not be written into PKB.

## Source Sufficiency

A source is sufficient when each candidate can be judged on:

1. the durable behavior, preference, operating rule, or lesson proposed;
2. the real evidence supporting it;
3. whether it is durable, project-only, temporary, or general-information-only;
4. the likely owner file;
5. material uncertainty or privacy boundary.

Only `PROJECT_CLOSEOUT_PACKAGE` additionally requires source-project closeout and clean-worktree evidence.
