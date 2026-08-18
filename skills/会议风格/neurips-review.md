# NeurIPS Review Style

Mimic the review style and standards of the Conference on Neural Information Processing Systems (NeurIPS). Generate rigorous, structured reviews that follow NeurIPS reviewer guidelines.

## When to Use

- Reviewing machine learning and AI papers targeting NeurIPS submission
- Evaluating papers in deep learning, optimization, reinforcement learning, probabilistic methods
- Preparing rebuttals for NeurIPS reviewer feedback
- Self-reviewing papers before NeurIPS submission deadline
- Training new reviewers on NeurIPS review standards

## Review Framework

### NeurIPS Review Structure

Every NeurIPS review must contain these sections in order:

1. **Summary** (1 paragraph)
   - Restate the paper's main contributions in your own words
   - Identify the core technical approach
   - State the claimed results/improvements
   - Show the authors you understood their work

2. **Strengths** (3-5 bullet points)
   - Novelty of the approach
   - Technical soundness
   - Quality of experimental evaluation
   - Clarity of presentation
   - Potential impact on the field

3. **Weaknesses** (3-5 bullet points)
   - Technical flaws or gaps
   - Missing experiments or baselines
   - Unclear claims or overstatements
   - Reproducibility concerns
   - Limited scope or generalizability

4. **Questions for Authors** (2-4 questions)
   - Specific technical questions
   - Requests for clarification
   - Suggestions for additional experiments
   - Questions about scalability or applicability

5. **Limitations** (1 paragraph)
   - Discuss limitations the authors may have overlooked
   - Ethical considerations if applicable
   - Potential negative societal impacts
   - Scope restrictions

6. **Rating** (1-10 scale)
7. **Confidence** (1-5 scale)
8. **Overall Assessment** (final paragraph)

### NeurIPS Scoring Rubric

| Score | Label | Description |
|-------|-------|-------------|
| 10 | Award quality | Groundbreaking contribution, fundamentally advances the field |
| 9 | Strong accept | Excellent paper with minor issues, clear accept |
| 8 | Accept | Solid contribution, above the acceptance threshold |
| 7 | Weak accept | Decent paper with some concerns, leaning toward accept |
| 6 | Borderline | Mixed signals, could go either way |
| 5 | Weak reject | Below threshold, concerns outweigh contributions |
| 4 | Reject | Significant issues, clear reject |
| 3 | Strong reject | Major flaws, fundamental problems |
| 2 | Very strong reject | Seriously flawed, unfixable issues |
| 1 | Reject | Should not be published, potentially harmful |

### Confidence Scale

| Score | Description |
|-------|-------------|
| 5 | Expert: Very familiar with the specific area, read the related work carefully |
| 4 | High: Familiar with the area, have done related work |
| 3 | Medium: Somewhat familiar, read some of the related work |
| 2 | Low: Not very familiar, general understanding only |
| 1 | None: Completely outside my area of expertise |

## Review Template

```markdown
## Summary

[Paper ID: XXXX]

This paper proposes [method/approach] for [problem/task]. The key idea is [brief description of the core technical contribution]. The authors [describe methodology in 2-3 sentences]. Experiments on [datasets/benchmarks] demonstrate [claimed improvements]. The paper claims [main claims].

## Strengths

- **S1:** [Novelty] [Specific description of what is novel and why it matters]
- **S2:** [Technical soundness] [Description of why the approach is technically sound]
- **S3:** [Experiments] [Specific strengths of the experimental evaluation]
- **S4:** [Clarity] [What aspects are well-written and clear]
- **S5:** [Impact] [Potential significance for the field]

## Weaknesses

- **W1:** [Technical concern] [Specific description of the issue and its impact]
- **W2:** [Missing experiments] [What experiments are missing and why they matter]
- **W3:** [Clarity issues] [Specific parts that are unclear or confusing]
- **W4:** [Overclaims] [Where the paper claims more than it delivers]
- **W5:** [Reproducibility] [What information is missing for reproduction]

## Questions for Authors

1. [Specific technical question about the method]
2. [Question about experimental setup or results]
3. [Question about applicability or limitations]
4. [Question about related work or positioning]

## Limitations

[Discuss limitations the authors should address, including potential ethical concerns, scalability issues, or scope restrictions. Be specific about what the paper does NOT cover and why that matters.]

## Rating: [1-10]

[1-2 sentence justification for the score]

## Confidence: [1-5]

[1 sentence explaining your confidence level]

## Overall Assessment

[Final paragraph summarizing your recommendation. State clearly whether you recommend acceptance or rejection. Reference your key strengths and weaknesses. If borderline, say what changes would change your mind.]
```

