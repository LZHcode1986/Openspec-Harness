# OpenSpec Migration Pack

This folder contains reusable assets for adapting OpenSpec to a specific project.

It is intended to be copied into another project and then tailored to that project's boundaries, authority sources, and workflow rules.

## How to use this pack

1. Use `config.yaml.example` as the English placeholder set.
2. Copy the schema skeleton from `schemas/project-schema/`.
3. Adopt the project-level gate documents.
4. Replace the target project's existing `propose` skill with `../../skills/openspec-propose/SKILL.md`.
5. Ask the user whether the project requires `test-driven-development`.
6. If the answer is no, stop there and do not configure the `apply` or `test-driven-development` skills.
7. If the answer is yes, replace the target project's existing `apply` skill with `../../skills/openspec-apply-change/SKILL.md`.
8. After configuring `apply`, ask whether `../../skills/test-driven-development/SKILL.md` should also be installed into the OpenSpec skills directory.

## Recommended order

1. `config.yaml.example`
2. `schemas/project-schema/`
3. `QUALITY-GATE.md`
4. `CHANGE-WORKING-AGREEMENT.md`
5. `ARCHIVE-CHECKLIST.md`
6. `../../skills/openspec-propose/SKILL.md`
7. Ask whether `test-driven-development` must be enabled
8. If yes, adopt `../../skills/openspec-apply-change/SKILL.md`
9. If the user also confirms installation, adopt `../../skills/test-driven-development/SKILL.md`

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
- `../../skills/test-driven-development/SKILL.md`: optional installation after explicit confirmation
- `propose-redesign.md`: design notes for the `propose` skill
- `apply-redesign.md`: design notes for the `apply` skill
- `TDD-apply-integration.md`: reference notes once TDD has been enabled
