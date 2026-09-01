# Project Delivery Governor

[中文](#中文) | [English](#english)

## 中文

`project-delivery-governor` 是一套面向 Codex 的项目交付治理 Skill。它帮助项目围绕用户真正需要完成的事情推进，同时保留必要的分工、独立质量检查和异常恢复能力。

### 它解决什么问题

- 项目被评测工具、内部状态、哈希或错误码带偏。
- 一个小目标被拆成过多任务和评审节点。
- 同一个问题反复验证，却没有获得新的判断依据。
- 开发完成了代码，但没有验证用户是否真正能够完成操作。
- Agent 或任务中断后被重复派发，造成重复修改或状态混乱。

### 核心流程

```text
说明用户场景
    ↓
确定当前版本主线
    ↓
冻结一个完整且有限的功能目标
    ↓
实施 → 独立质量检查 → 用户体验验收
    ↓
更新当前状态并停止
```

默认采用精简流程。只有涉及数据迁移、安全、外部副作用、不可逆操作、正式发布或严重事故恢复时，才增加更严格的控制。

### 主要能力

- 明确版本目标、范围和验收条件。
- 为产品决策、设计、实施、独立质量和用户验收划分职责。
- 区分当前阻塞、非阻塞问题、未来工作和工具问题。
- 控制重复评审、重复测试和无信息增益的排查。
- 处理任务未启动、中断、重复派发和迟到结果。
- 提供任务卡、问题定位、质量结论和阶段报告模板。

### 使用方式

安装后，在请求中直接引用：

```text
使用 $project-delivery-governor 梳理当前版本，采用最精简且足够安全的交付流程。
```

Codex 的正式执行规则位于 [`SKILL.md`](SKILL.md)，详细流程和模板位于 [`references/`](references/)。

### 使用边界

这个 Skill 用于多阶段项目、版本交付、任务协作、评审验收和异常恢复。普通且独立的小修改不需要为了使用它而增加额外流程。它也不会自动授权提交、推送、发布或执行其他外部操作。

## English

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
