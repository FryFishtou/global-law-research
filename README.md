# global-law-research
Structured workflow for global legal research — layered retrieval of Chinese secondary materials, English authoritative guidelines, law firm commentaries, AI-assisted searches, and local language materials, covering legal issue research in over 180 jurisdictions.
# Global Law Research Skill

[中文版](README_CN.md)

Claude Code skill for researching global law questions — structured workflow from Chinese/English resources to AI-assisted research.

Based on the methodology from [快速检索外国法问题：从中英文资料到AI的全方位指南！](https://mp.weixin.qq.com/s/5Bf6_KcCJ4XsRHq2NYPzOg) by 文刀二中.

## What It Does

A problem-oriented research assistant that helps you find reliable answers to global law questions efficiently. Instead of systematic academic study, it focuses on getting you to the right resource for your specific jurisdiction and legal topic.

### Core Features

- **Source Authority Hierarchy (L1-L4)** — Distinguishes primary law, authoritative guides, firm commentary, and AI-generated leads
- **Certainty Labels** — Tags information as `[法规原文]` `[权威指南]` `[一般评论]` `[待验证]` to prevent certainty inflation
- **Timeliness Sensitivity** — Flags rapidly evolving areas (sanctions, data privacy) vs stable domains (contract law principles)
- **Smart Navigation** — Uses WebSearch/WebFetch to verify resource links and extract table of contents, without summarizing legal content (avoids hallucination risk)
- **Topic-Resource Matching** — Maps 13 legal topics to their best specialized resources
- **Dual Research Paths** — Quick overview or comprehensive research report, user chooses
- **Word Output** — Generates law-firm-style .docx reports with proper footnotes via `document-skills:docx`

### Resource Coverage

**Free English Guides (L2):**
Chambers Practice Guides | Legal500 | ICLG | Lex Mundi | Doing Business series

**Specialized Databases:**
DLA Piper Data Protection | UNCTAD Investment Policy | WIPO Lex | ILO NATLEX | EUR-Lex | Global-Regulation.com

**Chinese Sources:**
商务部国别指南 | 金杜/中伦/走出去智库等大所公众号

**Regional Databases for Thin-Coverage Jurisdictions:**
AfricanLII | PacLII | SICE/OAS | EBRD

## Installation

Copy the `global-law-research/` directory into your Claude Code skills path:

```bash
cp -r global-law-research/ ~/.claude/skills/
```

Or reference it directly in your Claude Code configuration.

## File Structure

```
global-law-research/
├── SKILL.md                      # Main skill: workflow + methodology
└── references/
    └── resources.md              # Resource database with URLs, access info, search templates
```

## Usage

Trigger the skill by asking about global law in any form:

- "越南外商投资法的基本规定是什么？"
- "What are data protection requirements in Brazil?"
- "帮我调研一下沙特的公司法框架"
- "Compare labor law in Vietnam, Thailand and Indonesia"

The skill will ask you to choose:

1. **Jurisdiction** and **legal topic(s)** (single, multiple, or comprehensive)
2. **Quick overview** or **comprehensive research report**

Then deliver findings with footnoted sources.

## Output Format

- Substantive legal analysis first, resource links in footnotes
- Footnote format: `[^1]: Source Name — Title, URL`
- Optional Word (.docx) export in law firm style

## Methodology

Inspired by [deep-research](https://github.com/wshuyi/deep-research) 8-step methodology, adapted for legal research:

| Mechanism                | Application                                                  |
| ------------------------ | ------------------------------------------------------------ |
| Source Authority (L1-L4) | Legal source hierarchy: statutes > guides > firm articles > AI |
| Certainty Labels         | Never upgrade "may require" to "requires"                    |
| Timeliness Grading       | Sanctions law (3-6 months) vs contract principles (stable)   |
| Question Decomposition   | Break "set up factory in Vietnam" into sub-questions         |

## License

MIT

Copyright (c) 2026 Chong Liu

Additional Copyrights and Modifications:

Copyright (c) 2026 FryFishCN
