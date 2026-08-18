# ICML Review Style

Mimic the review style and standards of the International Conference on Machine Learning (ICML). Generate rigorous reviews emphasizing mathematical rigor, theoretical contributions, and sound experimental methodology.

## When to Use

- Reviewing machine learning papers targeting ICML submission
- Evaluating papers with strong theoretical components (optimization, generalization, statistical learning theory)
- Reviewing papers on kernel methods, online learning, bandits, reinforcement learning theory
- Preparing rebuttals for ICML reviewer feedback
- Self-reviewing papers before ICML submission deadline

## Review Framework

### ICML Review Structure

ICML reviews emphasize mathematical rigor and theoretical contributions. Every review must contain:

1. **Summary and Contributions** (1-2 paragraphs)
   - Restate the problem and main contributions
   - Identify theoretical contributions vs empirical contributions
   - Place contributions in context of existing work
   - Clearly state what is new vs what extends existing work

2. **Strengths** (3-5 points)
   - Theoretical novelty and rigor
   - Mathematical soundness of proofs
   - Quality of theoretical analysis
   - Experimental validation of theoretical claims
   - Clarity of mathematical exposition

3. **Weaknesses** (3-5 points)
   - Gaps in theoretical analysis
   - Incorrect or incomplete proofs
   - Missing assumptions or unrealistic assumptions
   - Weak experimental evaluation
   - Disconnect between theory and experiments

4. **Questions** (2-4 specific questions)
   - Technical questions about proofs or derivations
   - Questions about assumptions and their necessity
   - Questions about experimental methodology
   - Questions about scope and generalizability

5. **Detailed Comments** (numbered list)
   - Line-by-line or section-by-section feedback
   - Specific suggestions for improvement
   - Corrections to notation, equations, or statements
   - References to related work that should be discussed

6. **Score** (1-10)
7. **Confidence** (1-5)
8. **Ethics Review** (if applicable)

### ICML Scoring Rubric

| Score | Label | Description |
|-------|-------|-------------|
| 10 | Strong Accept | Significant theoretical advance with complete proofs and validation |
| 9 | Accept | Strong theoretical contribution, minor issues only |
| 8 | Accept | Solid contribution, above acceptance bar |
| 7 | Weak Accept | Decent contribution with some theoretical gaps |
| 6 | Borderline | Mixed quality, could go either way |
| 5 | Weak Reject | Below bar, theoretical concerns outweigh contributions |
| 4 | Reject | Significant theoretical flaws or limited contribution |
| 3 | Strong Reject | Major issues with theory or experiments |
| 2 | Very Strong Reject | Fundamental problems |
| 1 | Clear Reject | Should not be published |

### Mathematical Rigor Checklist

For papers with theoretical contributions, verify:

- [ ] All assumptions are clearly stated and numbered
- [ ] Theorems, lemmas, corollaries are properly formatted
- [ ] Proofs are complete (not "proofs deferred to appendix" for key results)
- [ ] Notation is consistent throughout (check symbols, subscripts, superscripts)
- [ ] Constants and dependencies are explicit (not hidden in O-notation)
- [ ] Convergence rates are compared to known lower bounds
- [ ] Complexity analysis is provided for algorithms
- [ ] Proof techniques are appropriate (not overly complicated when simpler exists)

## Review Template

