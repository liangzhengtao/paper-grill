<![CDATA[<div align="center">

# 🔥 paper-grill

**你的论文值得在审稿人看到之前获得一次诚实的评审。**

10个AI技能，模拟NeurIPS、ICML、ICLR、ACL、CVPR审稿风格。

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-10-blue)](#技能)

</div>

---

## 之前 → 之后

**泛泛的反馈：**
> "你的论文需要更多实验。写作可以改进。新颖性有限。"

**paper-grill评审：**
> **W1（缺失基线）：** 缺少与AdamW的比较。该方法在CIFAR-10上报告了95.2%（他们的表2），而你的方法是94.8%。没有这个比较，无法确定贡献是否推进了最新技术水平。**建议：** 在所有实验中添加AdamW作为基线，使用相同的超参数调优预算。

---

## 技能

### 会议风格

| 技能 | 会议 | 关注点 | 文件 |
|------|------|--------|------|
| NeurIPS审稿 | NeurIPS | 可复现性、理论严谨性、实验完整性 | `skills/会议风格/neurips-review.md` |
| ICML审稿 | ICML | 数学严谨性、收敛保证、消融研究 | `skills/会议风格/icml-review.md` |
| ICLR审稿 | ICLR | 表征新颖性、开放审稿礼仪、可视化 | `skills/会议风格/iclr-review.md` |
| ACL审稿 | ACL/EMNLP/NAACL | 语言学贡献、数据集质量、错误分析 | `skills/会议风格/acl-review.md` |
| CVPR审稿 | CVPR/ICCV/ECCV | 视觉质量、架构消融、基准比较 | `skills/会议风格/cvpr-review.md` |

### 通用审稿

| 技能 | 用途 | 文件 |
|------|------|------|
| 结构化审稿 | 通用审稿框架与评分标准 | `skills/通用审稿/structured-review.md` |
| 识别弱点 | 系统性弱点识别与严重程度分类 | `skills/通用审稿/identify-weaknesses.md` |
| 审稿校准 | 确保公平、一致、建设性的审稿 | `skills/通用审稿/review-calibration.md` |

### 投稿辅助

| 技能 | 用途 | 文件 |
|------|------|------|
| 回复撰写 | 撰写有效的作者回复 | `skills/投稿辅助/rebuttal-writing.md` |
| 论文自审 | 投稿前自审论文 | `skills/投稿辅助/paper-self-review.md` |

## 会议对比

| 会议 | 关注重点 | 评分范围 | 关键区别 |
|------|----------|----------|----------|
| **NeurIPS** | 可复现性、理论严谨性、实验完整性 | 1-10 | 广泛ML关注，强调可复现性 |
| **ICML** | 数学严谨性、收敛保证、证明 | 1-10 | 重理论，证明验证 |
| **ICLR** | 表征学习、开放审稿、可视化 | 1-10 | 开放审稿流程，公开回复 |
| **ACL** | 语言学贡献、数据集质量、错误分析 | 1-6 | NLP特定评估，需要人工评估 |
| **CVPR** | 视觉质量、消融研究、基准比较 | 1-10 | 强调视觉结果，定性评估 |

## 快速开始

### Cursor

1. 将技能文件复制到项目的 `.cursorrules` 或 `skills/` 目录
2. 在提示中引用技能：
   ```
   使用NeurIPS审稿技能，评审我的论文 paper.tex
   ```

### Claude Code

1. 将技能文件复制到项目目录
2. 在提示中引用技能：
   ```
   读取 skills/会议风格/neurips-review.md 并按照NeurIPS审稿模板评审我的论文
   ```

### Kimi Code

1. 将技能文件复制到项目目录
2. 在提示中引用技能：
   ```
   @skills/通用审稿/structured-review.md 使用结构化审稿框架评审我的论文
   ```

### 通用用法

任何AI编码助手都可以通过读取技能文件并遵循模板来使用这些技能。技能设计为自包含，包含清晰的说明、模板和示例。

## 每个技能包含

- **使用场景** - 明确的触发条件
- **审稿框架** - 结构化方法论
- **评分标准** - 每个分数级别的清晰标准
- **审稿模板** - 完整的填写式示例
- **示例审稿** - 好坏示例及解释
- **常见错误** - 审稿人和作者应避免的问题
- **中文版本** - 关键内容的中文版本

## 另请参阅

- [awesome-skills](https://github.com/anthropics/awesome-skills) - AI技能精选列表
- [awesome-research-figures](https://github.com/your-username/awesome-research-figures) - 科学图表生成技能
- [awesome-interview-skills](https://github.com/your-username/awesome-interview-skills) - AI面试准备
- [awesome-ai-rules](https://github.com/your-username/awesome-ai-rules) - AI编码规则和指南

## 贡献

欢迎贡献！请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解指南。

## 许可证

本项目采用MIT许可证 - 详见 [LICENSE](LICENSE) 文件。

---

<div align="center">

**为希望在审稿人给出意见前获得诚实反馈的研究者而制 🔥**

</div>
]]>