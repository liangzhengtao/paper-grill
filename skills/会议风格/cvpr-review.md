# CVPR/Vision Review Style

Mimic the review style and standards of CVPR (Computer Vision and Pattern Recognition) conferences including CVPR, ICCV, and ECCV. Generate rigorous reviews with computer vision-specific evaluation criteria.

## When to Use

- Reviewing computer vision papers targeting CVPR, ICCV, or ECCV submission
- Evaluating papers on image recognition, object detection, segmentation, 3D vision
- Reviewing papers with visual quality assessment and qualitative results
- Preparing rebuttals for CVPR-style reviewer feedback
- Self-reviewing vision papers before submission

## Review Framework

### CVPR Review Structure

Every CVPR review must contain:

1. **Summary** (1 paragraph)
   - Restate the paper's contributions
   - Identify the vision task and approach
   - Describe key results

2. **Strengths** (bullet points)
   - Novelty in architecture or method
   - Quality of visual results
   - Comprehensive ablation studies
   - Benchmark performance
   - Clarity of presentation

3. **Weaknesses** (bullet points)
   - Architecture concerns
   - Missing comparisons or experiments
   - Visual quality issues
   - Reproducibility problems
   - Overclaims

4. **Questions for Authors**
   - Technical questions about architecture/design choices
   - Questions about visual results
   - Questions about experimental methodology
   - Questions about generalizability

5. **Detailed Comments**
   - Section-by-section feedback
   - Specific suggestions for figures and visualizations
   - Corrections to claims or methodology

6. **Score** (1-10)
7. **Confidence** (1-5)

### CVPR Scoring Rubric

| Score | Label | Description |
|-------|-------|-------------|
| 10 | Strong Accept | Exceptional paper, likely best paper candidate |
| 9 | Accept | Excellent paper, clear accept |
| 8 | Accept | Good paper, above acceptance threshold |
| 7 | Weak Accept | Decent paper with some concerns |
| 6 | Borderline | Mixed quality |
| 5 | Weak Reject | Below threshold |
| 4 | Reject | Significant issues |
| 3 | Strong Reject | Major flaws |
| 2 | Very Strong Reject | Fundamental problems |
| 1 | Clear Reject | Should not be published |

### Computer Vision Specific Criteria

#### 1. Visual Quality Assessment

For CV papers, visual results are crucial:

**Qualitative Evaluation:**
- [ ] Are visual results shown for diverse examples (not cherry-picked)?
- [ ] Are failure cases shown and discussed?
- [ ] Are comparisons with baselines visualized side-by-side?
- [ ] Are attention maps, feature visualizations, or intermediate results shown?
- [ ] Do visual results support the quantitative claims?

**Image Quality Metrics:**
- PSNR, SSIM (image restoration)
- FID, IS (generation)
- LPIPS (perceptual similarity)
- mAP (detection)
- mIoU (segmentation)

#### 2. Architecture Analysis

For papers proposing new architectures:

- [ ] Are design choices justified with ablation studies?
- [ ] Is the architecture complexity analyzed (parameters, FLOPs)?
- [ ] Are visualizations of learned features provided?
- [ ] Is the architecture compared fairly with baselines (same data, compute)?
- [ ] Are failure modes analyzed?

#### 3. Ablation Studies

CVPR papers require thorough ablation:

- [ ] Each component of the method is ablated individually
- [ ] Ablations are on a standard benchmark (not toy examples)
- [ ] Ablation results are presented clearly (tables and/or figures)
- [ ] The contribution of each design choice is quantified
- [ ] Ablations justify the final architecture choices

#### 4. Benchmark Evaluation

- [ ] Standard benchmarks are used (ImageNet, COCO, etc.)
- [ ] Multiple benchmarks are used (not just one)
- [ ] State-of-the-art comparisons are recent (last 2 years)
- [ ] Evaluation metrics are standard for the task
- [ ] Results are reproducible (random seeds, hardware specified)

