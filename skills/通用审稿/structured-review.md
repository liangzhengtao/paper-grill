# Structured Review Framework

Universal structured review framework applicable to any academic paper. Provides rigorous methodology for evaluating research quality, novelty, and significance across all fields.

## When to Use

- Reviewing any academic paper with rigorous methodology
- Evaluating papers from conferences without specific style guides
- Training new reviewers on universal review principles
- Self-reviewing papers before submission to any venue
- Creating standardized review processes for research groups
- Calibrating review quality across different reviewers

## Review Framework

### Universal Review Structure

Every structured review must contain these sections:

1. **Executive Summary** (1 paragraph)
   - Restate the paper's main contributions
   - Identify the core approach and methodology
   - State the claimed results and significance
   - Provide your overall assessment

2. **Novelty Assessment**
   - Is the contribution new?
   - How does it differ from existing work?
   - What is the incremental vs. fundamental novelty?
   - Does it open new research directions?

3. **Significance Evaluation**
   - Does it address an important problem?
   - What is the potential impact?
   - Who will benefit from this work?
   - Does it advance the field?

4. **Clarity Assessment**
   - Is the paper well-written?
   - Is the methodology clearly described?
   - Are the results clearly presented?
   - Is the notation consistent?

5. **Technical Soundness**
   - Is the methodology correct?
   - Are the experiments well-designed?
   - Are the conclusions supported by evidence?
   - Are there any logical gaps?

6. **Experimental Evaluation**
   - Are experiments complete?
   - Are baselines appropriate?
   - Are metrics suitable?
   - Are results statistically significant?

7. **Related Work**
   - Is related work properly cited?
   - Is the paper fairly positioned against existing work?
   - Are any important references missing?

8. **Overall Assessment and Score**

### Scoring Rubric

#### Overall Quality Score (1-10)

| Score | Label | Description |
|-------|-------|-------------|
| 10 | Exceptional | Groundbreaking contribution, fundamentally advances the field |
| 9 | Excellent | Outstanding paper with minor issues only |
| 8 | Very Good | Strong contribution, clear accept |
| 7 | Good | Solid contribution with some concerns |
| 6 | Above Average | Decent contribution, leaning accept |
| 5 | Average | Borderline, could go either way |
| 4 | Below Average | Concerns outweigh contributions |
| 3 | Poor | Significant issues, leaning reject |
| 2 | Very Poor | Major flaws, clear reject |
| 1 | Unacceptable | Should not be published |

#### Component Scores (1-5 each)

| Component | 1 | 2 | 3 | 4 | 5 |
|-----------|---|---|---|---|---|
| Novelty | No new contribution | Incremental | Moderate | Significant | Groundbreaking |
| Significance | Trivial | Limited | Moderate | Important | Transformative |
| Clarity | Unreadable | Poorly written | Acceptable | Well written | Exceptional |
| Soundness | Flawed | Questionable | Adequate | Solid | Rigorous |
| Experiments | Missing | Insufficient | Adequate | Complete | Exhaustive |

### Confidence Scale

| Score | Description |
|-------|-------------|
| 5 | Expert: Deep expertise in this specific area |
| 4 | High: Familiar with the area and methodology |
| 3 | Medium: General familiarity, some expertise |
| 2 | Low: Limited familiarity with the area |
| 1 | None: Outside my area of expertise |

## Review Template

### Full Review Template

