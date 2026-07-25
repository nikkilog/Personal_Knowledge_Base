# Report Contract

## Phase-one Audit

Keep the default audit concise. Report:

### Repository Gate

- repository;
- branch;
- HEAD;
- Git status;
- safe to continue: `YES` or `NO`.

### Existing Coverage

State the relevant existing owner and whether the candidate is already covered.

### Candidate Decisions

For each material candidate include only:

- candidate;
- fact level;
- knowledge type;
- existing owner or coverage;
- recommended action;
- project-specific details to strip;
- unresolved decision, if any.

### Bounded Execution Package

Provide one recommended set of exact files and entries that may change after confirmation.

### No-action Items

Identify items that are already covered, project-only, unverified, temporary, sensitive, or without durable value.

Phase one must not modify, delete, stage, or commit.

Expand into detailed evidence tables only when a deletion, major compression, cross-file move, disputed classification, or other high-risk change requires it.

## Bridge and Source-mode Boundary

- A Chat-window Bridge with no eligible durable candidate returns `NO_PKB_ACTION_REQUIRED` and creates no Source Package.
- `ALREADY_IN_DESIRED_STATE` is a Skill execution result used after a valid source reaches repository routing and deduplication; it is not a replacement for the Bridge result.
- `CHAT_WINDOW_REVIEW` is the default independent source mode and must not inherit Project, Project Closeout, `PKB_SYNC_REQUIRED`, branch, commit, or clean-worktree gates.
- `PROJECT_CLOSEOUT_PACKAGE` is an optional compatibility entry whose closeout gates apply only in that source mode.

## Final Report

Report every field, using `NONE`, `NO`, or `N/A` where appropriate:

```text
PERSONAL_KNOWLEDGE_REVIEWED:
PACKAGE_SCHEMA_VERSION:
SOURCE_MODE:
SOURCE_SCOPE:
KNOWLEDGE_FOCUS:
EXECUTION_RESULT:
FILES_MODIFIED:
PERSONAL_CONTEXT_UPDATED:
PITFALL_LOG_UPDATED:
PKB_AGENTS_UPDATED:
PKB_PROJECT_UPDATED:
ARCHIVE_UPDATED:
KNOWLEDGE_ADDED:
KNOWLEDGE_MERGED:
KNOWLEDGE_MOVED:
ALREADY_COVERED:
PROJECT_ONLY_ITEMS:
WORKSPACE_RULE_FOLLOW_UP_REQUIRED:
PROJECT_SPECIFIC_DETAILS_ADDED:
SECRET_VALUES_EXPOSED:
SENSITIVE_INFERENCES_ADDED:
SEMANTIC_PRESERVATION_RESULT:
GIT_DIFF_CHECK:
COMMIT_HASH:
CURRENT_BRANCH:
WORKTREE_CLEAN:
PUSH_PERFORMED:
CLOUD_SYNC_PERFORMED:
OTHER_REPOS_MODIFIED:
NEXT_ACTION:
```

Use `ACTION_COMPLETED_NOW`, `ALREADY_IN_DESIRED_STATE`, or `BLOCKED` for `EXECUTION_RESULT`.

Never conflate candidate identification, file edits, validation, and commit state.
