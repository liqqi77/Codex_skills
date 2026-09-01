# Incident Recovery

## Separate the Facts

Treat these as different objects:

- **logical task** — the intended product outcome;
- **dispatch attempt** — one effort to assign the task;
- **runtime session** — the process or agent executing it;
- **artifact result** — files, decisions, or evidence produced;
- **gate decision** — authorized acceptance or return.

A session can disappear after producing a valid artifact. A worker can report completion while the gate remains unproven. Keeping these facts separate prevents duplicate work and false progress.

## Minimal Incident Classes

### Dispatch not accepted

No owner or execution exists. Correct the task card or capacity problem, then dispatch once.

### Accepted but not started

Check whether approval, environment setup, or capacity is blocking start. Do not create a duplicate owner until the first attempt is explicitly cancelled or proven absent.

### Waiting for approval or user input

Preserve artifacts and state the exact decision needed. Do not simulate approval or route around a meaningful product choice.

### Interrupted or lost session

Inspect shared artifacts and evidence first. Continue from the first unproven fact rather than restarting the logical task.

### Duplicate or overlapping work

Freeze additional mutation, select one authoritative artifact, compare only the conflicting surface, and retire the duplicate attempt. Never merge blindly.

### Late result

Compare the returned artifact with the current contract and baseline. Reuse it only if it still satisfies them; otherwise record it as historical evidence.

### Governed-data or state-store issue

Diagnose with the smallest read-only query. Back up before repair, use one owner for the mutation, and verify the specific invariant afterward. Do not turn the product board into a database debugging console.

## Recovery Sequence

1. Restate the logical product outcome and current gate.
2. Preserve existing artifacts; do not overwrite uncertain work.
3. Identify which of dispatch, start, completion, or gate is unproven.
4. Inspect the smallest authoritative evidence.
5. Choose one action: continue, reattach, redispatch, cancel duplicate, request approval, or return to design.
6. Assign one owner and one finite completion condition.
7. Update the current board once.
8. Resume the normal flow from the first unproven fact.

## Recovery Boundaries

An incident responder may inspect, preserve, classify, and restore execution. They must not silently:

- edit product artifacts to manufacture completion;
- change acceptance criteria;
- declare the quality gate;
- delete uncertain evidence;
- commit, push, publish, or release without authority.

## Anti-Loop Rules

- Do not redispatch an identical mutating task while an earlier attempt may still run.
- Do not poll unchanged state indefinitely; use bounded waits and report only changed information.
- After two recovery attempts with the same failure and no new evidence, reframe the cause or escalate the missing decision.
- Recovery ends when normal ownership and the next finite gate are restored, not when every historical inconsistency is explained.
