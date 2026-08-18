# Identify Weaknesses

Systematic framework for identifying weaknesses in academic papers. Use this skill to find problems before submission or during review, with severity classification and actionable recommendations.

## When to Use

- Finding problems in a paper before submission
- Conducting a thorough review during peer review
- Identifying fatal flaws that would lead to rejection
- Creating a weakness report for authors
- Training reviewers to spot common issues
- Self-reviewing papers to catch problems early

## Review Framework

### Weakness Categories

Weaknesses fall into these categories:

1. **Methodology Flaws**
   - Incorrect assumptions
   - Logical gaps in reasoning
   - Insufficient theoretical grounding
   - Inappropriate methodology for the problem

2. **Experimental Issues**
   - Missing baselines
   - Insufficient experiments
   - Inappropriate metrics
   - Lack of statistical rigor
   - Unfair comparisons

3. **Presentation Problems**
   - Unclear writing
   - Missing definitions
   - Inconsistent notation
   - Poor figure quality
   - Missing or incorrect references

4. **Scope Limitations**
   - Limited applicability
   - Missing important cases
   - Overgeneralized claims
   - Insufficient coverage

5. **Reproducibility Concerns**
   - Missing implementation details
   - Unavailable code/data
   - Insufficient hyperparameter reporting
   - Non-deterministic results

6. **Ethical Issues**
   - Bias in data or models
   - Potential for misuse
   - Missing ethical considerations
   - Privacy concerns

### Severity Classification

#### Fatal Flaws (Must Fix - Likely Rejection)

These issues are almost always rejection-worthy:

1. **Technical Errors**
   - Incorrect proofs or derivations
   - Fundamental methodology flaws
   - Invalid assumptions that invalidate results
   - Mathematical errors that affect conclusions

2. **Missing Core Experiments**
   - No comparison with obvious baselines
   - No evaluation on standard benchmarks
   - No ablation study for key components
   - No statistical significance testing

3. **Unsupported Claims**
   - Claims not backed by experiments
   - Overgeneralization from limited results
   - Misrepresenting prior work
   - Cherry-picking results

4. **Ethical Violations**
   - Plagiarism or self-plagiarism
   - Data fabrication or manipulation
   - Missing ethical approval for human subjects
   - Harmful applications without discussion

#### Major Issues (Should Fix - Likely Weak Reject/Borderline)

These issues significantly weaken the paper:

1. **Incomplete Evaluation**
   - Missing some important baselines
   - Limited dataset coverage
   - Insufficient ablation studies
   - No error analysis

2. **Weak Analysis**
   - Superficial discussion of results
   - Missing failure case analysis
   - No analysis of limitations
   - Insufficient visualization

3. **Presentation Issues**
   - Poorly written sections
   - Missing or confusing figures
   - Inconsistent terminology
   - Missing related work

4. **Scope Problems**
   - Limited applicability
   - Missing important use cases
   - Overclaimed generality

#### Minor Issues (Should Fix - Doesn't Affect Acceptance Decision)

These issues are fixable and don't significantly impact the contribution:

1. **Writing Quality**
   - Typos and grammar errors
   - Awkward phrasing
   - Minor clarity issues

2. **Presentation Details**
   - Figure quality issues
   - Table formatting
   - Reference formatting
   - Minor notation inconsistencies

3. **Supplementary Material**
   - Missing appendix content
   - Incomplete hyperparameter details
   - Minor code documentation

## Weakness Report Template