## Review Template

```markdown
# CVPR 2024 Review - Paper [ID]

## Summary

[Paper ID: XXXX]

This paper proposes [method/architecture name] for [vision task]. The key contribution is [describe core technical contribution]. The authors [describe methodology in 2-3 sentences, including architecture design, loss functions, training procedures]. Experiments on [benchmarks/datasets] demonstrate [claimed improvements]. Visual results show [describe visual quality].

## Strengths

- **S1:** [Novelty] [What is novel about the architecture/method?]
- **S2:** [Visual Quality] [How good are the visual results?]
- **S3:** [Ablation] [How thorough are the ablation studies?]
- **S4:** [Benchmarks] [How strong are the benchmark results?]
- **S5:** [Presentation] [Quality of figures, clarity of writing]

## Weaknesses

- **W1:** [Architecture Issues] [Problems with the proposed architecture]
- **W2:** [Missing Experiments] [What experiments are missing?]
- **W3:** [Visual Quality] [Issues with visual results]
- **W4:** [Fairness] [Are comparisons fair? Same data/compute?]
- **W5:** [Overclaims] [Where claims exceed evidence]

## Questions for Authors

1. [Question about architecture design choice]
2. [Question about visual results or failure cases]
3. [Question about experimental methodology]
4. [Question about generalizability or limitations]

## Detailed Comments

### Section 2 (Related Work)
- Missing comparison with [important recent work]
- The positioning against [method] needs clarification

### Section 3 (Method)
- Figure 2: The architecture diagram needs more detail - what are the channel dimensions?
- Equation 5: The loss function weighting λ is not justified. How was this value chosen?

### Section 4 (Experiments)
- Table 1: Missing comparison with [SOTA method] which reported [better results on same benchmark]
- Figure 4: The qualitative comparison cherry-picks favorable examples. Show failure cases too.
- Ablation (Table 3): Missing ablation on [key component]

## Score: [1-10]

[2-3 sentence justification]

## Confidence: [1-5]

[1 sentence about CV expertise]
```

## Example Reviews

### Good Example (Image Generation Paper, Score: 7)

