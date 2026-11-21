# Integration with deep-equity-research

推荐执行顺序：

1. `deep-equity-research` 完成主体识别、数据截止日、事实底稿。
2. 完成商业模式、财务、资本效率与初步估值。
3. 把初步 thesis、关键假设、市场隐含预期交给 `mental-models-audit`。
4. 默认先跑 quick-scan。
5. 高确信度/重大仓位/争议标的再跑 adversarial-audit。
6. 重大决策前可跑 deep-audit 作为100模型盲点扫描。
7. 将审计结果回填：
   - 商业模式：生态位、供需、交易成本
   - 护城河：规模、网络效应、反馈、竞争动态
   - 财务质量：Stock–Flow、边际、杠杆、尾部风险
   - 管理层：激励、委托代理、认知偏差
   - 增长：适应度景观、创造性破坏、路径依赖
   - 估值：基准率、情景、期望值、实物期权
   - 反方：反演、证伪、系统陷阱、军备竞赛
8. 最终报告只保留会改变结论的模型发现，不列100个模型名。

## 建议入口

在 deep-equity-research 的“形成多空两套解释”之后、“估值与反向估值”之前调用一次 quick-scan；
在最终结论前调用 adversarial-audit。
