# OpenSpec 资产迁移包

这是一套可直接迁移到其他项目的 OpenSpec 起始资产。

使用方式：
1. 先替换 `config.yaml.example` 里的项目占位符。
2. 再按需复制 `schemas/project-schema/` 下的模板。
3. 然后把三份门禁文档接入项目级工作流。
4. 必须把 `propose-改造思路.md` 落到你自己的技能或命令流程里，不能把它当成补充说明。
5. 在宣布迁移完成前，必须显式询问用户，项目是否还要接入 `apply-改造思路.md`。
6. 如果目标是 1:1 复刻本仓库资产，则 `apply-改造思路.md` 也必须接入。
7. 如果项目需要把 `TDD workflow` 接到 `apply` 阶段，再参考 `TDD-apply接入说明.md`。

迁移顺序建议：
1. `config.yaml.example`
2. `schemas/project-schema/`
3. `QUALITY-GATE.md`
4. `CHANGE-WORKING-AGREEMENT.md`
5. `ARCHIVE-CHECKLIST.md`
6. `propose-改造思路.md`，作为必迁移资产
7. 显式决定是否接入 `apply-改造思路.md`
8. 如果要接入，再读 `TDD-apply接入说明.md` 和 `apply-改造思路.md`

说明：
1. 这里不包含任何本项目业务实现内容。
2. 所有可变内容都用占位符标记，复制到新项目后再替换。
3. `schemas/project-schema/` 只是目录名示例，新项目可以保留，也可以改成自己的 schema 名称。
4. `propose-改造思路.md` 不是可选补充文档。
5. `apply-改造思路.md` 不是默认跳过项，而是必须记录结论的决策点。