```markdown
## Summary

This paper proposes "Frequency-Aware Diffusion Model" (FADM) for high-resolution image generation. The key insight is that diffusion models struggle with high-frequency details, and the authors propose a frequency-domain loss that operates on wavelet-transformed images. The method adds a multi-scale frequency discriminator that guides the diffusion process to generate sharper details. Experiments on FFHQ 1024×1024, LSUN Bedroom, and ImageNet 256×256 show improvements in FID and perceptual quality.

## Strengths

- **S1 (Novelty):** The frequency-domain approach is well-motivated and novel. The connection between diffusion model artifacts and high-frequency loss (Section 2.2, Figure 1) is insightful. The wavelet-based discriminator (Equation 8) is a creative solution.
- **S2 (Visual Quality):** Figure 3 shows compelling visual improvements, especially in textures (hair, fabric patterns) and fine details (eyes, text). The 1024×1024 face results (Figure 5) are impressive with sharp details.
- **S3 (Ablation):** Table 3 provides thorough ablation of each component (frequency loss, wavelet discriminator, multi-scale). The contribution of each component is clearly quantified. Figure 7 ablates the number of wavelet decomposition levels.
- **S4 (Benchmarks):** FID improvements are consistent across datasets: FFHQ (3.21→2.87), LSUN (2.95→2.71), ImageNet (3.94→3.62). These are meaningful improvements over strong baselines.
- **S5 (Presentation):** The paper is well-written with clear figures. The architecture diagram (Figure 2) is detailed and the training procedure (Algorithm 1) is clear.

## Weaknesses

- **W1 (Compute Analysis):** The multi-scale frequency discriminator adds significant parameters and compute. Table 2 reports FLOPs but not training time or GPU memory. For diffusion models that already require days to train, this overhead matters. A comparison at equal compute (train baseline longer) is needed.
- **W2 (Limited Resolution):** Experiments go up to 1024×1024 but the paper claims "high-resolution" generation. Recent work on 2048×2048 and 4K generation exists. How does FADM scale? The memory overhead of wavelet transforms at higher resolutions should be discussed.
- **W3 (Failure Cases):** Figure 4 shows 2 failure cases, but the analysis is superficial ("the model sometimes generates blurry backgrounds"). What types of content does the frequency loss hurt? Are there systematic failure modes (e.g., smooth regions, sky, water)?
- **W4 (Baseline Fairness):** The baseline diffusion model uses the default configuration from [citation], but FADM adds a complex training pipeline. A fair comparison should use the same total training compute for both. Also, the baseline doesn't use the same wavelet preprocessing.
- **W5 (Cherry-picking):** Figure 3 shows favorable examples. The supplementary should include random samples, not selected ones. The FID improvement is modest (0.3-0.4) and may not be perceptually significant in many cases.

## Questions for Authors

1. The frequency discriminator (Section 3.2) uses Haar wavelets. Have you explored other wavelet families (Daubechies, Morlet)? Is the method sensitive to this choice?
2. Table 1 shows FID but not IS, precision, or recall. For generation quality assessment, precision/recall curves would show whether the model improves fidelity, diversity, or both. Can you add these metrics?
3. The training procedure (Algorithm 1) alternates between diffusion and discriminator training. Is this stable? Have you observed mode collapse or training instabilities? What is the sensitivity to the training ratio?
4. How does FADM interact with different diffusion architectures? Experiments use only U-Net. Would it work with DiT or other transformer-based diffusion models?

## Detailed Comments

### Section 2
- Figure 1: The frequency analysis is compelling but only shows one image. A statistical analysis across many images would be stronger.

### Section 3
- Equation 8: The wavelet discriminator loss uses L1 norm. Have you tried L2 or perceptual loss? Justify the choice.
- Figure 2: The multi-scale architecture needs channel dimension annotations.

### Section 4
- Table 1: Add inference time comparison. Diffusion models are slow; if FADM adds inference overhead, that's a concern.
- Figure 5: The 1024×1024 results are impressive but cherry-picked. Add random samples in supplementary.

## Score: 7

The paper presents a novel frequency-domain approach to diffusion with solid visual improvements. The ablation is thorough and the results are consistent. However, compute analysis is incomplete and the baseline comparison may not be fair. The modest FID improvement needs better justification through perceptual studies or precision/recall analysis.

## Confidence: 4

I have published on generative models and image synthesis. I am familiar with diffusion model evaluation.

## Overall Assessment

I lean toward acceptance if the authors address the compute fairness concern in the rebuttal. The frequency-domain insight is valuable and the visual improvements are real. The key question is whether the improvement justifies the added complexity. A compute-matched comparison and precision/recall analysis would significantly strengthen the paper.
```

### Bad Example (What NOT to Do)

```markdown
## Summary

Paper does image generation with frequency stuff. Results look okay.

## Weaknesses
- FID improvement is small
- Lots of extra computation
- Only tested on faces

## Score: 4

Not good enough for CVPR.
```

**Problems:**
- Doesn't demonstrate understanding of the frequency-domain contribution
- "Results look okay" is not an assessment of visual quality
- "Small FID" ignores the consistent improvements across datasets
- "Only faces" is wrong - they test on LSUN and ImageNet too
- No strengths section
- Missing ablation discussion
- No questions for authors
- Score not justified

## CVPR-Specific Review Guidelines

### Image Generation Papers

- Check FID, IS, precision, recall
- Visual quality assessment (not just metrics)
- Diversity of generated samples
- Training stability and reproducibility
- Compute requirements

### Object Detection Papers

- mAP on standard benchmarks (COCO, Pascal VOC)
- AP at different IoU thresholds
- Inference speed (FPS)
- Anchor design analysis
- Failure case analysis