## Example Reviews

### Good Example (Score: 7, Weak Accept)

```markdown
## Summary

This paper proposes a novel attention mechanism called "Sparse Dynamic Attention" (SDA) for efficient transformer architectures. The key idea is to learn input-dependent sparsity patterns in the attention matrix using a lightweight gating network. The authors provide theoretical analysis showing that SDA maintains the expressiveness of full attention while reducing computational complexity from O(n²) to O(n log n). Experiments on ImageNet classification, COCO object detection, and language modeling demonstrate competitive or superior performance compared to existing efficient attention methods with 2-3x speedup.

## Strengths

- **S1:** The proposed gating mechanism for learning sparsity patterns is elegant and well-motivated. The connection to information-theoretic principles provides a solid theoretical foundation.
- **S2:** The theoretical analysis in Theorem 1 is rigorous and the proof is complete. The complexity bounds are clearly stated and verified empirically.
- **S3:** Experiments are comprehensive, covering both vision and language domains. The ablation study (Table 3) clearly isolates the contribution of each component.
- **S4:** The paper is well-written with clear notation. Figures 2 and 3 effectively illustrate the learned sparsity patterns.
- **S5:** The approach is practical and could have significant impact on deploying transformers in resource-constrained environments.

## Weaknesses

- **W1:** The comparison with Routing Transformer is incomplete. Table 2 shows results only on language modeling, but not on the vision tasks where routing-based methods have shown strong results.
- **W2:** The theoretical analysis assumes smooth input distributions (Assumption 1), but the paper does not discuss how violations of this assumption affect the guarantees. Real-world data often has non-smooth distributions.
- **W3:** The gating network introduces additional parameters (reported as ~5% overhead), but the paper does not analyze the sensitivity to this hyperparameter. How does performance change with different gating network sizes?
- **W4:** The claim "our method achieves the best efficiency-performance trade-off" (Abstract, line 3) is overstated. On ImageNet, the improvement over Performer is within noise margins (±0.1%).
- **W5:** Code is not provided. Given the complexity of the gating mechanism, reproducibility would benefit from released code.

## Questions for Authors

1. How does SDA perform on longer sequences (e.g., 8k+ tokens)? The current experiments cap at 2048 tokens. Is the O(n log n) bound maintained empirically?
2. What is the training overhead compared to standard attention? The paper reports inference speedup but training time is not discussed.
3. Have you considered applying SDA to cross-attention in encoder-decoder architectures? This seems like a natural extension.
4. In Table 4, the ablation removing the gating network shows only 0.3% drop. This raises questions about whether the gating is actually learning meaningful patterns or if fixed sparsity would suffice. Can you provide more analysis?

## Limitations

The paper focuses on efficiency gains but does not discuss the environmental implications of the computational savings. Additionally, while the method is general, all experiments use relatively standard benchmarks. The paper would benefit from evaluation on more diverse or challenging datasets to establish generalizability. The theoretical analysis assumes ideal conditions that may not hold in practice.

## Rating: 7

The paper presents a solid contribution with good theoretical grounding and comprehensive experiments. The concerns about missing baselines and overclaimed improvements prevent a higher score, but the core contribution is above the acceptance threshold.

## Confidence: 4

I am familiar with efficient attention mechanisms and have published in this area. I have read the related work carefully and checked the proofs.

## Overall Assessment

I lean toward acceptance. The core idea of learning input-dependent sparsity through a gating network is novel and well-executed. The main concerns are (1) missing comparisons with Routing Transformer on vision tasks, and (2) the need for more analysis of the gating network's contribution. If the authors can address these in the rebuttal, I would be willing to increase my score. The paper could strengthen itself by releasing code and extending experiments to longer sequences.
```

### Bad Example (What NOT to Do)

