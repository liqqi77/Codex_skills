# Review and Testing

## Review the Risk, Not the Ceremony

Begin with the first named risk in the task card. Examples:

- the user cannot complete the primary flow;
- data may be lost or relationships corrupted;
- a device or external provider may receive the wrong action;
- a contract permits ambiguous behavior;
- a visible interaction may be technically correct but unusable.

Do not start with generic completeness. The task is to decide whether the frozen slice is safe and useful enough to advance.

## Evidence Ladder

Use the lowest sufficient level and climb only when uncertainty remains:

| Level | Evidence | Use when |
|---|---|---|
| 1 | focused static, schema, or contract check | the risk is local and deterministic |
| 2 | targeted automated test | behavior can be isolated repeatably |
| 3 | integration or migration rehearsal | boundaries, storage, providers, or compatibility matter |
| 4 | representative user-flow test | end-to-end behavior or usability is claimed |
| 5 | release, rollback, or recovery exercise | failure is costly, external, or hard to reverse |

Passing a higher level does not require repeatedly rerunning lower levels unless the artifact changed in a way that invalidates them.

## Good Evidence

Evidence is useful when it is:

- tied to a named acceptance criterion;
- produced by the current artifact or representative environment;
- specific enough to reproduce;
- independent when it supports a quality gate;
- concise enough for the decision-maker to inspect;
- clear about what was not tested.

A large log, checksum collection, screenshot pile, or test count is not strong evidence by itself.

## Consolidated Independent Quality Pass

For a normal slice, one independent owner should cover:

1. scope and contract consistency;
2. review of changed code or product behavior;
3. targeted tests for the named risks;
4. regression around the affected user path;
5. blocker/non-blocker classification;
6. one conclusion: pass, pass with recorded follow-up, or return for finite rework.

Separate specialist testing only when a specialist risk exists, such as migration integrity, security, accessibility, device compatibility, or destructive recovery.

## Finite Rework

Every return must contain:

- the failing acceptance criterion;
- the smallest reproducible observation;
- why it blocks the user or gate;
- the expected corrected behavior;
- the evidence required on resubmission.

Do not return broad requests such as “improve quality,” “test more,” or “make the architecture better.” Advice that does not block the frozen slice belongs in follow-up work.

If two returns on the same risk still lack a finite target, the problem is design ambiguity. Stop the review loop and request a design decision.

## Human Experience Acceptance

For visible workflows, internal correctness is necessary but insufficient. Exercise the real flow and answer:

- Can a new user see what to do next?
- Are required inputs possible in the actual environment?
- Can mistakes be corrected or undone?
- Are empty, loading, error, and success states understandable?
- Does the flow preserve the user's context and choices?
- Is the result expressed in product language?

Record concrete scenes, not taste alone. A human rejection returns to the relevant design or implementation boundary; it does not automatically reopen the whole version.

## Stop Conditions

Stop validation and decide when:

- every frozen criterion has proportionate evidence;
- the first named risks are resolved or explicitly accepted;
- remaining findings are categorized and routed;
- another run would repeat the same setup and expected result;
- the decision-maker has enough information to pass or return the gate.
