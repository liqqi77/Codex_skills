# Product Mainline and Diagnosis

## Identify the Mainline

A task belongs on the product mainline when it directly enables, restores, or validates a capability a user needs in the active version. Examples include completing an add-item flow, preserving location relationships, restoring data, or making device pairing usable.

Supporting infrastructure belongs on the mainline only while it is necessary to prove or deliver that capability. An evaluator, harness, launcher, migration helper, or telemetry layer is not the product outcome.

Before spending meaningful time, answer:

- What can the user not complete?
- In which concrete scene does this occur?
- How severe or frequent is it?
- What is the earliest product step that diverges?
- Which version objective does it threaten?
- What is the smallest useful next decision?

If these answers are missing, pause implementation and reframe.

## Plain-Language Problem Frame

Use this compact form:

```text
User and scene:
Expected result:
Actual result:
User impact:
Earliest divergence:
Current causal hypothesis:
One check that would distinguish the hypothesis:
Smallest repair if confirmed:
```

An error message, stack trace, hash mismatch, status value, or evaluator failure may be evidence. It is not the problem statement unless it directly describes what the user experiences.

## Find the Earliest Cause

Trace backward from the visible failure:

1. user action;
2. interface state and input;
3. application rule or orchestration;
4. domain or data operation;
5. storage, provider, device, or external system;
6. supporting test or evaluation tool.

Repair the earliest confirmed divergence that is inside scope. Avoid patching every downstream symptom.

## Use Information Gain

Every probe must distinguish between plausible causes or reduce a named uncertainty. Record:

- the question;
- the expected observations for each hypothesis;
- the actual observation;
- the decision changed by the result.

After two probes on the same question produce no new information, stop. Rewrite the hypothesis, inspect a different boundary, or ask for the missing product decision. Do not add more logging or rerun the same test by habit.

## Contain Tool and Evaluator Failures

When a supporting tool fails:

1. determine whether the real product path can still be exercised;
2. perform one bounded check of the tool or environment;
3. if product evidence remains available, record the tool defect separately and continue the mainline;
4. if the tool is the only path to evidence, define the smallest replacement or manual check;
5. never redesign the product around a disposable evaluator.

Time spent on support tooling must remain visibly subordinate to user value.

## Control Architecture Work

Introduce a boundary only when it isolates a real responsibility, stabilizes an interface, enables independent testing, or prevents a named failure. Prefer a few clear modules—such as user interface, application orchestration, domain/data, device/provider integration—over layers created for symmetry.

Before adding abstraction, answer:

- Which current change becomes safer or simpler?
- Which owner or test gains a clear boundary?
- What duplication or coupling disappears?
- Can the abstraction be understood from its public contract?

If the benefit is hypothetical, defer it.

## Product-First Reporting

Bad report:

> State X advanced, hash Y matched, evaluator Z returned an internal code.

Useful report:

> A user can now select a photo, review recognized items, remove unwanted candidates in bulk, choose a storage location, and confirm the import. The remaining limitation is recognition quality on crowded images.

Internal evidence may follow, but it must support this conclusion rather than replace it.
