# ACL/NLP Review Style

Mimic the review style and standards of ACL (Association for Computational Linguistics) conferences including ACL, EMNLP, and NAACL. Generate rigorous reviews with NLP-specific evaluation criteria.

## When to Use

- Reviewing NLP papers targeting ACL, EMNLP, NAACL, or EACL submission
- Evaluating papers on language models, machine translation, text generation, information extraction
- Reviewing papers with NLP-specific evaluation (BLEU, ROUGE, human evaluation)
- Preparing rebuttals for ACL-style reviewer feedback
- Self-reviewing NLP papers before submission

## Review Framework

### ACL Review Structure

Every ACL review must contain:

1. **Summary** (1 paragraph)
   - Restate the paper's contributions
   - Identify the NLP task and approach
   - Describe key results

2. **Assessment of the Paper**
   - **Strengths** (bullet points)
     - Linguistic contribution
     - Technical novelty
     - Dataset/resource contribution
     - Evaluation methodology
     - Error analysis quality

   - **Weaknesses** (bullet points)
     - Missing linguistic analysis
     - Evaluation concerns
     - Dataset issues
     - Reproducibility problems
     - Overclaims

3. **Questions for Authors**
   - Technical questions about the method
   - Questions about linguistic phenomena
   - Questions about evaluation methodology
   - Questions about dataset construction

4. **Limitations**
   - Discuss linguistic limitations
   - Language coverage limitations
   - Potential biases in data or models
   - Ethical considerations

5. **Typos and Minor Issues**
   - List specific typos, formatting issues
   - Reference errors
   - Notation inconsistencies

6. **Overall Assessment and Score** (1-6 scale)
7. **Confidence** (1-5 scale)

### ACL Scoring Rubric

| Score | Label | Description |
|-------|-------|-------------|
| 6 | Strong Accept | Excellent paper, clear accept |
| 5 | Accept | Good paper, above acceptance threshold |
| 4 | Weak Accept | Decent paper with some concerns |
| 3 | Weak Reject | Below threshold, concerns outweigh strengths |
| 2 | Reject | Significant issues, clear reject |
| 1 | Strong Reject | Major flaws, fundamental problems |

### NLP-Specific Evaluation Criteria

#### 1. Linguistic Contribution

Evaluate whether the paper advances our understanding of language:

- Does the paper identify or address a specific linguistic phenomenon?
- Does the analysis provide insights into how models handle language?
- Are linguistic intuitions supported by evidence?
- Does the work generalize across languages or is it English-only?

#### 2. Evaluation Methodology

For NLP papers, evaluation must be rigorous:

**Automatic Metrics:**
- BLEU (machine translation)
- ROUGE (summarization)
- Perplexity (language modeling)
- F1 (information extraction, NER, etc.)
- Exact Match (question answering)
- BERTScore, BLEURT (generation quality)

