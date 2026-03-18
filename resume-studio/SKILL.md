---
name: resume-studio
description: Rewrite, tailor, and design resumes end to end. Use this whenever the user wants to improve a resume or CV, adapt it to a job description, convert an existing resume file (PDF, DOCX, markdown, or plain text) into a stronger version, generate an ATS-friendly resume, or produce a polished single-page A4 resume as HTML or PDF. Trigger even for casual requests like "make my resume look better," "redo my CV," "turn this into a one-page resume," "optimize this for this role," or "export my resume as PDF" when the task is primarily about resume content plus layout. Do not use this for general portfolio website design or cover-letter-only tasks unless the resume itself is the main deliverable.
---

# Resume Studio

Upgrade resume work from "rewrite some bullets" to a complete resume pipeline:

1. Understand and improve the content.
2. Align it to the target job or target direction.
3. If a designed artifact is requested, consult `frontend-design` and create a resume-specific HTML layout.
4. Export a render-balanced A4 single-page PDF.
5. Validate density, page count, and readability before handing it back.

This skill is for both content and artifact generation. Do not stop at generic advice when the user clearly wants a finished resume.

## When to use this skill

Use this skill when the user asks for any of the following:

- Tailoring a resume for a job description
- Improving or rewriting an existing resume or CV
- Converting a resume PDF into a stronger version
- Making a resume ATS-friendly
- Generating a beautiful resume PDF or HTML
- Creating a one-page A4 resume
- Fixing weak spacing, awkward density, or ugly resume layout
- Producing multiple resume variants such as ATS, designed, balanced, or fast-open

If the user mentions a resume file, PDF, DOCX, or existing resume content and wants it improved or reformatted, use this skill.

## Output modes

Pick the output mode that matches the request. If the user does not specify, choose the best default and explain the choice briefly.

- `ATS mode`
  Best for bulk applications and recruiter systems. Simple structure, standard headings, low styling.
- `Balanced PDF mode`
  Default designed output. Preserve strong design quality while avoiding the heavy visual effects that make PDFs render slowly.
- `Fast-open PDF mode`
  Use when the user explicitly prioritizes fast opening, instant clarity, or viewer compatibility over visual flair.
- `Content-only mode`
  Use when the user only wants revised markdown/text/JSON resume content and not an artifact.

## Core workflow

### 1. Capture source material

Start from what the user already has:

- Existing resume PDF, DOCX, markdown, or plain text
- Portfolio/project descriptions
- Job description
- Notes about target role, industry, geography, or seniority

If facts are missing, ask only for high-risk gaps. Do not interrogate the user for minor polish decisions if a reasonable assumption is enough.

### 2. Normalize and improve the resume content

Turn the raw source into structured resume content first.

Always extract or produce these sections where applicable:

- Name and contact details
- Professional summary
- Skills grouped by category
- Experience
- Projects
- Education

Improve the copy before designing:

- Clarify role scope and value
- Reorder content by relevance
- Tighten weak bullets
- Use action-result phrasing
- Quantify impact when truthfully available
- Remove fluff, repetition, and vague filler
- Use exact target-role terminology when a job description exists

For experience bullets, prefer:

`[Action] + [What] + [How] + [Result or value]`

### 3. Analyze the target

If a job description is provided, classify requirements:

| Priority | Meaning |
|----------|---------|
| P1 | Must-have qualifications, deal-breakers, keywords that must appear |
| P2 | Strongly preferred skills and adjacent experience |
| P3 | Bonus signals, style/culture alignment, nice-to-have tools |

Use this to:

- Re-rank the summary
- Reorder skills
- Choose which projects and bullets deserve top placement
- Inject exact terminology naturally for ATS

If no job description exists, infer a target direction from the user's background and stated goal.

## Content standards

### Summary

Write 2 to 4 short lines, not a bloated paragraph.

Include:

- Seniority or years of experience
- Core technical angle
- Domain or industry angle
- Distinguishing strength relevant to the target role

### Skills

Group skills into clear categories. Good categories:

- Languages / Frameworks
- Frontend / Backend
- Web3 / Solana
- Infrastructure / Tools

Do not dump every keyword into one line. Keep groups scannable.

### Experience and projects

Lead with the highest-signal items.

- Put the most relevant work first, not necessarily the oldest
- Keep each bullet specific
- Avoid bullets that only describe responsibility without value
- Do not fabricate metrics
- If metrics are unavailable, express scope or effect clearly

### Truthfulness

