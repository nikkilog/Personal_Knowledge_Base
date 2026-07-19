# Privacy, Deduplication, and Semantic Preservation

## Privacy Gate

- Keep PKB strictly local: do not push, publish, cloud-sync, or place it in shared storage.
- Never store Secret values, tokens, passwords, private keys, OAuth credentials, Service Account JSON, authentication JSON, or recovery codes.
- Never store AI-inferred sensitive personal attributes without explicit user confirmation.
- Remove unnecessary project paths, versions, hashes, IDs, run IDs, spreadsheet IDs, and one-off state.
- Preserve only the minimum context required to understand and execute a durable rule.

Exclude unsafe material rather than weakening these rules.

## Deduplication Priority

Evaluate candidates in this order:

1. `MERGE_INTO_EXISTING_ENTRY`
2. `UPDATE_EXISTING`
3. `CREATE_NEW_ENTRY`
4. `ALREADY_COVERED`
5. `NO_ACTION`

Prefer extending the best existing entry. Avoid synonymous duplicates and remove project-specific details. Do not abstract so aggressively that the rule loses its trigger, action, or verification method.

## Deletion Decision Boundary

Do not modify or delete source-project files from this Skill.

For PKB content deletion, major compression, or Archive cleanup:

- list the exact file, section, or entry;
- explain why it is superseded, duplicated, or being merged;
- state where surviving knowledge will remain;
- obtain explicit user approval before removal;
- use a screenshot or concrete entry list when that makes confirmation easier;
- do not treat Git history as a substitute for semantic-preservation review.

## Semantic Preservation Classification

Classify removed or rewritten content as:

- `SUPERSEDED_CORRECTLY`
- `DUPLICATE_REMOVED`
- `MERGED_INTO_EXISTING`
- `VALID_CONTENT_LOST`
- `NEEDS_CONFIRMATION`

Do not commit when `VALID_CONTENT_LOST` exists. Stop and request the single necessary decision when `NEEDS_CONFIRMATION` exists.
