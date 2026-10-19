# Research Paper Standard — 研究论文规范

> **One question → One challenge → One methodological solution → Convincing experiments → One evidence-based conclusion.**

**适用范围**：以纵向健康数据、时空预测、ML/DL 为例，也可供其他实证研究调整复用。规范不是要求一定开发复杂模型，而是用可信证据回答明确问题。

## Effective Rules（9/50）

| ID | Level | Priority | Rule | Verification / Pass Criteria | Project / Scope | Source / Evidence | Contributor | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PAP-C001 | Core | P0 | 全文围绕一个可检验的科学问题 | Abstract 与 Introduction 是否明确 RQ；主实验是否直接作答 | Research papers | 最初论文七标准，2026-10 | Xin-Ray（整理） | — |
| PAP-C002 | Core | P0 | 结果解释不得超过证据支持范围 | 逐条核对主张、统计不确定性和关联/因果措辞 | Research papers | 最初论文七标准，2026-10 | Xin-Ray（整理） | — |
| PAP-C003 | Core | P0 | 预测评估无数据泄漏且可复现 | 检查按患者划分、时间切点及仅训练集拟合预处理；复现实验指标 | Longitudinal ML | CARDIA/WHI 研究规范，2026-10 | Xin-Ray（整理） | — |
| PAP-C004 | Core | P0 | 比较公平并披露主指标和不确定性 | 审查 baseline、相同划分/标签、指标、CI、样本量 | ML prediction | 最初论文七标准，2026-10 | Xin-Ray（整理） | — |
| PAP-C005 | Core | P1 | Research Gap 和模型组件具有具体动机 | 逐个组件映射到数据挑战与对应消融实验 | Research papers | 最初论文七标准，2026-10 | Xin-Ray（整理） | — |
| PAP-C006 | Core | P1 | 实验及图表回答明确问题而非堆积最高分 | 每个实验写一句被验证的问题；检查正/负结果及图注是否完整 | Research papers | 最初论文七标准，2026-10 | Xin-Ray（整理） | — |
| PAP-X001 | Context | P1 | 验证空间信息相对纯时间模型的增益 | 比较相同划分/模型预算下的 Temporal-only 与 Spatial 结果和 CI | CARDIA/WHI | 时空论文范例，2026-10 | Xin-Ray（整理） | — |
| PAP-X002 | Context | P1 | 比较空间表达及搬迁者分组 | 核对 State/Region/Trajectory 与 Movers/Non-movers 的样本数、增益、CI | CARDIA/WHI | 时空论文范例，2026-10 | Xin-Ray（整理） | 合并空间粒度与子组分析 |
| PAP-X003 | Context | P1 | 实施消融和稳健性验证 | 检查去掉空间模块、更改设定、跨队列/种子的结果和负面结果 | CARDIA/WHI | 时空论文范例，2026-10 | Xin-Ray（整理） | — |

以下为解释和范例，不额外计入规则数量；冲突时以有效规则表为准。

## A. 好论文的七条标准

| 标准 | 核心要求 |
| --- | --- |
| 1. 一个核心问题 | 整篇论文围绕明确、可验证的 Research Question，不堆叠模型 |
| 2. 清楚的 Research Gap | 现有方法没解决什么？为什么值得研究？ |
| 3. 方法有明确动机 | 每个模型组件应对应一个具体的数据挑战 |
| 4. 实验回答问题（最重要） | 不只比较分数；解释差异意味着什么，以及哪些解释尚不能排除 |
| 5. 公平且可复现 | 一致合理的数据划分、基线、缺失处理、指标、记录与代码 |
| 6. 图表讲述故事 | 每张图回答一个具体问题 |
| 7. 结论与证据匹配 | 区分预测相关性、统计显著性、泛化与因果关系 |

**示例科学问题**：*Does spatial information provide additional predictive value beyond longitudinal health data?* 不只报告 Transformer 与 GRU 的分差，还要回答空间是否增益、搬迁者与未搬迁者是否不同、哪种地理粒度有效、什么条件下仍然有效。

## B. 六篇值得学习的论文

