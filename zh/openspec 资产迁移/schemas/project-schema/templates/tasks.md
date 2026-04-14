## 非目标提醒

<!-- 明确本次不做什么，防止任务分解时 scope 漂移。 -->

## MVP 建议范围

<!-- 明确最小可交付范围，优先完成哪个切片即可形成闭环。 -->

## 文件范围

<!-- 列出预计会修改的文件或目录。 -->

## 依赖关系

<!-- 列出任务与切片之间的阻塞关系。 -->

## 并行机会

<!-- 列出可并行执行的任务或任务组。 -->

## 任务顺序

<!-- 固定五段：Setup、Foundational / Blocking、Slice A、Slice B、Polish / Cross-Cutting。 -->

### 实施约束

- 进入 `apply` 后，如项目要求 `tdd-workflow`，则先按该 workflow 的 Step 0-7 执行。
- `tasks.md` 只承担范围拆分与进度跟踪，不在此处重复展开完整 TDD 细节。

## 1. 准备阶段

<!-- 项目初始化、上下文准备、必要资产同步。 -->

- [ ] 1.1 <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>
- [ ] 1.2 <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>

## 2. 基础 / 阻塞项

<!-- 所有切片共享的前置阻塞项；未完成前不得进入后续切片。 -->

- [ ] 2.1 <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>

## 3. 切片 A：<slice-name>

### 切片目标

<!-- 说明这个切片完成后，用户或系统能独立获得什么能力。 -->

### 独立验收标准

<!-- 说明该切片单独完成时如何验收，不依赖后续切片。 -->

- [ ] 3.1 [Slice-A] <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>
- [ ] 3.2 [P] [Slice-A] <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>

## 4. 切片 B：<slice-name>

### 切片目标

<!-- 说明这个切片完成后，用户或系统能独立获得什么能力。 -->

### 独立验收标准

<!-- 说明该切片单独完成时如何验收，不依赖后续切片。 -->

- [ ] 4.1 [Slice-B] <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>

## 5. 收尾 / 跨切片项

<!-- 收尾项、跨切片治理项、文档、回归、兼容性、观测性等。 -->

- [ ] 5.1 <task-description>
  - **文件 (Files):** <file-paths>
  - **验证命令 (Verification):** <verification-command>

## 就绪门禁

<!-- 进入 apply 前的统一检查。 -->
- [ ] 文件范围已明确
- [ ] 已明确 MVP 建议范围
- [ ] 已单列 Foundational / Blocking 任务
- [ ] 每个 Slice 都包含切片目标
- [ ] 每个 Slice 都包含独立验收标准
- [ ] 已标出 Parallel Opportunities
- [ ] 任务顺序逻辑连贯
- [ ] 每步任务都有对应的验证命令
- [ ] 任务条目保留 `1.1 / 1.2` 风格并支持 `[P]` 与 `[Slice-X]` 标签
- [ ] 任务粒度达到“实现者无需再猜”的级别