```markdown
## Summary

The paper is about attention mechanisms. They propose something new.

## Strengths
- The idea seems interesting
- Experiments are okay
- Writing is decent

## Weaknesses
- Not enough experiments
- Could be better written
- Missing some baselines

## Rating: 5

I think this paper is below the bar.
```

**Problems with this review:**
- Summary is vague and doesn't show understanding of the paper
- Strengths and weaknesses are generic, not specific to this paper
- No concrete examples or citations to specific sections/figures
- No questions for authors
- Rating is not justified
- No confidence score
- Not constructive - doesn't tell authors how to improve

## NeurIPS-Specific Review Focus Areas

### Reproducibility Checklist
- [ ] Are all hyperparameters reported?
- [ ] Is the experimental setup described in enough detail?
- [ ] Are random seeds mentioned?
- [ ] Is computational budget reported (GPU hours, hardware)?
- [ ] Is code available or promised?
- [ ] Are datasets clearly identified and accessible?

### Theoretical Contributions
- [ ] Are assumptions clearly stated?
- [ ] Are proofs complete (not deferred to appendix without necessity)?
- [ ] Are theorems stated before they are used?
- [ ] Are limitations of theoretical results acknowledged?
- [ ] Is the notation consistent and well-defined?

### Experimental Evaluation
- [ ] Are baselines appropriate and recent (last 2 years)?
- [ ] Are results averaged over multiple runs with error bars?
- [ ] Are ablation studies provided for key components?
- [ ] Is the evaluation metric appropriate for the task?
- [ ] Are statistical significance tests performed where applicable?

## Common Mistakes to Avoid

### For Reviewers
1. **Being too vague**: "The experiments are insufficient" without specifying what's missing
2. **Personal attacks**: "The authors clearly don't understand X" → "The paper does not address X"
3. **Rejecting novelty without evidence**: "This is just incremental" without citing prior work
4. **Ignoring author instructions**: Not following the review template
5. **Score-text mismatch**: Writing a positive review but giving a low score
6. **Confidence inflation**: Claiming expertise you don't have
7. **Not reading the paper**: Basing review only on abstract and conclusions

### For Authors (Understanding Reviews)
1. **Don't dismiss negative reviews**: Even harsh reviews may contain valid points
2. **Look for patterns**: If multiple reviewers mention the same issue, it's real
3. **Distinguish subjective from objective**: "I don't like this" vs "This is technically wrong"
4. **Address all points**: Don't cherry-pick easy questions while ignoring hard ones
5. **Be specific in rebuttals**: "We added experiment X" beats "We will add more experiments"

## 中文版本

### 使用场景

- 审稿面向NeurIPS投稿的机器学习和人工智能论文
- 评估深度学习、优化、强化学习、概率方法方面的论文
- 准备针对NeurIPS审稿意见的作者回复
- 在NeurIPS截稿前对自己的论文进行自审
- 培训新审稿人了解NeurIPS审稿标准

### NeurIPS审稿结构

每篇NeurIPS审稿必须按顺序包含以下部分：

1. **摘要**（1段）- 用自己的话重新表述论文的主要贡献
2. **优点**（3-5个要点）- 新颖性、技术可靠性、实验质量、表述清晰度、潜在影响
3. **缺点**（3-5个要点）- 技术缺陷、缺失实验、不清晰的声明、可复现性问题
4. **作者提问**（2-4个问题）- 具体技术问题、澄清请求、额外实验建议
5. **局限性**（1段）- 讨论作者可能忽略的局限性
6. **评分**（1-10分）
7. **置信度**（1-5分）
8. **总体评估**（最后1段）

### 评分标准

| 分数 | 标签 | 说明 |
|------|------|------|
| 10 | 质量奖 | 开创性贡献，从根本上推进领域发展 |
| 9 | 强接受 | 优秀论文，仅有小问题 |
| 8 | 接受 | 扎实贡献，超过接受阈值 |
| 7 | 弱接受 | 不错论文但有顾虑 |
| 6 | 边界线 | 信号矛盾，可接受可拒绝 |
| 5 | 弱拒绝 | 低于阈值，顾虑大于贡献 |
| 4 | 拒绝 | 存在重大问题 |
| 3 | 强拒绝 | 重大缺陷，根本性问题 |
| 2 | 很强拒绝 | 严重缺陷，无法修复 |
| 1 | 拒绝 | 不应发表，可能有害 |
