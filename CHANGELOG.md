# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Initial release of paper-grill skills collection

## [1.0.0] - 2024-XX-XX

### Added

#### Conference Style Skills (5)
- **NeurIPS Review** (`skills/会议风格/neurips-review.md`) - NeurIPS review style with focus on reproducibility, theoretical rigor, experimental completeness
- **ICML Review** (`skills/会议风格/icml-review.md`) - ICML review style emphasizing mathematical rigor, convergence guarantees, ablation studies
- **ICLR Review** (`skills/会议风格/iclr-review.md`) - ICLR open review format with focus on representation learning and visualization
- **ACL Review** (`skills/会议风格/acl-review.md`) - ACL/NLP review style with focus on linguistic contribution, dataset quality, error analysis
- **CVPR Review** (`skills/会议风格/cvpr-review.md`) - CVPR/vision review style with focus on visual quality, ablation on architectures, benchmark comparison

#### General Reviewing Skills (3)
- **Structured Review** (`skills/通用审稿/structured-review.md`) - Universal structured review framework with scoring rubric
- **Identify Weaknesses** (`skills/通用审稿/identify-weaknesses.md`) - Systematic weakness identification with severity classification
- **Review Calibration** (`skills/通用审稿/review-calibration.md`) - Ensuring fair, consistent, and constructive reviews

#### Submission Support Skills (2)
- **Rebuttal Writing** (`skills/投稿辅助/rebuttal-writing.md`) - Writing effective author responses to reviewer comments
- **Paper Self-Review** (`skills/投稿辅助/paper-self-review.md`) - Reviewing your paper before submission

#### Documentation
- README.md (English) with skills table, conference comparison, quick start guide
- README.zh.md (Chinese) with full Chinese translation
- CONTRIBUTING.md with contribution guidelines
- SECURITY.md with security policy
- CODE_OF_CONDUCT.md with Contributor Covenant Code of Conduct
- CHANGELOG.md (this file)

#### Infrastructure
- .gitignore for Python and common development files
- MIT License
- GitHub workflows (CI)
- Issue templates
- Pull request template

## [0.1.0] - 2024-XX-XX

### Added
- Project initialization
- Basic skill structure
- Template development

---

## How to Update This Changelog

1. Add new entries under the `[Unreleased]` section
2. When releasing, move `[Unreleased]` entries to the new version
3. Update the version number and date
4. Follow the categories: Added, Changed, Deprecated, Removed, Fixed, Security

## Categories

- **Added** for new features
- **Changed** for changes in existing functionality
- **Deprecated** for soon-to-be removed features
- **Removed** for now removed features
- **Fixed** for any bug fixes
- **Security** in case of vulnerabilities
