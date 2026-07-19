# Source Package Contract

## Purpose

A PKB task started after project closeout may not have access to the earlier project thread. The source package must therefore be self-contained enough to classify durable knowledge without reopening or reinterpreting the source project.

## `PROJECT_CLOSEOUT_PACKAGE`

The package should contain, where applicable:

- source project or workstream name;
- project closeout summary;
- files updated and their responsibilities;
- current project phase;
- current authoritative code, notebook, scripts, and documents;
- superseded artifacts or decisions not to reopen;
- project-specific pitfalls already preserved in the source project;
- candidate cross-project preferences and reusable pitfalls;
- unresolved items that remain project-only;
- branch, commit, and clean-worktree evidence;
- confirmation that no cloud publication or cross-repository modification occurred.

The package may be pasted text, a user-provided file, or a local file explicitly supplied through `SOURCE_FILE`.

## Source Sufficiency

A source is sufficient when PKB can determine:

1. what durable behavior or lesson is being proposed;
2. what real evidence supports it;
3. whether it is project-only or cross-project;
4. whether the source project has already preserved its own current state;
5. whether the source project is closed and clean.

Do not request full project history when a verified closeout report is sufficient.

## `CURRENT_CODEX_THREAD`

Use only when the current task actually includes the relevant project work and closeout evidence. Never assume access to an earlier task or hidden Codex thread.

## `USER_PROVIDED_SOURCE_PACKAGE`

Use for user-supplied knowledge that is not necessarily tied to a project closeout, such as a web research package, a pasted operating principle, or a manually assembled set of incidents.

## `LOCAL_SOURCE_FILE`

Use only the explicitly supplied local file. Do not browse neighboring project files unless separately authorized and necessary.

## `REPOSITORY_ONLY`

Use only to audit the current PKB for duplication, structure, or already-covered knowledge. It does not authorize inventing source evidence for new preferences or pitfalls.
