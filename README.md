# Let AI Optimize Your OpenSpec Workflow

This repository is a methodology pack for customizing OpenSpec around project constraints.

Chinese version: [`../README.md`](../README.md)

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

Using Codex as an example:

1. Give the full [`OpenSpec-Workflow-Customization-Methodology.md`](OpenSpec-Workflow-Customization-Methodology.md) file to the agent.
2. Select `GPT-5.4`.
3. Tell the agent to first list a `todo list`, then execute each item in order.
4. During execution, follow the repository's authoritative documents first.
5. Handle project context, `config`, `schema`, gates, and working agreement before moving on to later changes.
6. If the project facts are unclear, fill them in first instead of guessing.

## Recommended reading order

1. Read this `README.md` first.
2. Then read [`Repository-Guide.md`](Repository-Guide.md).
3. Then read [`OpenSpec-Workflow-Customization-Methodology.md`](OpenSpec-Workflow-Customization-Methodology.md).
4. Then read [`openspec-migration-pack/README.md`](openspec-migration-pack/README.md).
5. Then read the three gate documents.
6. Read the comparison page when you want a direct comparison with stock OpenSpec.

## Detailed contents

| Area | English entry | Purpose |
| --- | --- | --- |
| Repository guide | [Repository-Guide.md](Repository-Guide.md) | Reading order and navigation |
| Main methodology | [OpenSpec-Workflow-Customization-Methodology.md](OpenSpec-Workflow-Customization-Methodology.md) | Core methodology |
| Migration pack overview | [openspec-migration-pack/README.md](openspec-migration-pack/README.md) | How to reuse the assets |
| Quality gate | [openspec-migration-pack/QUALITY-GATE.md](openspec-migration-pack/QUALITY-GATE.md) | Proposal readiness check |
| Working agreement | [openspec-migration-pack/CHANGE-WORKING-AGREEMENT.md](openspec-migration-pack/CHANGE-WORKING-AGREEMENT.md) | Change discipline |
| Archive checklist | [openspec-migration-pack/ARCHIVE-CHECKLIST.md](openspec-migration-pack/ARCHIVE-CHECKLIST.md) | Post-archive normalization |
| Schema example | [openspec-migration-pack/schemas/project-schema/README.md](openspec-migration-pack/schemas/project-schema/README.md) | Project schema skeleton |
| Propose redesign notes | [openspec-migration-pack/propose-redesign.md](openspec-migration-pack/propose-redesign.md) | Proposal hardening |
| Apply redesign notes | [openspec-migration-pack/apply-redesign.md](openspec-migration-pack/apply-redesign.md) | Apply hardening |
| TDD integration | [openspec-migration-pack/TDD-apply-integration.md](openspec-migration-pack/TDD-apply-integration.md) | Optional implementation gate |
| Comparison page | [OpenSpec-vs-This-Workflow.md](OpenSpec-vs-This-Workflow.md) | Difference from stock OpenSpec |

## License

[MIT](../LICENSE)
