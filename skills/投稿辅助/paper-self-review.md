# Paper Self-Review

Review your own paper before submission to catch problems early. This skill provides a systematic checklist, quality gates, and simulation techniques to see your paper through a reviewer's eyes.

## When to Use

- Reviewing your own paper before submitting to a conference
- Conducting a final quality check before the deadline
- Simulating the reviewer perspective on your work
- Identifying fatal flaws before submission
- Ensuring your paper meets the venue's standards
- Preparing for potential reviewer questions and concerns

## Review Framework

### Self-Review Process

#### Phase 1: Fresh Eyes (1-2 days before deadline)

Take a break from the paper, then review as if seeing it for the first time:

1. **Read the abstract only** - Does it clearly state the contribution?
2. **Read the introduction** - Is the problem well-motivated?
3. **Scan figures and tables** - Are they clear and informative?
4. **Read the conclusion** - Does it match the abstract?
5. **Check the references** - Are they complete and relevant?

#### Phase 2: Deep Review (Day before deadline)

Conduct a thorough technical review:

1. **Technical soundness** - Is the methodology correct?
2. **Experimental evaluation** - Are experiments comprehensive?
3. **Claims validation** - Are claims supported by evidence?
4. **Presentation quality** - Is the paper well-written?
5. **Reproducibility** - Can someone replicate this work?

#### Phase 3: Reviewer Simulation (Day of deadline)

Simulate the reviewer perspective:

1. **Identify weaknesses** - What will reviewers criticize?
2. **Prepare for questions** - What will reviewers ask?
3. **Check for fatal flaws** - Are there deal-breakers?
4. **Assess novelty** - Is the contribution clear?
5. **Evaluate significance** - Does it matter?

### Self-Review Checklist

#### Abstract

- [ ] States the problem clearly
- [ ] Describes the approach concisely
- [ ] Mentions key results/claims
- [ ] Fits within word limit
- [ ] Doesn't oversell the contribution
- [ ] Matches the paper content

#### Introduction

- [ ] Motivates the problem well
- [ ] States the research gap clearly
- [ ] Lists specific contributions
- [ ] Provides paper organization
- [ ] Cites relevant context
- [ ] Doesn't overclaim novelty

#### Related Work

- [ ] Covers key related papers
- [ ] Positions the work clearly
- [ ] Doesn't miss obvious references
- [ ] Fairly represents prior work
- [ ] Highlights differences from this work

#### Methodology

- [ ] Clearly describes the approach
- [ ] Defines all notation
- [ ] Provides algorithms/formulas
- [ ] Justifies design choices
- [ ] States assumptions clearly
- [ ] Discusses limitations

#### Experiments

- [ ] Uses standard benchmarks
- [ ] Compares with appropriate baselines
- [ ] Reports multiple metrics
- [ ] Includes ablation studies
- [ ] Provides statistical significance
- [ ] Shows error bars/confidence intervals
- [ ] Discusses failure cases

#### Results

- [ ] Results support the claims
- [ ] Tables and figures are clear
- [ ] Improvements are contextualized
- [ ] No cherry-picking of results
- [ ] Fair comparison with baselines

#### Discussion/Conclusion

- [ ] Summarizes contributions
- [ ] Discusses limitations honestly
- [ ] Suggests future work
- [ ] Doesn't overclaim
- [ ] Matches abstract/introduction

#### Presentation

- [ ] No typos or grammar errors
- [ ] Consistent notation
- [ ] Clear figures and tables
- [ ] Proper references
- [ ] Within page limit
- [ ] Follows formatting guidelines

### Common Fatal Flaws

Check for these deal-breakers:

#### 1. Missing Key Baseline

**Problem:** Not comparing with an obvious baseline method

**Check:** List all methods that have published results on your benchmarks. Are any missing?

**Fix:** Add the comparison. If you can't, explain why (e.g., code not available, different setting).

#### 2. Overclaimed Contributions

**Problem:** Claims that aren't supported by experiments

**Check:** For each claim in the abstract/introduction, find the supporting evidence. Is any claim unsupported?

**Fix:** Weaken unsupported claims or add supporting experiments.

#### 3. Theoretical Errors

**Problem:** Errors in proofs or derivations

**Check:** Have someone else verify your math. Check assumptions, derivations, conclusions.

**Fix:** Correct errors. If major, consider whether the contribution still holds.

#### 4. Data Contamination

**Problem:** Test data used in training

**Check:** Verify data splits. Check for data leakage. Ensure no overlap between train/test.

**Fix:** Re-split data and re-run experiments if contaminated.

#### 5. Incomplete Evaluation

**Problem:** Missing important experiments

**Check:** Does your evaluation include:
- Standard benchmarks?
- Multiple metrics?
- Ablation studies?
- Statistical significance?

