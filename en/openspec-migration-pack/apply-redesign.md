# Proposed `apply` Redesign

This document explains how to upgrade OpenSpec `apply` from "implement tasks directly" into "follow the schema-driven implementation flow first, then execute tasks".

## Goal

- Make `apply` actually honor the dynamic `apply.instruction` from the schema.
- If the project requires `tdd-workflow`, execute `Step 0` through `Step 7` before implementation.
- Keep `tasks.md` focused on scope and progress while `apply` controls the execution order.

## Recommended changes

1. After `openspec instructions apply --change "<name>" --json`, read the dynamic instruction.
2. If the instruction or project rules require `tdd-workflow`, read that skill first and only then start coding.
3. Do not treat `tasks.md` as the only source of order; it should track slices, scope, and checkboxes.
4. Only mark tasks done after the corresponding TDD step has been completed and verified.
5. Guardrails should explicitly forbid skipping `RED -> GREEN -> REFACTOR`.

## Recommended execution order

1. Select the change
2. Read `openspec status`
3. Read `openspec instructions apply`
4. Decide whether `tdd-workflow` is required from `apply.instruction`
5. Read the context files
6. Execute implementation according to the required workflow

## What to replace during migration

- the exact command names or skill names used by OpenSpec
- the project-specific implementation skill name
- the project-specific TDD skill name
- the project-specific test and verification commands

