---
name: pkb-knowledge-absorption
description: Independently review durable knowledge from any Chat window, project closeout package, user-provided source package, local source file, current Codex thread, or PKB repository audit. Route stable personal context, reusable working methods, verified cross-project pitfalls, and PKB-local operating rules into one authoritative owner; deduplicate before writing; remove project-only and temporary details; preserve semantics; validate privacy and repository boundaries; and close approved PKB changes independently in local Git. Do not require Project Closeout for chat-window review. Do not modify source projects or Workspace_Control, record temporary state, push, publish, or cloud-sync.
---

# PKB Knowledge Absorption

## 1. Purpose

Use this Skill to turn a self-contained source package or PKB repository audit into a small, durable, non-duplicative PKB update.

PKB Knowledge Absorption is an **independent capability**. It may run after any Chat window, whether or not that window belongs to a Project and whether or not Project Closeout has occurred.

The Skill must:

1. verify the PKB repository and source mode;
2. route each candidate to one authoritative owner;
3. check existing coverage before drafting;
4. keep temporary, project-only, and unsupported details out of PKB;
5. propose one bounded execution package;
6. write only after the selected execution mode authorizes it;
7. validate and, when authorized, commit the PKB independently.

PKB does not replace source-project documentation, and Project Closeout is not a prerequisite for general chat-window absorption.

## 2. Inputs

- `PACKAGE_SCHEMA_VERSION`: required for package-based modes; supported value: `1`.
- `TARGET_REPO_PATH`: PKB repository path. If omitted, resolve from the current Git root and block if the repository is not clearly the PKB.
- `EXPECTED_BRANCH`: expected PKB branch; default `main`.
- `EXPECTED_DIRTY_FILES`: expected pre-existing PKB modifications; default `NONE`.
- `SOURCE_MODE`:
  - `CHAT_WINDOW_REVIEW` (default)
  - `PROJECT_CLOSEOUT_PACKAGE`
  - `CURRENT_CODEX_THREAD`
  - `USER_PROVIDED_SOURCE_PACKAGE`
  - `LOCAL_SOURCE_FILE`
  - `REPOSITORY_ONLY`
- `SOURCE_PACKAGE`: required for `CHAT_WINDOW_REVIEW`, `PROJECT_CLOSEOUT_PACKAGE`, and `USER_PROVIDED_SOURCE_PACKAGE`.
- `SOURCE_FILE`: required for `LOCAL_SOURCE_FILE`.
- `KNOWLEDGE_FOCUS`: `PERSONAL_CONTEXT`, `PITFALLS`, `PKB_OPERATING_RULES`, or `ALL` (default).
- `EXECUTION_MODE`: `AUDIT_ONLY`, `AUDIT_THEN_CONFIRM` (default), or `DIRECT_EXECUTE_AFTER_SAFE_GATE`.
- `COMMIT_MODE`: `NO_COMMIT` (default) or `COMMIT_AFTER_VALIDATION`.

Unknown parameter names, unsupported enum values, or unsupported package schema versions must return `BLOCKED`. Do not guess aliases such as `PKB_COMMIT_MODE`.

Read [Source package contract](references/source-package-contract.md) for non-repository sources.

## 3. Source-mode Gates

### `CHAT_WINDOW_REVIEW`

This is the default independent mode.

Require:

- `PKB_ABSORPTION_RECOMMENDED: YES`;
- a self-contained minimum summary of the Chat window;
- at least one candidate with a supported fact level;
- explicit exclusions for temporary, project-only, sensitive, or unsupported content;
- candidate-level fact levels and uncertainties.

Do **not** require:

- a Project;
- Project Closeout;
- `PKB_SYNC_REQUIRED`;
- source-project branch, commit, or clean-worktree evidence.

A project or closeout result may be included as optional context. It does not become a gate.

If the source package contains no eligible candidate after local PKB deduplication and routing, return `ALREADY_IN_DESIRED_STATE`; do not create an empty commit.

### `PROJECT_CLOSEOUT_PACKAGE`

Require:

- `PKB_SYNC_REQUIRED: YES` or an equivalent explicit project-closeout instruction;
- a self-contained project closeout summary;
- enough evidence that the source project preserved its own Current state;
- local closeout and clean-worktree evidence;
- candidate durable knowledge and project-only exclusions.