```markdown
# Weakness Report: [Paper Title]
## Paper ID: [ID]

---

## Executive Summary

This report identifies [N] weaknesses in the paper, categorized by severity:
- **Fatal Flaws:** [N] issues that must be addressed
- **Major Issues:** [N] issues that should be addressed
- **Minor Issues:** [N] issues that would improve the paper

**Overall Assessment:** [1-2 sentences summarizing the weakness landscape]

---

## Fatal Flaws

### F1: [Title of Fatal Flaw]

**Category:** [Methodology / Experiments / Claims / Ethics]

**Location:** [Section, page, line numbers]

**Description:**
[Detailed description of the issue]

**Evidence:**
[Specific evidence supporting this assessment - quotes, equations, results]

**Impact:**
[How this flaw affects the paper's conclusions and validity]

**Recommendation:**
[Specific, actionable recommendation for fixing this issue]

---

### F2: [Title of Fatal Flaw]

[Same structure as above]

---

## Major Issues

### M1: [Title of Major Issue]

**Category:** [Evaluation / Analysis / Presentation / Scope]

**Location:** [Section, page, line numbers]

**Description:**
[Detailed description of the issue]

**Evidence:**
[Specific evidence]

**Impact:**
[How this issue weakens the paper]

**Recommendation:**
[Specific, actionable recommendation]

---

### M2: [Title of Major Issue]

[Same structure as above]

---

## Minor Issues

### m1: [Title of Minor Issue]

**Location:** [Section, page, line numbers]

**Description:** [Brief description]

**Recommendation:** [Brief recommendation]

---

### m2: [Title of Minor Issue]

[Same structure]

---

## Weakness Matrix

| Weakness | Category | Severity | Fixable? | Effort Required |
|----------|----------|----------|----------|-----------------|
| F1: [Title] | Methodology | Fatal | Maybe | High |
| F2: [Title] | Experiments | Fatal | Yes | Medium |
| M1: [Title] | Evaluation | Major | Yes | Medium |
| M2: [Title] | Presentation | Major | Yes | Low |
| m1: [Title] | Writing | Minor | Yes | Low |

---

## Recommendations Priority

### Must Address (for acceptance)
1. [Most critical issue]
2. [Second most critical issue]

### Should Address (significantly strengthens paper)
1. [Important improvement]
2. [Important improvement]

### Nice to Have (improves quality)
1. [Minor improvement]
2. [Minor improvement]

---

## Conclusion

[2-3 paragraphs summarizing the overall weakness landscape, what needs to change for the paper to be acceptable, and your confidence in the assessment.]
```

## Example Weakness Reports

### Good Example (ML Paper)

