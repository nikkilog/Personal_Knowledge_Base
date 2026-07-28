# Personal Knowledge Base Repository Rules

> Scope: This file applies only to the `Personal_Knowledge_Base` repository.
>
> Purpose: Define mandatory operating, privacy, ownership, editing, validation, local Git, and GitHub read-only mirror rules. Personal preferences belong in `PERSONAL_CONTEXT.md`; reusable incidents belong in `PITFALL_LOG.md`.

## 1. Rule Priority and Authorization

- A current, explicit user instruction controls task-specific choices when it is consistent with higher-level safety requirements.
- This file defines the repository's mandatory default rules. A request to permanently change one of these rules must be explicit and must update this file.
- `PERSONAL_CONTEXT.md` describes preferences and default collaboration patterns; it does not by itself authorize deletion, destructive overwrite, cross-repository modification, staging, commit, push, publication, cloud synchronization, or writing unconfirmed personal information.
- A Skill or Source Package may provide execution details and source facts, but it must not silently override this file.

When PKB files conflict, use this order for repository interpretation:

1. current explicit user instruction;
2. `AGENTS.md` mandatory repository rules;
3. the active Skill execution contract;
4. `PROJECT.md` PKB status and Current entry points;
5. `PERSONAL_CONTEXT.md` durable preferences;
6. `PITFALL_LOG.md` experience-based guidance.

## 2. Storage, Authority, and GitHub Mirror

- The local `Personal_Knowledge_Base` repository and its local files are the sole editing source and authoritative Current.
- Local Git is the routine version-history mechanism.
- The GitHub repository `nikkilog/Personal_Knowledge_Base` may be maintained as a read-only online mirror so online ChatGPT sessions can retrieve task-relevant PKB knowledge.
- All PKB edits, deduplication, validation, and commits must be completed locally. Do not edit PKB directly through GitHub, an online AI session, or another cloud copy.
- Mirror synchronization must start from a validated local commit and requires explicit user authorization. The GitHub mirror must not develop an independent Current or unreviewed history.
- Do not synchronize or back up the repository to Google Drive, iCloud, OneDrive, Dropbox, shared storage, or another cloud service unless this rule is explicitly changed.
- Do not copy PKB files into CAH or another project repository.
- Encrypted offline backup is allowed.

## 3. Credentials and Privacy

- Never store Secret values, tokens, passwords, private keys, authentication JSON, Service Account JSON, OAuth credential files, recovery codes, or equivalent credential material.
- A necessary Secret name or non-sensitive configuration key may be recorded only when it is needed to explain a durable operating rule; its value must never be recorded.
- Do not write AI-inferred personal or sensitive attributes unless the user explicitly confirms them.
- Remove unnecessary project names, absolute project paths, versions, branches, commits, hashes, run IDs, spreadsheet IDs, folder IDs, and other one-off identifiers from PKB knowledge.
- Preserve only the minimum context required to understand and apply a durable rule.

## 4. Access Rules

- Ordinary code tasks must not read `PERSONAL_CONTEXT.md` by default.
- Read `PERSONAL_CONTEXT.md` only when the user explicitly requests it, the task directly depends on durable personal context, or an approved PKB knowledge-absorption workflow requires it.
- When the user asks an online ChatGPT session to consult PKB, search the GitHub mirror using task-relevant terms and read only the matched files and necessary sections or paragraphs. Expand the search only when the first retrieval is insufficient; do not read all four Current Markdown files merely for formality.
- PKB provides durable preferences, governance rules, and reusable Pitfalls; it is not evidence of an external project's current implementation. For work on an existing project, the source project's Current files, actual code, and user-supplied reference assets are authoritative for current contracts. If those sources are unavailable or do not establish a material detail, request evidence instead of inventing it.
- For an audit based on files supplied by the user, use the supplied Current copies as the source of truth. Do not silently substitute older Library copies or neighboring files.

## 5. Authoritative File Responsibilities

- `AGENTS.md`: mandatory PKB-local operating, privacy, file-ownership, deduplication, archive, validation, and Git rules.
- `PROJECT.md`: the PKB repository's own purpose, Current files, status, maintenance entry point, and current maintenance focus.
- `PERSONAL_CONTEXT.md`: durable personal background, working preferences, communication preferences, output and acceptance habits, and cross-project collaboration preferences.
- `PITFALL_LOG.md`: incidents that actually occurred and have reusable, sufficiently established causes and verified or strongly evidenced handling.
- `archive/`: fully retired knowledge assets with independent traceability value that Git history alone cannot express.

Do not duplicate the same detailed rule across multiple owner files. A short cross-reference is allowed when necessary.

