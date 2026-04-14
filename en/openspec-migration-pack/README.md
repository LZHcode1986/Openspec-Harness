# OpenSpec Migration Pack

This folder contains reusable assets for adapting OpenSpec to a specific project.

It is intended to be copied into another project and then tailored to that project's boundaries, authority sources, and workflow rules.

## How to use this pack

1. Use `config.yaml.example` as the English placeholder set.
2. Copy the schema skeleton from `schemas/project-schema/`.
3. Adopt the project-level gate documents.
4. Adapt the `propose` and `apply` guidance to your own workflow.
5. If your implementation phase must follow TDD, connect that rule through `TDD-apply-integration.md`.

## Recommended order

1. `config.yaml.example`
2. `schemas/project-schema/`
3. `QUALITY-GATE.md`
4. `CHANGE-WORKING-AGREEMENT.md`
5. `ARCHIVE-CHECKLIST.md`
6. `propose-redesign.md`
7. `TDD-apply-integration.md`
8. `apply-redesign.md`

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
- `propose-redesign.md`: propose hardening notes
- `apply-redesign.md`: apply hardening notes
- `TDD-apply-integration.md`: TDD integration notes
