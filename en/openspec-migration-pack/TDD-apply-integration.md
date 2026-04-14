# TDD Integration for `apply`

This document explains how to connect a TDD workflow to the OpenSpec `apply` phase when the project requires it.

## Purpose

- Keep implementation behavior consistent with project-level TDD rules.
- Make `apply` follow the TDD entry point rather than bypassing it.
- Preserve the separation between planning artifacts and implementation execution.

## Integration rule

- If `apply.instruction` or the project policy requires TDD, `apply` must invoke the TDD workflow before implementation starts.

## Recommended flow

1. Resolve the current change.
2. Read the `apply.instruction`.
3. Detect whether TDD is required.
4. Load the TDD workflow instructions.
5. Run the TDD steps in order.
6. Execute implementation only after the workflow allows it.

## Notes

- Keep the TDD flow outside `tasks.md`.
- Use `tasks.md` only for scope, slices, and progress tracking.
- Use verification commands to prove each task slice is complete.