## 6. Editing, Deduplication, and Archive Rules

- Modify Current files in place inside the repository.
- Do not create parallel Current copies named `final`, `updated`, `fixed`, `new`, `最新版`, `(1)`, or similar.
- Routine edit history belongs in Git History; it must not create Archive copies.
- Before adding knowledge, search the correct owner file and prefer, in order:
  1. merge into an existing entry;
  2. update an existing entry;
  3. create a new entry only when no adequate owner exists.
- If knowledge is already fully covered, do not modify files and do not create an empty commit.
- Cross-file movement must use the semantic result `MOVED_TO_CORRECT_DOCUMENT`; identify the former owner and the surviving owner, then remove duplicate detailed text only after confirming semantic preservation.
- A substantial deletion, compression, merge, or relocation must not lose valid triggers, actions, limitations, or verification methods.

## 7. Definitions

- **Current**: the single authoritative file or entry that remains in active use and is updated in place.
- **Formal project closeout**: the relevant source-project work has completed its necessary documentation and validation, its related changes are locally committed or explicitly dispositioned, and its worktree is clean enough to hand off stable knowledge.
- **Necessary merge**: a branch or integration step whose result is required to identify the source project's authoritative state. Do not create merge commits, rebase, or squash merely to satisfy formality.
- **Independent PKB closeout**: source-project work and PKB work use separate repositories, separate diffs, and separate commits.

## 8. Independent Chat Review and Project Closeout Compatibility

- Any Chat window may independently run a PKB Review, whether or not it belongs to a Project.
- The default independent entry is `SOURCE_MODE: CHAT_WINDOW_REVIEW`.
- `CHAT_WINDOW_REVIEW` does not require a Project, Project Closeout, `PKB_SYNC_REQUIRED`, or source-project branch, commit, and clean-worktree evidence.
- If the Chat-window Bridge finds no eligible durable candidate, it returns `NO_PKB_ACTION_REQUIRED` and creates no Source Package.
- `PROJECT_CLOSEOUT_PACKAGE` is an optional compatibility and convenience entry. Its closeout and `PKB_SYNC_REQUIRED` gates apply only in that source mode.
- Ordinary general information, one-off facts, project Current state, and candidates classified as `INFERENCE` or `NEEDS_CONFIRMATION` do not enter PKB.

- After a formal project closeout, actively check whether the work produced durable personal preferences, reusable collaboration rules, verified cross-project Pitfalls, or changes to PKB-local operating rules. This is an additional convenience path, not a prerequisite for independent Chat Review.
- Complete and clean the source project before editing PKB. During this handoff flow, do not keep both the source repository and PKB repository under active uncommitted editing at the same time.
- Project-specific state, versions, identifiers, Current files, next steps, business rules, and readable repository facts remain in the source project.
- A Source Package is a transport format, not independent evidence. Its fact level must come from the underlying user statement or observed workflow, not from the confidence of the summary wording.
- Evaluate candidates independently. One incomplete candidate does not block other valid candidates; only a failed repository, privacy, source-integrity, or authorization gate blocks the whole task.

## 9. Modification Gates

- Modify `AGENTS.md` only when PKB-local operating rules, privacy boundaries, file responsibilities, deduplication, archive handling, validation, or Git rules change.
- Modify `PROJECT.md` only when the PKB repository's own status, structure, Current entry points, or maintenance workflow changes.
- Do not update either file merely because a new preference or Pitfall was absorbed.
- Deletion, destructive rewrite, archive movement, or removal of an existing numbered Pitfall requires explicit approval of the exact scope.

## 10. Minimum Validation and Commit Rules

After approved edits, perform the smallest validation set that can prove correctness:

1. confirm the change is in the correct owner file;
2. confirm no synonymous duplicate was created;
3. confirm no project-only or temporary state entered PKB;
4. confirm no Secret value or unconfirmed sensitive inference was added;
5. run `git diff --check`;
6. inspect `git status --short` and `git diff --stat`;
7. confirm only approved files changed;
8. for a deletion, merge, major compression, or cross-file move, verify semantic preservation and the surviving owner;
9. create no empty commit.

Full hashes, byte-level manifests, or exact-runtime evidence are required only when the task specifically claims exact file identity, Current-to-Runtime equality, or evidence bound to exact bytes. They are not routine requirements for ordinary Markdown edits.

- Commit only when the user has authorized execution and the selected workflow permits a commit.
- PKB commits must be independent from source-project commits.
- Upload or push a validated local commit to the GitHub read-only mirror only when the user has explicitly authorized that synchronization.
- Never publish or cloud-sync PKB through another destination unless the governing rule is explicitly changed.
