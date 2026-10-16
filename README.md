# physics-lab-report · 大学物理实验报告技能

一个用于 AI 编程助手的 [Skill](https://code.claude.com/docs/en/skills)：自动撰写大学物理实验**预习报告**与**数据处理及实验结论**，内置误差理论与不确定度计算规范、评分格式要求、报告句式范例。

技能本身为山东大学（威海）普通物理实验课定制，但误差理论、报告结构、句式与讲义库机制可直接迁移到同类课程。

## 功能

- **模式一 · 实验预习**：给出实验名称，产出报告纸前四节——实验目的、实验仪器、实验原理（含不确定度传递公式预告）、实验步骤及操作要点。
- **模式二 · 数据处理与结论**：给出实验名称 + 测量数据，先对记录表中已填的派生量（平均值、$u_A$、$u_B$、合成不确定度等）逐项审核，再完成数据处理、误差分析与实验结论两节。
- **讲义库机制**：把课程讲义提炼成结构化要点文件（`references/讲义/`），点名实验时以讲义为第一依据而非通用模板。**本仓库不附带讲义内容**（整理自学校课程配套讲义，仅限自用）；文件夹内的 README 说明了自建讲义库的格式，未建库时技能自动回退通用模板。
- **反馈自进化**：每次调用先读 `references/反馈记录.md`，已确认的纠正与偏好优先于默认写法；新的定型意见会追加进该表，越用越贴合使用者课程的实际要求。

## 目录结构

```
physics-lab-report/
├── SKILL.md                              # 主指令：模式判定、输出格式、两种模式的写法
└── references/
    ├── 01-误差理论与数据处理规范.md        # 不确定度评定/传递/修约、仪器允差表
    ├── 02-评分要求与格式规范.md            # 课程评分标准与预习报告清单
    ├── 03-报告范例与句式.md               # 各节句式、表格样式、同类骨架
    ├── 反馈记录.md                        # 使用中定型的纠正与偏好（优先级最高）
    └── 讲义/                              # 讲义库（本仓库为空，见讲义/README.md 自建说明）
```

## 安装

技能遵循标准的 `SKILL.md` + frontmatter 格式，适用于 ZCode、Claude Code 等支持 Skills 的助手。

**ZCode**（用户级，全局可用）：

```bash
git clone https://github.com/zjp2555-stack/physics-lab-report-skill.git
cp -r physics-lab-report-skill/physics-lab-report ~/.zcode/skills/
```

**Claude Code**（项目级）：

```bash
git clone https://github.com/zjp2555-stack/physics-lab-report-skill.git
cp -r physics-lab-report-skill/physics-lab-report <你的项目>/.claude/skills/
```

安装后新开会话即可自动触发；也可以直接说"用 physics-lab-report 技能处理这组数据"。

## 使用示例

```
帮我写"液体表面张力系数的测定"的预习报告
```

```
霍尔效应实验数据如下（附表），处理数据并给出不确定度和结论
```

## 说明

- `references/` 中的规范依据课程误差理论课件与评分标准整理；讲义内容不随仓库发布。
- 报告内容为 AI 按规范生成，誊写前请自行核对仪器清单、原始读数等以当次实验实际为准的信息。
