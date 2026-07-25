# Privacy, Deduplication, and Semantic Preservation

## Privacy Gate

- Keep PKB strictly local. Do not push, publish, cloud-sync, or place it in shared storage.
- Never store Secret values, tokens, passwords, private keys, OAuth credentials, Service Account JSON, authentication JSON, or recovery codes.
- Necessary Secret names or non-sensitive configuration keys may be kept only when required to explain a durable rule; never store values.
- Never store AI-inferred sensitive personal attributes without explicit user confirmation.
- Remove unnecessary project paths, versions, branches, commits, hashes, IDs, run IDs, spreadsheet IDs, folder IDs, and one-off state.
- Preserve only the minimum context required to understand and apply the durable rule.

Exclude unsafe material rather than weakening these rules.

## Deduplication

Evaluate candidates in this order:

1. `MERGE_INTO_EXISTING_ENTRY`
2. `UPDATE_EXISTING`
3. `CREATE_NEW_ENTRY`
4. `ALREADY_COVERED`
5. `NO_ACTION`

Do not create a new entry merely because wording differs. Preserve the trigger, action, limitation, and verification method; do not abstract until the rule becomes vague.

## Source and Evidence

A Source Package is a transport format, not independent evidence.

- `USER_CONFIRMED` requires a clear user statement.
- `USER_PROVIDED` means the user supplied the underlying fact; it does not automatically confirm an AI interpretation.
- `OBSERVED_WORKFLOW` requires concrete execution or repeated workflow evidence.
- `INFERENCE` and `NEEDS_CONFIRMATION` must not be written as formal PKB knowledge.

Confident summary wording must not upgrade evidence level.

## Candidate-level Handling

Judge candidates independently. An incomplete or project-only candidate does not block other valid candidates.

Block the whole task only for a failed repository, privacy, source-integrity, authorization, or schema gate.

## Semantic Preservation

Use detailed review only for substantial deletion, compression, merge, Archive movement, responsibility change, or cross-file movement.

Classify affected content as applicable:

- `SUPERSEDED_CORRECTLY`
- `DUPLICATE_REMOVED`
- `MERGED_INTO_EXISTING`
- `MOVED_TO_CORRECT_DOCUMENT`
- `HISTORICAL_ONLY`
- `VALID_CONTENT_LOST`
- `NEEDS_CONFIRMATION`
- `OUT_OF_SCOPE_CHANGE`

Do not commit when `VALID_CONTENT_LOST` or `OUT_OF_SCOPE_CHANGE` exists.

## Traceability

Do not put project-only provenance back into PKB正文 merely for traceability.

- PKB正文 stores the abstract durable rule.
- The PKB commit message or audit report may record the source scenario and absorption action.
- The source project retains detailed project evidence.
