# Academic Slides Standard

> Return to [Standards Library](../../README.md). For AI generation also see [CLAUDE.md](CLAUDE.md) and [slide-patterns.json](slide-patterns.json).

> **内容让观众愿意听，视觉让观众容易懂；每次汇报都沿用相同的设计语言。**

本仓库提供可复用的学术研究汇报规范，分为 **Content Design（内容与叙事）** 和 **Visual Design（视觉与交互）**。适用于 AI、Computer Science、Healthcare 等研究。具体设计值见 [design-tokens.json](./design-tokens.json)。

## A. Content Design — 如何让内容吸引人？

### 七条核心规则

1. **先结论，后解释（Conclusion First）**：开场说明研究什么、发现什么、为什么重要。探索性研究要清楚区分假设、观察和已经验证的结论。
2. **总—分—总（Structure）**：核心观点 → 背景与挑战 → 方法与证据 → 总结。
3. **一页一个观点（One Slide, One Message）**：每页只回答一个主要问题。
4. **标题就是结论（Assertion Titles）**：避免只有主题的标题。❌ “Model Performance”；✅ “Our Model Achieves the Highest Mean PR-AUC”。对差异显著性没有证据时不写 “Significantly Outperforms”。
5. **图表优先，文字辅助（Show, Don't Tell）**：用图表、流程图、模型架构图讲清关系，关键数字直接标注。
6. **讲故事，而不是堆信息（Storytelling）**：**Scenario → Problem → Gap → Solution → Evidence → Takeaway**，让每一步回答观众刚产生的问题。
7. **少即是多（Less Is More）**：删除不支持核心观点的信息；通常每页只讲 30–60 秒，根据内容复杂度调整。

### 开场：先建立直观场景

- 前 1–3 页优先使用**真实场景图片、简短案例或直观示意图**，帮助非本领域观众迅速理解问题。
- 避免一上来出现复杂公式、密集文献综述或网络结构图。
- 每张图片有明确教学作用：展示 **谁遇到了什么问题、为何重要**；注明来源，保护隐私。
- 场景 → 可观察的问题 → 技术挑战 → 研究问题，逐步进入方法。

### 学术研究 Slides 推荐结构（8–10 页）

| 页面 | 核心问题 |
| --- | --- |
| 1. Takeaway / Scenario | 最重要的研究问题或发现是什么？用图片建立场景 |
| 2. Background | 为什么值得研究？ |
| 3. Research Gap | 现有方法有什么不足？ |
| 4. Proposed Method | 我们如何解决？ |
| 5. Model Design | 模型为什么这样设计？ |
| 6. Experimental Setup | 如何公平验证？ |
| 7. Main Results | 结果是否支持观点？ |
| 8. Analysis / Ablation | 为什么有效？哪些条件下有效？ |
| 9. Limitations | 有哪些限制，哪些推论尚不成立？ |
| 10. Conclusion | 观众应该记住什么？ |

> **Slides 不是论文的缩写，而是帮助观众理解并评估核心观点的视觉叙事。**

**内容验收：**观众只看每页标题和关键图表，就能理解研究故事；每个主要结论都有对应的证据。

---

## B. Visual Design — 如何让形式统一、易懂？

### 1. 视觉身份（Visual Identity）

- **固定 16:9 宽屏、浅色背景、简洁的技术研究风格**，不要为每篇论文重新选一套皮肤。
- 使用同一套 **颜色、字体层级、空间间距、图表样式和动画节奏**。
- 颜色表达语义，而非装饰：**蓝色 = Proposed Method**；**灰色 = Baseline**；**青色 = Method Component**；**橙色 = Key Highlight**。
- 同一个语义在所有页面、所有论文中使用相同颜色。必要时增加文字/图例，不只靠颜色区分。
- 推荐样式 Token 在 [design-tokens.json](./design-tokens.json)；数值是初始默认值，可按会场调整。

### 2. 排版层级（Typography & Layout）

