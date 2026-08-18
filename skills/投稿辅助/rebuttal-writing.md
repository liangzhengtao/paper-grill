# Rebuttal Writing

Write effective author responses (rebuttals) to reviewer comments. This skill provides strategies, templates, and examples for addressing different types of reviewer feedback during the rebuttal period.

## When to Use

- Responding to reviewer comments during rebuttal period
- Writing author responses for NeurIPS, ICML, ICLR, ACL, CVPR
- Addressing unfair or incorrect reviews
- Planning rebuttal strategy for multiple reviewers
- Crafting responses that change reviewer scores
- Training authors on effective rebuttal writing

## Review Framework

### Rebuttal Strategy

#### 1. Triage: Categorize Reviewer Comments

Before writing, categorize each comment:

**Category A: Valid Technical Points**
- These are correct criticisms
- Response: Acknowledge, fix, show results

**Category B: Misunderstandings**
- Reviewer misunderstood your paper
- Response: Clarify, provide additional explanation

**Category C: Disagreements**
- You disagree with the reviewer
- Response: Provide evidence, explain your reasoning

**Category D: Missing Information**
- Reviewer asks for information you have but didn't include
- Response: Provide the information directly

**Category E: Unfair Reviews**
- Reviewer is incorrect or unreasonable
- Response: Politely correct with evidence

#### 2. Prioritize: Address High-Impact Issues First

Prioritize in this order:
1. Issues raised by multiple reviewers
2. Fatal flaws (if any)
3. Major issues that affect scores
4. Questions that block understanding
5. Minor issues and suggestions

#### 3. Structure: Follow the Template

Use a clear structure:
- Thank reviewers for feedback
- Address each reviewer separately
- Group similar concerns across reviewers
- Be specific and concise
- Provide evidence (new experiments, references)

### Tone Guidelines

**Do:**
- Be professional and respectful
- Acknowledge valid criticism
- Show appreciation for feedback
- Be specific and evidence-based
- Be concise but complete

**Don't:**
- Be defensive or dismissive
- Attack reviewers personally
- Make promises you can't keep
- Be vague or hand-wavy
- Ignore concerns

### Response Types

#### Type 1: Agree + Fix

When the reviewer is right, acknowledge and show the fix.

**Template:**
```
We thank the reviewer for this important point. [Acknowledge the issue]. We have [describe the fix]. [Show evidence: new results, additional experiments].
```

#### Type 2: Disagree + Explain

When you disagree, provide evidence and reasoning.

**Template:**
```
We respectfully disagree with this assessment because [reason]. [Provide evidence: references, experiments, theoretical justification]. [Clarify any misunderstanding].
```

#### Type 3: Clarify Misunderstanding

When the reviewer misunderstood, clarify without being condescending.

**Template:**
```
We apologize for the unclear presentation. [Clarify the point]. Specifically, [explain what you actually did/claimed]. We have revised Section X to make this clearer.
```

#### Type 4: Additional Experiments

When you need to add experiments.

**Template:**
```
We thank the reviewer for this suggestion. We have conducted the requested experiment: [describe experiment]. Results show [findings]. [Explain how this addresses the concern].
```

## Rebuttal Template

```markdown
# Author Response

We thank all reviewers for their detailed and constructive feedback. We address each reviewer's concerns below.

## Response to Reviewer 1

### [Topic 1 from Reviewer 1]

**Reviewer Concern:** [Quote or paraphrase the concern]

**Our Response:**
[Your response, following one of the response types above]

[If applicable: New results or experiments]

### [Topic 2 from Reviewer 1]

[Same structure]

---

## Response to Reviewer 2

[Same structure as Reviewer 1]

---

## Response to Reviewer 3

[Same structure as Reviewer 1]

---

## Summary of Changes

Based on reviewer feedback, we have made the following improvements:

1. [Change 1 with brief description]
2. [Change 2 with brief description]
3. [Change 3 with brief description]

[If space permits: Address concerns raised by multiple reviewers in a joint response]

## Joint Response to Common Concerns

Several reviewers raised concerns about [common topic]. We address these together:

[Unified response to shared concerns]
```

## Example Rebuttals

### Good Example (Addressing Valid Criticism)

**Reviewer Concern (W1):**
"The comparison with AdamW is missing. This is a critical baseline that should be included."

