# Skills Guide

本目录存放本仓库提供的技能实现，它们是迁移 OpenSpec 工作流时的直接源资产。

## 角色划分

- `skills/openspec-propose/SKILL.md`
  - `propose` 的默认实现
  - 配置本仓库到其他项目时的必配资产
  - Agent 必须用它覆盖用户原有的 `propose` skill

- `skills/openspec-apply-change/SKILL.md`
  - `apply` 的条件实现
  - 只有在用户确认项目需要 `test-driven-development` 后，Agent 才能用它覆盖用户原有的 `apply` skill

- `skills/test-driven-development/SKILL.md`
  - `test-driven-development` 的参考实现
  - 只有在用户确认项目需要 `test-driven-development`，并且同意把该 skill 安装到 OpenSpec skills 目录时，才进行配置

## 标准配置顺序

1. 先迁移 `config.yaml.example`、schema 和三个 gate 文档。
2. 再用 `skills/openspec-propose/SKILL.md` 覆盖目标项目原有的 `propose` skill。
3. 然后询问用户，项目是否需要 `test-driven-development`。
4. 如果用户不需要，则停止在这里，不配置 `apply` skill，也不配置 `test-driven-development` skill。
5. 如果用户需要，则用 `skills/openspec-apply-change/SKILL.md` 覆盖目标项目原有的 `apply` skill。
6. 同时修改 `config.yaml` 和 schema，把代码变更前默认要求 `test-driven-development` 的规则写入项目配置。
7. 完成 `apply` skill 后，再询问用户是否还要把 `skills/test-driven-development/SKILL.md` 安装到 OpenSpec skills 同目录。

## 说明

- `zh/openspec 资产迁移/propose-改造思路.md` 与 `apply-改造思路.md` 现在只用于解释设计思路，不再是主迁移入口。
- 如果用户目标是 1:1 复刻本仓库，则仍按上述顺序执行，只是第一轮 TDD 询问更可能得到“是”。