```markdown
# Review for Paper [ID]

## Summary and Contributions

This paper studies [problem area] and makes the following contributions:

1. **Theoretical:** [Describe theoretical contribution - e.g., new convergence bound, generalization guarantee, complexity result]
2. **Algorithmic:** [Describe algorithmic contribution - e.g., new algorithm, improved complexity]
3. **Empirical:** [Describe experimental contribution - e.g., validation on benchmarks, comparison with baselines]

The main technical approach involves [brief description of methods]. The key theoretical result (Theorem X) states that [informal statement of main theorem]. This improves upon the prior work of [citation] by [specific improvement].

## Strengths

- **S1 (Theoretical Novelty):** [Specific description of what is theoretically novel]
- **S2 (Mathematical Quality):** [Assessment of proof quality, rigor of analysis]
- **S3 (Significance):** [Why this theoretical result matters for the field]
- **S4 (Experiments):** [How well experiments validate theoretical claims]
- **S5 (Presentation):** [Quality of mathematical writing and exposition]

## Weaknesses

- **W1 (Theoretical Gap):** [Specific gap in theory - missing cases, unstated assumptions, incomplete analysis]
- **W2 (Proof Issues):** [Specific issues with proofs - errors, gaps, unclear steps]
- **W3 (Assumption Validity):** [Are assumptions realistic? What happens when they're violated?]
- **W4 (Experimental Weakness):** [Missing experiments, weak baselines, poor validation of theory]
- **W5 (Limited Scope):** [What's not covered that should be]

## Questions

1. [Specific question about a proof step or derivation]
2. [Question about the necessity of an assumption]
3. [Question about experimental methodology]
4. [Question about extensions or generalizations]

## Detailed Comments

### Section 2 (Preliminaries)
- Line XX: Notation inconsistency - \theta is used for both the parameter and the step size
- Equation (3): The bound assumes Lipschitz continuity but this isn't stated in Assumption 1

### Section 3 (Main Results)
- Theorem 1: The dependence on dimension d should be made explicit in the main text, not just the appendix
- Proof of Lemma 2: Step 3 uses Jensen's inequality but the convexity condition isn't verified

### Section 4 (Algorithm)
- Algorithm 1: The stopping criterion is not specified. What guarantees convergence?
- Table 1: Missing comparison with [important baseline method]

### Section 5 (Experiments)
- The synthetic experiments don't validate the key theoretical prediction about [specific claim]
- Real-world experiments should include error bars over multiple runs

## Score: [1-10]

[2-3 sentence justification]

## Confidence: [1-5]

[1 sentence about your expertise and confidence]

## Overall Assessment

[Final paragraph with clear recommendation. For theoretical papers, specifically assess:
1. Is the theory sound and novel?
2. Are the proofs correct and complete?
3. Do experiments validate the theory?
4. Is the contribution significant enough for ICML?]
```

## Example Reviews

### Good Example (Theoretical Paper, Score: 8)