**Response:**
```
We thank the reviewer for this important suggestion. We agree that AdamW is a critical baseline. We have added AdamW to all experiments and provide the updated results below.

**Updated Table 1 (CIFAR-10):**
| Method | Accuracy |
|--------|----------|
| SGD | 93.2% |
| Adam | 93.8% |
| AdamW | 94.1% |
| **Ours** | **94.8%** |

Our method still outperforms AdamW by 0.7%, confirming the contribution. The improvement is consistent across all benchmarks (see updated Tables 2-3 in the revised paper).

We note that the improvement over AdamW is smaller than over Adam, which we now discuss in Section 4.4. The key advantage of our method is [specific advantage], which is not captured by AdamW's weight decay.
```

**Why this is good:**
- Acknowledges the valid point
- Provides concrete new results
- Shows the contribution still holds
- Discusses implications
- References specific tables

### Good Example (Clarifying Misunderstanding)

**Reviewer Concern:**
"The theoretical analysis assumes Lipschitz continuity (Assumption 2), but the experiments use ReLU networks which are not Lipschitz."

**Response:**
```
We apologize for the unclear presentation. The Lipschitz assumption is not about the activation function but about the loss landscape. Specifically:

1. **Assumption clarification:** Assumption 2 states that the loss function L(θ) is L-smooth (i.e., ∇L is L-Lipschitz). This is a standard assumption in optimization theory (see [reference 1, 2, 3]) and holds for ReLU networks with bounded inputs and weights.

2. **Why it holds:** While individual ReLU units are not Lipschitz, the composition of ReLU layers with bounded weights results in a Lipschitz continuous function (see [reference 4], Theorem 3.1). Our experiments use weight decay, which bounds the weights and ensures the assumption holds.

3. **Empirical validation:** We have added an experiment measuring the actual smoothness of the loss landscape during training (new Figure 4). The measured smoothness constant L remains bounded, confirming the assumption.

We have revised Section 2.1 to make this clearer and added the new Figure 4 to the paper.
```

**Why this is good:**
- Polite clarification
- Specific technical explanation
- References to support the point
- New empirical evidence
- Shows paper revision

### Good Example (Disagreeing with Evidence)

**Reviewer Concern:**
"The improvement of 0.5% is not significant and may be within noise margins."

**Response:**
```
We respectfully disagree that the improvement is within noise margins. We provide additional evidence:

1. **Statistical significance:** The improvement is statistically significant with p < 0.01 (paired t-test over 5 runs). We have added this analysis to Table 1.

2. **Consistency:** The improvement is consistent across all 3 benchmarks (CIFAR-10: +0.5%, CIFAR-100: +0.6%, ImageNet: +0.4%). Random noise would not be consistent across datasets.

3. **Effect size:** While 0.5% may seem small, on CIFAR-10 this represents a 7.7% relative error reduction (from 6.5% to 6.0% error rate). This is significant for this benchmark where improvements are hard to achieve.

4. **Practical impact:** In production systems, 0.5% accuracy improvement can translate to [specific business/scientific impact].

We acknowledge the improvement is modest but argue it is meaningful for this established benchmark.
```

**Why this is good:**
- Respectful disagreement
- Multiple lines of evidence
- Statistical significance
- Contextualizes the improvement
- Acknowledges limitations

### Bad Example (What NOT to Do)

**Reviewer Concern:**
"The novelty is limited. This is just an incremental improvement over [existing method]."

**Response:**
```
We disagree. Our method is fundamentally different from [existing method]. The reviewer clearly did not understand our contribution. We suggest the reviewer read our paper more carefully.
```

**Why this is bad:**
- Defensive and dismissive
- Personal attack on reviewer
- No evidence provided
- No explanation of the difference
- Will not change the reviewer's mind
- May antagonize the reviewer

### Better Version of the Bad Example

**Response:**
```
We thank the reviewer for this concern and apologize if the distinction was not clear. We clarify the key differences below:

**Difference 1:** [Existing method] uses [approach A], while our method uses [approach B]. This matters because [reason with evidence].

**Difference 2:** [Existing method] requires [assumption/condition], while our method works without this. This is important because [reason].

**Empirical comparison:** We have added a direct comparison with [existing method] in Table 2, showing our method achieves [improvement] because of these differences.

We have revised Section 2 (Related Work) to more clearly position our contribution against [existing method].
```

**Why this is better:**
- Professional and respectful
- Specific technical differences
- Evidence provided
- Shows paper improvement
- Likely to change reviewer's mind

## Handling Specific Scenarios

### Scenario 1: Reviewer Asks for Experiments You Can't Do