This mode is only a convenience path from Project Closeout. It is not required for `CHAT_WINDOW_REVIEW`.

If the package says `PKB_SYNC_REQUIRED: NO`, return `ALREADY_IN_DESIRED_STATE` with no PKB modification.

If the field is missing or ambiguous in this specific mode, return `BLOCKED` and request only the missing status.

### `CURRENT_CODEX_THREAD`

Use only when the current Codex task actually contains the source work and evidence. Do not assume access to an earlier task or hidden thread.

### `USER_PROVIDED_SOURCE_PACKAGE`

Use for user-supplied durable knowledge not necessarily tied to a project closeout. Do not impose project branch or clean-worktree requirements unless the package itself depends on a source repository.

### `LOCAL_SOURCE_FILE`

Read only the explicitly supplied source file unless the user separately authorizes broader source access.

### `REPOSITORY_ONLY`

Audit the current PKB for structure, ownership, duplication, or already-covered knowledge. Do not invent new source evidence.

## 4. Repository Gate

Before any write:

1. verify `pwd`, Git root, repository identity, branch, and HEAD;
2. run `git status --short`;
3. compare actual changes with `EXPECTED_DIRTY_FILES`;
4. stop on unexplained modifications, conflicts, or deletions;
5. read the repository's `AGENTS.md` before applying this Skill.

Never stash, reset, restore, checkout, overwrite, or silently absorb around a failed gate.

## 5. Sources to Read

Always read:

- `AGENTS.md`
- `PROJECT.md`
- `PERSONAL_CONTEXT.md`
- `PITFALL_LOG.md`

Read only the references required by the candidate types:

- always: [Knowledge routing](references/knowledge-routing.md) and [Privacy and deduplication](references/privacy-and-dedup.md);
- package-based source: [Source package contract](references/source-package-contract.md);
- Pitfall candidate: [Pitfall quality](references/pitfall-quality.md);
- reporting: [Report contract](references/report-contract.md).

Avoid `archive/` unless traceability is necessary.

## 6. Owner Routing Comes First

Classify every detailed candidate before drafting.

Use exactly one knowledge type:

- `PERSONAL_CONTEXT`
- `PITFALL`
- `PKB_OPERATING_RULE`
- `PROJECT_ONLY`
- `WORKSPACE_RULE`
- `GENERAL_INFORMATION_ONLY`
- `NO_ACTION`

Use exactly one recommended action:

- `MERGE_INTO_EXISTING_ENTRY`
- `UPDATE_EXISTING`
- `CREATE_NEW_ENTRY`
- `ALREADY_COVERED`
- `KEEP_IN_PROJECT_ONLY`
- `UPDATE_WORKSPACE_CONTROL_SEPARATELY`
- `GENERAL_INFORMATION_NO_PKB_WRITE`
- `NO_ACTION`

Prefer, in order:

1. `MERGE_INTO_EXISTING_ENTRY`
2. `UPDATE_EXISTING`
3. `CREATE_NEW_ENTRY`

Do not write the same detailed knowledge into more than one owner file. Use only a short cross-reference when necessary.

Reviewing every Chat window does not mean storing every answer. Ordinary general information without durable user-specific, operational, or verified Pitfall value is `GENERAL_INFORMATION_ONLY`.

## 7. Candidate-level Decisions

Evaluate candidates independently.

A candidate with incomplete evidence may be marked `NEEDS_CONFIRMATION`, `PROJECT_ONLY`, `GENERAL_INFORMATION_ONLY`, or `NO_ACTION` without blocking other valid candidates.

Block the whole task only for a failed global gate, such as:

- wrong or unsafe PKB repository;
- unknown PKB worktree changes;
- missing required source package;
- unresolved privacy or authorization issue;
- unsupported package schema;
- source-project closeout failure in `PROJECT_CLOSEOUT_PACKAGE` mode only.

A Source Package is a transport format, not independent evidence. Its fact level comes from the underlying user statement or observed workflow, not from the confidence of the summary wording.

## 8. Authoritative Owners

- `AGENTS.md`: mandatory PKB-local operating, privacy, file-responsibility, deduplication, archive, validation, and Git rules.
- `PROJECT.md`: the PKB repository's own purpose, Current files, status, and maintenance entry point.
- `PERSONAL_CONTEXT.md`: durable personal background, work preferences, communication preferences, output and acceptance habits, reusable collaboration methods, and cross-project operating preferences.
- `PITFALL_LOG.md`: incidents that actually occurred and have a reusable trigger, observable symptom, sufficiently established cause, correct handling, and verification.
- `archive/`: fully retired knowledge assets with independent traceability value that Git history alone cannot express.

