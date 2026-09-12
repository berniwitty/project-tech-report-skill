# project-tech-report — 项目技术报告写作 Skill（Claude Code）

**中文** | [English](README.en.md)

把一个已完成的大模型 / 机器学习项目，按固定模板写成一份**面向学习、面试与简历**的完整技术报告。产出是成品，不是待填框架。

## 报告长什么样

固定的顶层区域，顺序不变：

```
标题
阅读前须知（提示框：写给谁 / 数字口径 / 项目一句话）
摘要（项目目的 / 主要结论 / 技术栈）
第一部分：项目技术报告
    1. 任务是什么，为什么难（具体例子 / 判分规则 / 指标同例对比 / 场景表 / 基线的分段分解）
    2. 评测口径：先证明尺子是准的
    3..N. 阶段 k：这一步在做什么 / 做法与结果 / 对照实验 / 阶段结论
    N+1. 综合分析（各阶段贡献 + 与外部基准的对照）
第二部分：面试会追到的基础知识（0. 名词理顺；每个方法一节：机制 / 数据与目标函数 + 手算 / 与本项目的联系 / 边界与误区）
第三部分：面试问题（每题：💡 思路 + 🗣 参考答案）
简历段落与使用方式（两种用法 / 简历原文 / 面试时要主动说清的边界）
附：术语表
```

三条贯穿全文的原则：

1. **目标是任务本身，不是超过谁。** 开头回答的是这个任务是什么、为什么难、要把哪个量提上去，并单列一段「立项时的非目标」。跑分对照是结果的一部分，不是立项目的。
2. **外部基准只出现在两处**：校准评测口径，以及正文接近结尾的一张结果对照表。对照表必须列全场景、把落后的格子也写出来，并同时说明三条前提：训练数据是否相同、训练方式是否相同、样本量是否相同。
3. **零基础可读。** 术语第一次出现就地解释，指标用同一个例子算出三种口径，文末给术语表。

写法上的几条硬规定：对照实验固定「已有结果 / 理论分析 / 后续方案 / 结论」四块；阶段结论提示框必须写「必须主动说的边界」；每个数字带分母；一次改多个变量时写「一揽子改动」，归因留给消融；负结果如实写并给机制；没测到数字的路线写「成本结论」而不是「负结果」；简历原文一字不改，报告向简历对齐；禁止比喻和模糊指代；删掉面试官不会问的内容（文件路径、脚本名、运维细节）。

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

Skill 会先向你要四样输入：立项文档（规格、预注册、目标与非目标）、事实源（实验记录、结果表、配置、代码）、简历段落（如有）、外部基准或论文（如有）。项目目的取自立项文档，不从模板反推。报告写到项目的 `docs/TECH_REPORT.md`，标题层级按 Notion 四级标题设计，粘贴后直接成为标题块；指定 Notion 页面时会整页写入。

与 `llm-interview-notes` 的区别：那个 skill 只产出简历驱动的背诵问答；本 skill 产出叙事完整的技术报告，任务定义、理论与简历都是正文的一部分，面试问答只是其中一节。

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
