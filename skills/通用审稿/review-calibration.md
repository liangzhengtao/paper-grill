# Review Calibration

Calibrate your review quality to ensure fairness, consistency, and constructiveness. Detect and mitigate common reviewer biases. Write reviews that help authors improve their work.

## When to Use

- Ensuring your reviews are fair and consistent
- Calibrating review standards across a research group
- Training new reviewers on best practices
- Detecting and mitigating personal biases
- Improving the constructiveness of your feedback
- Preparing for meta-reviewer responsibilities

## Review Framework

### Calibration Principles

1. **Consistency**: Apply the same standards to all papers
2. **Fairness**: Evaluate based on merit, not personal preferences
3. **Constructiveness**: Help authors improve, not just criticize
4. **Specificity**: Cite specific issues with evidence
5. **Professionalism**: Maintain respectful tone throughout

### Review Quality Dimensions

#### 1. Technical Accuracy

**Good:**
- Specific technical issues cited with evidence
- Mathematical errors identified with correct solutions
- Methodology flaws explained clearly

**Bad:**
- Vague claims of technical issues
- "The math is wrong" without specifying what
- "Methodology is flawed" without explaining how

#### 2. Constructiveness

**Good:**
- "Consider adding experiment X to address concern Y"
- "The clarity would improve by reorganizing Section 3"
- "Comparison with [method] would strengthen the evaluation"

**Bad:**
- "This is bad"
- "Needs more work"
- "I don't like this approach"

#### 3. Specificity

**Good:**
- "Equation 5 has a sign error: the second term should be negative"
- "Table 2 is missing comparison with [SOTA method] which reported 95.2% on this benchmark"
- "Figure 3 is unclear because the legend overlaps with the data"

**Bad:**
- "The math has errors"
- "Missing baselines"
- "Figures are unclear"

#### 4. Fairness

**Good:**
- Evaluating based on conference standards, not personal taste
- Acknowledging contributions even when recommending rejection
- Comparing fairly with baselines (same data, compute)

**Bad:**
- Rejecting because the topic isn't interesting to you
- Holding authors to higher standards than accepted papers
- Comparing with baselines that used more data/compute

## Common Reviewer Biases

### 1. Confirmation Bias

**What it is:** Looking for evidence that confirms your initial impression

**Symptoms:**
- Reading selectively to find flaws after forming initial opinion
- Dismissing positive results that contradict your view
- Focusing on weaknesses while ignoring strengths

**Mitigation:**
- Read the entire paper before forming an opinion
- Deliberately look for strengths after identifying weaknesses
- Re-evaluate after reading author responses

### 2. Authority Bias

**What it is:** Being influenced by the authors' reputation or affiliation

**Symptoms:**
- Giving more favorable reviews to famous authors
- Being more critical of unknown authors
- Assuming institutional prestige equals paper quality

**Mitigation:**
- Focus on the paper, not the authors
- Apply the same rubric regardless of author identity
- Double-blind review helps but isn't perfect

### 3. Novelty Bias

**What it is:** Overvaluing novelty at the expense of solid work

**Symptoms:**
- Rejecting solid papers because they're "incremental"
- Accepting flashy but flawed papers because they're "novel"
- Confusing novelty with quality

**Mitigation:**
- Use the rubric: novelty is one dimension, not the only one
- Consider significance and soundness equally
- Incremental progress is still progress

### 4. Confirmation of Methodology Bias

**What it is:** Preferring papers that use your preferred methods

**Symptoms:**
- Rejecting papers because they use different methods
- Being more critical of unfamiliar approaches
- Assuming your methodology is the only valid one

**Mitigation:**
- Evaluate based on whether the method works, not whether it's your method
- Consider that different problems may need different methods
- Ask: "Is this a valid approach?" not "Is this my approach?"

### 5. Negativity Bias

**What it is:** Giving more weight to weaknesses than strengths

**Symptoms:**
- One weakness outweighs multiple strengths
- Focusing on what's wrong rather than what's right
- Recommending rejection based on minor issues

**Mitigation:**
- Explicitly balance strengths and weaknesses
- Use the rubric to weight different aspects
- Ask: "Does this contribution advance the field?"

### 6. Anchoring Bias

**What it is:** Being influenced by other reviewers or prior expectations

**Symptoms:**
- Adjusting your score after seeing other reviews
- Being influenced by the venue's acceptance rate
- Setting expectations based on previous submissions

