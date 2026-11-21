---
name: mental-models-audit
description: '使用《跨学科思维模型100讲》对应的100个原子审查器，对上市公司、行业、商业模式、政策、战略或投资命题进行跨学科审计。支持 quick-scan、deep-audit 与 adversarial-audit；输出相关性、证据、机制、反方、未知数、证伪条件和后续模型路由。'
metadata:
  version: "0.1.0"
---

# Mental Models Audit Router

## 角色

你不是在展示模型名词，而是在做 **模型选择、证据审查和结构化反证**。

默认研究对象可以是：

- 上市公司
- 行业
- 商业模式
- 政策/制度
- 战略命题
- 已形成的投资 thesis

若与 `deep-equity-research` 联用，事实与数字必须继承其数据源、时间口径与零虚构纪律。

## 核心原则

1. **模型是工具，不是答案。** 不得为了“用满100个模型”强行制造内容。
2. **先判相关性，再分析。** 每个原子模型先给 `Material / Secondary / Not material`。
3. **独立证据优先。** 多个模型如果依赖同一事实，不得当成多份独立确认。
4. **机制优先于类比。** 必须解释因果/博弈/反馈机制。
5. **反方必须真实。** 最强反例不能是稻草人。
6. **显式未知。** 证据不足时输出 unknowns，不用故事补齐。
7. **可证伪。** Material 模型至少给一个可观察的 falsification condition。
8. **避免重复计数。** 模型重叠时合并为机制簇，而不是重复加分。

## 三种模式

### quick-scan

适合首次研究。

- 从100模型中选约10–20个
- 至少覆盖：认识论/统计、商业经济、系统、博弈或战略、心理偏差
- 只选择能改变结论或下一步研究优先级的模型
- 最终给出：Top positive mechanisms、Top risks、Critical unknowns、Next evidence

### deep-audit

适合高确信度 thesis、重大仓位前或年度复盘。

- 100模型全部经过相关性判断
- Not material 项只需一句原因，禁止硬写
- Material 项完整执行审查
- 汇总时将相似模型聚为机制簇
- 输出覆盖率：哪些关键机制已有证据，哪些仍是盲区

### adversarial-audit

适合“攻击已有结论”。

- 默认 thesis 可能错
- 优先调用反演、基准率、竞争、替代、尾部风险、系统陷阱、制度激励、护城河侵蚀、情景与证伪相关模型
- 主动寻找能让 bull case 失效的证据
- 不为了唱反调而反对；证据不足时明确写 unknown

## 路由流程

1. 定义研究对象与 thesis。
2. 列出当前事实底稿与数据缺口。
3. 判断问题类型：事实 / 因果 / 风险 / 商业质量 / 组织制度 / 战略。
4. 读取 `config/model-registry.yaml`，按 tags 与 trigger 选模型。
5. 运行选中的原子 Skill。
6. 对结果做去重：同一底层机制只保留一条主结论，其他作为佐证。
7. 检查模型冲突：哪些模型给出相反建议？冲突来自什么边界条件？
8. 输出统一审计报告。
9. 若与 deep-equity-research 联用，把结果映射回：商业模式、护城河、财务质量、增长、估值、反方、证伪与跟踪清单。

## 统一输出

每个原子 Skill 至少返回：

- model
- relevance
- question
- evidence_for
- evidence_against
- mechanism
- implication
- bull_case_impact
- bear_case_impact
- unknowns
- falsification
- confidence
- next_models

见 `schema/audit-output.yaml`。

## 停止规则

满足任一条件可停止继续调用模型：

- 新模型只重复既有机制，不增加信息
- 关键结论受制于数据缺口，继续推理不能提高质量
- 已得到足以改变行动的证据
- 当前决策高度可逆，继续分析的信息边际价值低

不要把“100个模型”变成新的 Analysis Paralysis。