**Fix:** Add missing experiments before submission.

#### 6. Unfair Comparison

**Problem:** Comparing under unequal conditions

**Check:** Are baselines given:
- Same data?
- Same compute budget?
- Same hyperparameter tuning?

**Fix:** Ensure fair comparison conditions.

### Scoring Rubric for Self-Review

#### Overall Quality Score (1-10)

| Score | Readiness | Action |
|-------|-----------|--------|
| 9-10 | Ready | Submit with confidence |
| 7-8 | Nearly Ready | Minor revisions needed |
| 5-6 | Needs Work | Significant revisions needed |
| 3-4 | Major Issues | Substantial rewrite needed |
| 1-2 | Not Ready | Fundamental problems |

#### Component Scores (1-5)

| Component | 1 | 3 | 5 |
|-----------|---|---|---|
| Novelty | Incremental | Moderate | Significant |
| Soundness | Flawed | Adequate | Rigorous |
| Experiments | Insufficient | Adequate | Comprehensive |
| Clarity | Poor | Acceptable | Excellent |
| Significance | Limited | Moderate | Important |

### Quality Gates

Before submission, verify these gates:

#### Gate 1: Contribution Clear?

- [ ] Can you state the contribution in one sentence?
- [ ] Is this contribution novel?
- [ ] Is this contribution significant?
- [ ] Is this contribution supported by evidence?

#### Gate 2: Evaluation Complete?

- [ ] Standard benchmarks used?
- [ ] Appropriate baselines compared?
- [ ] Ablation studies included?
- [ ] Statistical significance tested?
- [ ] Error bars provided?

#### Gate 3: Presentation Ready?

- [ ] No typos/grammar errors?
- [ ] Figures clear and informative?
- [ ] Notation consistent?
- [ ] References complete?
- [ ] Within page limit?

#### Gate 4: Reproducibility Ensured?

- [ ] Code available (or promised)?
- [ ] Hyperparameters reported?
- [ ] Data splits described?
- [ ] Random seeds specified?
- [ ] Hardware requirements noted?

#### Gate 5: Reviewer Preparedness?

- [ ] Weaknesses identified?
- [ ] Questions anticipated?
- [ ] Rebuttal points prepared?
- [ ] Backup experiments ready?

## Review Template

### Self-Review Scorecard

```markdown
# Self-Review Scorecard: [Paper Title]
## Target Venue: [Conference Name]
## Date: [Date]

---

## Component Assessment

### 1. Novelty (1-5)

**Score:** [ ]

**Self-Assessment:**
- What is novel about this work?
- How does it differ from existing work?
- Is the novelty incremental or fundamental?

**Evidence:**
- [Specific novel contribution 1]
- [Specific novel contribution 2]

**Reviewer Concerns:**
- What might reviewers say about novelty?
- How would you respond?

---

### 2. Soundness (1-5)

**Score:** [ ]

**Self-Assessment:**
- Is the methodology correct?
- Are there any technical errors?
- Are assumptions reasonable?

**Evidence:**
- [Proofs verified by: name/date]
- [Experiments validated: description]

**Reviewer Concerns:**
- What technical issues might reviewers raise?
- How would you respond?

---

### 3. Experiments (1-5)

**Score:** [ ]

**Self-Assessment:**
- Are experiments comprehensive?
- Are baselines appropriate?
- Are metrics suitable?

**Evidence:**
- Benchmarks: [list]
- Baselines: [list]
- Metrics: [list]

**Reviewer Concerns:**
- What experiments might reviewers request?
- Can you add them before the deadline?

---

### 4. Clarity (1-5)

**Score:** [ ]

**Self-Assessment:**
- Is the paper well-written?
- Are figures and tables clear?
- Is notation consistent?

**Evidence:**
- Proofread by: [name/date]
- Figures reviewed by: [name/date]

**Reviewer Concerns:**
- What might be unclear to reviewers?
- How would you clarify?

---

### 5. Significance (1-5)

**Score:** [ ]

**Self-Assessment:**
- Does this work matter?
- Who will benefit?
- What is the potential impact?

**Evidence:**
- [Application/use case 1]
- [Application/use case 2]

**Reviewer Concerns:**
- How might reviewers question significance?
- How would you respond?

---

## Overall Assessment

**Total Score:** [Sum of component scores] / 25

**Readiness Level:** [Ready / Nearly Ready / Needs Work / Major Issues / Not Ready]

**Critical Issues to Fix:**
1. [Issue 1]
2. [Issue 2]

**Minor Issues to Fix:**
1. [Issue 1]
2. [Issue 2]

---

## Reviewer Simulation

### Anticipated Questions

1. [Question 1 from potential reviewer]
2. [Question 2 from potential reviewer]
3. [Question 3 from potential reviewer]

### Anticipated Weaknesses

1. [Weakness 1 that reviewers might raise]
2. [Weakness 2 that reviewers might raise]
3. [Weakness 3 that reviewers might raise]

### Prepared Responses

1. [Response to anticipated weakness 1]
2. [Response to anticipated weakness 2]
3. [Response to anticipated weakness 3]

---

## Pre-Submission Checklist

### Technical Quality
- [ ] All proofs verified
- [ ] All experiments run
- [ ] All results validated
- [ ] No data contamination
- [ ] Fair comparisons

### Presentation Quality
- [ ] Paper proofread
- [ ] Figures high-quality
- [ ] Tables formatted
- [ ] References complete
- [ ] Notation consistent

### Submission Requirements
- [ ] Within page limit
- [ ] Proper formatting
- [ ] Supplementary material ready
- [ ] Code/data available
- [ ] Author information correct

### Final Checks
- [ ] Abstract matches paper
- [ ] Introduction matches contributions
- [ ] Experiments support claims
- [ ] Conclusion is honest
- [ ] No overselling

---

## Decision

**Recommendation:** [ ] Submit [ ] Revise [ ] Delay

**Reasoning:**
[2-3 sentences explaining your recommendation]

**If revising, priority items:**
1. [Most critical revision]
2. [Second most critical revision]

**If delaying, reason:**
[Explanation of why the paper isn't ready]
```