**Mitigation:**
- Write your review before reading others
- Evaluate based on the rubric, not external factors
- Re-calibrate if your score is significantly different from others

### 7. Halo Effect

**What it is:** Letting one strong aspect inflate your overall assessment

**Symptoms:**
- High score because the writing is excellent, despite technical flaws
- Low score because of poor writing, despite solid contributions
- One impressive result masking other issues

**Mitigation:**
- Score each dimension independently
- Use the component scores in the rubric
- Don't let one aspect dominate your assessment

### 8. Leniency/Severity Bias

**What it is:** Consistently scoring too high or too low

**Symptoms:**
- All your scores are above average (or below)
- You rarely recommend rejection (or acceptance)
- Your scores don't match the distribution

**Mitigation:**
- Compare your scores with the distribution
- Use the rubric descriptions, not gut feeling
- Calibrate with accepted papers

## Self-Assessment Checklist

### Before Writing the Review

- [ ] I have read the entire paper carefully
- [ ] I understand the main contributions
- [ ] I have checked the math/proofs
- [ ] I have verified the experimental setup
- [ ] I have read related work to assess novelty
- [ ] I am not influenced by author identity
- [ ] I have not formed an opinion before reading

### While Writing the Review

- [ ] I am specific about issues (citing sections, equations, tables)
- [ ] I provide actionable recommendations
- [ ] I balance strengths and weaknesses
- [ ] I use professional, respectful language
- [ ] I justify every score with evidence
- [ ] I don't let one aspect dominate my assessment

### After Writing the Review

- [ ] My scores match the rubric descriptions
- [ ] My review would be helpful to the authors
- [ ] I would be comfortable if this review were public
- [ ] I have checked for personal biases
- [ ] My confidence score reflects my actual expertise
- [ ] I have not been influenced by other reviewers

## Bias Detection Guide

### Questions to Ask Yourself

**Before Reviewing:**
1. Do I know who the authors are? If yes, does that influence my expectations?
2. Is this a topic I'm excited about? If yes, am I being too lenient?
3. Is this a topic I dislike? If yes, am I being too harsh?
4. Have I rejected similar papers before? If yes, am I applying the same standards?

**During Reviewing:**
1. Am I focusing too much on weaknesses?
2. Am I dismissing strengths because they don't fit my narrative?
3. Am I being specific enough in my criticism?
4. Am I providing constructive suggestions?

**After Reviewing:**
1. Does my score match my written assessment?
2. Would I be comfortable if the authors knew my identity?
3. Am I confident in my expertise for this paper?
4. Have I been fair compared to similar papers?

### Red Flags in Your Review

- You recommend rejection but can't articulate why
- Your strengths section is much shorter than weaknesses
- You use words like "trivial", "obvious", "just"
- You focus on presentation rather than substance
- You don't provide specific examples or citations
- Your score doesn't match your written assessment
- You haven't read the supplementary material
- You dismiss the work without understanding it

## Good vs. Bad Review Examples

### Good Review Excerpt

```markdown
## Strengths
- **S1:** The proposed method (Equation 5) is novel and well-motivated. The connection to information theory (Theorem 1) provides theoretical grounding that is often missing in this area.
- **S2:** Experiments are comprehensive, including ablation studies (Table 3) that isolate the contribution of each component. The comparison with 5 recent baselines on 3 benchmarks is thorough.
- **S3:** The paper is clearly written with consistent notation. Figures 2 and 3 effectively illustrate the method and results.

## Weaknesses
- **W1:** The comparison with [SOTA method] is missing. This method reported 95.2% on CIFAR-10 (their Table 2), compared to your 94.8%. Without this comparison, it's unclear if the contribution advances the state-of-the-art.
- **W2:** The theoretical analysis (Theorem 1) assumes Lipschitz continuity (Assumption 2), but the experiments use ReLU networks which are not Lipschitz. The paper should discuss this gap.
- **W3:** Error analysis is missing. The paper reports average accuracy but doesn't analyze what types of examples the method fails on. This would help readers understand when to apply the method.

## Recommendation
I recommend weak accept (score 7). The contribution is solid and the paper is well-written, but the missing SOTA comparison (W1) and theoretical gap (W2) prevent a higher score. If the authors address these in the rebuttal, I would increase my score.
```

### Bad Review Excerpt

```markdown
## Weaknesses
- Not novel enough
- Experiments are weak
- Writing is poor

## Score: 3
Reject.
```

