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

Content tailoring in this skill is adapted from `tailored-resume-generator` and extended for designed resume artifact generation.

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

### 1. Gather source material

Start from what the user already has:

- Existing resume PDF, DOCX, markdown, or plain text
- Portfolio/project descriptions
- Job description
- Notes about target role, industry, geography, or seniority

If a job description exists, prefer getting the full posting plus company name and job title.

If the user already has a resume, use it as the foundation. If not, gather only the highest-value missing inputs:

- Work history with titles, companies, dates, and responsibilities
- Education
- Core skills and tools
- Notable achievements, metrics, or scope
- Certifications, awards, publications, or links when relevant

Ask only for high-risk gaps. Do not interrogate the user for minor polish decisions if a reasonable assumption is enough.

### 2. Analyze job requirements

If a job description is provided, classify requirements:

| Priority | Meaning |
|----------|---------|
| P1 | Must-have qualifications, deal-breakers, and keywords that must appear |
| P2 | Strongly preferred skills, adjacent experience, and important competencies |
| P3 | Bonus signals, culture alignment, and nice-to-have tools |

Explicitly extract:

- Must-have qualifications such as years of experience, required skills, and education
- Key technical skills, tools, and methodologies
- Soft skills such as communication, leadership, or collaboration
- Industry knowledge or domain experience
- Repeated keywords and phrases for ATS
- Company values, tone, or culture signals

If no job description exists, infer a target direction from the user's background and stated goal.

### 3. Map candidate experience to requirements

For each important requirement:

- Identify matching experience from the candidate's background
- Use transferable skills if there is no direct match
- Note gaps that should be de-emphasized, reframed, or addressed in recommendations
- Identify unique strengths that deserve top placement

Use this mapping to:

- Re-rank the summary
- Reorder skills
- Choose which projects and bullets deserve top placement
- Inject exact terminology naturally for ATS
- Decide what to omit, compress, or move down

### 4. Structure the tailored resume content

Turn the raw source into structured resume content before designing.

Always extract or produce these sections where applicable:

- Name and contact details
- Professional summary
- Skills grouped by category
- Experience
- Projects
- Education

Optional sections when they materially help:

- Certifications and licenses
- Awards or recognition
- Publications or speaking
- Volunteer work relevant to the role
- Additional links such as GitHub, portfolio, or case studies

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

### 5. Optimize for ATS and recruiter scanability

Keep the content machine-readable and recruiter-readable at the same time.

Prefer:

- Standard section headings
- Exact target-role terminology used naturally
- Both acronym and full-form terminology where relevant
- Straightforward chronology and consistent labels
- Skills that can be substantiated by the candidate's actual experience

Avoid:

- Keyword stuffing
- Decorative formatting that breaks parsing
- Unsupported claims added only to satisfy a posting
- Overly creative section names in ATS-oriented variants

### 6. Format and present

For content-only delivery, default to markdown unless the user requests plain text or another format.

Use these formatting rules:

- Keep to one page for candidates with under 10 years of experience unless the user clearly needs more
- Two pages can be appropriate for more senior profiles when the content truly justifies it
- Use reverse chronological order unless a career-change case clearly benefits from a hybrid structure
- Keep contact information prominent
- Maintain a clean, scannable layout with white space and consistent spacing

If the user wants a designed artifact, continue into the HTML and PDF workflow below rather than stopping at text.

### 7. Provide strategic recommendations

After delivering the tailored resume, provide brief high-value follow-through when useful:

- Strengths analysis: what makes the candidate competitive for this role
- Gap analysis: what requirements are not fully met and how to address them honestly
- Interview preparation: talking points and stories suggested by the revised resume
- Cover letter hooks: 2 to 3 angles or opening lines worth expanding

Keep this concise when the user mainly wants a finished artifact, but do not omit important gaps or risks.

### 8. Iterate and refine

Offer refinement paths when they materially help:

- Adjust emphasis or tone
- Add or remove sections
- Generate alternative versions for different roles
- Produce ATS and designed variants from the same source
- Create more conservative or more modern visual versions when a designed output is requested

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

When a job description exists:

- Put required tools and core technologies first
- Use the exact terminology used in the job description where truthful

Do not dump every keyword into one line. Keep groups scannable.

### Experience and projects

Lead with the highest-signal items.

- Put the most relevant work first, not necessarily the oldest
- Keep each bullet specific
- Avoid bullets that only describe responsibility without value
- Do not fabricate metrics
- If metrics are unavailable, express scope or effect clearly
- Reorder bullets within a role to emphasize the best target-role matches
- Highlight outcomes, scale, ownership, and tools used

### Truthfulness

Never fabricate experience, titles, metrics, timelines, or shipped work.

### Career stage and candidate type adjustments

Adapt the resume strategy to the candidate, not just the job description.

#### Career changers

