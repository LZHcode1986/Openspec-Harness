# TDD apply 接入说明

这份说明用于把 `test-driven-development` 作为默认实施纪律接入 OpenSpec 的 `apply` 阶段。

## 目标

- 保持 `propose` 轻量，不把完整 TDD 细节压进 `tasks.md`。
- 在真正实施时，强制按 `RED -> GREEN -> REFACTOR` 执行 TDD。
- 让迁移到其他项目时，可以直接复制这条实施约束。

## 接入方式

1. 在 schema 的 `apply.instruction` 中写明：进入实施前先读取并遵循 `test-driven-development`。
2. 在 `tasks.md` 中只保留一句简洁的实施约束，不展开完整 TDD 细节。
3. 在 `openspec/config.yaml` 的 `rules.implementation` 中补一条轻量规则，保证工作流一致。
4. 在 `openspec-apply-change` 这类实施技能里，显式要求读取 `apply.instruction`，并在进入任务执行前先按 `RED -> GREEN -> REFACTOR` 执行。
5. 其余 TDD 步骤由 `test-driven-development` 自己定义，不在 OpenSpec 模板里重复展开。

## 使用边界

- 这不是 `propose` 阶段的规划规则。
- 这不是实施细节的替代品。
- 这是一条把 TDD 放到 `apply` 阶段的入口约束。

## 迁移时的最小改动点

- `schema.yaml` 的 `apply.instruction`
- `tasks.md` 中的一条实施约束
- `config.yaml` 的 `rules.implementation`
- `openspec-apply-change` 或等价实施技能
