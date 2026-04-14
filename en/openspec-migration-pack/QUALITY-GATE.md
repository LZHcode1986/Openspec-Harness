# Readiness Gate

This document is the final gate in the `propose` flow.

Use it to ensure the planning artifacts are not only structurally complete, but also ready for implementation.

## 1. Architecture authority check

- [ ] Does the proposal stay consistent with the main spec and architecture authority?
- [ ] Are front-end / back-end or upstream / downstream authority boundaries explicit?
- [ ] Are no undocumented authority sources introduced?

## 2. Requirement clarity check

- [ ] Is the scope explicitly listed?
- [ ] Are the non-goals explicitly listed?
- [ ] Are risks and mitigations identified?
- [ ] Are acceptance criteria clear and testable?
- [ ] Are there any vague statements that look complete but cannot be implemented?

## 3. Architecture and interface impact check

- [ ] Are the affected objects, files, modules, and interfaces listed?
- [ ] Are API or contract changes explained?
- [ ] Is state transition impact described?
- [ ] Is persistence impact described?

## 4. Implementation readiness check

- [ ] Are the task slices granular enough that the implementer does not need to guess?
- [ ] Does each task include a file scope?
- [ ] Does each task include a concrete verification command?
- [ ] Is the MVP scope explicit?
- [ ] Are foundational or blocking tasks separated?
- [ ] Does each slice have its own acceptance criteria?
- [ ] Are parallel opportunities marked?
- [ ] Do tasks preserve the `1.1 / 1.2` style and support `[P]` and `[Slice-X]` labels?

## 5. Archive safety check

- [ ] Can this change be merged into the main spec safely after archive?

