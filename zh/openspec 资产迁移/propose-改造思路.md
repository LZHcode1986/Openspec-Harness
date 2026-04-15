# propose 流程改造思路

这份文档现在只用于解释 `skills/openspec-propose/SKILL.md` 为什么这样设计，不再作为迁移主入口。

它描述的是：如何把 OpenSpec 的 `propose` 从“覆盖率检查”升级为“统一就绪门禁”。

## 目标
- 让 `propose` 在进入 `apply` 前完成最终放行判断。
- 把覆盖率、可实施性、归档安全放到同一条流程里执行。
- 避免 proposal、design、specs、tasks 彼此脱节。

## 建议改造点
1. 在 `propose` 的末尾增加统一就绪门禁。
2. gate 必须一次性检查以下内容：
   - 范围与非目标
   - 风险与验收标准
   - 架构 authority 一致性
   - state transition / persistence / contract 影响
   - tasks 粒度、文件范围、验证命令
   - archive safety
3. 把 `QUALITY-GATE.md` 作为门禁的唯一检查依据。
4. 让 `propose` 在输出上明确标记：
   - 哪些内容已满足
   - 哪些内容阻塞进入 `apply`
   - 哪些内容需要回写到 proposal / design / specs / tasks

## 推荐执行顺序
1. 先读 `config.yaml`
2. 再读 proposal / design / specs / tasks
3. 再执行统一就绪门禁
4. 通过后才允许进入 `apply`

## 迁移时需要替换的内容
- `OpenSpec` 的具体命令名或技能名
- 你项目自己的文档路径
- 你项目自己的权威来源名称
- 你项目自己的验证命令