**Why the bad example is problematic:**
- No strengths section
- Weaknesses are vague and not actionable
- No specific citations to issues
- Score not justified
- No constructive suggestions
- No consideration of what the paper does well

## Calibration Exercises

### Exercise 1: Score Calibration

Read a paper and score it using the rubric. Then compare with:
1. Other reviewers' scores
2. The actual decision (accepted/rejected)
3. Your scores on similar papers

### Exercise 2: Bias Detection

Review a paper, then check:
1. Did you know the authors? If yes, did it influence you?
2. Is your score consistent with your written review?
3. Did you balance strengths and weaknesses?

### Exercise 3: Constructiveness Check

After writing a review, ask:
1. Would this review help the authors improve?
2. Are my suggestions specific and actionable?
3. Would I be comfortable if this review were public?

## Common Mistakes to Avoid

### Calibration Mistakes
1. **Central tendency**: Avoiding extreme scores
2. **Personal standards**: Applying your standards instead of the community's
3. **Inconsistency**: Different standards for different papers
4. **Anchoring**: Being influenced by other reviewers

### Constructiveness Mistakes
1. **Vague criticism**: "Needs more work" without specifics
2. **No suggestions**: Criticizing without offering solutions
3. **Tone**: Being dismissive or condescending
4. **Ignoring context**: Not considering the venue's standards

## 中文版本

### 使用场景

- 确保你的审稿公平且一致
- 校准研究小组的审稿标准
- 培训新审稿人掌握最佳实践
- 检测和缓解个人偏见
- 提高反馈的建设性
- 准备担任元审稿人职责

### 校准原则

1. **一致性**：对所有论文应用相同标准
2. **公平性**：基于价值评估，而非个人偏好
3. **建设性**：帮助作者改进，不仅仅是批评
4. **具体性**：引用具体问题并提供证据
5. **专业性**：始终保持尊重的语气

### 常见审稿人偏见

#### 1. 确认偏见
**是什么**：寻找证据来确认你的初始印象
**症状**：形成初始意见后选择性阅读以寻找缺陷
**缓解**：在形成意见前阅读全文；在识别弱点后刻意寻找优点

#### 2. 权威偏见
**是什么**：受作者声誉或机构影响
**症状**：给著名作者更 favorable 的审稿；对未知作者更苛刻
**缓解**：关注论文本身，而非作者；应用相同的评分标准

#### 3. 新颖性偏见
**是什么**：过度重视新颖性而忽视扎实的工作
**症状**：因为"增量性"而拒绝扎实的论文；接受华而不实但有缺陷的论文
**缓解**：使用评分标准：新颖性是一个维度，不是唯一维度

#### 4. 方法论偏见
**是什么**：偏好使用你喜欢的方法的论文
**症状**：因为使用不同方法而拒绝论文；对不熟悉的方法更苛刻
**缓解**：基于方法是否有效来评估，而非是否是你的方法

#### 5. 消极偏见
**是什么**：给予弱点比优点更大的权重
**症状**：一个弱点超过多个优点；基于小问题建议拒稿
**缓解**：明确平衡优点和缺点；使用评分标准来加权不同方面

#### 6. 锚定偏见
**是什么**：受其他审稿人或先前期望的影响
**症状**：看到其他审稿后调整分数；受会议接受率影响
**缓解**：在阅读其他审稿前写出你的审稿；基于评分标准评估

#### 7. 光环效应
**是什么**：让一个强项影响整体评估
**症状**：因为写作优秀而给高分，尽管有技术缺陷
**缓解**：独立评估每个维度；使用组件评分

#### 8. 宽松/严格偏见
**是什么**：始终评分过高或过低
**症状**：所有分数都高于（或低于）平均值
**缓解**：将你的分数与分布比较；使用评分标准描述

### 自评清单

**审稿前：**
- [ ] 我已仔细阅读全文
- [ ] 我理解主要贡献
- [ ] 我已检查数学/证明
- [ ] 我不受作者身份影响
- [ ] 我在阅读前未形成意见

**审稿中：**
- [ ] 我对问题具体（引用章节、公式、表格）
- [ ] 我提供建设性建议
- [ ] 我平衡优点和缺点
- [ ] 我使用专业、尊重的语言

**审稿后：**
- [ ] 我的分数与评分标准描述匹配
- [ ] 我的审稿对作者有帮助
- [ ] 如果这篇审稿公开，我会感到舒适
- [ ] 我已检查个人偏见