- 标题 **30–36 pt**，正文 **20–24 pt**，注释 **14–16 pt**；演讲会场过远时进一步放大。
- 字体统一为 **Aptos / Arial**，除公式、特殊符号外不要随意增加字体。
- 默认采用左对齐、统一页边距（1920 × 1080 基准下 **64 px**）。
- 统一间距阶梯：**8 / 16 / 24 / 32 px**，而非手动随意摆放。
- 每页保留足够留白；大图、短标题优先，不要将论文段落截图放上去。

### 3. 图像与图表（Imagery & Data Visualization）

- 开场优先大幅图片；方法页优先可编辑架构图；结果页优先清晰对比图。
- Baselines 使用灰色；Proposed Method 使用蓝色；橙色只突出最需要注意的一处。
- 所有结果图统一坐标轴、单位、图例位置、网格线、标签字号。
- 不使用误导性截断、缺失单位或未经说明的显著性标记。
- 模型结构图统一模块形状、箭头粗细和颜色语义。

### 4. 逐步呈现（Progressive Disclosure & Motion）

- **每次点击只展开一个逻辑步骤**：问题 → 对应模块 → 输出 → 结果。
- 默认使用 **Appear / Fade（0.3–0.4 秒）**；不为了炫技使用旋转、弹跳和复杂转场。
- 用高亮当前区域、淡化非当前区域，引导观众视线。
- 对外分享时也必须可理解：导出 PDF 应保留最后完整状态；必要时将构建步骤拆成多页，避免动画信息丢失。
- 动画是演讲节奏，不是装饰。

### 5. 可复用页面模式（Slide Patterns）

| Pattern | 典型布局 | 使用场景 |
| --- | --- | --- |
| Scenario | 大图 + 一个短句/问题 | 开场、研究动机 |
| Gap | 现有方法 → 限制 → 待解决问题 | 研究空白 |
| Method | 模型模块图 + 逐步解释 | 方法、架构 |
| Results | 主图表 + 短结论 + 必要指标 | 主实验结果 |
| Ablation / Interpretation | 对比图 + 关键观察 | 消融与解释 |
| Conclusion | 1–3 个 takeaway + 一句展望 | 收尾 |

新的内容**先选择 Pattern，再填数据**；不要为每页重新发明一种设计。六种模式的机器可读布局和出现顺序见 [slide-patterns.json](slide-patterns.json)。

### 6. Token 层级与跨软件迁移

1. **Primitive Tokens**：颜色 hex、字号、间距、基础动画时长。
2. **Semantic Tokens**：primary / baseline / method-component / highlight 等角色。
3. **Component Tokens**：标题区、图表、模型模块、标注等的细节。
4. **Slide Patterns**：使用组件组成的 Scenario、Method、Results 等固定布局。

`design-tokens.json` 是**设计参数来源**，不是 PowerPoint/Keynote 可直接原生导入的主题格式。实际可通过脚本或工具把参数映射为 PowerPoint Slide Master、Keynote 母版、Figma 组件/Variables；不同工具仍需各自适配。

---

## C. 每次做新 Slides 的流程

1. **先写故事**：列出观众必须理解的研究问题、证据、结论。
2. **只写结论式标题**：检查按顺序阅读标题是否能讲通故事。
3. **从六种 Patterns 选版式**，优先使用图片和图表。
4. **从 Design Tokens 读取样式**，禁止随意添加新颜色、字号、布局。
5. **设计逐次点击节奏**：每次出现一项信息，最后一帧独立可读。
6. **投影与 PDF 双重检查**：远距离可读、颜色一致、图表真实、缺少动画时仍完整。

## 最终判断标准

- **内容**：观众能否在两分钟内理解场景与研究问题？
- **形式**：观众能否在不重新适应视觉语言的情况下理解下一份论文汇报？
- **连贯性**：只看标题与主图，能否复述研究故事？
- **证据**：每条主张是否有实验或材料支持，限定条件是否清楚？

**核心目标：内容可以每次不同，视觉语言不变；迭代的是同一套学术设计系统。**

## D. Claude / AI 生成

如果使用 Claude Code，先读取 [CLAUDE.md](CLAUDE.md)，再使用 [design-tokens.json](design-tokens.json) 和 [slide-patterns.json](slide-patterns.json)。JSON 只提供规则，需要 PPTX 生成器执行；如果不支持原生逐项点击动画，应采用逐步复制页面作为退化方案，并说明限制。
