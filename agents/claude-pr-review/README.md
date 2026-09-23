# 🤖 Claude PR Review Agent (CLI & GitHub Action)

A sub-agent for Claude Code that analyzes pull request diffs, checks for security regressions, missing tests, and maintainability concerns, and formats structured Markdown review comments with risk indicators and confidence scores.

---

## 🚀 Features

- **CLI Mode**: Review any public or private GitHub PR with a single command:
  ```bash
  python3 agents/claude-pr-review/claude_review.py --pr https://github.com/owner/repo/pull/123
  ```
- **Post Directly to GitHub**:
  ```bash
  python3 agents/claude-pr-review/claude_review.py --pr https://github.com/owner/repo/pull/123 --post-comment
  ```
- **GitHub Actions Workflow**: Auto-review incoming PRs using `.github/workflows/claude-pr-review.yml`.
- **Structured Markdown Output**:
  - 📋 Summary of changes (2–3 sentences)
  - ⚠️ Identified risks & blast radius
  - 💡 Improvement suggestions
  - 🎯 Multi-dimensional Confidence Score (High / Medium / Low)

---

## 🧪 Verified Real-World Sample Outputs

1. [Deen-Bridge/dnb-backend#470 Sample Review](sample_review_pr470.md)
2. [claude-builders-bounty/claude-builders-bounty#4451 Sample Review](sample_review_pr4451.md)
