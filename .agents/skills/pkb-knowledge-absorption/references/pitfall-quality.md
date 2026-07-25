# Pitfall Quality

## Eligibility

Add or materially update a Pitfall only when:

- the problem actually occurred;
- the observable symptom is known;
- the cause is sufficiently established;
- the correct handling was verified or strongly evidenced;
- recurrence is plausible;
- the lesson has cross-task reuse value.

If evidence remains incomplete, keep it project-only, mark the candidate `NEEDS_CONFIRMATION` or `NO_ACTION`, or merge only the verified portion into an existing entry.

## Required Content

A current Pitfall must preserve:

- status;
- problem and reusable scope;
- observable symptom;
- root cause and material wrong handling;
- correct handling;
- verification and prevention.

Do not create vague reminders such as “be careful,” “remember to check,” or “there may be a problem.”

## Merge and Split

Merge entries when they have the same trigger, root cause, repair mechanism, and verification logic.

Split entries when they can occur independently or have materially different causes, handling, or verification, even if they share the same project or technology.

A broad topic such as Git, Notebook, Google, or API is not by itself a reason to merge.

## Number Stability

- Assigned `P` numbers are permanent.
- Do not renumber after reordering.
- Do not reuse retired numbers.
- When an entry is merged or superseded, keep the old number as a short redirect to the surviving entry.

## Lifecycle

Use only:

- `已确认`
- `部分确认`
- `待验证`
- `已废弃`
- `已替代`

Platform behavior can change. “已确认” means verified in the recorded environment, not guaranteed forever. If applicability becomes uncertain, mark it `待验证`; when replaced, mark it `已替代` and identify the successor.

`待验证` is only for an existing incident that actually occurred and whose original cause and handling were sufficiently established, but whose current platform applicability now needs re-verification. It must not be used to admit a conjecture, an event that did not occur, an unresolved root cause, `INFERENCE`, or `NEEDS_CONFIRMATION` as a formal Pitfall.
