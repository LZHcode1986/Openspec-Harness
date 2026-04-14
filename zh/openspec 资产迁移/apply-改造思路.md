# apply 流程改造思路

这份文档描述如何把 OpenSpec 的 `apply` 从“按任务直接实现”升级为“先遵循 schema 的实施流程，再推进任务”。

## 目标

- 让 `apply` 真正执行 schema 中的 `apply.instruction`。
- 当项目要求 `tdd-workflow` 时，先走 `Step 0 -> Step 7`，再推进具体实现。
- 保持 `tasks.md` 负责范围与进度，保持实施顺序由 `apply` 控制。

## 建议改造点

1. 在 `openspec instructions apply --change "<name>" --json` 之后，读取动态 `instruction`。
2. 如果 `instruction` 或项目规则命中 `tdd-workflow`，先读取该 skill，再进入编码。
3. 不把 `tasks.md` 当成唯一顺序来源；它只跟踪切片、范围和勾选状态。
4. 只有在对应 TDD 步骤完成并验证后，才允许勾选相关任务。
5. Guardrails 要明确禁止跳过 `RED -> GREEN -> REFACTOR`。

## 推荐执行顺序

1. 先选中 change
2. 再读取 `openspec status`
3. 再读取 `openspec instructions apply`
4. 根据 `apply.instruction` 判断是否需要切到 `tdd-workflow`
5. 读取 context files
6. 按要求的实施流程推进任务

## 迁移时需要替换的内容

- `OpenSpec` 的具体命令名或技能名
- 你项目自己的实施 skill 名称
- 你项目自己的 TDD skill 名称
- 你项目自己的测试与验证命令
