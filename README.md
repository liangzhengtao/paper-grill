<![CDATA[<div align="center">

# 🔥 paper-grill

**Your paper deserves an honest review before the reviewers see it.**

10 AI skills mimicking NeurIPS, ICML, ICLR, ACL, CVPR review styles.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-10-blue)](#skills)

</div>

---

## Before → After

**Generic feedback:**
> "Your paper needs more experiments. The writing could be better. Novelty is limited."

**paper-grill review:**
> **W1 (Missing Baseline):** The comparison with AdamW is missing. This method reported 95.2% on CIFAR-10 (their Table 2), compared to your 94.8%. Without this comparison, it's unclear if the contribution advances the state-of-the-art. **Recommendation:** Add AdamW as a baseline in all experiments using the same hyperparameter tuning budget.

---

## Skills

### 会议风格 (Conference Styles)

| Skill | Conference | Focus | File |
|-------|-----------|-------|------|
| NeurIPS Review | NeurIPS | Reproducibility, theoretical rigor, experimental completeness | `skills/会议风格/neurips-review.md` |
| ICML Review | ICML | Mathematical rigor, convergence guarantees, ablation studies | `skills/会议风格/icml-review.md` |
| ICLR Review | ICLR | Novelty of representations, open review etiquette, visualization | `skills/会议风格/iclr-review.md` |
| ACL Review | ACL/EMNLP/NAACL | Linguistic contribution, dataset quality, error analysis | `skills/会议风格/acl-review.md` |
| CVPR Review | CVPR/ICCV/ECCV | Visual quality, ablation on architectures, benchmark comparison | `skills/会议风格/cvpr-review.md` |

### 通用审稿 (General Reviewing)

| Skill | Purpose | File |
|-------|---------|------|
| Structured Review | Universal review framework with scoring rubric | `skills/通用审稿/structured-review.md` |
| Identify Weaknesses | Systematic weakness identification with severity classification | `skills/通用审稿/identify-weaknesses.md` |
| Review Calibration | Ensuring fair, consistent, and constructive reviews | `skills/通用审稿/review-calibration.md` |

### 投稿辅助 (Submission Support)

| Skill | Purpose | File |
|-------|---------|------|
| Rebuttal Writing | Writing effective author responses to reviewers | `skills/投稿辅助/rebuttal-writing.md` |
| Paper Self-Review | Reviewing your paper before submission | `skills/投稿辅助/paper-self-review.md` |

## Conference Comparison

| Conference | What They Focus On | Scoring Scale | Key Differentiator |
|------------|-------------------|---------------|-------------------|
| **NeurIPS** | Reproducibility, theoretical rigor, experimental completeness | 1-10 | Broad ML focus, emphasis on reproducibility |
| **ICML** | Mathematical rigor, convergence guarantees, proofs | 1-10 | Heavy theory focus, proof verification |
| **ICLR** | Representation learning, open review, visualization | 1-10 | Open review process, public rebuttals |
| **ACL** | Linguistic contribution, dataset quality, error analysis | 1-6 | NLP-specific evaluation, human eval required |
| **CVPR** | Visual quality, ablation studies, benchmark comparison | 1-10 | Visual results emphasis, qualitative evaluation |

## Quick Start

### Cursor

1. Copy the skill files to your project's `.cursorrules` or `skills/` directory
2. Reference the skill in your prompt:
   ```
   Using the NeurIPS review skill, review my paper at paper.tex
   ```

### Claude Code

1. Copy the skill files to your project directory
2. Reference the skill in your prompt:
   ```
   Read skills/会议风格/neurips-review.md and review my paper following the NeurIPS review template
   ```

### Kimi Code

1. Copy the skill files to your project directory
2. Reference the skill in your prompt:
   ```
   @skills/通用审稿/structured-review.md review my paper with the structured review framework
   ```

### General Usage

Any AI coding assistant can use these skills by reading the skill files and following the templates. The skills are designed to be self-contained with clear instructions, templates, and examples.

## Each Skill Includes

- **When to Use** - Clear trigger conditions
- **Review Framework** - Structured methodology
- **Scoring Rubric** - Clear criteria for each score level
- **Review Templates** - Complete, fill-in-the-blank examples
- **Example Reviews** - Good and bad examples with explanations
- **Common Mistakes** - What to avoid for reviewers and authors
- **中文版本** - Chinese version of key content

## See Also

- [awesome-skills](https://github.com/anthropics/awesome-skills) - Curated list of AI skills
- [awesome-research-figures](https://github.com/your-username/awesome-research-figures) - Scientific figure generation skills
- [awesome-interview-skills](https://github.com/your-username/awesome-interview-skills) - AI-powered interview preparation
- [awesome-ai-rules](https://github.com/your-username/awesome-ai-rules) - AI coding rules and guidelines

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Made with 🔥 for researchers who want honest feedback before the reviewers give it**

</div>
]]>