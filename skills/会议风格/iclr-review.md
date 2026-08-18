# ICLR Review Style

Mimic the review style and standards of the International Conference on Learning Representations (ICLR). Generate rigorous reviews following ICLR's open review format with emphasis on representation learning, learned features, and public review etiquette.

## When to Use

- Reviewing representation learning papers targeting ICLR submission
- Evaluating papers on self-supervised learning, contrastive learning, generative models
- Reviewing papers submitted to ICLR's open review platform
- Preparing author responses during ICLR's public rebuttal period
- Self-reviewing papers before ICLR submission deadline

## Review Framework

### ICLR Open Review Format

ICLR uses an open review system where reviews are public. This creates unique considerations:

1. **Transparency**: Reviews are visible to everyone, not just authors
2. **Accountability**: Reviewers must stand behind their assessments
3. **Constructiveness**: Public criticism requires professional tone
4. **Author Response**: Authors can respond publicly, creating dialogue
5. **Community Input**: Other researchers can comment on reviews

### ICLR Review Structure

Every ICLR review must contain:

1. **Summary** (1 paragraph)
   - Concise overview of the paper's contributions
   - Core methodology and approach
   - Main results and claims

2. **Strengths** (bullet points)
   - Novelty in representation learning approaches
   - Quality of learned representations (visualization, probing)
   - Theoretical contributions to understanding representations
   - Experimental design and evaluation methodology
   - Clarity of presentation and reproducibility

3. **Weaknesses** (bullet points)
   - Issues with representation quality or evaluation
   - Missing comparisons or insufficient baselines
   - Gaps in theoretical understanding
   - Reproducibility concerns
   - Overstated claims

4. **Questions for Authors**
   - Specific technical questions
   - Clarification requests
   - Suggestions for additional analysis

5. **Limitations and Societal Impact**
   - Discuss limitations not addressed by authors
   - Potential negative societal impacts
   - Ethical considerations

6. **Rating** (1-10)
7. **Confidence** (1-5)
8. **Code of Ethics Confirmation**

### ICLR Scoring Rubric

| Score | Label | Description |
|-------|-------|-------------|
| 10 | Award Candidate | Exceptional paper, best in the session |
| 9 | Strong Accept | Excellent, clear accept |
| 8 | Accept | Good paper, above bar |
| 7 | Weak Accept | Decent, leaning accept |
| 6 | Borderline | Mixed signals |
| 5 | Weak Reject | Below bar, leaning reject |
| 4 | Reject | Clear reject |
| 3 | Strong Reject | Significant issues |
| 2 | Very Strong Reject | Fundamental problems |
| 1 | Clear Reject | Should not be published |

### Representation Learning Specific Criteria

For representation learning papers, evaluate:

1. **Representation Quality**
   - Linear probe accuracy on learned representations
   - Visualization of learned features (t-SNE, UMAP, activation maps)
   - Transfer learning performance to downstream tasks
   - Representation collapse analysis (for self-supervised methods)

2. **Theoretical Understanding**
   - Analysis of what the representations capture
   - Connection to information-theoretic principles
   - Understanding of when/why the method works
   - Characterization of failure modes

3. **Evaluation Methodology**
   - Appropriate downstream tasks for evaluation
   - Fair comparison with baselines (same pretraining data, compute)
   - Ablation studies isolating key components
   - Analysis of learned representations (not just final performance)

## Review Template

```markdown
# ICLR 2024 Review - Paper [ID]

## Summary

[Paper ID: XXXX]

This paper proposes [method name] for [learning task]. The key contribution is [describe core idea for learning representations]. The authors [describe methodology - architecture, loss function, training procedure]. The learned representations are evaluated on [downstream tasks/benchmarks]. Main results show [key findings].

## Strengths

- **S1:** [Novelty] [What is new about this representation learning approach?]
- **S2:** [Representation Quality] [Evidence that the learned representations are good]
- **S3:** [Evaluation] [Strengths of the experimental evaluation]
- **S4:** [Analysis] [Insights into what the representations learn]
- **S5:** [Presentation] [Clarity, reproducibility]

## Weaknesses

- **W1:** [Representation Issues] [Problems with representation quality or evaluation]
- **W2:** [Missing Comparisons] [Important baselines not compared with]
- **W3:** [Analysis Gaps] [Missing analysis of learned representations]
- **W4:** [Reproducibility] [Missing details for reproduction]
- **W5:** [Overclaims] [Where the paper claims more than it shows]

## Questions for Authors

1. [Technical question about the method]
2. [Question about representation analysis]
3. [Question about experimental setup]
4. [Suggestion for additional evaluation]

## Limitations and Societal Impact

[Discuss limitations not addressed by authors. Consider potential negative impacts: bias in learned representations, computational cost, environmental impact, potential misuse.]

## Rating: [1-10]

[2-3 sentence justification]

## Confidence: [1-5]

[1 sentence about expertise]

## Code of Ethics: I confirm that I have read the ICLR Code of Ethics and believe this paper is in compliance.
```