**Human Evaluation:**
- Inter-annotator agreement (κ or Krippendorff's α)
- Annotation guidelines provided
- Diverse annotator pool
- Statistical significance tests
- Evaluation dimensions clearly defined (fluency, adequacy, coherence)

**Checklist:**
- [ ] Are automatic metrics appropriate for the task?
- [ ] Is human evaluation conducted for generation tasks?
- [ ] Are multiple evaluation metrics reported (not just one)?
- [ ] Are statistical significance tests performed?
- [ ] Is the evaluation set representative and not cherry-picked?

#### 3. Dataset Quality

For papers introducing datasets:

- [ ] Is the data collection methodology described?
- [ ] Are annotation guidelines provided?
- [ ] Is inter-annotator agreement reported?
- [ ] Is the dataset diverse and representative?
- [ ] Are biases in the data acknowledged?
- [ ] Is the dataset publicly available?
- [ ] Is the data license specified?

#### 4. Error Analysis

Strong NLP papers include error analysis:

- What types of errors does the model make?
- Are there patterns in failures (e.g., long sentences, rare words)?
- How do errors correlate with linguistic phenomena?
- What can we learn from the errors?

## Review Template

```markdown
# ACL 2024 Review - Paper [ID]

## Summary

[Paper ID: XXXX]

This paper addresses [NLP task] by proposing [method/approach]. The key contribution is [describe main contribution - method, dataset, analysis]. The authors [describe methodology in 2-3 sentences]. Experiments on [datasets/benchmarks] show [main results]. The paper provides [linguistic analysis/insights] showing [findings about language/model behavior].

## Assessment

### Strengths

- **S1:** [Linguistic Contribution] [What linguistic insights does the paper provide?]
- **S2:** [Technical Approach] [What is novel about the method?]
- **S3:** [Evaluation] [How is evaluation conducted rigorously?]
- **S4:** [Error Analysis] [What insights come from error analysis?]
- **S5:** [Resources] [Does the paper contribute datasets, tools, or resources?]

### Weaknesses

- **W1:** [Linguistic Gap] [What linguistic analysis is missing?]
- **W2:** [Evaluation Issues] [Problems with metrics, baselines, or human eval]
- **W3:** [Dataset Concerns] [Issues with data quality, bias, or representativeness]
- **W4:** [Reproducibility] [Missing details for reproduction]
- **W5:** [Overclaims] [Where claims exceed evidence]

## Questions for Authors

1. [Question about linguistic phenomena or analysis]
2. [Question about evaluation methodology]
3. [Question about dataset construction or quality]
4. [Question about generalizability across languages/domains]

## Limitations

[Discuss linguistic limitations, language coverage, potential biases, ethical considerations. Be specific about what the paper does NOT cover.]

## Typos and Minor Issues

- Page X, Line Y: [specific typo or error]
- Table X: [formatting issue]
- Reference [N]: [citation error]

## Overall Assessment

### Score: [1-6]

[2-3 sentence justification focusing on linguistic contribution, technical quality, and evaluation rigor]

### Confidence: [1-5]

[1 sentence about NLP expertise]

### Final Comments

[Clear recommendation with specific conditions for acceptance]
```

## Example Reviews

### Good Example (Machine Translation Paper, Score: 5)

```markdown
## Summary

This paper proposes "Linguistically-Informed Attention" (LIA) for neural machine translation, which incorporates syntactic dependency information into the transformer architecture. The key idea is to bias the self-attention mechanism using dependency parse trees, allowing the model to focus on syntactically relevant tokens. Experiments on WMT English-German and English-French benchmarks show improvements of +0.8 BLEU and +0.6 BLEU respectively. The paper also provides analysis of attention patterns showing that LIA produces more linguistically plausible attention distributions.

## Assessment

### Strengths

- **S1 (Linguistic Motivation):** The paper is well-motivated linguistically. The argument that standard attention may miss syntactic dependencies (Section 2.1) is compelling and supported by linguistic theory. The connection to formal language theory (Theorem 1) provides theoretical grounding.
- **S2 (Technical Approach):** The dependency-aware attention mask (Equation 7) is elegantly designed. It's a minimal modification to standard attention that can be dropped in to existing architectures.
- **S3 (Evaluation):** The paper reports BLEU, chrF++, and COMET metrics, which is good practice. Statistical significance tests (paired bootstrap resampling) are conducted. The evaluation includes multiple language pairs.
- **S4 (Error Analysis):** Table 4 provides a detailed error taxonomy showing improvements in syntactic phenomena (agreement, long-distance dependencies). This is exactly the kind of analysis NLP papers should include.
- **S5 (Reproducibility):** Code and data are available. Hyperparameters are detailed in Appendix A.

### Weaknesses

- **W1 (Language Coverage):** The evaluation is limited to European languages (En-De, En-Fr, En-Ro). Given that the method relies on dependency parsing, performance on morphologically rich languages (Turkish, Finnish) or languages with free word order (Japanese, Korean) would strengthen the claims. How does LIA perform when the parser quality degrades for low-resource languages?
- **W2 (Parser Dependency):** The method requires dependency parses as input. The paper acknowledges this (Section 4.3) but doesn't fully analyze the impact. What happens when the parser makes errors? An experiment with noisy parses would be valuable. Additionally, many low-resource languages lack high-quality parsers.
- **W3 (Automatic Metrics Only):** While BLEU, chrF++, and COMET are reported, there is no human evaluation. For a paper making linguistic claims about translation quality, human evaluation of fluency and adequacy is essential. Automatic metrics may not capture the linguistic phenomena the paper claims to improve.
- **W4 (Baseline Fairness):** The baselines use the default transformer configuration, but LIA adds syntactic parsing overhead. A fair comparison should account for total computation time, not just model parameters. Also, the baseline lacks the preprocessing pipeline that LIA requires.
- **W5 (English-Centric):** The dependency parsing is applied only to the source side (English). For En→De translation, the German output also has syntactic structure. Why not apply LIA to the target side in an autoregressive manner?

## Questions for Authors

1. How does LIA perform on language pairs where the source language has free word order (e.g., Japanese→English)? The dependency structure is less informative when word order is flexible.
2. Table 3 shows improvements on WMT benchmarks, but these are high-resource settings. Have you evaluated on low-resource translation (e.g., IWSLT benchmarks) where linguistic priors might be more helpful?
3. The attention visualization (Figure 3) is compelling but only shows 3 examples. Can you provide quantitative analysis of attention patterns across the full test set? For example, correlation between attention weights and dependency distances.
4. What is the inference overhead of the dependency parsing step? For production MT systems, this matters.

## Limitations

The paper's main limitation is language coverage. The reliance on dependency parsing limits applicability to languages with available parsers. The paper should discuss this limitation and potential solutions (e.g., universal dependencies, multilingual parsers). Additionally, the evaluation does not assess whether LIA helps with specific challenging phenomena (e.g., idioms, metaphors) where syntax alone is insufficient.

## Typos and Minor Issues

- Page 3, Line 15: "dependecy" → "dependency"
- Table 2: Missing "±" for standard deviations on BLEU scores
- Appendix A: Reference to "Equation (12)" should be "Equation (11)"
- Figure 2: Caption is cut off

## Overall Assessment

### Score: 5

The paper makes a solid contribution with linguistically motivated modifications to NMT. The error analysis (Table 4) is a strength. However, the lack of human evaluation, limited language coverage, and insufficient analysis of parser dependency prevent a higher score.

### Confidence: 4

I have published on NMT and linguistically-informed models. I am familiar with the baselines and evaluation methodology.

### Final Comments

I lean toward acceptance if the authors can address two key concerns in the rebuttal: (1) add human evaluation for at least one language pair, and (2) provide analysis of parser error impact. The linguistic motivation is strong and the method is practical, but the evaluation needs to be more rigorous to support the linguistic claims.
```

### Bad Example (What NOT to Do)

```markdown
## Summary

This paper tries to add syntax to NMT. Not very interesting.

## Weaknesses
- BLEU improvement is small
- Only tested on 2 language pairs
- Parsing adds overhead

## Score: 2

Reject. Not enough improvement.
```

**Problems:**
- Doesn't show understanding of the paper
- "Small BLEU improvement" ignores the linguistic analysis
- "Only 2 language pairs" is not a fatal flaw for an ACL paper
- No strengths section
- Missing human evaluation concern (the real issue)
- No questions for authors
- No error analysis discussion
- Score not justified

## NLP-Specific Review Guidelines

### Machine Translation Papers

- Check evaluation metrics (BLEU alone is insufficient)
- Verify language pair coverage
- Assess human evaluation quality
- Consider domain specificity
- Check for data contamination

### Language Model Papers

- Evaluate on diverse benchmarks (not just perplexity)
- Check for training data contamination
- Assess linguistic capabilities (syntax, semantics, pragmatics)
- Consider computational cost and environmental impact
- Evaluate fairness and bias

### Text Generation Papers

- Human evaluation is essential
- Check for repetition, coherence, faithfulness
- Evaluate diverse generation (not just one sample)
- Assess controllability
- Check for hallucination

### Information Extraction Papers

- Evaluate on multiple datasets
- Check for entity/relation coverage
- Assess cross-domain generalization
- Evaluate error types
- Consider real-world applicability

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Overvaluing BLEU**: BLEU improvements of 0.5 may not be meaningful
2. **Undervaluing analysis**: Linguistic analysis is a contribution, not just numbers
3. **Ignoring human eval**: Automatic metrics are insufficient for generation tasks
4. **English-centric thinking**: Not considering multilingual challenges
5. **Missing error analysis**: Just reporting numbers without understanding errors

### Author Mistakes
1. **Only BLEU**: Report multiple metrics including human evaluation
2. **Cherry-picked examples**: Show diverse examples, including failures
3. **No error analysis**: Always analyze what your model gets wrong
4. **Ignoring linguistic theory**: NLP should be informed by linguistics
5. **English-only**: Consider multilingual evaluation

## 中文版本

### 使用场景

- 审稿面向ACL、EMNLP、NAACL投稿的NLP论文
- 评估语言模型、机器翻译、文本生成、信息抽取方面的论文
- 审稿具有NLP特定评估指标（BLEU、ROUGE、人工评估）的论文
- 准备针对ACL风格审稿意见的作者回复
- 在投稿前自审NLP论文

### ACL审稿结构

每篇ACL审稿必须包含：

1. **摘要**（1段）- 重新表述论文贡献、NLP任务和方法、关键结果
2. **论文评估**
   - 优点（要点列表）- 语言学贡献、技术新颖性、数据集贡献、评估方法论、错误分析质量
   - 缺点（要点列表）- 缺失的语言学分析、评估问题、数据集问题、可复现性问题
3. **作者提问**- 关于方法、语言现象、评估方法论的技术问题
4. **局限性**- 语言学局限性、语言覆盖局限、潜在偏见、伦理考量
5. **拼写错误和小问题**- 具体拼写错误、格式问题、引用错误
6. **总体评估和评分**（1-6分）
7. **置信度**（1-5分）

### NLP特定评估标准

#### 1. 语言学贡献
- 论文是否识别或处理特定语言现象？
- 分析是否提供关于模型如何处理语言的见解？
- 语言学直觉是否有证据支持？
- 工作是否跨语言泛化还是仅限英语？

#### 2. 评估方法论
**自动指标：** BLEU（机器翻译）、ROUGE（摘要）、困惑度（语言建模）、F1（信息抽取）
**人工评估：** 标注者间一致性、标注指南、多样化标注者池、统计显著性检验

#### 3. 数据集质量
- 数据收集方法论是否描述清楚？
- 标注指南是否提供？
- 标注者间一致性是否报告？
- 数据集是否多样且有代表性？
- 数据中的偏见是否被承认？

#### 4. 错误分析
- 模型犯什么类型的错误？
- 失败中是否有模式（如长句子、罕见词）？
- 错误是否与语言现象相关？
- 我们能从错误中学到什么？

### 评分标准

| 分数 | 标签 | 说明 |
|------|------|------|
| 6 | 强接受 | 优秀论文，明确接受 |
| 5 | 接受 | 好论文，超过接受阈值 |
| 4 | 弱接受 | 不错论文但有顾虑 |
| 3 | 弱拒绝 | 低于阈值 |
| 2 | 拒绝 | 重大问题 |
| 1 | 强拒绝 | 主要缺陷 |