| 论文 | 发表 | 可以学习什么 |
| --- | --- | --- |
| [RETAIN: An Interpretable Predictive Model for Healthcare](https://papers.nips.cc/paper_files/paper/2016/hash/231141b34c82aa95e48810a9d1b33a79-Abstract.html) | NeurIPS 2016 | 从可解释性需求推导模型设计 |
| [Recurrent Neural Networks for Multivariate Time Series with Missing Values (GRU-D)](https://www.nature.com/articles/s41598-018-24271-9) | Scientific Reports 2018 | 针对医疗时序缺失值设计方法 |
| [Patient Subtyping via Time-Aware LSTM Networks](https://www.kdd.org/kdd2017/papers/view/patient-subtyping-via-time-aware-lstm-networks) | KDD 2017 | 处理不规则随访时间 |
| [Temporal Fusion Transformers](https://doi.org/10.1016/j.ijforecast.2021.03.012) | International Journal of Forecasting 2021 | 模型架构、变量选择、消融与解释 |
| [Reconstructing individual-level exposures in cohort analyses of environmental risks: an example with the UK Biobank](https://www.nature.com/articles/s41370-023-00635-w) | Journal of Exposure Science & Environmental Epidemiology 2024 | 居住历史、迁徙和空间暴露；注意它不是疾病预测模型 |
| [PopNet: Real-Time Population-Level Disease Prediction with Data Latency](https://doi.org/10.1145/3485447.3512127) | WWW 2022 | 空间与时间的预测设计；研究是区域级而非个体级 |

**优先阅读**：T-LSTM（纵向方法动机）、UK Biobank exposure（迁徙与空间历史）、TFT（复杂模型的实验论证）。引用时应核查论文完整元数据与适用领域。

## C. 针对 CARDIA / WHI 研究的实验规则

| 实验 | 需要回答的问题 |
| --- | --- |
| Temporal-only vs Spatiotemporal | 加入空间信息是否有额外预测价值？ |
| State / Region / Trajectory | 哪种空间表示最有价值？ |
| Movers vs Non-movers | 搬迁历史是否调节空间信息的预测增益？ |
| Logistic / GBDT / Transformer / GNN | 增益是否依赖复杂模型或额外参数？ |
| Ablation | 哪个空间模块/特征带来收益？ |
| Robustness & Validation | 收益是否稳定？是否受数据泄漏、混杂、队列差异影响？ |

**执行原则：**

- **患者级数据隔离**：重复观测不跨训练/测试；插补、标准化、特征选择只从训练集拟合。
- **时间正确性**：严格界定观测窗口与预测时间，杜绝未来地区、迁徙记录和健康标签泄漏。
- **公平对照**：使用相同划分、标签、预测窗口和合理的超参搜索预算。
- **报告不确定性**：报告各组增益、置信区间、队列差异、负面结果；主指标可采用 patient-weighted PR-AUC（视具体任务而定），并考虑校准和类别比例。
- **分组解释谨慎**：检查 movers / non-movers 样本量、分布与选择偏倚。
- **不把预测写成因果**：地点提高预测效果，并不意味着地点导致疾病。

## D. 五类核心图

1. **Figure 1 — Research Motivation**：患者跨年度居住位置与纵向健康记录，直观看出空间问题。
2. **Figure 2 — Model Architecture**：时间编码、空间编码和预测模块如何连接。
3. **Figure 3 — Main Performance**：严格匹配的 temporal-only 与 spatiotemporal 对照及不确定性。
4. **Figure 4 — Subgroup Analysis**：搬迁者/未搬迁者、各疾病任务的空间增益。
5. **Figure 5 — Ablation & Robustness**：空间表示、模块删减及敏感性分析。

图的数量是建议，不是硬性要求。轴、单位、指标、图例和样本量必须清楚。

## E. 正式检查框架

- [TRIPOD+AI (BMJ, 2024)](https://www.bmj.com/content/385/bmj-2023-078378)：临床预测模型研究的**报告透明性**指南。
- [PROBAST+AI (BMJ, 2025)](https://www.bmj.com/content/388/bmj-2024-082505)：预测模型研究的**偏倚风险、质量与适用性**评估工具。

它们用途不同，也不能替代目标期刊的规范或数据使用协议。

## F. 投稿前 Checklist

- [ ] 一个明确且可被实验回答的 Research Question
- [ ] Research Gap 有文献依据，方法组件有动机
- [ ] 数据、划分、缺失处理和评估可复现，无未来/患者信息泄漏
- [ ] 有公平的简单模型与复杂模型对照
- [ ] 主结果回答研究问题，并报告不确定性和负面结果
- [ ] 图表与文字不夸大显著性、因果性及临床意义
- [ ] 报告限制、泛化风险、适用范围与数据发布约束
- [ ] 满足投稿期刊和适用报告指南

**最终原则：先确定论文要证明什么，再反向设计模型、实验和图表。不要先训练大量模型，最后从分数中寻找研究故事。**