## Example Reviews

### Good Example (Self-Supervised Learning Paper, Score: 8)

```markdown
## Summary

This paper proposes "Representation Alignment Contrastive Learning" (RACL), a new self-supervised learning method that aligns representations across different augmentation views using a novel asymmetric loss function. The key insight is that standard contrastive learning may discard task-relevant information through aggressive augmentation, and the authors propose to weight augmentation pairs by their mutual information. Experiments on ImageNet linear evaluation, transfer learning to 7 downstream tasks, and few-shot learning demonstrate improvements over SimCLR, MoCo v3, and BYOL.

## Strengths

- **S1 (Novelty):** The asymmetric loss function (Equation 5) that weights pairs by estimated mutual information is novel. This goes beyond standard contrastive learning by explicitly considering what information each augmentation preserves.
- **S2 (Representation Quality):** Linear probe accuracy on ImageNet (Table 1) shows consistent improvement over baselines (+1.2% over MoCo v3). More importantly, Figure 4 shows that the learned representations maintain more semantic information as measured by centered kernel alignment (CKA) with supervised features.
- **S3 (Evaluation):** The evaluation is complete, including linear evaluation, fine-tuning, few-shot learning, and representation analysis. The 7 downstream tasks span diverse domains (classification, detection, segmentation, retrieval).
- **S4 (Analysis):** Figure 5 analyzing the information bottleneck behavior provides genuine insight into why the method works. The visualization of attention maps (Figure 6) shows the model focuses on more semantically meaningful regions.
- **S5 (Reproducibility):** The authors provide code and detailed hyperparameters. The method is described clearly enough to reimplement.

## Weaknesses

- **W1 (Missing Analysis):** The paper does not analyze representation collapse, which is a critical issue for self-supervised methods. How does RACL prevent collapse? Is it the asymmetric loss, the stop-gradient, or something else? An ablation isolating these components is needed.
- **W2 (Compute Comparison):** Table 1 reports accuracy but not compute. The mutual information estimation (Section 3.2) adds computational overhead. A fair comparison should report performance vs. compute, not just final accuracy. How does RACL compare to baselines at the same compute budget?
- **W3 (Limited Scale):** All experiments use ResNet-50. Recent work shows that self-supervised methods behave differently at larger scales (ViT-L, ViT-H). The paper should validate on at least one larger architecture.
- **W4 (Augmentation Dependence):** The method's core idea is about augmentation weighting, but the paper does not analyze sensitivity to the augmentation policy. What happens with different augmentation strengths or types?
- **W5 (Claim Overstatement):** The abstract claims "superior representations across all evaluation protocols" but Table 3 shows RACL is worse than BYOL on 2 of 7 transfer tasks. The claim should be more nuanced.

## Questions for Authors

1. In Algorithm 1, the mutual information estimate uses a separate network p_φ. How sensitive is the method to this network's architecture? Have you tried simpler alternatives (e.g., using the main encoder's features directly)?
2. Figure 4 shows CKA alignment with supervised features improves. But isn't the goal of self-supervised learning to learn representations that DON'T just mimic supervised ones? What task-relevant information does RACL capture that supervised learning misses?
3. The memory bank for mutual information estimation (Section 3.2) uses a queue of size 65536. How does performance change with smaller queues? This is important for memory-constrained settings.
4. Have you evaluated on structured prediction tasks (e.g., object detection with COCO) where representation quality matters more than linear separability?

## Limitations and Societal Impact

The paper does not discuss the computational cost of the method, which is important given the current focus on efficient AI. The mutual information estimation adds non-trivial overhead. Additionally, while the paper evaluates on diverse downstream tasks, it does not assess whether the learned representations amplify biases present in the training data (ImageNet has known biases). The authors should discuss these limitations and potential mitigation strategies.

## Rating: 8

The paper makes a solid contribution to self-supervised learning with a novel loss function and complete evaluation. The representation analysis (Figures 4-6) provides genuine insights. The main concerns are missing collapse analysis and compute comparison, but these can be addressed in the rebuttal.

## Confidence: 4

I have published on self-supervised learning and contrastive methods. I am familiar with the baselines compared.

## Code of Ethics: I confirm that I have read the ICLR Code of Ethics and believe this paper is in compliance.

## Overall Assessment

I recommend acceptance. The core contribution (asymmetric loss with mutual information weighting) is novel and well-motivated. The experimental evaluation is complete and the representation analysis provides real insights. The main concerns (collapse analysis, compute comparison) are addressable. I look forward to seeing the authors' response and will update my review accordingly.
```

