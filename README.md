# Deep Equity Research

一个面向上市公司基本面研究的 Agent Skill，默认使用中文输出。

它支持：

- 对指定上市公司进行深度研究。
- 每日筛选一家值得研究的上市公司。
- 分析商业模式、ROE/ROIC、杜邦驱动、客户粘性和定价权。
- 评估管理层、经济护城河、市场预期与安全边际。
- 输出三情景估值、敏感性分析、证伪红线与空头观点。

## 安装

使用 Skills CLI：

```bash
npx skills add TangHuaiZhe/deep-equity-research
```

也可以将 `SKILL.md` 复制到 Agent 的 Skills 目录。

## 使用示例

```text
用 deep-equity-research 分析贵州茅台。
```

```text
今天推荐一家值得深度研究的上市公司。
```

## 数据要求

本 Skill 要求通过可用的行情、财报、公告和检索工具核验关键数据。找不到的数据必须明确标注缺失，不得虚构。

金融数据工具与 API 凭据需要由使用者自行配置。请勿将 API Key 提交到仓库。

## 免责声明

本项目仅用于研究和信息分析，不构成个性化投资建议，也不承诺任何投资收益。
