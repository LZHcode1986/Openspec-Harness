# Repository Guide

## What to read first

1. Read the root `README.md` to understand the repository position.
2. Read `./OpenSpec-Workflow-Customization-Methodology.md` to understand the main methodology.
3. Read `./openspec-migration-pack/README.md` to understand how the migration pack works.
4. Read `./openspec-migration-pack/QUALITY-GATE.md`, `CHANGE-WORKING-AGREEMENT.md`, and `ARCHIVE-CHECKLIST.md` together.
5. Read `./openspec-migration-pack/schemas/project-schema/README.md` to understand the schema skeleton.
6. Read `./openspec-migration-pack/propose-redesign.md` as a required migration asset.
7. Make an explicit decision on `./openspec-migration-pack/apply-redesign.md`; if the goal is 1:1 reuse, treat it as required.
8. Read `./OpenSpec-vs-This-Workflow.md` last if you want the comparison with upstream OpenSpec.

## If this is your first visit

- Start with `README.md`
- Then read `./OpenSpec-vs-This-Workflow.md`
- Then read the main methodology document

## If you want to reuse this workflow

- Start with `./openspec-migration-pack/README.md`
- Then read `config.yaml.example`
- Then read `schemas/project-schema/`
- Then read the three gate documents
- Then read `propose-redesign.md` and wire it into your `propose` workflow
- Then explicitly decide whether `apply-redesign.md` must also be wired into your `apply` workflow

## If you want to customize this workflow

- Update the main methodology first
- Then update the migration pack overview
- Then update the schema skeleton
- Then align the gate documents
- Finally align the `propose` / `apply` redesign guidance so they stay in sync with the documented workflow
