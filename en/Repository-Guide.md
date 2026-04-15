# Repository Guide

## What to read first

1. Read the root `README.md` to understand the repository position.
2. Read `./OpenSpec-Workflow-Customization-Methodology.md` to understand the main methodology.
3. Read `./openspec-migration-pack/README.md` to understand how the migration pack works.
4. Read `./skills/README.md` and `./skills/openspec-propose/SKILL.md` to understand the skill roles and the primary `propose` migration asset.
5. Read `./openspec-migration-pack/QUALITY-GATE.md`, `CHANGE-WORKING-AGREEMENT.md`, and `ARCHIVE-CHECKLIST.md` together.
6. Read `./openspec-migration-pack/schemas/project-schema/README.md` and `config.yaml.example` to understand the schema and project-context skeleton.
7. If the user enables `test-driven-development`, then read `./skills/openspec-apply-change/SKILL.md`.
8. Read `./OpenSpec-vs-This-Workflow.md` last if you want the comparison with upstream OpenSpec.

## If this is your first visit

- Start with `README.md`
- Then read `./OpenSpec-vs-This-Workflow.md`
- Then read the main methodology document

## If you want to reuse this workflow

- Start with `./openspec-migration-pack/README.md`
- Then read `./skills/README.md`
- Then replace the target project's `propose` skill with `./skills/openspec-propose/SKILL.md`
- Then read `config.yaml.example`, `schemas/project-schema/`, and the three gate documents
- Then ask whether `test-driven-development` must be enabled
- If yes, wire in `./skills/openspec-apply-change/SKILL.md`

## If you want to customize this workflow

- Update the main methodology first
- Then update the migration pack overview
- Then update the `skills/` implementations
- Then update the schema skeleton
- Then align the gate documents
- Finally align the redesign notes so they stay in sync with the documented workflow