```markdown
# Weakness Report: Adaptive Gradient Methods for Non-Convex Optimization
## Paper ID: 5678

---

## Executive Summary

This report identifies 6 weaknesses in the paper, categorized by severity:
- **Fatal Flaws:** 1 issue that must be addressed
- **Major Issues:** 3 issues that should be addressed
- **Minor Issues:** 2 issues that would improve the paper

**Overall Assessment:** The paper has one critical experimental flaw (missing key baseline) and several issues with analysis and presentation. The core contribution is potentially solid but undermined by incomplete evaluation.

---

## Fatal Flaws

### F1: Missing Key Baseline Comparison

**Category:** Experiments

**Location:** Section 4 (Experiments), Tables 1-3

**Description:**
The paper proposes a new adaptive gradient method but does not compare with AdamW, which is the current standard for adaptive optimization in deep learning. The paper compares with Adam, SGD, and AdaGrad, but AdamW (which decouples weight decay) has been shown to significantly outperform Adam in most settings (Loshchilov & Hutter, 2019).

**Evidence:**
- Table 1 compares with Adam, SGD, AdaGrad but not AdamW
- The authors cite [Loshchilov & Hutter, 2019] in related work but don't compare
- Recent benchmarks (e.g., [citation]) show AdamW is the de facto standard

**Impact:**
Without comparison with AdamW, it's impossible to know if the proposed method actually improves over the current best adaptive method. The claimed improvements over Adam may not hold against AdamW.

**Recommendation:**
Add AdamW as a baseline in all experiments. Use the same hyperparameter tuning budget for AdamW as for the proposed method. If the proposed method still outperforms AdamW, the contribution is much stronger.

---

## Major Issues

### M1: Insufficient Ablation Study

**Category:** Evaluation

**Location:** Section 4.3 (Ablation Study)

**Description:**
The ablation study (Table 3) only ablates two components: the adaptive learning rate and the momentum term. The proposed method has three key components (adaptive learning rate, momentum, and gradient clipping), but gradient clipping is not ablated.

**Evidence:**
- Table 3 shows results for "w/o adaptive LR" and "w/o momentum"
- Missing: "w/o gradient clipping"
- Algorithm 1 shows three components but only two are ablated

**Impact:**
Without ablating gradient clipping, it's unclear which component contributes most to the improvement. The paper claims the adaptive learning rate is key (Section 4.3, line 15), but this isn't fully supported.

**Recommendation:**
Add "w/o gradient clipping" row to Table 3. Also consider ablating different clipping thresholds to understand sensitivity.

---

### M2: Missing Error Analysis

**Category:** Analysis

**Location:** Section 4 (Experiments)

**Description:**
The paper reports average performance but provides no error analysis. There's no discussion of:
- When does the method fail?
- What types of problems benefit most?
- Are there systematic failure modes?

**Evidence:**
- No failure case discussion
- No analysis of per-task/per-dataset performance variation
- No visualization of optimization trajectories

**Impact:**
Without error analysis, readers can't understand when to use this method vs. alternatives. The paper would be much stronger with analysis of when/why the method works.

**Recommendation:**
Add a section analyzing:
1. Cases where the method underperforms baselines
2. Problem characteristics that correlate with improvement
3. Visualization of optimization trajectories for representative cases

---

### M3: Overclaimed Generality

**Category:** Claims

**Location:** Abstract, Introduction, Conclusion

**Description:**
The paper claims the method "works for all non-convex optimization problems" (Abstract, line 8) but experiments are limited to:
- 2 synthetic functions
- ResNet-18 on CIFAR-10
- BERT fine-tuning on GLUE

**Evidence:**
- Abstract: "for all non-convex optimization problems"
- Experiments: only 3 settings tested
- Missing: GANs, reinforcement learning, scientific computing

**Impact:**
The claim is much stronger than the evidence supports. Readers may be misled about the method's applicability.

**Recommendation:**
Either:
1. Weaken the claim to "for deep learning optimization" and test on more DL settings
2. Add experiments on more diverse non-convex problems (GANs, RL, etc.)

---

## Minor Issues

### m1: Missing Standard Deviations

**Location:** Tables 1-3

**Description:** Results are reported without standard deviations or confidence intervals.

**Recommendation:** Add standard deviations from multiple runs (at least 3-5) to all result tables.

---

### m2: Figure Quality

**Location:** Figures 2, 4

**Description:** Figures are low resolution and difficult to read.

**Recommendation:** Provide high-resolution figures (at least 300 DPI) with clear labels.

---

## Weakness Matrix

| Weakness | Category | Severity | Fixable? | Effort Required |
|----------|----------|----------|----------|-----------------|
| F1: Missing AdamW | Experiments | Fatal | Yes | Medium |
| M1: Incomplete Ablation | Evaluation | Major | Yes | Low |
| M2: No Error Analysis | Analysis | Major | Yes | Medium |
| M3: Overclaimed Generality | Claims | Major | Yes | Low |
| m1: No Std Devs | Presentation | Minor | Yes | Low |
| m2: Figure Quality | Presentation | Minor | Yes | Low |

---

## Recommendations Priority

### Must Address (for acceptance)
1. Add AdamW baseline comparison (F1)
2. Complete ablation study (M1)

### Should Address (significantly strengthens paper)
1. Add error analysis section (M2)
2. Calibrate claims to match evidence (M3)

### Nice to Have (improves quality)
1. Add standard deviations to tables (m1)
2. Improve figure quality (m2)

---

## Conclusion

The paper has a potentially valuable contribution in the adaptive gradient method, but the evaluation is incomplete. The missing AdamW comparison is a critical gap that must be addressed - without it, the claimed improvements are not convincing. The incomplete ablation and missing error analysis also weaken the paper significantly.

If the authors address the fatal flaw (add AdamW comparison) and the major issues (complete ablation, add error analysis, calibrate claims), the paper could be suitable for acceptance. The core algorithmic contribution appears sound, but the experimental evaluation needs significant improvement.

My confidence in this assessment is high (4/5) as I am familiar with optimization methods and the baselines compared.
```

### Bad Example (What NOT to Do)

```markdown
# Weakness Report

## Problems
- Not enough experiments
- Writing is bad
- Novelty is limited

## Recommendation
Reject.
```

