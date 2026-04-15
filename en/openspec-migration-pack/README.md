# OpenSpec Migration Pack

This folder contains reusable assets for adapting OpenSpec to a specific project.

It is intended to be copied into another project and then tailored to that project's boundaries, authority sources, and workflow rules.

## How to use this pack

1. Before any configuration work, ask whether the project requires `test-driven-development`.
2. Use `config.yaml.example` as the English placeholder set.
3. Copy the schema skeleton from `schemas/project-schema/`.
4. Adopt the project-level gate documents.
5. Replace the target project's existing `propose` skill with `../../skills/openspec-propose/SKILL.md`.
6. If the answer is no, stop there and do not configure the `apply` or `test-driven-development` skills.
7. If the answer is yes, replace the target project's existing `apply` skill with `../../skills/openspec-apply-change/SKILL.md`.
8. Then check whether the target project already has `test-driven-development`; if not, configure `../../skills/test-driven-development/SKILL.md` into the OpenSpec skills directory.

## Recommended order

1. Ask whether `test-driven-development` must be enabled
2. `config.yaml.example`
3. `schemas/project-schema/`
4. `QUALITY-GATE.md`
5. `CHANGE-WORKING-AGREEMENT.md`
6. `ARCHIVE-CHECKLIST.md`
7. `../../skills/openspec-propose/SKILL.md`
8. If yes, adopt `../../skills/openspec-apply-change/SKILL.md`
9. Then check whether the target project already has `test-driven-development`; if not, adopt `../../skills/test-driven-development/SKILL.md`

## What this pack is not

- It is not a code implementation package.
- It does not contain project-specific business logic.
- It does not require copying every file as-is.

## Files at a glance

- `README.md`: English overview
- `QUALITY-GATE.md`: readiness gate
- `CHANGE-WORKING-AGREEMENT.md`: active change rules
- `ARCHIVE-CHECKLIST.md`: archive normalization checklist
- `config.yaml.example`: project context example
- `schemas/project-schema/`: schema and template skeleton
- `../../skills/openspec-propose/SKILL.md`: primary migration source for the `propose` workflow
- `../../skills/openspec-apply-change/SKILL.md`: conditional migration source for the `apply` workflow
- `../../skills/test-driven-development/SKILL.md`: if TDD is enabled, check whether the target project already has it; if not, configure it
- `propose-redesign.md`: design notes for the `propose` skill
- `apply-redesign.md`: design notes for the `apply` skill
- `TDD-apply-integration.md`: reference notes once TDD has been enabled
