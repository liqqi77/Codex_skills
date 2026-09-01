---
name: project-delivery-governor
description: Govern versioned product delivery around one user-visible mainline, proportionate roles and gates, independent quality evidence, human acceptance, and bounded recovery. Use when organizing multi-stage development, task boards, agent collaboration, reviews, rework, releases, or a drifting or over-governed project. Do not use to add ceremony to an ordinary isolated edit that has no existing project gate.
---

# Project Delivery Governor

Make governance serve delivery. Protect the product mainline, assign clear responsibility, obtain enough independent evidence to decide, and then stop.

## Begin With the Product Mainline

Read the smallest authoritative set that reveals the current product state: roadmap or version matrix, active version summary, current task board, relevant design or contract, and the code or product surface being changed. Prefer current files over chat recollection and archived procedures.

State the work in plain language before creating tasks:

- who is using the product and in what scene;
- what they expect to complete;
- what actually blocks, confuses, or slows them;
- which user-visible capability is affected;
- where the experience first diverges from expectation;
- what decision or deliverable this version must produce.

If the issue cannot be explained without internal states, hashes, error codes, or tool names, the product problem is not yet clear. Use [product-mainline-and-diagnosis.md](references/product-mainline-and-diagnosis.md).

## Select the Smallest Sufficient Flow

Use **LEAN** by default:

1. Freeze one bounded product slice and its acceptance criteria.
2. Give one owner the implementation task.
3. Give one independent owner a consolidated quality task covering review and targeted testing.
4. Ask for human experience acceptance when behavior, wording, or interaction is user-visible.
5. Close the slice, update the board, and stop.

Add a design task and one design review only when a real product, data, or interface decision remains unresolved.

Use **STRICT** only when the work touches persistent-data migration, credentials, security, external side effects, irreversible operations, release integrity, disputed evidence, or recovery from a serious incident. Strict mode adds evidence; it does not authorize unlimited stages.

Before adding any gate, ask what decision it changes. Keep it only if it produces a product or test artifact, freezes an interface or acceptance rule, resolves the first named risk, or records an authorized human decision. Otherwise merge, reuse, or remove it. See [delivery-flow.md](references/delivery-flow.md).

## Assign Roles, Not Model Names

Use only the roles the slice needs:

- **Product authority**: decides user value, scope, and trade-offs.
- **Governor**: freezes scope, routes work, maintains the single board, and declares gates from evidence.
- **Design owner**: resolves product, architecture, data, or interface ambiguity.
- **Implementation owner**: changes the product and supplies targeted self-check evidence.
- **Independent quality owner**: reviews and tests without editing the implementation being judged.
- **Human experience owner**: accepts or rejects the real user flow.

One person or agent may hold multiple non-conflicting roles on a small slice, but the author must not independently approve their own work. A reviewer reports evidence; only the governor or product authority advances the gate.

## Keep One Truth and One Board

Maintain one current-state capsule:

- active version and product objective;
- completed capabilities;
- current slice and owner;
- next gate and its finite acceptance rule;
- known product risks and blockers;
- deliberately deferred work.

Use a minimal task lifecycle: dispatched, started, completed, gate passed or returned. Track separate dispatch, start, completion, and gate facts only when recovery needs the distinction. Do not create competing status files or treat stale activity as proof of completion.

Write every task card with one product outcome, explicit in-scope and out-of-scope boundaries, owned files or interfaces, allowed mutations, acceptance evidence, return conditions, and the next recipient. Templates are in [templates.md](references/templates.md).

## Route Findings Without Expanding the Slice

Classify every finding:

- **Current blocker**: prevents the frozen acceptance criteria; return it to the implementation owner.
- **Current non-blocker**: record it without widening the current task.
- **Future work**: place it in the roadmap or backlog; do not let it replace the active version.
- **Tool or environment issue**: perform one bounded check, then sideline it unless it blocks product evidence.

If two rounds on the same risk fail to produce a finite acceptance rule, stop implementation and return to design. Do not use repeated execution as a substitute for diagnosis.

## Stop Drift and Ceremony

Pause and reframe when any of these occurs:

- two consecutive formal turns produce no new artifact, decision, or risk reduction;
- a third unchanged validation run is proposed;
- an evaluator, harness, launcher, or test helper becomes the main work instead of the product experience;
- reports center on states, hashes, error codes, or governance fields rather than the affected user scene;
- dormant or unreachable code blocks the active product path;
- a proof artifact has no downstream consumer or decision;
- the team can describe the error but cannot say what the user cannot accomplish.

Use hashes only for artifact identity or release integrity. Use structured state only where concurrent dispatch, recovery, or durable audit genuinely depends on it. Never create evidence merely to prove that evidence exists.

## Validate in Proportion to Risk

Use the lowest sufficient rung:

1. focused static or contract check;
2. targeted automated test;
3. integration or migration rehearsal;
4. real user-flow test;
5. release or recovery exercise.

Start with the first named risk. Increase scope only when earlier evidence reveals uncertainty. Independent quality should produce one consolidated conclusion with blockers separated from advice. Human experience acceptance is mandatory for a claimed improvement to a visible workflow. See [review-and-testing.md](references/review-and-testing.md).

## Recover Incidents Without Rewriting History

Separate the logical task, dispatch attempt, runtime session, product result, and gate decision. A lost or interrupted session does not erase a valid artifact; a completed worker message does not prove that the product gate passed.

When progress is abnormal, classify the event, preserve existing artifacts, select one recovery action, and continue from the first unproven fact. Do not redispatch the same mutation blindly or let an incident responder alter product artifacts or approve the gate. Use [incident-recovery.md](references/incident-recovery.md).

## Report Product Outcomes First

Lead each stage report with:

1. what users can now do, or still cannot do;
2. the scenario affected;
3. what changed and the evidence that matters;
4. remaining risk or deferred work;
5. the next authorized gate.

Stop after the authorized gate. Do not infer permission to commit, push, release, publish, upload, or begin the next version.

## Reference Map

- [delivery-flow.md](references/delivery-flow.md): modes, roles, state, boards, version lifecycle.
- [product-mainline-and-diagnosis.md](references/product-mainline-and-diagnosis.md): user-centered framing and bounded diagnosis.
- [review-and-testing.md](references/review-and-testing.md): gate value, evidence, rework, and acceptance.
- [incident-recovery.md](references/incident-recovery.md): abnormal-session and duplicate-work recovery.
- [templates.md](references/templates.md): compact reusable cards and reports.
- [project-evolution.md](references/project-evolution.md): lessons distilled from successive project versions.
