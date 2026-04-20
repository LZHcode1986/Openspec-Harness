# OpenSpec vs This Workflow

## Summary

This workflow is built on OpenSpec, but it adds stronger project-specific control.

If stock OpenSpec is a generic planning framework, this workflow is a project-customized constraint system around that framework.

## Comparison

| Area | Stock OpenSpec | This workflow |
| --- | --- | --- |
| Primary focus | Generic planning and spec flow | Project-specific adaptation and constraint enforcement |
| Customization point | Mostly templates and workflow usage | Config, schema, gate, and document hierarchy |
| Readiness check | Structural validation plus workflow judgment | Proofability, tasks readiness, and implementation done checks |
| Main spec behavior | Can drift toward change-delta language | Should remain a stable source of truth |
| Archive role | Close the change | Close the change and normalize the main spec |
| Implementation boundary | Often implicit | Explicitly separated from planning artifacts |
| Best fit | Broad, lightweight use | Projects with authority sources, state machines, or strong boundaries |

## What this workflow adds

- a project context block in configuration
- a custom schema per project
- proofability-first planning
- a user guide for change discipline
- a tasks readiness gate
- an implementation done check
- an active change discipline
- an archive normalization checklist
- clearer separation between planning and implementation

## When to use it

Use this workflow when:

- your project has non-negotiable architecture constraints
- your spec generation needs stronger guardrails
- you want AI to respect project boundaries before implementation
- you want archive to produce a clean main spec, not a residual delta stack

## When not to use it

Do not use this workflow when:

- you only need a generic planning template
- your project has no meaningful authority boundary
- you want the fastest possible setup and do not need project-specific rigor

