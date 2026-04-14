# Proposed `propose` Redesign

This document explains how to upgrade OpenSpec `propose` from a coverage check into a unified readiness gate.

## Goal

- Make `propose` perform the final go / no-go decision before `apply`.
- Keep coverage, implementability, and archive safety in one flow.
- Prevent proposal, design, specs, and tasks from drifting apart.

## Recommended changes

1. Add a unified readiness gate at the end of `propose`.
2. Make the gate check the following in a single pass:
   - scope and non-goals
   - risks and acceptance criteria
   - architecture authority consistency
   - state transition, persistence, and contract impact
   - task granularity, file scope, and verification commands
   - archive safety
3. Treat `QUALITY-GATE.md` as the single source of truth for the gate.
4. Make the `propose` output state clearly show:
   - what is already satisfied
   - what blocks entry into `apply`
   - what must be written back into proposal / design / specs / tasks

## Recommended execution order

1. Read `config.yaml`
2. Read proposal / design / specs / tasks
3. Run the unified readiness gate
4. Enter `apply` only after the gate passes

## What to replace during migration

- the exact command names or skill names used by OpenSpec
- the project-specific document paths
- the project-specific authority names
- the project-specific verification commands

