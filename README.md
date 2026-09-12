# project-tech-report — 项目技术报告写作 Skill（Claude Code）

**中文** | [English](README.en.md)

把一个已完成的大模型 / 机器学习项目，按固定模板写成一份**面向学习、面试与简历**的完整技术报告。产出是成品，不是待填框架。

## 报告长什么样

固定七个顶层区域，顺序不变：

```
标题
阅读前请注意（提示框：用途、简历免责、配合阅读、版本、状态、项目定位）
文档组织思路（一行箭头链 + 逐项说明）
摘要（项目目的 / 主要结论 / 技术栈）
第一部分：项目技术报告
    1. 项目目标
    2. 总体技术方案（等宽字符流程图）
    3..N. 阶段 k：阶段目标 / 评测 / 核心方法 / 对照实验 / 阶段结论
    N+1. 各阶段的综合分析
第二部分：理论基础与应掌握知识（每个主题：对应实践 → 解决什么问题 → 数据与目标 → 与本项目的联系 → 误区）
第三部分：面试问题（每题：💡 思路 + 🗣 参考答案）
简历示例与项目使用方式（重要说明 / 两种使用方式 / 简历初稿）
```

写法上的几条硬规定：核心方法每一小节以"**本段要讲清楚**"开头、"综上"收束；对照实验固定"已有结果 / 理论分析 / 后续方案 / 结论"四块；阶段结论带"**核心结果**"提示框；每个数字带分母；一次改多个变量时写"一揽子改动"，归因留给消融；负结果如实写并给机制；没测到数字的路线写"成本结论"而不是"负结果"；禁止比喻和模糊指代。

格式来源：小红书账号「不转到大模型不改名」发布的《面向 Agent 的本地小模型结构化输出后训练与部署》报告，原文提取见 [`references/example-report-excerpt.md`](references/example-report-excerpt.md)。

## 安装

macOS / Linux / Git Bash：

```bash
git clone https://github.com/berniwitty/project-tech-report-skill ~/.claude/skills/project-tech-report
```

Windows PowerShell：

```powershell
git clone https://github.com/berniwitty/project-tech-report-skill "$env:USERPROFILE\.claude\skills\project-tech-report"
```

装好后重开 Claude Code 会话即可被识别。

## 使用

在 Claude Code 里说下面任意一句，或直接输入 `/project-tech-report`：

- 「按模板写项目技术报告」
- 「把这个项目整理成技术报告」
- 「项目学习报告」「面试前突击资料」「最终报告」

Skill 会先向你要三样输入：项目事实源（文档、实验记录、结果表、配置、代码）、简历段落（如有）、已有的面试笔记（如有）。报告写到项目的 `docs/TECH_REPORT.md`，标题层级按 Notion 四级标题设计，粘贴后直接成为标题块。

与 `llm-interview-notes` 的区别：那个 skill 只产出简历驱动的背诵问答；本 skill 产出叙事完整的技术报告，理论与简历是正文的一部分，面试问答只是其中一节。

## 文件

| 文件 | 作用 |
|---|---|
| [`SKILL.md`](SKILL.md) | 规则本体：全文结构、每个区域的定义与要求、写作规范、交付与检查清单 |
| [`templates/REPORT_TEMPLATE.md`](templates/REPORT_TEMPLATE.md) | 可直接填写的报告骨架，每个区域附引导句 |
| [`references/example-report-excerpt.md`](references/example-report-excerpt.md) | 范例报告原文提取，用于对照格式与文风 |

## 产出示例

ShopWeaver 项目（ShopSimulator 基准上 Qwen3-8B 的多智能体蒸馏与数据飞轮后训练）按本模板重写的报告：`docs/TECH_REPORT.md`，见 ShopWeaver 仓库。

## License

MIT