```markdown
# Review: [Paper Title]
## Paper ID: [ID]

---

## 1. Executive Summary

[Paper Title] proposes [method/approach] for [problem/task]. The key contribution is [describe main contribution]. The authors [describe methodology in 2-3 sentences]. Results on [datasets/evaluations] demonstrate [claimed improvements]. The paper claims [main claims about significance].

**Overall Assessment:** [1-2 sentences summarizing your recommendation]

---

## 2. Novelty Assessment

### Score: [1-5]

**What is novel:**
- [Specific novel contribution 1]
- [Specific novel contribution 2]

**Relation to existing work:**
- How it differs from [most similar prior work]: [explanation]
- Incremental vs. fundamental novelty: [assessment]

**Novelty justification:** [2-3 sentences explaining the novelty score]

---

## 3. Significance Evaluation

### Score: [1-5]

**Problem importance:**
- [Why this problem matters]
- [Who is affected by this problem]
- [Current state of solutions]

**Potential impact:**
- [Immediate impact on the field]
- [Long-term implications]
- [Broader impact beyond the specific area]

**Significance justification:** [2-3 sentences explaining the significance score]

---

## 4. Clarity Assessment

### Score: [1-5]

**Writing quality:**
- [Assessment of overall writing quality]
- [Specific strengths or weaknesses in presentation]

**Methodology description:**
- [Is the method clearly explained?]
- [Are algorithms/formulas clear?]

**Results presentation:**
- [Are figures and tables clear?]
- [Are results properly interpreted?]

**Notation and terminology:**
- [Is notation consistent?]
- [Are terms properly defined?]

**Specific clarity issues:**
- [List specific issues with page/line references]

---

## 5. Technical Soundness

### Score: [1-5]

**Methodology correctness:**
- [Is the approach technically correct?]
- [Are there any errors in reasoning?]

**Logical coherence:**
- [Do conclusions follow from results?]
- [Are there any logical gaps?]

**Assumptions:**
- [Are assumptions clearly stated?]
- [Are assumptions reasonable?]

**Limitations:**
- [Are limitations acknowledged?]
- [Do limitations affect conclusions?]

---

## 6. Experimental Evaluation

### Score: [1-5]

**Experiment design:**
- [Are experiments well-designed?]
- [Do experiments test the right things?]

**Baselines:**
- [Are baselines appropriate and recent?]
- [Is comparison fair (same data, compute)?]

**Metrics:**
- [Are metrics suitable for the task?]
- [Are multiple metrics reported?]

**Statistical validity:**
- [Are results averaged over multiple runs?]
- [Are error bars/confidence intervals provided?]
- [Are statistical significance tests performed?]

**Reproducibility:**
- [Is the method reproducible?]
- [Are hyperparameters reported?]
- [Is code available?]

**Missing experiments:**
- [What experiments are missing?]
- [Why do they matter?]

---

## 7. Related Work

### Assessment: [Satisfactory / Needs Improvement]

**Properly cited:**
- [Key related works that are properly discussed]

**Missing references:**
- [Important related works that should be cited]
- [Why they are relevant]

**Positioning:**
- [Is the paper fairly positioned against existing work?]
- [Are contributions clearly distinguished from prior work?]

---

## 8. Questions for Authors

1. [Specific technical question]
2. [Question about methodology or results]
3. [Question about applicability or limitations]
4. [Suggestion for additional experiments or analysis]

---

## 9. Detailed Comments

### Major Issues
1. [Issue 1 with specific reference]
2. [Issue 2 with specific reference]

### Minor Issues
1. [Minor issue 1]
2. [Minor issue 2]

### Suggestions for Improvement
1. [Suggestion 1]
2. [Suggestion 2]

---

## 10. Overall Assessment

### Component Scores
- Novelty: [1-5]
- Significance: [1-5]
- Clarity: [1-5]
- Soundness: [1-5]
- Experiments: [1-5]

### Overall Score: [1-10]

### Confidence: [1-5]

### Recommendation: [Accept / Weak Accept / Borderline / Weak Reject / Reject]

### Final Comments
[2-3 paragraphs with detailed justification for your recommendation. Reference specific strengths and weaknesses. State what would change your mind.]
```

### Quick Review Template (1 Paragraph)

```markdown
**Paper:** [Title]
**Summary:** [1-2 sentences on what the paper does]
**Strengths:** [1-2 key strengths]
**Weaknesses:** [1-2 key weaknesses]
**Score:** [1-10] ([Label])
**Recommendation:** [Accept/Reject with brief justification]
```

## Example Reviews

### Good Example (Full Review, Score: 7)

