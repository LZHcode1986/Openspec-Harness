# OpenSpec 资产迁移包

这是一套可直接迁移到其他项目的 OpenSpec 起始资产。

使用方式：
1. 先替换 `config.yaml.example` 里的项目占位符。
2. 再按需复制 `schemas/project-schema/` 下的模板。
3. 然后把三份门禁文档接入项目级工作流。
4. 最后把 `propose` 改造思路落到你自己的技能或命令流程里。
5. 如果项目需要把 `TDD workflow` 接到 `apply` 阶段，再参考 `TDD-apply接入说明.md`。
6. 如果项目还需要让 `apply` skill 真正遵守这条规则，再参考 `apply-改造思路.md`。

迁移顺序建议：
1. `config.yaml.example`
2. `schemas/project-schema/`
3. `QUALITY-GATE.md`
4. `CHANGE-WORKING-AGREEMENT.md`
5. `ARCHIVE-CHECKLIST.md`
6. `propose-改造思路.md`
7. `TDD-apply接入说明.md`
8. `apply-改造思路.md`

说明：
1. 这里不包含任何本项目业务实现内容。
2. 所有可变内容都用占位符标记，复制到新项目后再替换。
3. `schemas/project-schema/` 只是目录名示例，新项目可以保留，也可以改成自己的 schema 名称。