**Response Strategy:**
```
We appreciate this suggestion. Due to [resource constraints / ethical considerations / data availability], we cannot perform this exact experiment. However, we provide the following alternative:

[Describe alternative experiment that addresses the same concern]

Results show [findings], which addresses the reviewer's concern about [specific issue].
```

### Scenario 2: Reviewers Disagree with Each Other

**Response Strategy:**
```
We note that Reviewer X and Reviewer Y have different views on [topic].

Reviewer X suggests [X's position], while Reviewer Y suggests [Y's position].

We believe both perspectives have merit and have addressed them as follows:
- For Reviewer X's concern: [response]
- For Reviewer Y's concern: [response]

[If applicable: The difference may be due to [explanation of why they disagree]]
```

### Scenario 3: Reviewer Missed Key Information in Your Paper

**Response Strategy:**
```
We thank the reviewer for this question. This is actually addressed in our paper:

- **Section X, Paragraph Y:** [Quote or paraphrase the relevant section]
- **Table Z:** [Reference the relevant results]

We apologize if this was not clear enough. We have revised the presentation to make this more prominent in Section X.
```

### Scenario 4: Multiple Reviewers Raise the Same Concern

**Response Strategy:**
```
We address this concern, raised by Reviewers 1, 2, and 3, in a joint response.

**Shared Concern:** [Summarize the common concern]

**Our Response:**
[Unified response that addresses all reviewers' specific points]

[Provide evidence that satisfies all reviewers]
```

## Common Mistakes to Avoid

### Author Mistakes

1. **Being defensive**: "The reviewer is wrong" → "We respectfully disagree because..."
2. **Promising experiments**: "We will add this" → "We have added this with results..."
3. **Vague responses**: "We addressed this" → "We added Table X showing Y"
4. **Ignoring concerns**: Skipping hard questions while answering easy ones
5. **Overpromising**: Claiming results you can't deliver in the rebuttal period

### Structural Mistakes

1. **Too long**: Exceeding the word/page limit
2. **Too short**: Not providing enough detail
3. **Poor organization**: Mixing responses to different reviewers
4. **Missing evidence**: Making claims without support
5. **No summary**: Not listing the changes you made

## 中文版本

### 使用场景

- 在回复期内回复审稿意见
- 为NeurIPS、ICML、ICLR、ACL、CVPR撰写作者回复
- 处理不公平或不正确的审稿
- 为多位审稿人规划回复策略
- 撰写能改变审稿人分数的回复
- 培训作者掌握有效回复写作技巧

### 回复策略

#### 1. 分类：将审稿意见分类

**A类：有效的技术观点**
- 正确的批评
- 回复：承认、修复、展示结果

**B类：误解**
- 审稿人误解了你的论文
- 回复：澄清，提供额外解释

**C类：分歧**
- 你不同意审稿人
- 回复：提供证据，解释你的推理

**D类：缺失信息**
- 审稿人要求你有但未包含的信息
- 回复：直接提供信息

**E类：不公平审稿**
- 审稿人不正确或不合理
- 回复：礼貌地用证据纠正

#### 2. 优先级：优先处理高影响问题

1. 多位审稿人提出的问题
2. 致命缺陷（如果有）
3. 影响分数的重大问题
4. 阻碍理解的问题
5. 小问题和建议

#### 3. 结构：遵循模板

- 感谢审稿人反馈
- 单独处理每位审稿人
- 将跨审稿人的类似关注点分组
- 具体且简洁
- 提供证据（新实验、参考文献）

### 语气指南

**应该做的：**
- 专业且尊重
- 承认有效批评
- 对反馈表示感谢
- 基于证据且具体
- 简洁但完整

**不应该做的：**
- 防御性或轻蔑
- 人身攻击审稿人
- 做无法兑现的承诺
- 含糊或敷衍
- 忽视关注点

### 回复类型

#### 类型1：同意 + 修复
```
感谢审稿人指出这个重要问题。[承认问题]。我们已经[描述修复]。[展示证据：新结果、额外实验]。
```

#### 类型2：不同意 + 解释
```
我们尊重地不同意这个评估，因为[原因]。[提供证据：参考文献、实验、理论证明]。[澄清任何误解]。
```

#### 类型3：澄清误解
```
我们为表述不清道歉。[澄清要点]。具体来说，[解释你实际做了什么/声称了什么]。我们已修订第X节以使其更清晰。
```

#### 类型4：额外实验
```
感谢审稿人的建议。我们已进行了请求的实验：[描述实验]。结果显示[发现]。[解释这如何解决关注点]。
```
