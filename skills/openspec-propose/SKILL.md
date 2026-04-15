---
name: openspec-propose
description: Propose a new change with all artifacts generated in one step. Use when the user wants to quickly describe what they want to build and get a complete proposal with design, specs, and tasks ready for implementation.
license: MIT
compatibility: Requires openspec CLI.
metadata:
  author: openspec
  version: "1.1"
  generatedBy: "1.2.0"
---

Propose a new change - create the change and generate all artifacts in one step.

I'll create a change with artifacts:
- proposal.md (what & why)
- design.md (how)
- tasks.md (implementation steps)

When ready to implement, run /opsx:apply

---

**Input**: The user's request should include a change name (kebab-case) OR a description of what they want to build. It may also include one or more source files that the proposal must be decomposed from.

If the request explicitly says `according to <file-path-list>, start task decomposition` or `按照 <文件路径列表> 开始做任务分解`, then:
- `<file-path-list>` means the source file or files that define the decomposition input for this change
- those files may be one file or multiple files
- those files are input references, not output targets, unless the user separately asks to edit them
- the propose workflow MUST use those files as the basis for decomposition
- the file list may change per change, but this workflow MUST stay fixed

**Steps**

1. **Identify the change and the decomposition source files**

   Determine:
   - the change name (or derive one from the user's description)
   - any user-supplied source file paths
   - whether the user explicitly requested task decomposition from those files

   If the user provided source files for decomposition, read every listed file before creating or updating any artifact. Treat those files as the primary source for:
   - scope
   - constraints
   - capabilities
   - interfaces or contracts
   - acceptance boundaries
   - explicit non-goals

   If no clear goal is provided, ask:
   > "What change do you want to work on? Describe what you want to build or fix."

   From their description, derive a kebab-case name (e.g., "add user authentication" → `add-user-auth`).

   **IMPORTANT**: Do NOT proceed without understanding what the user wants to build.

2. **If source files are provided, perform decomposition before writing artifacts**

   Build a decomposition result from the supplied file(s):
   - extract requirement items, constraints, invariants, interfaces, contracts, and acceptance expectations
   - group them into capability slices or work packages
   - identify dependencies, cross-cutting risks, and validation checkpoints
   - note any explicit ambiguity, conflict, or out-of-scope item

   This decomposition is part of the propose phase itself. Do not require the user to restate this workflow on every change.

3. **Create the change directory**
   ```bash
   openspec new change "<name>"
   ```
   This creates a scaffolded change at `openspec/changes/<name>/` with `.openspec.yaml`.

4. **Get the artifact build order**
   ```bash
   openspec status --change "<name>" --json
   ```
   Parse the JSON to get:
   - `applyRequires`: array of artifact IDs needed before implementation (e.g., `["tasks"]`)
   - `artifacts`: list of all artifacts with their status and dependencies

5. **Create artifacts in sequence until apply-ready**

   Use the task-planning tool available in the environment (for example `update_plan`; if a checklist tool exists, use it) to track progress through the artifacts.
   The progress list MUST explicitly include these coverage-check milestones in order:
   - source decomposition complete
   - `proposal.md` drafted
   - proposal coverage check complete
   - `design.md` drafted
   - design coverage check complete
   - `specs/*` drafted
   - `tasks.md` drafted
   - final traceability review complete
   - final readiness gate complete

   **IMPORTANT**: coverage checks and readiness checks are in-process gates, not end-of-flow clean-up work. Do not postpone them until after all artifacts are written.

   Loop through artifacts in dependency order (artifacts with no pending dependencies first):

   a. **For each artifact that is `ready` (dependencies satisfied)**:
      - Get instructions:
        ```bash
        openspec instructions <artifact-id> --change "<name>" --json
        ```
      - The instructions JSON includes:
        - `context`: Project background (constraints for you - do NOT include in output)
        - `rules`: Artifact-specific rules (constraints for you - do NOT include in output)
        - `template`: The structure to use for your output file
        - `instruction`: Schema-specific guidance for this artifact type
        - `outputPath`: Where to write the artifact
        - `dependencies`: Completed artifacts to read for context
      - Read any completed dependency files for context
      - Keep the user-supplied decomposition source files as authoritative context throughout the propose flow
      - Create the artifact file using `template` as the structure
      - Apply `context` and `rules` as constraints - but do NOT copy them into the file
      - Show brief progress: "Created <artifact-id>"

      Artifact-specific workflow:
      - `proposal.md`: write the change intent, scope, capability slices, risks, and rationale from the decomposition result
      - Immediately after `proposal.md`, run **Proposal Coverage Check** before writing `design.md`
      - `design.md`: write the implementation structure, interfaces, sequencing, and validation strategy for every non-deferred proposal item
      - Immediately after `design.md`, run **Design Coverage Check** before writing `specs/*` or `tasks.md`
      - `specs/*` and `tasks.md`: derive them only from the validated proposal/design pair
      - `tasks.md` 必须遵循 OpenSpec x spec-kit 融合结构：Setup -> Foundational / Blocking -> Slice A -> Slice B -> Polish / Cross-Cutting
      - `tasks.md` 必须包含 MVP 范围、依赖关系、并行机会、切片目标、独立验收标准
      - 每个任务必须保持 `1.1 / 1.2` 风格，并支持 `[P]` 与 `[Slice-X]` 标签
      - Immediately after `specs/*` + `tasks.md`, run **Final Traceability Review**
      - Immediately after Final Traceability Review, run **Final Readiness Gate** using `openspec/QUALITY-GATE.md` before declaring the change ready

      Required coverage-gate enforcement:
      - **Proposal Coverage Check** (BLOCKS design.md)
        - BEFORE writing design.md, extract every requirement/constraint from source file(s)
        - For each item, mark status: `covered` (proposal addresses it), `deferred` (explicitly postponed), `out_of_scope` (explicitly excluded), or `conflict` (contradicts another requirement)
        - Output the full coverage table in the conversation
        - If any item is unmapped or ambiguous: update proposal.md to cover it, then re-check
        - DO NOT proceed to design.md until every source item has an explicit status
      - **Design Coverage Check** (BLOCKS specs/* and tasks.md)
        - BEFORE writing specs or tasks, verify every non-deferred proposal item has a corresponding design decision
        - Verify no design decision contradicts source file(s)
        - Output the full coverage table in the conversation
        - If any proposal item lacks design coverage: update design.md, then re-check
        - DO NOT proceed to specs/tasks until all non-deferred items are covered
      - **Final Traceability Review** (BLOCKS declaring apply-ready)
        - AFTER writing specs/* and tasks.md, verify the full chain: source files -> proposal -> design -> specs -> tasks
        - Output the full traceability table in the conversation
        - If any gap exists: update the deficient artifact (proposal/design/specs/tasks), then re-check
        - DO NOT report apply-ready status until the chain is complete with zero unmapped items
      - **Final Readiness Gate** (BLOCKS declaring apply-ready)
        - AFTER Final Traceability Review passes, read `openspec/QUALITY-GATE.md`
        - Evaluate the change against the four gate dimensions: coverage completeness, authority consistency, implementability, archive safety
        - Output the readiness checklist result in the conversation
        - If any item fails: update the deficient artifact and re-run the gate
        - DO NOT report apply-ready status until Final Readiness Gate passes

      任务分解要求：
      - 先写 `Setup` 任务，用于上下文准备和基础脚手架
      - 再写 `Foundational / Blocking` 任务，用于放置必须先完成的共享前置项
      - 按能力切片拆分实现，每个切片都必须可以独立验收
      - 每个切片都要写 `切片目标` 和 `独立验收标准`
      - 最后补 `Polish / Cross-Cutting` 任务，用于收尾、文档、兼容性、回归和可观测性工作
      - 可并行任务标记 `[P]`
      - 切片归属标记 `[Slice-A]`、`[Slice-B]` 或同类标签
      - 每条任务都要写明文件范围和验证命令

   b. **Continue until all `applyRequires` artifacts are complete**
      - After creating each artifact, re-run `openspec status --change "<name>" --json`
      - Check if every artifact ID in `applyRequires` has `status: "done"` in the artifacts array
      - Stop when all `applyRequires` artifacts are done

   c. **If an artifact requires user input** (unclear context):
      - Use **AskUserQuestion tool** to clarify
      - Then continue with creation

6. **Show final status**
   ```bash
   openspec status --change "<name>"
   ```

**Output**

After completing all artifacts and finishing Final Traceability Review plus Final Readiness Gate, summarize:
- Change name and location
- List of artifacts created with brief descriptions
- What's ready: "All artifacts created! Ready for implementation."
- Prompt: "Run `/opsx:apply` or ask me to implement to start working on the tasks."

**Artifact Creation Guidelines**

- Follow the `instruction` field from `openspec instructions` for each artifact type
- The schema defines what each artifact should contain - follow it
- Read dependency artifacts for context before creating new ones
- If the user supplied one or more files for decomposition, use them as required source inputs rather than optional background
- Use `template` as the structure for your output file - fill in its sections
- **IMPORTANT**: `context` and `rules` are constraints for YOU, not content for the file
  - Do NOT copy `<context>`, `<rules>`, `<project_context>` blocks into the artifact
  - These guide what you write, but should never appear in the output
- Keep the workflow fixed when decomposition files are provided:
  - source files -> decomposition
  - `proposal.md` -> proposal coverage check
  - `design.md` -> design coverage check
  - `specs/*` + `tasks.md`
  - final traceability review
  - final readiness gate via `openspec/QUALITY-GATE.md`

- If you produce any process task list / plan / checklist while executing this skill, you MUST include the three coverage-gate tasks and the final readiness gate explicitly:
  - proposal coverage check
  - design coverage check
  - final traceability review
  - final readiness gate

**Guardrails**
- Create ALL artifacts needed for implementation (as defined by schema's `apply.requires`)
- Always read dependency artifacts before creating a new one
- Do not skip decomposition when the user explicitly anchors the change to one or more files
- Do not skip the intermediate coverage checks between proposal and design
- Do not defer Proposal Coverage Check until after `design.md`
- Do not defer Design Coverage Check until after `specs/*` or `tasks.md`
- Do not defer Final Traceability Review until after you have already declared the change ready
- Do not skip Final Readiness Gate after Final Traceability Review
- Do not treat the listed source files as optional reference material
- Do not declare the change ready if any source requirement is still unmapped, ambiguous, or in conflict without being explicitly called out
- Do not declare the change ready if `openspec/QUALITY-GATE.md` has unresolved failures
- If context is critically unclear, ask the user - but prefer making reasonable decisions to keep momentum
- If a change with that name already exists, ask if user wants to continue it or create a new one
- Verify each artifact file exists after writing before proceeding to next
