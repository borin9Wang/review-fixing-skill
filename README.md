<div align="center">

# Review Fixing Skill

### 依据稿件与批注修订综述，让改动有依据、有范围、可追溯

![Format](https://img.shields.io/badge/Format-SKILL.md-2563eb)
![Language](https://img.shields.io/badge/Language-中文%20%7C%20English-0f766e)
![Focus](https://img.shields.io/badge/Focus-Manuscript%20Revision-b45309)

**指定基线 · 批注落实 · 科学修订 · 成果保留 · 持续扩展**

[快速开始](#快速开始) · [功能介绍](#功能介绍) · [使用示例](#使用示例) · [扩展规则](#持续扩展) · [English](README.en.md)

</div>

---

一套用于修改已有学术综述的 Codex Skill。围绕用户指定版本、导师批注或审稿意见，修订论证、证据、指标、语言、图表和补充材料，保留已经准确、清楚且核实过的成果。

**仓库名为 `review-fixing-skill`，技能名和调用名沿用 `review-revision`。** 因此安装文件夹使用 `review-revision`，调用时使用 `$review-revision`，与既有本地技能保持一致。

## 功能介绍

| 能力 | 具体作用 |
|---|---|
| 确定修改基线 | 使用指定版本，识别正文、公式、图表、引用、修订和批注 |
| 控制改动范围 | 区分语言润色、定点修改与整体重构，按问题选择修改幅度 |
| 落实导师或审稿意见 | 将意见关联到实际位置、待解决问题、具体改动及回复 |
| 修复综述论证 | 补足研究意义、共同认识和差异解释，消除重复与脱节 |
| 核对修改涉及的证据 | 核回受影响的原文与 SI，使新句子与引用支持范围一致 |
| 保护科学含义 | 保留指标定义、参照、模型假设、计量范围及必要试验条件 |
| 优化科学表达 | 明确陈述已有认识，压缩没有新增信息的防御性套话 |
| 维护图表与公式 | 优先保留正确对象，同步图注、编号、正文解释与 SI |
| 检查交付质量 | 检查实际版面、引文和交叉引用，说明本轮真正完成的核验 |
| 持续积累修稿经验 | 使用 R01–R12 核心编号及限定范围的补充规则维护要求 |

## 修改思路

```text
指定稿件 + 修改目标 + 批注
             ↓
确认位置与问题 → 判断修改幅度 → 核回受影响证据
             ↓
具体修订 → 同步关联内容 → 检查文件 → 交付改稿与说明
```

当批注建议的图表或结论缺少依据时，选择有证据支持的替代方案并解释原因。用户已经明确要求整体重构时，按该授权执行。

## 快速开始

需要支持本地 `SKILL.md` 的 Codex 环境。本仓库提供修订规则；读取 Word 批注、渲染文档、检索原文和绘图等能力取决于宿主环境可用的工具。

将仓库克隆到技能目录，文件夹名使用 `review-revision`。

**Windows PowerShell**

```powershell
$reviewSkillRoot = if ($env:CODEX_HOME) { Join-Path $env:CODEX_HOME 'skills' } else { Join-Path $HOME '.codex\skills' }
New-Item -ItemType Directory -Path $reviewSkillRoot -Force | Out-Null
git clone https://github.com/borin9Wang/review-fixing-skill.git (Join-Path $reviewSkillRoot 'review-revision')
```

**macOS / Linux**

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/borin9Wang/review-fixing-skill.git "${CODEX_HOME:-$HOME/.codex}/skills/review-revision"
```

若已经安装同名技能，请先合并自己的新增规则，避免覆盖个性化内容。在能识别该技能的会话中，用 `$review-revision` 明确调用。

## 使用示例

**按导师批注小修**

```text
使用 $review-revision，以附件中的 V3 为基线处理导师批注。
优先做必要的局部修改，保留已核实的数据、公式、引用和图像。
交付修订稿，并简述每项重要意见的落实位置。
```

**提升综合论证和语言清晰度**

```text
使用 $review-revision，检查第四节的研究案例是否支持小标题。
补足研究意义与比较结论，压缩重复提醒，保留必要的科学条件。
```

**处理审稿意见**

```text
使用 $review-revision，根据稿件与审稿意见完成修订和回复。
对证据不足的建议提供合理替代方案，不编造数据或引用。
说明实际核回了哪些来源，以及哪些问题仍需补充材料。
```

## 持续扩展

可以直接告诉助手：

> 把这条加入综述修改 Skill：小修时优先保留已核实的公式和图像。

> 修改 R02：用户只要求语言润色时，不调整章节结构或新增科学结论。

> 这条规则只用于当前期刊，保存为限定范围的补充要求。

| 文件 | 维护内容 |
|---|---|
| [SKILL.md](SKILL.md) | 跨项目适用的核心修订规则 |
| [references/additions.md](references/additions.md) | 项目、期刊或作者偏好及适用范围 |
| [CONTRIBUTING.md](CONTRIBUTING.md) | 规则的归类、合并、编号与提交方式 |

新要求可以追加、修订或替代原条目；同类内容合并，既有编号保持稳定。源项目示例仅在其标明的范围内适用，某次修订的版本号和字数不会自动变成永久要求。

## 与写作 Skill 配合

| 任务 | 选择 |
|---|---|
| 指定版本上的定点修改、语言润色、批注落实 | 本仓库：`review-revision` |
| 已明确要求整体重构 | 本仓库控制修订范围，可结合写作 Skill 建立新论证 |
| 从文献、笔记或提纲起草全新综述 | [review-writing-skill](https://github.com/borin9Wang/review-writing-skill)，调用名 `review-writing` |

本 Skill 服务于作者修稿；期刊审稿报告或独立同行评审属于不同任务。

## 仓库结构

```text
review-fixing-skill/
├── SKILL.md
├── agents/openai.yaml
├── references/additions.md
├── README.md
├── README.en.md
├── CONTRIBUTING.md
└── .github/ISSUE_TEMPLATE/rule-request.md
```

## 方法来源

规则来自实际综述的多轮修订经验，并吸收 Karen V. Fernandez（2019）的教程 [Critically reviewing literature: A tutorial for new researchers](https://doi.org/10.1016/j.ausmj.2019.05.001) 中关于主题组织、综合陈述、评价研究贡献与不足及发现研究机会的原则。

版本基线、改动幅度、公式图像保护、批注追溯和交付检查等具体要求来自修稿实践。仓库不包含原教程全文、研究论文 PDF 或未公开稿件。
