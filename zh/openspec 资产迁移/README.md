# OpenSpec 资产迁移包

这是一套可直接迁移到其他项目的 OpenSpec 起始资产。

使用方式：
1. 先替换 `config.yaml.example` 里的项目占位符。
2. 再按需复制 `schemas/project-schema/` 下的模板。
3. 然后把三份门禁文档接入项目级工作流。
4. 必须用 `../../skills/openspec-propose/SKILL.md` 覆盖目标项目原有的 `propose` skill。
5. 然后必须询问用户，项目是否需要 `test-driven-development`。
6. 如果用户不需要，则不配置 `apply` skill，也不安装 `test-driven-development` skill。
7. 如果用户需要，则用 `../../skills/openspec-apply-change/SKILL.md` 覆盖目标项目原有的 `apply` skill。
8. 完成 `apply` skill 后，必须再次询问用户，是否还要把 `../../skills/test-driven-development/SKILL.md` 安装到 OpenSpec skills 同目录。

迁移顺序建议：
1. `config.yaml.example`
2. `schemas/project-schema/`
3. `QUALITY-GATE.md`
4. `CHANGE-WORKING-AGREEMENT.md`
5. `ARCHIVE-CHECKLIST.md`
6. `../../skills/openspec-propose/SKILL.md`
7. 询问用户是否启用 `test-driven-development`
8. 如果启用，再接入 `../../skills/openspec-apply-change/SKILL.md`
9. 如果用户还确认安装 `test-driven-development` skill，再接入 `../../skills/test-driven-development/SKILL.md`

说明：
1. 这里不包含任何本项目业务实现内容。
2. 所有可变内容都用占位符标记，复制到新项目后再替换。
3. `schemas/project-schema/` 只是目录名示例，新项目可以保留，也可以改成自己的 schema 名称。
4. `skills/openspec-propose/SKILL.md` 是主迁移入口。
5. `skills/openspec-apply-change/SKILL.md` 只有在用户启用 `test-driven-development` 后才配置。
6. `propose-改造思路.md` 和 `apply-改造思路.md` 现在只作为设计说明保留。
