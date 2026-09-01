# Project Delivery Governor

[English](README.md) | [中文](README.zh-CN.md)

`project-delivery-governor` is a Codex Skill for governing product delivery. It keeps work centered on what users need to accomplish while preserving proportionate ownership, independent quality evidence, human acceptance, and incident recovery.

### Problems It Addresses

- Evaluation tools, internal states, hashes, or error codes displace the product mainline.
- Small outcomes are split into too many tasks and review gates.
- The same problem is repeatedly tested without producing new information.
- Code is completed without confirming that users can complete the actual workflow.
- Interrupted or duplicated agent tasks create conflicting changes and unclear state.

### Core Flow

```text
describe the user scenario
        ↓
identify the active version mainline
        ↓
freeze one complete and bounded product outcome
        ↓
implementation → independent quality → human acceptance
        ↓
update current state and stop
```

The Skill uses a lean flow by default. Stricter controls are added only for data migration, security, external side effects, irreversible operations, release integrity, or serious incident recovery.

### Main Capabilities

- Define version outcomes, scope, and finite acceptance criteria.
- Separate product, design, implementation, independent quality, and human acceptance responsibilities.
- Route current blockers, non-blockers, future work, and tool issues separately.
- Stop repeated reviews, repeated tests, and investigations with no information gain.
- Recover tasks that never started, were interrupted, were duplicated, or returned late.
- Provide compact templates for task cards, diagnosis, quality conclusions, and stage reports.

### Usage

After installation, reference the Skill directly in a request:

```text
Use $project-delivery-governor to organize this version with the leanest flow that is sufficiently safe.
```

The executable Codex instructions are in [`SKILL.md`](SKILL.md). Detailed workflows and templates are under [`references/`](references/).

### Boundaries

Use this Skill for multi-stage projects, version delivery, task coordination, reviews, acceptance, and recovery. Do not add ceremony to an ordinary isolated edit merely to invoke it. The Skill does not grant permission to commit, push, release, publish, or perform other external actions.