- Emphasize transferable skills
- Build a narrative that explains the transition clearly
- Use projects and adjacent experience to bridge credibility gaps

#### Recent graduates

- Lead more strongly with education, projects, internships, and relevant coursework
- Highlight leadership, initiative, and hands-on work
- Avoid padding the resume with weak filler experience

#### Senior executives

- Lead with an executive summary
- Focus on strategic scope, leadership, growth, and organizational impact
- Include board, speaking, or public credibility signals when they matter
- Emphasize revenue, hiring, operational scale, and transformation outcomes

#### Technical roles

- Keep technical skills prominent
- Include GitHub, portfolio, or equivalent links when relevant and available
- Mention engineering practices or methodologies such as Agile when they help the fit

#### Creative roles

- Include portfolio links prominently
- Highlight campaigns, shipped creative work, or client outcomes
- Mention relevant tools and software proficiencies
- Allow a slightly more expressive designed layout while preserving ATS readability when needed

### Length and personal-information rules

- Prefer one page for candidates with under 10 years of experience unless the user clearly needs more
- Two pages can be appropriate for more senior profiles when the content truly justifies it
- Avoid first-person pronouns
- Do not include age, photo, marital status, or similar personal details unless explicitly required for a specific market and the user asks for it
- Do not list every historical role if it weakens relevance; compress or omit low-signal older experience when appropriate

## Designed artifact workflow

When the user wants a designed resume artifact, do not directly jump from raw text to PDF. Use this sequence:

1. Improve the resume content.
2. Decide the design direction from the content itself.
3. Read the bundled frontend-design guidance at `references/frontend-design/SKILL.md`.
4. Load only the relevant frontend-design reference files for the task.
5. Create HTML first.
6. Export PDF from the HTML.
7. Validate visual balance and rendering behavior.

## Bundled frontend-design guidance

`resume-studio` includes a vendored copy of the full `frontend-design` skill under `references/frontend-design/`, so users do not need to pre-install `frontend-design` separately.

When the user wants a designed resume artifact, always read:

- `references/frontend-design/SKILL.md`

Then consult only the reference files needed for the current design problem:

- `references/frontend-design/reference/typography.md` for type scale, pairing, measure, and loading
- `references/frontend-design/reference/color-and-contrast.md` for OKLCH palettes, tinted neutrals, contrast, and theming
- `references/frontend-design/reference/spatial-design.md` for layout rhythm, spacing, alignment, and composition
- `references/frontend-design/reference/motion-design.md` for transitions, sequencing, and reduced-motion choices
- `references/frontend-design/reference/interaction-design.md` for states, affordances, disclosure, and controls
- `references/frontend-design/reference/responsive-design.md` for adaptation across viewport sizes and container contexts
- `references/frontend-design/reference/ux-writing.md` for labels, microcopy, empty states, and clarity

Use this bundled guidance to answer:

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

## ATS optimization rules

When producing ATS-friendly output, keep the content machine-readable and recruiter-readable at the same time.

Prefer:

- Standard section headings such as `Professional Summary`, `Skills`, `Experience`, `Projects`, and `Education`
- Exact keywords from the target role used naturally
- Both acronym and full-form terminology where relevant, such as `LLM (large language model)` or `CI/CD (continuous integration and continuous delivery)`
- Simple bullet structures and straightforward chronology

Avoid:

- Tables for primary resume content
- Icon-only labels for critical information
- Graphics or layout tricks that interfere with parsing
- Complex formatting that makes field extraction unreliable

If the deliverable is a designed PDF, preserve ATS readability by keeping the text selectable and the reading order clear.

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

## Content-only resume template

When the user asks for a text or markdown resume, this structure is the default:

```markdown
# CANDIDATE NAME
Email | Phone | LinkedIn | Portfolio

## PROFESSIONAL SUMMARY
[2-4 lines aligned to the target role]

## SKILLS
- **Category**: Skill 1, Skill 2, Skill 3

## EXPERIENCE
**Title** | Company | Dates
- Achievement / impact bullet

## PROJECTS
**Project** | Context | Dates
- Relevant implementation or result

## EDUCATION
**Degree** | School | Year
```

Keep this structure simple unless the user requests another format.

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
- Use the bundled `references/frontend-design/` guidance for resume-specific HTML decisions when a designed artifact is needed
- Keep the PDF single-page A4 unless the user clearly wants otherwise
- Tune layout density so the page feels complete without obvious bottom voids
- Keep ATS, recruiter readability, and visual polish aligned rather than treating them as separate problems

Do not:

- Stop at a generic ATS markdown draft if the user asked for a PDF deliverable
- Export a visually heavy PDF that opens sluggishly if a balanced variant would satisfy the request better
- Treat resume design like a landing page or poster
- Overdecorate at the expense of scanability
- Fabricate credentials or impact
- Lose the adapted `tailored-resume-generator` content rigor just because the skill can now produce designed artifacts
