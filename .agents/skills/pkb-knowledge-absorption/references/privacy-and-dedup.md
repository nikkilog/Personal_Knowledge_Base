# Privacy and Deduplication

## Privacy Gate

- Keep the PKB strictly local: do not push, publish, cloud-sync, or place it in shared storage.
- Never store Secret values, tokens, passwords, private keys, OAuth credentials, Service Account JSON, or authentication JSON.
- Never store AI-inferred sensitive personal attributes without explicit user confirmation.
- Remove unnecessary project paths, versions, hashes, IDs, and run IDs.

Exclude unsafe material rather than weakening these rules. Preserve only the minimum context required to understand and execute a durable rule.

## Deduplication Priority

Evaluate candidates in this order:

1. `MERGE_INTO_EXISTING_ENTRY`
2. `UPDATE_EXISTING`
3. `CREATE_NEW_ENTRY`
4. `ALREADY_COVERED`
5. `NO_ACTION`

Prefer extending the best existing entry. Avoid synonymous duplicates, remove project-specific details, and retain enough context for execution. Do not abstract so aggressively that the rule loses its trigger, action, or verification method.
