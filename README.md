# Let AI Optimize Your OpenSpec Workflow

This repository is a methodology pack for customizing OpenSpec around project constraints.

中文页面: [`zh/README.md`](zh/README.md)

Upstream OpenSpec: <https://github.com/Fission-AI/OpenSpec>

Before using this repository, you must complete the base OpenSpec configuration first.

## What this is

- A methodology for adapting OpenSpec to a specific project
- A set of documents for validation, archive safety, and change control
- A reusable schema and template skeleton
- A guide for helping AI work according to project constraints

## What problem this solves

OpenSpec works well for lightweight planning, but many projects need stronger constraints.

The common failure modes are:

- `propose` generates documents but leaves gaps
- `tasks.md` is too coarse, so execution falls into guessing, hallucination, or drift
- `archive` syncs specs back into the main library in a way that degrades the source of truth

## What this adds beyond stock OpenSpec

- Project context is defined first: boundaries, authority sources, canonical objects, and state machines
- Schema is used to encode project constraints into templates and generated structure
- A unified readiness gate decides whether a proposal can enter `apply`
- Active Change rules require implementation discoveries to be written back into documents
- Archive checks prevent the main spec from degrading into leftover change deltas
- Proposal, design, and tasks each have a clearer responsibility
- TDD can be connected when the project needs stronger implementation discipline

## Who it is for

- People who like the lightweight and automated OpenSpec workflow, but need stronger control over project drift
- Projects with clear boundaries, authority sources, canonical objects, or state machines
- New projects that already have a technical direction and want OpenSpec to help with SDD-style execution
- People who want AI to help organize project specifications

## Who it is not for

- Users who do not want to configure OpenSpec
- Projects where a single sentence is enough for AI to understand and start implementing
- Users who do not want to maintain config, schema, or gate documents and just want to start immediately
- Users who do not want AI to follow project rules and prefer free-form generation

## How AI should use this repo

Tell the agent: "Configure this repository for me: https://github.com/LZHcode1986/Openspec-Harness".

When adapting this workflow to another project:

- Treat `en/openspec-migration-pack/propose-redesign.md` as a required workflow asset, not optional notes
- Explicitly ask the user whether the target project should also adopt `en/openspec-migration-pack/apply-redesign.md`
- If the goal is to reproduce this repository 1:1, include both redesign documents

## Recommended reading order

1. Read this `README.md` first.
2. Then read [`en/Repository-Guide.md`](en/Repository-Guide.md).
3. Then read [`en/OpenSpec-Workflow-Customization-Methodology.md`](en/OpenSpec-Workflow-Customization-Methodology.md).
4. Then read [`en/openspec-migration-pack/README.md`](en/openspec-migration-pack/README.md).
5. Then read the three gate documents and `propose-redesign.md`.
6. Then make an explicit decision on `apply-redesign.md`; if you want a 1:1 reproduction, read it as a required asset.
7. Read the comparison page when you want a direct comparison with stock OpenSpec.

## Detailed contents

| Area | English entry | Purpose |
| --- | --- | --- |
| Repository guide | [en/Repository-Guide.md](en/Repository-Guide.md) | Reading order and navigation |
| Main methodology | [en/OpenSpec-Workflow-Customization-Methodology.md](en/OpenSpec-Workflow-Customization-Methodology.md) | Core methodology |
| Migration pack overview | [en/openspec-migration-pack/README.md](en/openspec-migration-pack/README.md) | How to reuse the assets |
| Quality gate | [en/openspec-migration-pack/QUALITY-GATE.md](en/openspec-migration-pack/QUALITY-GATE.md) | Proposal readiness check |
| Working agreement | [en/openspec-migration-pack/CHANGE-WORKING-AGREEMENT.md](en/openspec-migration-pack/CHANGE-WORKING-AGREEMENT.md) | Change discipline |
| Archive checklist | [en/openspec-migration-pack/ARCHIVE-CHECKLIST.md](en/openspec-migration-pack/ARCHIVE-CHECKLIST.md) | Post-archive normalization |
| Schema example | [en/openspec-migration-pack/schemas/project-schema/README.md](en/openspec-migration-pack/schemas/project-schema/README.md) | Project schema skeleton |
| Propose redesign notes | [en/openspec-migration-pack/propose-redesign.md](en/openspec-migration-pack/propose-redesign.md) | Required workflow asset for `propose` hardening |
| Apply redesign notes | [en/openspec-migration-pack/apply-redesign.md](en/openspec-migration-pack/apply-redesign.md) | Explicit migration decision for `apply` hardening |
| TDD integration | [en/openspec-migration-pack/TDD-apply-integration.md](en/openspec-migration-pack/TDD-apply-integration.md) | Optional implementation gate |
| Comparison page | [en/OpenSpec-vs-This-Workflow.md](en/OpenSpec-vs-This-Workflow.md) | Difference from stock OpenSpec |

## License

[MIT](LICENSE)
