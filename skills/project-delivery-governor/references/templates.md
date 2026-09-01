# Compact Templates

Use only the fields needed by the current project. Delete empty sections instead of filling them with ceremony.

## Current-State Capsule

```markdown
# Current State

- Active version:
- User-visible objective:
- Delivered capabilities:
- Current slice:
- Owner:
- Next gate:
- Acceptance rule:
- Current blockers:
- Known product risks:
- Deliberately deferred:
- Authoritative links:
```

## Task Card

```markdown
# Task: <product outcome>

## Why now
User and scene:
Blocked or missing capability:
Version objective affected:

## Scope
In scope:
Out of scope:
Owned files or interfaces:
Allowed mutations:

## Acceptance
- Observable outcome:
- First named risk:
- Required evidence:
- Explicit non-goals:

## Routing
Owner:
Independent reviewer:
Return when:
Next recipient or gate:
```

## Product Diagnosis

```markdown
# Product Problem

- User and scene:
- Expected result:
- Actual result:
- User impact:
- Earliest divergence:
- Current hypothesis:
- Discriminating check:
- Smallest repair if confirmed:
- Tool or infrastructure issues kept separate:
```

## Independent Quality Report

```markdown
# Quality Conclusion: PASS | PASS WITH FOLLOW-UP | RETURN

## Product conclusion
What the user can or cannot complete:

## Evidence against acceptance criteria
- Criterion:
  Evidence:
  Result:

## Findings
Current blockers:
Current non-blockers:
Future work:
Environment or tool issues:

## Residual risk

## Required next decision
```

## Human Experience Report

```markdown
# Experience Conclusion: ACCEPT | RETURN

- Representative user and device/environment:
- Task attempted:
- Steps that were clear:
- Points of confusion or blockage:
- Error recovery and undo behavior:
- Result shown to the user:
- Blocking corrections, if any:
- Non-blocking suggestions:
```

## Stage Report

```markdown
# Stage Result

1. User-visible outcome:
2. Scenario affected:
3. Material change:
4. Evidence that changes the decision:
5. Remaining risk or deferred work:
6. Next authorized gate:
```

## Gate-Value Note

Use before adding a new formal review, test stage, status field, or proof artifact.

```markdown
- Named risk protected:
- New information produced:
- Finite pass condition:
- Downstream decision and owner:
- Why an existing gate cannot absorb it:
- Cost and stop condition:
```

If this note cannot be completed plainly, do not add the gate.
