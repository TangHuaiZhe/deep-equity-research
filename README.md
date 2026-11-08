# Deep Equity Research

一个面向上市公司基本面研究的 Agent Skill，默认使用中文输出。

它支持：

- 对指定上市公司进行深度研究。
- 每日筛选一家值得研究的上市公司。
- 分析商业模式、ROE/ROIC、杜邦驱动、客户粘性和定价权。
- 评估管理层、经济护城河、市场预期与安全边际。
- 输出三情景估值、敏感性分析、证伪红线与空头观点。

## 安装

本项目不需要发布到 npm。以下命令会临时运行 npm 上的 `skills` CLI，再从 GitHub 克隆本仓库并安装其中的 `SKILL.md`。

安装到当前项目：

```bash
npx skills add TangHuaiZhe/deep-equity-research
```

安装到本机的全局 Agent Skills 目录：

```bash
npx skills add TangHuaiZhe/deep-equity-research --global
```

也可以将 `SKILL.md` 手动复制到目标 Agent 的 Skills 目录。仓库必须保持可访问；如果仓库是私有仓库，使用者需要具备相应的 GitHub 访问权限。

## 使用示例

```text
用 deep-equity-research 分析贵州茅台。
```

```text
今天推荐一家值得深度研究的上市公司。
```

## 数据要求

本 Skill 默认通过平安资讯/证券 Skill 获取行情和财务数据，并结合财报、公告核验关键数据。平安资讯未安装、未配置或不可用时，会尝试使用腾讯自选股 Skill。找不到的数据必须明确标注缺失，不得虚构。

使用前，请按平安资讯 Skill 的说明在本机配置 `PINGAN_SKILL_APIKEY`。未检测到 API Key 时，Skill 会尝试使用已配置的腾讯自选股；两者均不可用时才停止完整研究并提示完成接入。请勿将 API Key 提交到仓库或粘贴到公开对话中。

## 免责声明

本项目仅用于研究和信息分析，不构成个性化投资建议，也不承诺任何投资收益。
