# Active Change Working Agreement

This document defines how OpenSpec should be used in this project.

The goal is to treat OpenSpec as a change workspace, not as a post-hoc archive folder.

## 1. Change creation rules

- Plan before implementation.
- When the intent and main path are the same, update the current change first.
- When the boundary changes materially, create a new change.

## 2. Knowledge write-back

- If implementation reveals a misunderstanding, write the correction back into the current change's proposal, design, specs, or tasks.
- Do not update code only and leave the documents stale.

## 3. Archive timing

- Archive is only for a change that is ready to close and merge into the formal spec library.
- Archive is allowed only when all of the following are true:
  1. The intended implementation scope is complete.
  2. Code and proposal / design / specs / tasks are aligned again.
  3. All promised verification commands have been run successfully.
  4. Important new knowledge discovered during implementation has been written back into the change docs.
  5. Archive will not degrade the main spec.

## 4. Implementation positioning

- OpenSpec owns planning, constraints, traceability, and archive safety.
- Code implementation, testing, and delivery rules remain part of the project's own implementation workflow.