### Segmentation Papers

- mIoU on standard benchmarks
- Per-class IoU analysis
- Boundary quality assessment
- Inference speed
- Generalization across datasets

### 3D Vision Papers

- 3D reconstruction quality
- Novel view synthesis metrics
- Geometric accuracy
- Real-world applicability
- Computational requirements

## Common Mistakes to Avoid

### Reviewer Mistakes
1. **Only looking at numbers**: Visual quality matters, not just FID/mAP
2. **Ignoring compute**: Fair comparison requires equal compute
3. **Missing ablation**: Ablation studies are essential for CV papers
4. **Cherry-picking acceptance**: Evaluate on diverse examples, not just shown ones
5. **Outdated baselines**: Comparing with 2-year-old methods isn't fair

### Author Mistakes
1. **Cherry-picked results**: Show random samples, not just best cases
2. **Missing failure cases**: Always discuss limitations and failures
3. **Unfair baselines**: Compare with recent methods at equal compute
4. **No ablation**: Always ablate your design choices
5. **Metrics only**: Include qualitative evaluation alongside metrics

## 中文版本

### 使用场景

- 审稿面向CVPR、ICCV、ECCV投稿的计算机视觉论文
- 评估图像识别、目标检测、分割、3D视觉方面的论文
- 审稿具有视觉质量评估和定性结果的论文
- 准备针对CVPR风格审稿意见的作者回复
- 在投稿前自审视觉论文

### CVPR审稿结构

每篇CVPR审稿必须包含：

1. **摘要**（1段）- 重新表述论文贡献、视觉任务和方法、关键结果
2. **优点**（要点列表）- 架构新颖性、视觉结果质量、全面消融研究、基准性能、表述清晰度
3. **缺点**（要点列表）- 架构问题、缺失比较或实验、视觉质量问题、可复现性问题
4. **作者提问**- 关于架构/设计选择、视觉结果、实验方法论的技术问题
5. **详细评论**- 逐节反馈、图表和可视化建议
6. **评分**（1-10分）
7. **置信度**（1-5分）

### 计算机视觉特定评估标准

#### 1. 视觉质量评估
**定性评估：**
- [ ] 是否展示了多样化样本的视觉结果（非精选）？
- [ ] 是否展示并讨论了失败案例？
- [ ] 是否与基线进行了并排比较可视化？
- [ ] 是否展示了注意力图、特征可视化或中间结果？
- [ ] 视觉结果是否支持定量声明？

**图像质量指标：** PSNR、SSIM（图像修复）、FID、IS（生成）、LPIPS（感知相似度）、mAP（检测）、mIoU（分割）

#### 2. 架构分析
- [ ] 设计选择是否有消融研究支持？
- [ ] 架构复杂度是否分析（参数、FLOPs）？
- [ ] 是否提供学习特征的可视化？
- [ ] 与基线的比较是否公平（相同数据、计算量）？

#### 3. 消融研究
- [ ] 方法的每个组件是否单独消融？
- [ ] 消融是否在标准基准上进行（非玩具示例）？
- [ ] 消融结果是否清晰呈现（表格和/或图表）？
- [ ] 每个设计选择的贡献是否量化？

### 评分标准

| 分数 | 标签 | 说明 |
|------|------|------|
| 10 | 强接受 | 杰出论文，可能是最佳论文候选 |
| 9 | 接受 | 优秀论文，明确接受 |
| 8 | 接受 | 好论文，超过接受阈值 |
| 7 | 弱接受 | 不错论文但有顾虑 |
| 6 | 边界线 | 质量混合 |
| 5 | 弱拒绝 | 低于阈值 |
| 4 | 拒绝 | 重大问题 |
| 3 | 强拒绝 | 主要缺陷 |
| 2 | 很强拒绝 | 根本性问题 |
| 1 | 明确拒绝 | 不应发表 |