```markdown
# Review: Efficient Graph Neural Networks via Adaptive Sparsification
## Paper ID: 1234

---

## 1. Executive Summary

"Efficient Graph Neural Networks via Adaptive Sparsification" proposes a method to reduce computational cost of graph neural networks by adaptively sparsifying the adjacency matrix during message passing. The key insight is that not all edges contribute equally to node representations, and the authors learn a sparsification policy using a lightweight gating network. Experiments on ogbn-arxiv, ogbn-products, and Reddit show 2-4x speedup with less than 1% accuracy loss.

**Overall Assessment:** This is a solid practical contribution that addresses an important scalability problem. The method is well-motivated and the experiments are complete, though the theoretical analysis could be stronger.

---

## 2. Novelty Assessment

### Score: 3

**What is novel:**
- Adaptive edge-level sparsification learned end-to-end with the GNN
- Lightweight gating network that adds minimal overhead
- Theoretical analysis of information loss from sparsification

**Relation to existing work:**
- Differs from [GraphSAGE] which samples neighbors randomly: this method learns which edges to keep
- Differs from [Cluster-GCN] which partitions graphs: this method operates at edge level
- Incremental rather than fundamental novelty: builds on existing ideas of attention and gating

**Novelty justification:** The contribution is incremental but practical. The core idea of learning which edges to keep is not entirely new, but the specific implementation is well-designed.

---

## 3. Significance Evaluation

### Score: 4

**Problem importance:**
- Scalability of GNNs is a major bottleneck for real-world applications
- Many important graphs (social networks, knowledge graphs) are too large for standard GNNs
- Current solutions sacrifice too much accuracy or require complex engineering

**Potential impact:**
- Immediate: enables GNN deployment on larger graphs
- Long-term: may inspire more efficient GNN architectures
- Broader: benefits any application using GNNs (recommendations, drug discovery)

**Significance justification:** The scalability problem is important and the solution is practical. The impact is limited to GNN efficiency rather than opening new research directions.

---

## 4. Clarity Assessment

### Score: 4

**Writing quality:**
- Well-written with clear motivation and presentation
- Good use of figures to illustrate the method (Figures 2, 3)
- Algorithm pseudocode is clear and well-commented

**Methodology description:**
- The gating network (Section 3.2) is clearly explained
- The training procedure (Section 3.3) could be more detailed
- Loss function components are well-motivated

**Results presentation:**
- Tables are clear with proper baselines
- Figures show meaningful ablation results
- Speedup numbers are presented fairly

**Notation and terminology:**
- Consistent notation throughout
- All symbols are defined before use

**Specific clarity issues:**
- Page 4, Line 12: "the network learns" - specify which network
- Table 2: Missing standard deviations for accuracy

---

## 5. Technical Soundness

### Score: 4

**Methodology correctness:**
- The sparsification approach is technically sound
- The gating network design is appropriate
- The training procedure is correct

**Logical coherence:**
- Claims are supported by experiments
- Conclusions follow from results

**Assumptions:**
- Assumes graph structure is informative (valid for most applications)
- Assumes edge importance can be learned (validated empirically)

**Limitations:**
- Limited to transductive settings (acknowledged)
- May not work well for very sparse graphs (not discussed)

---

## 6. Experimental Evaluation

### Score: 4

**Experiment design:**
- Well-designed experiments on standard benchmarks
- Tests both accuracy and efficiency

**Baselines:**
- Appropriate baselines: GraphSAGE, Cluster-GCN, GraphSAINT
- Recent methods included (2022-2023)

**Metrics:**
- Accuracy, speedup, memory usage
- Missing: convergence speed, robustness analysis

**Statistical validity:**
- Results averaged over 5 runs
- Error bars provided in main table
- Statistical significance not explicitly tested

**Reproducibility:**
- Code available on GitHub
- Hyperparameters detailed in Appendix A
- Hardware specifications provided

**Missing experiments:**
- Missing: comparison with [recent efficient GNN method]
- Missing: analysis on graphs with different characteristics (density, degree distribution)

---

## 7. Related Work

### Assessment: Satisfactory

**Properly cited:**
- GraphSAGE, Cluster-GCN, GraphSAINT properly discussed
- Attention mechanisms in GNNs well covered

**Missing references:**
- [Recent paper on graph sparsification] should be discussed
- [Paper on learned graph structures] is relevant

**Positioning:**
- Well-positioned against sampling-based methods
- Could better distinguish from attention-based methods

---

## 8. Questions for Authors

1. How does the method perform on graphs with very heterogeneous degree distributions (e.g., power-law graphs)? The current benchmarks are relatively homogeneous.
2. The gating network adds ~5% parameters. Have you tried simpler sparsification methods (e.g., top-k on edge weights) to justify this complexity?
3. What happens when the sparsification ratio is very aggressive (>90% edges removed)? Is there a graceful degradation?
4. Have you considered applying this to heterogeneous graphs or dynamic graphs?

---

## 9. Detailed Comments

### Major Issues
1. Table 2: Missing comparison with [important baseline]
2. Section 4.3: The convergence analysis assumes convexity but GNN training is non-convex

### Minor Issues
1. Page 3, Line 8: "GNN" should be defined on first use
2. Figure 4: Legend is too small
3. Appendix B: Reference to "Equation 12" should be "Equation 11"

### Suggestions for Improvement
1. Add analysis of how sparsification affects different graph properties
2. Include convergence speed comparison
3. Discuss limitations more thoroughly in the main text

---

## 10. Overall Assessment

### Component Scores
- Novelty: 3/5
- Significance: 4/5
- Clarity: 4/5
- Soundness: 4/5
- Experiments: 4/5

### Overall Score: 7

### Confidence: 4

### Recommendation: Weak Accept

### Final Comments

This paper makes a solid practical contribution to GNN efficiency. The method is well-designed, clearly presented, and thoroughly evaluated. The main weakness is limited novelty - the core idea builds on existing work in attention and gating. However, the practical impact is significant and the experiments are convincing.

I recommend weak accept with the following conditions:
1. Add the missing baseline comparison
2. Discuss limitations more thoroughly
3. Address the convergence analysis concern

If these are addressed, I would be willing to increase my score.
```

