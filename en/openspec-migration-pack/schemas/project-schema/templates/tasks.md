# Non-goal Reminder

<!-- State what is not included in this change to prevent scope drift during task decomposition. -->

## Recommended MVP Scope

<!-- State the smallest deliverable slice that still forms a closed loop. -->

## File Scope

<!-- List the files or directories that are expected to change. -->

## Dependencies

<!-- List dependencies between tasks or slices. -->

## Parallel Opportunities

<!-- List tasks or task groups that can be done in parallel. -->

## Task Order

<!-- Keep the five-stage structure: Setup, Blocking, Slice A, Slice B, Reconciliation. -->

### Implementation Constraints

- When entering `apply`, execute `test-driven-development` first and follow `RED -> GREEN -> REFACTOR`.
- `tasks.md` is only for scope breakdown and progress tracking; do not repeat the full TDD details here.
- If the change is `interactive`, the first item in `Blocking` must be `Proof Task`.

## 1. Setup

<!-- Project initialization, context prep, and required asset synchronization. -->

- [ ] 1.1 <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>
- [ ] 1.2 <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>

## 2. Blocking

<!-- Shared prerequisites for all slices; do not proceed before these are complete. -->

- [ ] 2.1 <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>

## 3. Slice A: <slice-name>

### Slice Goal

<!-- Explain what the user or system can do independently when this slice is complete. -->

### Independent Acceptance Criteria

<!-- Explain how to verify the slice without depending on later slices. -->

- [ ] 3.1 [Slice-A] <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>
- [ ] 3.2 [P] [Slice-A] <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>

## 4. Slice B: <slice-name>

### Slice Goal

<!-- Explain what the user or system can do independently when this slice is complete. -->

### Independent Acceptance Criteria

<!-- Explain how to verify the slice without depending on later slices. -->

- [ ] 4.1 [Slice-B] <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>

## 5. Reconciliation

<!-- Wrap-up items, cross-cutting governance, docs, regression, compatibility, observability, etc. -->

- [ ] 5.1 <task-description>
  - **Files:** <file-paths>
  - **Verification:** <verification-command>

## Readiness Gate

<!-- Unified checks before entering apply. -->
- [ ] File scope is explicit
- [ ] MVP scope is explicit
- [ ] Blocking tasks are separated
- [ ] Every slice has a slice goal
- [ ] Every slice has independent acceptance criteria
- [ ] Parallel opportunities are marked
- [ ] Task order is coherent
- [ ] Every step has a verification command
- [ ] Task items preserve the `1.1 / 1.2` style and support `[P]` and `[Slice-X]` labels
- [ ] Task granularity is detailed enough that the implementer does not need to guess

