# propose 流程改造思路

这份文档现在只用于解释 `skills/openspec-propose/SKILL.md` 为什么这样设计，不再作为迁移主入口。

它描述的是：如何把 OpenSpec 的 `propose` 从“多轮 coverage gate”收敛为“proofability-first 的轻量规划流程”。

## 目标
- 让 `propose` 在进入 `design` 前先完成 `proofability check`。
- 把真实入口、用户路径、authority 单源和验证方式先写清。
- 避免 proposal、design、specs、tasks 彼此脱节。

## 建议改造点
1. 在 `proposal.md` 完成后先执行 `proofability check`。
2. check 重点只看：
   - 真实入口
   - 用户操作顺序
   - authority 单源
   - 明确不算完成的证据
   - 最终验证方式
3. 不再把 proposal coverage / design coverage 作为独立门禁。
4. `tasks readiness check` 只在 `tasks.md` 完成后执行，用于确认任务是否已能进入 `apply`。
5. 让 `propose` 在输出上明确标记：
   - 哪些内容已满足
   - 哪些内容需要回写到 proposal / design / specs / tasks

## 推荐执行顺序
1. 先读 `config.yaml`
2. 再读 proposal / design / specs / tasks
3. 再继续写 design / specs / tasks
4. 最后执行 `tasks readiness check`
5. 通过后才允许进入 `apply`

## 迁移时需要替换的内容
- `OpenSpec` 的具体命令名或技能名
- 你项目自己的文档路径
- 你项目自己的权威来源名称
- 你项目自己的验证命令
