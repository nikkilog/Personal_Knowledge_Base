# Report Contract

## Phase-one Audit

Report at least:

- Repository Context
- Sources Read
- Existing Coverage
- Personal Context Candidates
- Pitfall Candidates
- PKB Operating Rule Candidates
- Workspace Rule Candidates
- Knowledge Absorption Plan
- No-action Items
- Recommended Execution Package

Do not present an identified candidate as a file modification or a modification as a committed change.

## Final Report

Report every field, using `NONE`, `NO`, or `N/A` where appropriate:

```text
SOURCE_MODE:
KNOWLEDGE_FOCUS:
EXECUTION_RESULT:
FILES_MODIFIED:
PERSONAL_CONTEXT_UPDATED:
PITFALL_LOG_UPDATED:
PKB_AGENTS_UPDATED:
PKB_PROJECT_UPDATED:
KNOWLEDGE_ADDED:
KNOWLEDGE_MERGED:
ALREADY_COVERED:
PROJECT_ONLY_ITEMS:
WORKSPACE_RULE_FOLLOW_UP_REQUIRED:
PROJECT_SPECIFIC_DETAILS_ADDED:
SECRET_VALUES_EXPOSED:
SENSITIVE_INFERENCES_ADDED:
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
