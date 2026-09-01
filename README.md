# Codex Skills

[中文](#中文) | [English](#english)

## 中文

这是一个可复用的 Codex Skills 集合，用于扩展 Codex 在项目开发、交付治理和任务协作方面的工作方式。

### 已收录的 Skill

- [`project-delivery-governor`](skills/project-delivery-governor/README.md)：围绕产品主线组织版本、任务分工、独立评审、用户验收和异常恢复，避免过度评审、重复验证及工具偏离主线。

### 目录结构

```text
Codex_skills/
├── README.md
└── skills/
    └── project-delivery-governor/
        ├── SKILL.md
        ├── README.md
        ├── agents/
        └── references/
```

### 使用方式

将需要的 Skill 文件夹复制到项目的 `.agents/skills/`，或者个人 Codex Skills 目录中。安装后，可通过 Skill 名称调用，例如：

```text
使用 $project-delivery-governor 规划并推进这个版本。
```

`SKILL.md` 是 Codex 使用的正式指令入口，`README.md` 用于帮助人理解 Skill。

## English

This repository is a collection of reusable Codex Skills for software development, delivery governance, and task collaboration.

### Available Skills

- [`project-delivery-governor`](skills/project-delivery-governor/README.md): Keeps version delivery centered on a user-visible product mainline, with proportionate task ownership, independent review, human acceptance, and bounded incident recovery.

### Repository Structure

```text
Codex_skills/
├── README.md
└── skills/
    └── project-delivery-governor/
        ├── SKILL.md
        ├── README.md
        ├── agents/
        └── references/
```

### Usage

Copy the desired Skill folder into the project's `.agents/skills/` directory or a personal Codex Skills directory. Invoke it by name after installation, for example:

```text
Use $project-delivery-governor to plan and deliver this version.
```

`SKILL.md` is the instruction entry point used by Codex. `README.md` is human-facing documentation.
