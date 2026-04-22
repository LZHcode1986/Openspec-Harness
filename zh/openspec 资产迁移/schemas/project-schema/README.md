# project-schema 骨架

这是一个可迁移的 OpenSpec schema 示例骨架。

目录结构：
- `schema.yaml`：定义 artifact 顺序、依赖关系和统一说明
- `templates/proposal.md`：提案模板
- `templates/design.md`：设计模板
- `templates/spec.md`：规范模板
- `templates/tasks.md`：任务模板

补充说明：
- 把默认的 `test-driven-development` 入口约束写进 `apply.instruction`，不要把完整 TDD 流程压进 `propose` 或 `tasks` 模板正文。
- `tasks.md` 采用 `Setup -> Blocking -> Slice A -> Slice B -> Reconciliation` 结构；如果是 `interactive` change，`Blocking` 第一项必须是 `Proof Task`。
- 如果 `tasks.md` 显式定义了 `Slice A` 或 `Slice B` 的 `verifier` gate，就要把它们写成独立的切片边界校验任务，并明确校验范围和 `PASS/FAIL` 条件。

迁移原则：
- 保留结构，不复制本项目业务名词
- 只保留方法论和约束
- 所有项目专有内容都用占位符替换