```markdown
## Summary and Contributions

This paper analyzes the convergence properties of stochastic gradient descent (SGD) with momentum in the non-convex setting. The authors prove that SGD with Polyak momentum achieves an ε-stationary point in O(1/ε^{3/2}) iterations under L-smoothness and bounded variance assumptions, improving the previous O(1/ε^2) rate. The key technical innovation is a novel Lyapunov function that accounts for the momentum term's effect on the gradient noise.

Contributions:
1. **Theoretical:** Tight convergence rate for momentum SGD in non-convex optimization (Theorem 1)
2. **Algorithmic:** Adaptive momentum parameter schedule based on estimated gradient variance (Algorithm 1)
3. **Empirical:** Validation on training ResNet-50 on ImageNet, showing 15% faster convergence

## Strengths

- **S1 (Theoretical Novelty):** The Lyapunov function V_k = f(x_k) + (β/2)||x_k - x_{k-1}||^2 is elegant and the analysis is tight. The matching lower bound (Theorem 2) shows the rate cannot be improved without additional assumptions.
- **S2 (Mathematical Quality):** Proofs are complete and well-structured. Lemma 3 (noise reduction via momentum) is a standalone contribution that could be useful beyond this paper.
- **S3 (Significance):** Resolving the convergence rate of momentum SGD is an important open problem cited in multiple prior works. This result has implications for practical deep learning optimization.
- **S4 (Experiments):** The adaptive schedule (Figure 2) demonstrates clear practical benefit. The ablation study isolating the effect of each component is well-designed.
- **S5 (Presentation):** Mathematical exposition is clear. Notation is consistent. Proofs follow a logical progression.

## Weaknesses

- **W1 (Assumption Limitation):** Assumption 2 (bounded variance) is strong and often violated in deep learning where variance grows with batch size. The paper should discuss this limitation more explicitly and consider the relaxed assumption σ² ≤ G·f(x*) used in [citation].
- **W2 (Missing Analysis):** The paper analyzes only the single-node setting. Distributed momentum SGD has additional considerations (communication compression, heterogeneous data) that would make the analysis more impactful.
- **W3 (Experimental Scale):** Experiments use only ResNet-50 on ImageNet. The paper should validate on at least one more architecture (e.g., Transformer) and one more domain (e.g., NLP) to establish generalizability.
- **W4 (Lower Bound Scope):** The lower bound (Theorem 2) applies only to deterministic momentum methods. An information-theoretic lower bound for stochastic methods would strengthen the contribution.

## Questions

1. In the proof of Theorem 1, Line 15, you use the inequality E[||g_k||^2] ≤ 2E[||∇f(x_k)||^2] + 2σ^2. This requires independence between g_k and x_k, but x_k depends on g_{k-1}. Can you clarify the conditioning?
2. What is the dependence of the convergence rate on the condition number L/μ? For strongly convex problems, momentum methods are known to achieve O(√(L/μ) log(1/ε)). Does your analysis recover this rate?
3. The adaptive schedule in Algorithm 1 requires estimating σ^2_k at each iteration. What is the computational overhead of this estimation?
4. Have you considered the case where the momentum parameter β is learned rather than scheduled? Recent work on learned optimizers suggests this could be beneficial.

## Detailed Comments

### Section 2
- Definition 1: The L-smoothness assumption should be stated for the stochastic gradients as well, not just the true gradients
- Equation (5): The step size η_k should be indexed by k in the algorithm description

### Section 3
- Theorem 1: Consider adding a table summarizing the rates of different methods for easy comparison
- Proof of Lemma 3: The use of Young's inequality could be more explicit

### Section 4
- Algorithm 1: Add a comment about the initialization of σ^2_0
- Figure 1: The y-axis should be log-scale to better show convergence rates

## Score: 8

This paper makes a significant theoretical contribution by resolving the convergence rate of momentum SGD. The analysis is rigorous and the proofs are complete. The main weakness is the strong assumption on gradient variance, but this is common in the literature and the paper acknowledges it. The practical contribution of the adaptive schedule adds value.

## Confidence: 5

I have published multiple papers on stochastic optimization and convergence analysis. I have verified the proofs carefully.

## Overall Assessment

I recommend acceptance. The theoretical contribution (tight convergence rate for momentum SGD) is significant and fills an important gap in the literature. The proofs are correct and well-presented. The practical adaptive schedule demonstrates that the theory has real-world impact. The main concern about Assumption 2 (bounded variance) is a limitation but does not invalidate the contribution. The authors should discuss this limitation more explicitly and consider extensions to the distributed setting in the final version.
```

### Bad Example (What NOT to Do)

```markdown
## Summary

The paper is about SGD with momentum. They prove convergence rates.

## Strengths
- Theory seems correct
- Experiments show improvement

## Weaknesses
- Theory is hard to follow
- Not enough experiments
- Assumptions are strong

## Score: 5

The paper needs more work.
```

**Problems:**
- Summary doesn't demonstrate understanding of the specific contribution
- No specific references to theorems, lemmas, or proof steps
- "Theory is hard to follow" is not actionable - which part?
- "Not enough experiments" - what specifically is missing?
- Score is unjustified
- No detailed comments
- Missing confidence score

## ICML-Specific Review Guidelines

### Evaluating Theoretical Contributions

For theoretical papers at ICML, assess:

1. **Novelty of proof technique**: Is the proof approach new or does it just combine existing techniques?
2. **Tightness of bounds**: Are the bounds tight? Is there a matching lower bound?
3. **Necessity of assumptions**: Are all assumptions necessary? Can some be relaxed?
4. **Comparison to prior bounds**: How much does this improve over existing results?
5. **Generality vs specificity**: Is the result general enough to be useful but specific enough to be non-trivial?

