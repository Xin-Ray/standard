# Standards Library | 可复用规范库

> **Define once, reuse everywhere. 规范一次沉淀，长期反复使用。**

这是为个人、研究者、团队及 AI 助手准备的开放规范库。它不只服务于 Slides，而是持续积累**论文、演示、邮件沟通及其他工作流程的可执行规则**。任何人都可以阅读、引用与按需改造。

## 如何更新本规范库（必读）

**新增或修改规则必须署名，并说明项目与来源；同时标注 P0（必须）、P1（推荐）、P2（可选）及 Core / Context / Preference 层级。** 统一使用以下表头：

| ID | Level | Priority | Rule | Project / Scope | Source / Evidence | Contributor | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |

具体执行方式见 **[CONTRIBUTING.md — 贡献与规则治理规范](CONTRIBUTING.md)**。仓库初版由 **[Xin-Ray](https://github.com/Xin-Ray)** 整理；外部导师与合作者的要求应逐条引用原始反馈，不得仅凭推测署名。

## 已有规范

| Category | Standard | 内容 |
| --- | --- | --- |
| 📄 Research Papers | [Paper Writing & Experimental Standards](standards/papers/README.md) | 科学问题、Research Gap、方法动机、公平实验、图表及正式指南 |
| 🎞️ Presentations | [Academic Slides Standards](standards/slides/README.md) | **Content Design**：叙事、场景图、结论式标题；**Visual Design**：版式、逐次点击、图表与一致性 |
| 🎨 Design System | [Slides Design Tokens](standards/slides/design-tokens.json) | 颜色、文字层级、间距、语义色、动画参数 |
| 🤖 AI Slide Generation | [Claude Guide](standards/slides/CLAUDE.md) · [Slide Patterns](standards/slides/slide-patterns.json) | 指导 Claude 按统一的视觉规则和版式生成 Slides |

## 计划扩充

- **Email & Replies**：教授/合作伙伴邮件、简洁表达、确认、催办和礼貌回复规范（尚未编写）。
- **Research Workflow**：阅读文献、实验记录、数据复现、同行评审。
- **Engineering**：代码风格、PR Review、文档与发布流程。

## 三类规则

1. **Content / Substance**：做什么、讲什么，为什么重要。
2. **Form / Presentation**：如何组织信息并形成统一表达风格。
3. **Process / Quality**：执行步骤、复核标准、检查清单。

## 如何使用

- **人类使用**：打开对应规范，依据步骤执行，并用文末 Checklist 检查。
- **AI 使用**：将对应 Markdown 文件 URL 提供给 AI，要求先读规范，再执行任务并标注不适用的例外。
- **贡献规范**：在 `standards/<topic>/README.md` 新增条目，先遵循 [CONTRIBUTING.md](CONTRIBUTING.md) 的来源归属与优先级表，再按 Scope → Principles → Workflow → Examples → Checklist → References 组织详细说明；配套配置与模板放在同目录。

## 目录

```text
standards/
├── papers/
│   └── README.md
└── slides/
    ├── README.md
    ├── design-tokens.json
    ├── slide-patterns.json
    └── CLAUDE.md
```

原仓库 `slides` 已更名为 `standard`。根目录旧版 [design-tokens.json](design-tokens.json) 暂时保留供历史引用；未来请使用分类目录的版本。

**原则**：规范是可以共享和调整的起点，不应压过具体任务证据、期刊要求或沟通对象的实际需求。