## Example Self-Reviews

### Good Example (ML Paper, Ready for Submission)

```markdown
# Self-Review Scorecard: Efficient Attention via Sparse Gating
## Target Venue: NeurIPS 2024
## Date: 2024-05-20

---

## Component Assessment

### 1. Novelty (4/5)

**Self-Assessment:**
The key novelty is learning input-dependent sparsity patterns through a lightweight gating network. This differs from fixed sparsity patterns (Sparse Transformer) and random sparsity (Routing Transformer).

**Evidence:**
- Novel gating mechanism (Section 3.1, Equation 5)
- Theoretical analysis of expressiveness (Theorem 1)
- Connection to information theory (Section 3.3)

**Reviewer Concerns:**
- Reviewers may say this is incremental over attention mechanisms
- Response: The specific gating approach is novel and we provide theoretical grounding

---

### 2. Soundness (4/5)

**Self-Assessment:**
The methodology is correct. Proofs have been verified by [co-author name]. Assumptions are standard in the literature.

**Evidence:**
- Proofs verified by: [co-author], May 15, 2024
- Assumptions match [reference 1, 2]

**Reviewer Concerns:**
- Assumption 2 (bounded variance) may be questioned
- Response: We discuss this limitation and show empirical validation

---

### 3. Experiments (4/5)

**Self-Assessment:**
Comprehensive evaluation on 3 benchmarks with 5 baselines. Includes ablation studies and statistical significance.

**Evidence:**
- Benchmarks: ImageNet, COCO, GLUE
- Baselines: Full attention, Linformer, Performer, Routing Transformer, BigBird
- Metrics: Accuracy, FLOPs, memory, speed
- Ablation: Table 3 ablates all components

**Reviewer Concerns:**
- May request comparison with FlashAttention
- Response: Can add if requested; preliminary results show our method is orthogonal

---

### 4. Clarity (4/5)

**Self-Assessment:**
Well-written with clear figures. Proofread by [name]. Figures reviewed by [name].

**Evidence:**
- Proofread by: [colleague], May 18, 2024
- Figures reviewed by: [colleague], May 19, 2024

**Reviewer Concerns:**
- Section 3.2 could be clearer
- Response: Revised for clarity on May 19

---

### 5. Significance (4/5)

**Self-Assessment:**
Addresses an important problem (transformer efficiency). Has practical applications for deployment.

**Evidence:**
- Deployed in [production system]
- Used by [company/research group]

**Reviewer Concerns:**
- May question if improvement is significant enough
- Response: 2-3x speedup with <1% accuracy loss is significant

---

## Overall Assessment

**Total Score:** 20/25

**Readiness Level:** Ready

**Critical Issues to Fix:**
1. None - paper is ready

**Minor Issues to Fix:**
1. Final proofread for typos
2. Verify all references are correct

---

## Reviewer Simulation

### Anticipated Questions

1. How does this compare with FlashAttention?
2. What happens with very long sequences (>8k tokens)?
3. Is the gating network actually learning meaningful patterns?

### Anticipated Weaknesses

1. Missing FlashAttention comparison
2. Limited to 2048 tokens in experiments
3. Ablation shows gating adds modest improvement

### Prepared Responses

1. FlashAttention is orthogonal (memory efficiency) while ours is about compute efficiency. Preliminary comparison shows they can be combined.
2. We acknowledge this limitation and provide complexity analysis showing O(n log n) should hold.
3. The gating contribution is clearer in the theoretical analysis; empirical improvement is modest but consistent.

---

## Decision

**Recommendation:** [✓] Submit [ ] Revise [ ] Delay

**Reasoning:**
The paper is ready for submission. The contribution is clear, experiments are comprehensive, and the presentation is polished. Minor issues can be fixed before the final version.
```

