# Codex Skills

[English](README.md) | [中文](README.zh-CN.md)

This repository is a collection of reusable Codex Skills for software development, delivery governance, and task collaboration.

### Available Skills

- [`project-delivery-governor`](project-delivery-governor/README.md): Keeps version delivery centered on a user-visible product mainline, with proportionate task ownership, independent review, human acceptance, and bounded incident recovery.

### Repository Structure

```text
Codex_skills/
├── README.md
├── README.zh-CN.md
└── project-delivery-governor/
    ├── SKILL.md
    ├── README.md
    ├── README.zh-CN.md
    ├── agents/
    └── references/
```

### Usage

Copy the desired Skill folder into the project's `.agents/skills/` directory or a personal Codex Skills directory. Invoke it by name after installation, for example:

```text
Use $project-delivery-governor to plan and deliver this version.
```

`SKILL.md` is the instruction entry point used by Codex. `README.md` is human-facing documentation.