### Bad Example (What NOT to Do)

```markdown
## Summary

Paper makes GNNs faster. Not very interesting.

## Weaknesses
- Not novel enough
- Experiments are okay
- Writing is okay

## Score: 4

Reject.
```

**Problems:**
- No structured assessment
- "Not novel enough" without justification
- Missing novelty, significance, clarity, soundness scores
- No questions for authors
- No detailed comments
- Score not justified

## Calibration Guide

### How to Calibrate Your Reviews

1. **Read accepted papers**: Understand what quality level gets accepted
2. **Compare with other reviews**: Read reviews of the same paper
3. **Use the rubric**: Don't just give a gut feeling score
4. **Be consistent**: Apply the same standards to all papers
5. **Justify every score**: If you can't explain it, reconsider

### Common Scoring Errors

1. **Central tendency**: Avoiding extreme scores (all 5s and 6s)
2. **Halo effect**: Letting one strong aspect inflate all scores
3. **Confirmation bias**: Looking for evidence to support initial impression
4. **Anchoring**: Being influenced by other reviewers' scores
5. **Leniency/severity**: Consistently scoring too high or too low

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Being too brief**: A 3-sentence review helps no one
2. **Being too long**: A 10-page review is overwhelming
3. **Missing the point**: Focusing on minor issues while missing major contributions
4. **Personal bias**: Rejecting work that contradicts your own
5. **Not reading carefully**: Skimming and missing key contributions

### Author Mistakes (Understanding Reviews)
1. **Ignoring structure**: Reviews follow a structure for a reason
2. **Defensive responses**: "The reviewer is wrong" rarely helps
3. **Not addressing all points**: Cherry-picking easy questions
4. **Vague rebuttals**: "We will add experiments" without specifics

## 中文版本

### 使用场景

- 使用严格方法论审稿任何学术论文
- 评估没有特定风格指南的会议论文
- 培训新审稿人掌握通用审稿原则
- 在投稿前对自己的论文进行自审
- 为研究小组创建标准化审稿流程
- 校准不同审稿人之间的审稿质量

### 通用审稿结构

每篇结构化审稿必须包含以下部分：

1. **执行摘要**（1段）- 重新表述论文的主要贡献、核心方法和方法论、声称的结果和意义
2. **新颖性评估**（1-5分）- 贡献是否新颖、与现有工作有何不同、增量新颖性 vs 根本性新颖性
3. **重要性评估**（1-5分）- 是否解决重要问题、潜在影响、谁将受益
4. **清晰度评估**（1-5分）- 写作质量、方法论描述、结果呈现、符号一致性
5. **技术可靠性**（1-5分）- 方法论是否正确、实验设计是否合理、结论是否有证据支持
6. **实验评估**（1-5分）- 实验是否全面、基线是否适当、指标是否合适
7. **相关工作**- 相关工作是否正确引用、与现有工作的定位
8. **总体评估和评分**

### 评分标准

| 分数 | 标签 | 说明 |
|------|------|------|
| 10 | 杰出 | 开创性贡献，从根本上推进领域发展 |
| 9 | 优秀 | 杰出论文，仅有小问题 |
| 8 | 很好 | 强贡献，明确接受 |
| 7 | 好 | 扎实贡献，有一些顾虑 |
| 6 | 中等偏上 | 不错贡献，倾向于接受 |
| 5 | 平均 | 边界线，可接受可拒绝 |
| 4 | 中等偏下 | 顾虑大于贡献 |
| 3 | 差 | 重大问题，倾向于拒绝 |
| 2 | 很差 | 主要缺陷，明确拒绝 |
| 1 | 不可接受 | 不应发表 |

### 组件评分（每项1-5分）

| 组件 | 1 | 2 | 3 | 4 | 5 |
|------|---|---|---|---|---|
| 新颖性 | 无新贡献 | 增量性 | 中等 | 显著 | 开创性 |
| 重要性 | 微不足道 | 有限 | 中等 | 重要 | 变革性 |
| 清晰度 | 难以阅读 | 写作差 | 可接受 | 写作好 | 杰出 |
| 可靠性 | 有缺陷 | 有疑问 | 充足 | 扎实 | 严谨 |
| 实验 | 缺失 | 不足 | 充足 | 全面 | 详尽 |
