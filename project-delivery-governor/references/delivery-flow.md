# Delivery Flow

## Authority Order

Resolve conflicts in this order unless the project explicitly defines a stronger rule:

1. current user direction and authorized product decisions;
2. current version scope, acceptance criteria, and active task board;
3. frozen contracts, data rules, and architecture decisions;
4. current product behavior and executable evidence;
5. historical documents and prior conversation.

History explains why a rule exists; it does not silently override the active version.

## Governance Modes

### LEAN

Use for normal, reversible, bounded delivery.

```text
product slice frozen
        ↓
implementation
        ↓
one independent quality pass
        ↓
human experience acceptance, if visible
        ↓
close and update current truth
```

A design task may precede implementation when acceptance or interfaces are genuinely ambiguous. A separate design reviewer is optional and must resolve a named risk.

### STRICT

Use only for elevated risk:

- persistent-data schema or migration;
- credentials, permissions, privacy, or security;
- external messages, payments, device commands, or other side effects;
- destructive or hard-to-reverse operations;
- release identity and rollback integrity;
- evidence disputes or serious incident recovery.

Strict mode may add a frozen contract, migration rehearsal, specialist review, release manifest, or rollback exercise. Add only the control connected to the risk.

## Roles and Boundaries

| Role | Accountable for | Must not do |
|---|---|---|
| Product authority | user value, priority, scope, trade-offs | let internal defects silently replace the roadmap |
| Governor | scope freeze, routing, board, gate declaration | self-approve implementation evidence |
| Design owner | acceptance, interface, data and architecture decisions | turn a bounded slice into speculative redesign |
| Implementation owner | product change and focused self-check | declare independent quality approval |
| Independent quality owner | review, targeted tests, blocker conclusion | edit the artifact being judged in the same pass |
| Human experience owner | real-flow acceptance | substitute internal test success for usability judgment |

On a small task, combine roles only when independence is not compromised. The product authority and governor may be the same person. Design and implementation may be combined if the decision is already frozen. Implementation and independent quality must remain separate for a claimed gate.

## Minimal State

Keep the lifecycle small:

1. **Dispatched**: a bounded task card has an owner.
2. **Started**: the owner accepted the task and began work.
3. **Completed**: the owner returned the required artifact and evidence.
4. **Gate passed or returned**: the authorized decision-maker accepted it or sent finite rework.

When recovery requires precision, record four facts separately:

- **D** — dispatch was accepted;
- **S** — execution actually started;
- **C** — the requested artifact completed;
- **G** — the product gate passed.

Do not make these fields a ritual. If no concurrency or recovery ambiguity exists, one task status and its evidence are enough.

## The Single Board

The current board is a routing surface, not a diary. It should show:

- active version and user-visible objective;
- current slice, owner, and next gate;
- finite acceptance criteria;
- dependencies that actually block work;
- current blockers and deliberately deferred items;
- links to the authoritative design, artifact, and evidence.

Avoid duplicate boards for roles, models, sessions, and incident states. Archive historical detail after closeout; keep the active view short.

## Version Lifecycle

### 1. Frame

Describe the user scene, expected outcome, actual obstacle, affected capability, and earliest divergence. Separate roadmap work from defects and infrastructure chores.

### 2. Freeze

Choose one bounded slice. Define what is in scope, what is explicitly deferred, and how a person can recognize completion.

### 3. Design only what is uncertain

Freeze interfaces, data rules, or interaction decisions needed for implementation. Do not design future versions inside the current slice.

### 4. Implement

Give one owner authority over named files or interfaces. Require focused self-checks tied to the acceptance rule.

### 5. Independent quality

Combine code review, contract review, and targeted testing into one pass unless a named specialist risk requires separation.

### 6. Experience acceptance

For user-visible changes, exercise the actual path in representative conditions and record what was easy, confusing, blocked, or missing.

### 7. Close

Update the single source of truth with delivered capability, evidence, residual risk, and deferred work. Stop unless the next version is explicitly authorized.

## Gate Addition Test

Add a gate only when all are true:

1. it protects a named product or operational risk;
2. it produces information not already available;
3. it has a finite pass condition;
4. a named downstream decision consumes its output;
5. its cost is proportionate to the slice.

If any answer is no, merge the check into an existing role or remove it.