### Evaluating Empirical Contributions

Even for theory papers, experiments should:

1. **Validate theoretical predictions**: Do experiments confirm the theoretical convergence rates?
2. **Test assumption violations**: What happens when assumptions are violated?
3. **Compare with baselines**: Are baselines appropriate and recent?
4. **Report computational costs**: How much does the theoretical improvement cost in practice?
5. **Provide ablation studies**: Which components contribute to the improvement?

### Mathematical Writing Standards

Check that the paper follows these standards:

- All symbols are defined before first use
- Theorem environments are properly formatted (Theorem, Lemma, Corollary, Proposition, Definition, Assumption)
- Proofs are clearly separated from the main text
- Equations are numbered consistently
- Figures use consistent notation with the text
- Algorithm pseudocode is provided for complex methods

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Accepting weak theory**: "The proof looks right" without verifying each step
2. **Rejecting good theory**: "I don't understand the proof technique" when the technique is valid but unfamiliar
3. **Demanding unrealistic experiments**: Requiring experiments that would cost thousands of GPU hours for a theory paper
4. **Ignoring the theory**: Focusing only on experiments for a theory paper
5. **Not checking assumptions**: Missing that key assumptions are violated in practice

### Author Mistakes (Understanding Reviews)
1. **Ignoring proof feedback**: Reviewers may catch real errors
2. **Defensive responses**: "The reviewer doesn't understand" - they might, and you might be wrong
3. **Not adding experiments**: Even theory papers benefit from empirical validation
4. **Overclaiming**: "We solve optimization" vs "We improve convergence for specific cases"

## 中文版本

### 使用场景

- 审稿面向ICML投稿的机器学习论文
- 评估具有强理论成分的论文（优化、泛化、统计学习理论）
- 审稿关于核方法、在线学习、老虎机、强化学习理论的论文
- 准备针对ICML审稿意见的作者回复
- 在ICML截稿前对自己的论文进行自审

### ICML审稿结构

ICML审稿强调数学严谨性和理论贡献。每篇审稿必须包含：

1. **摘要与贡献**（1-2段）- 重新表述问题和主要贡献，区分理论贡献和实验贡献
2. **优点**（3-5点）- 理论新颖性、数学严谨性、证明质量、实验验证、数学表述清晰度
3. **缺点**（3-5点）- 理论分析缺陷、证明错误或不完整、不现实的假设、实验评估薄弱
4. **问题**（2-4个具体问题）- 关于证明步骤的技术问题、假设必要性问题
5. **详细评论**（编号列表）- 逐节反馈、具体改进建议
6. **评分**（1-10分）
7. **置信度**（1-5分）

### 数学严谨性检查清单

- [ ] 所有假设是否清晰陈述并编号
- [ ] 定理、引理、推论格式是否正确
- [ ] 证明是否完整（关键结果不延迟到附录）
- [ ] 符号是否全文一致
- [ ] 常数和依赖关系是否明确
- [ ] 收敛速率是否与已知下界比较
- [ ] 算法是否提供复杂度分析

### 评分标准

| 分数 | 标签 | 说明 |
|------|------|------|
| 10 | 强接受 | 重大理论突破，证明完整且有验证 |
| 9 | 接受 | 强理论贡献，仅有小问题 |
| 8 | 接受 | 扎实贡献，超过接受阈值 |
| 7 | 弱接受 | 不错贡献但有理论缺陷 |
| 6 | 边界线 | 质量混合 |
| 5 | 弱拒绝 | 低于阈值 |
| 4 | 拒绝 | 重大理论缺陷 |
| 3 | 强拒绝 | 理论或实验重大问题 |
| 2 | 很强拒绝 | 根本性问题 |
| 1 | 明确拒绝 | 不应发表 |
