# Resume Studio

End-to-end resume improvement and resume artifact generation.

`resume-studio` is designed for users who want more than resume bullet cleanup. It improves the writing, aligns the content to a target role, and can produce a polished single-page A4 resume as HTML and PDF.

## What it does

- Rewrites and tightens resume copy
- Tailors resumes to a job description
- Converts existing resume PDFs or raw text into stronger structured resume content
- Produces ATS-friendly resume variants
- Creates designed HTML resumes
- Exports render-balanced A4 single-page PDFs
- Optimizes layout density to avoid obvious bottom whitespace

## Best fit

This skill is especially useful when the user wants a finished deliverable instead of general advice.

Typical prompts:

- "Tailor my resume to this staff frontend job."
- "Turn this PDF resume into a better single-page A4 PDF."
- "Make my resume ATS-friendly, then give me a designed version too."
- "I want a resume that looks polished but opens quickly as a PDF."

## Output modes

- `ATS mode`: low-styling, recruiter-system-friendly
- `Balanced PDF mode`: default design output, polished without heavy rendering cost
- `Fast-open PDF mode`: optimized for viewer speed and compatibility
- `Content-only mode`: revised resume text without a designed artifact

## Design philosophy

The skill treats resumes as both content and layout problems.

It improves the words first, then chooses a design direction appropriate to the candidate, then builds a print-oriented A4 HTML resume before exporting PDF. It bundles the full `frontend-design` guidance locally so the design workflow remains self-contained and does not depend on a separately installed skill.

Its resume-content tailoring workflow is based on `tailored-resume-generator`, then extended with artifact-generation and PDF-quality rules specific to `resume-studio`.

## Packaging notes

Core files:

- `SKILL.md`
- `references/resume-design.md`
- `evals/evals.json`

This skill is intended for public distribution on `skills.sh`, so the trigger description is intentionally broad enough to catch resume rewriting, resume design, and resume PDF generation tasks.
