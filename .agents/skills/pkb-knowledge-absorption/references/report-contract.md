# Report Contract

## Phase-one Audit

Report at least:

### Repository Context

- repository;
- branch;
- HEAD;
- Git status;
- whether it is safe to continue.

### Sources Read

List the actual PKB files and source package/thread/file evidence read.

### Existing Coverage

State what the current PKB already covers and where.

### Candidate Tables

- Personal Context Candidates
- Pitfall Candidates
- PKB Operating Rule Candidates
- Workspace Rule Candidates

For each candidate include:

- candidate knowledge;
- source evidence;
- expected durability;
- applicability;
- current owner or coverage;
- project-specific details to remove;
- knowledge type;
- recommended action.

### Knowledge Absorption Plan

Include:

- knowledge type;
- candidate;
- existing owner;
- target file;
- recommended action;
- write/merge method;
- project-specific information removed;
- whether an update is needed.

### Files Proposed

List only files that may actually change.

### No-action Items

Explicitly identify knowledge that is already covered, project-only, unverified, temporary, sensitive, or without durable value.

### Recommended Execution Package

Provide one unique recommended package. Phase one must not modify, delete, stage, or commit.

Do not present an identified candidate as a file modification or a modification as a committed change.

## Final Report

Report every field, using `NONE`, `NO`, or `N/A` where appropriate:

```text
PERSONAL_KNOWLEDGE_REVIEWED:
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

Use `ACTION_COMPLETED_NOW`, `ALREADY_IN_DESIRED_STATE`, or `BLOCKED` for `EXECUTION_RESULT`. Never conflate audit findings, edits, validation, and commit state.