Never fabricate experience, titles, metrics, timelines, or shipped work.

## Designed artifact workflow

When the user wants a designed resume artifact, do not directly jump from raw text to PDF. Use this sequence:

1. Improve the resume content.
2. Decide the design direction from the content itself.
3. Consult `frontend-design` if available.
4. Create HTML first.
5. Export PDF from the HTML.
6. Validate visual balance and rendering behavior.

## How to use `frontend-design`

If `frontend-design` is available and the user wants a designed resume, explicitly use it.

Use it to answer:

- What visual tone fits this candidate?
- What typography direction matches the candidate's field?
- Should the layout feel editorial, refined technical, minimal professional, or portfolio-adjacent?
- How can the design feel intentional without becoming heavy or gimmicky?

Resume-specific rule:

Do not blindly apply flashy product-landing-page aesthetics. Resume design must remain scannable, printable, and recruiter-friendly.

## HTML resume rules

The designed resume should be built as a print-oriented HTML document.

Required constraints:

- Standard A4 page
- Target a true single-page layout unless the user clearly wants multi-page
- Text must remain selectable in the exported PDF
- Use a strong but restrained visual direction
- Avoid decorative elements that compete with content

Always add print-aware CSS:

- `@page { size: A4; margin: 0; }`
- Explicit page container sized for A4
- Print color adjustment only when needed

## Balanced PDF rules

The balanced PDF is the default designed output. It should look polished but open faster than heavy Chrome-generated art PDFs.

### Keep

- One coherent type family or a disciplined pairing
- 2 to 3 font weights maximum
- A small number of accent colors
- Simple borders, rules, and flat fills
- At most one subtle gradient if it materially improves the design

### Avoid

- `mask-image`
- Full-page grid overlays
- Full-page pseudo-element textures
- Multiple transparent layers across the whole page
- Blur effects
- Shadows used as decoration
- Glassmorphism
- Excessive gradients
- Image-backed layouts

These often create PDF resources that render slowly or appear blurry for a moment on open.

## Page density and whitespace control

The resume should feel intentionally filled, not cramped and not sparse.

Aim for:

- Single-page A4 occupancy that uses most of the page
- No obvious dead zone at the bottom
- Even section rhythm
- Readable but compact line lengths
- Clear hierarchy between summary, skills, projects, experience, and education

When refining layout:

- Expand or compress spacing gradually
- Adjust font sizes by small steps
- Rebalance section padding before changing content drastically
- Prefer reorganizing blocks over shrinking everything indiscriminately

If there is obvious bottom whitespace, do not ship it without trying to rebalance:

- tighten oversized top spacing
- slightly enlarge key body text or section spacing
- spread density across sections
- rebalance summary, skills, and experience proportions

## Validation checklist

Before handing off a designed PDF, verify:

- PDF is the intended page count
- Text is selectable
- Bottom whitespace is not visually distracting
- No section feels crushed while another has excess air
- Typography is legible at normal zoom
- The layout still reads clearly in plain text extraction

If a screenshot tool is available, inspect the exported result visually.

If the PDF opens with a visible blur-to-sharp delay, simplify the design in this order:

1. remove masks and full-page overlays
2. remove transparency-heavy surfaces
3. reduce gradient usage
4. reduce custom font complexity
5. if needed, switch to a faster `fast-open` output

## Suggested file outputs

When building resume artifacts, prefer leaving behind reusable source files, not only the final PDF.

Typical outputs:

- `resume-source.md`
- `resume-data.json`
- `resume-designed.html`
- `resume-balanced.pdf`
- optional preview screenshot

This makes later tailoring much faster.

## Report structure

When returning the final result to the user, summarize briefly:

1. what content was improved
2. what output mode was produced
3. where the files are
4. any remaining tradeoff, such as "balanced render" vs "maximum visual flair"

## Best practices

Do:

- Use this skill for full resume artifact generation, not only text cleanup
- Improve the writing before designing
- Let the candidate's profile drive the visual direction
- Use `frontend-design` for resume-specific HTML decisions when a designed artifact is needed
- Keep the PDF single-page A4 unless the user clearly wants otherwise
- Tune layout density so the page feels complete without obvious bottom voids

Do not:

- Stop at a generic ATS markdown draft if the user asked for a PDF deliverable
- Export a visually heavy PDF that opens sluggishly if a balanced variant would satisfy the request better
- Treat resume design like a landing page or poster
- Overdecorate at the expense of scanability
- Fabricate credentials or impact