**Problems:**
- No categorization by severity
- No specific locations cited
- No evidence provided
- No actionable recommendations
- No weakness matrix
- Too vague to be useful

## Severity Matrix

### How to Assess Severity

| Criterion | Fatal | Major | Minor |
|-----------|-------|-------|-------|
| **Impact on conclusions** | Invalidates | Weakens | Doesn't affect |
| **Fixability in rebuttal** | Difficult/Impossible | Possible with effort | Easy |
| **Scope of issue** | Fundamental | Significant | Surface-level |
| **Reviewer reaction** | Rejection likely | Borderline | Unaffected |
| **Author response** | Must address experimentally | Should address | Can acknowledge |

### Common Fatal Flaws by Field

**Machine Learning:**
- Missing key baselines (especially SOTA)
- No comparison on standard benchmarks
- Theoretical errors in proofs
- Data contamination

**NLP:**
- No human evaluation for generation tasks
- Only BLEU reported (no other metrics)
- Cherry-picked examples
- Missing error analysis

**Computer Vision:**
- Cherry-picked visual results
- No ablation studies
- Unfair compute comparison
- Missing failure cases

**Systems:**
- Unrealistic assumptions
- Missing overhead analysis
- No real-world evaluation
- Incomplete comparison

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Categorizing everything as fatal**: Not everything is a deal-breaker
2. **Being too lenient**: Real problems should be called out
3. **Vagueness**: "Needs more work" without specifics
4. **Not citing evidence**: Claims without proof
5. **Missing the forest for trees**: Focusing on minor issues while missing major ones

### Author Mistakes (Understanding Reports)
1. **Defensiveness**: "The reviewer is wrong" - they might have a point
2. **Ignoring severity**: Not all issues are equal - prioritize
3. **Fixing symptoms**: Addressing surface issues while ignoring root causes
4. **Not responding**: Silence implies agreement

## 中文版本

### 使用场景

- 在投稿前发现论文中的问题
- 在同行评审期间进行彻底审查
- 识别会导致拒稿的致命缺陷
- 为作者创建弱点报告
- 培训审稿人发现常见问题
- 自审论文以尽早发现问题

### 弱点类别

弱点分为以下类别：

1. **方法论缺陷**
   - 不正确的假设
   - 推理中的逻辑空白
   - 理论基础不足
   - 不适合问题的方法论

2. **实验问题**
   - 缺失基线
   - 实验不足
   - 不合适的指标
   - 缺乏统计严谨性
   - 不公平的比较

3. **表述问题**
   - 写作不清晰
   - 缺失定义
   - 符号不一致
   - 图表质量差
   - 缺失或错误的引用

4. **范围局限性**
   - 适用性有限
   - 缺失重要案例
   - 过度泛化的声明
   - 覆盖不足

5. **可复现性问题**
   - 缺失实现细节
   - 代码/数据不可用
   - 超参数报告不足
   - 非确定性结果

6. **伦理问题**
   - 数据或模型中的偏见
   - 滥用可能性
   - 缺失伦理考量
   - 隐私问题

### 严重程度分类

#### 致命缺陷（必须修复 - 可能导致拒稿）

1. **技术错误**- 不正确的证明或推导、根本性方法论缺陷
2. **缺失核心实验**- 无明显基线比较、无标准基准评估
3. **不支持的声明**- 无实验支持的声明、从有限结果过度泛化
4. **伦理违规**- 剽窃、数据造假、缺失伦理审批

#### 重大问题（应该修复 - 可能弱拒/边界线）

1. **不完整评估**- 缺失部分重要基线、有限数据集覆盖
2. **弱分析**- 结果讨论肤浅、缺失失败案例分析
3. **表述问题**- 写作差、缺失或混乱的图表
4. **范围问题**- 适用性有限、缺失重要用例

#### 小问题（应该修复 - 不影响接受决定）

1. **写作质量**- 拼写和语法错误、表达尴尬
2. **表述细节**- 图表质量问题、表格格式、引用格式
3. **补充材料**- 缺失附录内容、超参数细节不完整
