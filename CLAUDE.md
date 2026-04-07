# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

`resume-studio` is a **Claude Code skill** (not a traditional software project). It defines a resume rewriting and PDF generation pipeline that Claude Code agents execute. The entire deliverable is the skill definition and its bundled references — there is no build system, no runtime dependencies, and no package manager.

Distribution: `npx skills add https://github.com/0xMoat/resume-studio --skill resume-studio -g -y`

## Repository structure

```
skills/resume-studio/
├── SKILL.md                        # Primary skill definition (source of truth)
├── README.md                       # Installation and usage guide
├── evals/evals.json                # 3 evaluation prompts (Chinese)
└── references/
    └── resume-design.md            # Typography, color, spatial design for resume PDF
```

## How the skill works

The skill triggers when a user asks to improve, tailor, or design a resume. Core pipeline:

1. **Gather** source material (PDF/DOCX/markdown + optional job description)
2. **Analyze** job requirements → P1/P2/P3 priority classification
3. **Map** candidate experience to requirements
4. **Structure** tailored resume content (summary, skills, experience, projects, education)
5. **Optimize** for ATS and recruiter scanability
6. **Format** — content-only (markdown) or designed artifact (HTML → PDF)
7. **Provide** strategic recommendations (strengths, gaps, interview hooks)
8. **Iterate** and refine

Four output modes: `ATS`, `Balanced PDF` (default designed), `Fast-open PDF`, `Content-only`.

## Key design decisions

- **Content before design**: Always improve the resume copy before touching layout.
- **Consolidated design reference**: `references/resume-design.md` contains typography, color, and spatial design guidance scoped to resume PDF. Adapted from Anthropic's frontend-design skill (Apache 2.0).
- **Resume ≠ landing page**: Designed resumes must stay scannable, printable, recruiter-friendly. No glassmorphism, no full-page overlays, no heavy gradients.
- **Balanced PDF defaults**: 1 type family, 2–3 weights, 2–3 accent colors, simple borders/flat fills. Avoid `mask-image`, blur, transparency layers.
- **Single-page A4**: Default target. Two pages only for senior profiles with justification.
- **Truthfulness**: Never fabricate experience, metrics, or credentials.

## Editing guidelines

- `SKILL.md` is the authoritative skill definition. All workflow, content standards, and design rules live here.
- When modifying the skill workflow, keep the 8-step pipeline structure intact.
- Evals are in Chinese — maintain this convention.
- `references/resume-design.md` is a standalone reference adapted from upstream; update it directly as needed.

## Commits

Follow conventional commits: `feat(resume-studio):`, `chore(repo):`, `docs(readme):`, etc.
