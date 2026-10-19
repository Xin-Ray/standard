# Contribution & Rule Governance | 规范贡献与维护规则

> **每一条规则必须可追溯：谁提出、来自哪个项目、依据是什么、是否必须执行。**

维护者与最初规范整理者：**Xin-Ray**（GitHub: [@Xin-Ray](https://github.com/Xin-Ray)）。本仓库使用 AI 辅助整理文稿；**AI 整理不等于原始观点归属**。

## 优先级（所有主题一致）

| 优先级 | 名称 | 执行要求 |
| --- | --- | --- |
| **P0** | Must / 必须 | 强制检查；不满足须修正，或明确记录适用性例外及理由 |
| **P1** | Should / 推荐 | 默认遵循；可以针对场景调整并说明原因 |
| **P2** | Optional / 可选 | 风格建议或参考实践，不作为硬性门槛 |

**规则层级与优先级不是一回事**：`Core` = 跨项目通用原则；`Context` = 某项目、导师或场景的约束；`Preference` = 可选风格。通用原则可为 P0；项目要求也可能为 P0；具体冲突应以安全/伦理/法律、数据协议及正式投稿要求优先，不可仅以贡献者职位判定。

## 统一规则表格格式（新增及维护一律使用）

| ID | Level | Priority | Rule | Project / Scope | Source / Evidence | Contributor | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| SLD-C001 | Core | P0 | 一页一个主要观点 | General Academic Slides | 本仓库初版整理（2026-10） | Xin-Ray | AI 辅助撰写 |
| SLD-X001 | Context | P1 | 示例：将某项导师反馈转成可执行规则 | Project + version | 待核对：反馈邮件/批注/录音/日期 | 待核实 | **示例，未生效，不可当成真实导师原话** |

字段含义：
- **ID**：长期稳定、不可重用。例如 `SLD-C001`（Slides/Content）、`SLD-V001`（Slides/Visual）、`PAP-C001`（Paper/Core）、`EML-C001`（Email）。重大修改保留 ID 并记录版本与变更；完全替换则废止旧规则并新增 ID。
- **Level**：Core / Context / Preference。
- **Priority**：P0 / P1 / P2，严格区分“必须”和“建议”。
- **Rule**：一句可验证、可执行的要求，避免只有口号。
- **Project / Scope**：可通用写 General；项目特定写明确项目及版本，如 `HealthCom TISA 2026 / deck v5`。
- **Source / Evidence**：提供可访问 URL、文件、反馈日期与定位（页码/段落/邮件引用）；若资料未公开，写 `Private feedback, date, location`，**绝不泄露私有资料**。仅有转述时标注 `User recollection — unverified`。
- **Contributor**：实际提出原始要求的人；多位贡献者按 `提议人；整理人；审核人` 标明角色，不能将 AI 文字润色当作教师提出的规则。
- **Notes**：适用前提、例外、验证方式、状态（Proposed / Verified / Adopted / Deprecated）。

## 贡献步骤（每次更新必做）

1. 找到具体项目/原始文件/反馈，并拆解为独立、可执行的规则，一条规则一行。
2. 为每条规则标注 **ID、Level、Priority、Project、Source、Contributor、Notes**；来源缺失先标 `Proposed / Unverified`，不署名于推测对象。
3. 通用规则写在对应 `standards/<topic>/README.md`；特定项目的原始反馈可另设 `standards/<topic>/sources/<project>.md`，保留项目来源与反馈摘录或非敏感摘要。
4. 若同一规则来自多人，保留 **Original proposer** 与 **Adapted/curated by**，不可覆盖最早贡献记录。
5. 发生冲突：先看适用范围、项目硬约束与证据；不直接删除异议，写明取舍与例外。
6. 提交 Git commit / PR，写清新增/修改的规则 ID、来源及贡献者；重要变更在对应规范的 Changelog 记录日期与原因。
7. 更新文档索引；AI 生成内容需要人工校验引用和归属。

## 来源归属示例：教授华芳的指导

以后整理华芳教授在 HealthCom / TISA PPT 中的意见时，**逐条**记录。例如：收到明确批注“限制汇报为 10 页”，才可建立：

| ID | Level | Priority | Rule | Project / Scope | Source / Evidence | Contributor | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| SLD-X010 | Context | P0 | 演讲稿/幻灯片控制在 10 页以内 | HealthCom TISA 2026（示例） | 需附反馈日期及原始邮件/批注定位 | Hua Fang（若证据核实）；Xin-Ray（整理） | **示例待核验，尚未正式收录为生效规则** |

不要把 Xin-Ray 的内容设计建议统一归给华芳教授；也不要把针对某一投稿的导师要求自动升级为所有 PPT 的通用 P0。若后续经验证具有通用价值，可新增 Core 规则，并保留原始贡献链。

## 修订记录

| Date | Change | Curator |
| --- | --- | --- |
| 2026-10-19 | 创建统一优先级、规则表格、来源与贡献机制 | Xin-Ray（AI-assisted drafting） |