### Bad Example (What NOT to Do)

```markdown
# Self-Review

## Score: 10/10

Everything looks great. No issues. Ready to submit.

## Weaknesses: None
```

**Problems:**
- No honest self-assessment
- Perfect score is unrealistic
- No weaknesses identified (every paper has some)
- No component scores
- No reviewer simulation
- No checklist

### Better Version

```markdown
# Self-Review

## Score: 7/10

### Strengths:
- Novel contribution
- Comprehensive experiments
- Clear writing

### Weaknesses:
- Missing comparison with [method]
- Limited to 2 datasets
- Some figures could be clearer

### To Fix Before Submission:
1. Add [method] comparison
2. Add 1 more dataset if time permits
3. Improve Figure 3 quality
```

## Common Mistakes to Avoid

### Self-Review Mistakes

1. **Overconfidence**: "This paper is perfect" - no paper is
2. **Not taking a break**: Reviewing immediately after writing
3. **Not simulating reviewers**: Missing obvious criticisms
4. **Skipping the checklist**: Rushing through quality gates
5. **Not getting feedback**: Self-reviewing without external input

### Pre-Submission Mistakes

1. **Last-minute rush**: Not leaving time for self-review
2. **Ignoring weaknesses**: Hoping reviewers won't notice
3. **Overclaiming**: Overselling the contribution
4. **Incomplete experiments**: Submitting with missing baselines
5. **Poor presentation**: Typos, unclear figures, bad notation

## 中文版本

### 使用场景

- 在投稿前自审论文
- 在截稿前进行最终质量检查
- 模拟审稿人视角审视你的工作
- 在投稿前识别致命缺陷
- 确保论文符合会议标准
- 为潜在审稿人问题和关注点做准备

### 自审流程

#### 阶段1：新鲜眼光（截稿前1-2天）

休息一下，然后像第一次看到一样审阅：

1. **只读摘要** - 是否清楚说明了贡献？
2. **读引言** - 问题是否有良好动机？
3. **扫描图表** - 是否清晰且信息丰富？
4. **读结论** - 是否与摘要匹配？
5. **检查引用** - 是否完整且相关？

#### 阶段2：深度审阅（截稿前一天）

进行彻底的技术审查：

1. **技术可靠性** - 方法论是否正确？
2. **实验评估** - 实验是否全面？
3. **声明验证** - 声明是否有证据支持？
4. **表述质量** - 论文是否写得好？
5. **可复现性** - 别人能否复制这项工作？

#### 阶段3：审稿人模拟（截稿当天）

模拟审稿人视角：

1. **识别弱点** - 审稿人会批评什么？
2. **准备问题** - 审稿人会问什么？
3. **检查致命缺陷** - 是否有deal-breaker？
4. **评估新颖性** - 贡献是否清晰？
5. **评估重要性** - 是否重要？

### 常见致命缺陷

#### 1. 缺失关键基线
**问题**：未与明显基线方法比较
**检查**：列出所有在你的基准上发表结果的方法。是否有缺失？
**修复**：添加比较。如果不能，解释原因。

#### 2. 过度声称贡献
**问题**：无实验支持的声明
**检查**：对于摘要/引言中的每个声明，找到支持证据。是否有声明无支持？
**修复**：削弱无支持的声明或添加支持实验。

#### 3. 理论错误
**问题**：证明或推导中的错误
**检查**：让别人验证你的数学。检查假设、推导、结论。
**修复**：纠正错误。如果重大，考虑贡献是否仍然成立。

#### 4. 数据污染
**问题**：测试数据用于训练
**检查**：验证数据分割。检查数据泄露。确保训练/测试无重叠。
**修复**：如果污染，重新分割数据并重新运行实验。

#### 5. 不完整评估
**问题**：缺失重要实验
**检查**：你的评估是否包括标准基准、多指标、消融研究、统计显著性？
**修复**：在投稿前添加缺失实验。

#### 6. 不公平比较
**问题**：在不平等条件下比较
**检查**：基线是否获得相同数据、相同计算预算、相同超参数调优？
**修复**：确保公平比较条件。

### 评分标准

| 分数 | 准备状态 | 行动 |
|------|----------|------|
| 9-10 | 准备好 | 自信提交 |
| 7-8 | 接近准备好 | 需要小修改 |
| 5-6 | 需要工作 | 需要显著修改 |
| 3-4 | 重大问题 | 需要大量重写 |
| 1-2 | 未准备好 | 根本性问题 |