### Bad Example (What NOT to Do in Open Review)

```markdown
## Summary

Paper uses contrastive learning. Nothing new here.

## Weaknesses
- Just another contrastive learning paper
- Incremental improvement
- Authors don't understand the field

## Rating: 3

Reject.
```

**Why this is problematic for ICLR open review:**
- **Public visibility**: This dismissive review will be seen by the community
- **Not constructive**: Doesn't help authors improve
- **Personal attack**: "Authors don't understand" is inappropriate
- **Not specific**: "Nothing new" without citing what IS new
- **Unprofessional**: Public reviews should maintain professional standards
- **Missing sections**: No strengths, questions, or ethics confirmation

## ICLR Open Review Etiquette

### Do's

1. **Be professional**: Your review is public and reflects on you
2. **Be specific**: Cite specific equations, figures, sections
3. **Be constructive**: Suggest how to improve, not just what's wrong
4. **Be fair**: Evaluate the paper on its merits, not your preferences
5. **Be responsive**: Update your review after author response if they address your concerns
6. **Acknowledge limits**: If something is outside your expertise, say so

### Don'ts

1. **Don't be dismissive**: "This is trivial" without explaining why
2. **Don't make it personal**: Criticize the work, not the authors
3. **Don't be vague**: "Needs more experiments" without specifying what
4. **Don't reject novelty unfairly**: "Just another X" ignores incremental progress
5. **Don't ignore author responses**: If they address your concerns, acknowledge it
6. **Don't coordinate reviews**: Discussing reviews with other reviewers is unethical

### Author Response Guidelines

When writing author responses for ICLR:

1. **Be concise**: Reviewers read many responses
2. **Be specific**: Point to exact experiments/results that address concerns
3. **Be professional**: Even if reviews are unfair, maintain courtesy
4. **Prioritize**: Address the most important concerns first
5. **Follow through**: If you promise experiments in the rebuttal, do them

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Treating it like anonymous review**: Open review requires higher standards
2. **Not engaging with author responses**: The rebuttal period is for dialogue
3. **Being too harsh**: Public criticism has more impact than private
4. **Bandwagon effects**: Seeing other negative reviews and piling on
5. **Confidence inflation**: Claiming expertise you don't have in a public forum

### Author Mistakes
1. **Defensive responses**: "The reviewer is wrong" - they might have a point
2. **Not responding**: Silence looks bad in open review
3. **Promising experiments**: Don't promise what you can't deliver
4. **Ignoring weak reviews**: Even bad reviews may contain valid points
5. **Public arguments**: Keep the discussion professional

## 中文版本

### 使用场景

- 审稿面向ICLR投稿的表征学习论文
- 评估自监督学习、对比学习、生成模型方面的论文
- 在ICLR开放审稿平台上审稿
- 在ICLR公开回复期准备作者回复
- 在ICLR截稿前对自己的论文进行自审

### ICLR开放审稿格式

ICLR使用开放审稿系统，审稿内容公开可见。这带来独特考量：

1. **透明性**：审稿内容对所有人可见，不仅限作者
2. **问责性**：审稿人必须为其评估负责
3. **建设性**：公开批评需要专业态度
4. **作者回复**：作者可以公开回复，形成对话
5. **社区参与**：其他研究者可以评论审稿意见

### 表征学习特定评估标准

对于表征学习论文，评估：

1. **表征质量**
   - 学习表征的线性探测准确率
   - 学习特征的可视化（t-SNE、UMAP、激活图）
   - 到下游任务的迁移学习性能
   - 表征坍塌分析（自监督方法）

2. **理论理解**
   - 分析表征捕获了什么
   - 与信息论原理的联系
   - 理解方法何时/为何有效
   - 失败模式的特征化

3. **评估方法论**
   - 适当的下游任务评估
   - 与基线的公平比较（相同预训练数据、计算量）
   - 隔离关键组件的消融研究
   - 学习表征的分析（不仅是最终性能）

### ICLR开放审稿礼仪

**应该做的：**
1. 保持专业：你的审稿是公开的，反映你的形象
2. 具体明确：引用具体公式、图表、章节
3. 建设性：建议如何改进，不仅仅是指出问题
4. 公平公正：根据论文本身价值评估
5. 积极回应：在作者回复后更新你的审稿

**不应该做的：**
1. 不要轻蔑：不要无解释地说"这很平凡"
2. 不要人身攻击：批评工作，而非作者
3. 不要含糊不清：不要只说"需要更多实验"
4. 不要不公平地拒绝新颖性
5. 不要忽视作者回复
6. 不要协调审稿：与其他审稿人讨论审稿内容是不道德的