Personal preferences do not authorize deletion, destructive overwrite, cross-repository modification, commit, push, publication, cloud synchronization, or writing unconfirmed personal information.

## 9. Two-phase Default

### `AUDIT_ONLY`

Read, classify, deduplicate, and report. Never write, stage, or commit.

### `AUDIT_THEN_CONFIRM`

Phase one is read-only. Return:

- repository gate result;
- existing coverage;
- candidate decisions;
- one bounded execution package;
- no-action items.

Do not modify, delete, stage, or commit.

After explicit confirmation, modify only approved files and entries. Commit only when `COMMIT_MODE` is `COMMIT_AFTER_VALIDATION`.

### `DIRECT_EXECUTE_AFTER_SAFE_GATE`

Use only when the user explicitly authorizes direct execution and every repository, source, privacy, deletion, and scope gate passes.

## 10. Semantic Preservation

Routine merges and wording improvements do not require a heavy audit. A detailed semantic-preservation review is required when the change includes:

- substantial deletion or compression;
- cross-file movement;
- Pitfall merge or retirement;
- Archive movement;
- responsibility or structure changes.

Use these outcomes where applicable:

- `SUPERSEDED_CORRECTLY`
- `DUPLICATE_REMOVED`
- `MERGED_INTO_EXISTING`
- `MOVED_TO_CORRECT_DOCUMENT`
- `HISTORICAL_ONLY`
- `VALID_CONTENT_LOST`
- `NEEDS_CONFIRMATION`
- `OUT_OF_SCOPE_CHANGE`

Do not commit when `VALID_CONTENT_LOST` or `OUT_OF_SCOPE_CHANGE` exists. Stop only on the exact unresolved decision when `NEEDS_CONFIRMATION` exists.

Pitfall numbers are permanent. A merged or superseded Pitfall keeps its number as a short redirect; numbers are never reassigned.

## 11. Validation Before Commit

After approved edits, perform the smallest validation set that proves correctness:

1. confirm every change is in the correct owner file;
2. confirm no synonymous duplicate was created;
3. confirm no project-only, temporary, rapidly changing, or general-information-only content entered PKB;
4. confirm no Secret value or unconfirmed sensitive inference was added;
5. confirm cross-file moves have one surviving owner;
6. run `git diff --check`;
7. inspect `git status --short` and `git diff --stat`;
8. confirm only approved files changed;
9. create no empty commit.

Use full hashes, byte-level manifests, or exact-runtime evidence only when the task claims exact file identity, Current-to-Runtime equality, or evidence bound to exact bytes. Do not make them routine Markdown-edit gates.

Never push, publish, or cloud-sync.

## 12. Result States

Return exactly one execution result:

- `ACTION_COMPLETED_NOW`: approved changes were made and validated.
- `ALREADY_IN_DESIRED_STATE`: all eligible knowledge was already covered or the supplied candidates require no PKB write; no files changed and no empty commit was created.
- `BLOCKED`: a global gate or exact required decision is missing.

Keep candidate identification, file edits, validation, and commit state separate.

## 13. Minimum Contract Checks

When this Skill or its Bridge Prompt changes, verify at least:

1. a non-project Chat window with no durable candidate returns `NO_PKB_ACTION_REQUIRED` at the Bridge stage;
2. a non-project Chat window with a durable user-confirmed preference produces a valid `CHAT_WINDOW_REVIEW` package;
3. `CHAT_WINDOW_REVIEW` does not require Project Closeout, `PKB_SYNC_REQUIRED`, project branch, commit, or clean-worktree evidence;
4. a project Chat window may use `CHAT_WINDOW_REVIEW` before or without Project Closeout;
5. `PROJECT_CLOSEOUT_PACKAGE` remains supported as an optional convenience path;
6. fully covered candidates create no edit or commit;
7. mixed valid and invalid candidates are handled independently;
8. Secret values, general-information-only content, temporary state, and project-only details are excluded;
9. unknown PKB worktree changes block writes;
10. incorrect parameter names or unsupported schema versions block clearly.
