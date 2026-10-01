---
name: application-writer
description: Generates highly targeted, fact-based motivation and PR (Public Relations/Pitch) statements, including application emails and cover letters.
version: 1.1.0
author: TSR (@iam-tsr, https://github.com/iam-tsr/application-writer)
license: MIT
domain: Career Development, Recruitment, Professional Communication
---

# Application Writer: Fact-Based Pitch Generation
The **Application Writer** skill generates highly targeted, fact-based motivation and PR (Public Relations/Pitch) statements, including application emails and cover letters. It strictly aligns a candidate's verified resume with the **specific job description provided by the user**, producing tailored pitch variations while maintaining absolute factual integrity and strict relevance to the target role.

## Input Dependencies (Mandatory)
To execute this skill, the agent **must** receive the following from the user. If the Job Description is missing, the agent must halt and request it.

1. **The Job Description (JD):** The exact text, link, or detailed summary of the target role/company requirements provided by the user. *(Crucial: All generated pitches must be anchored to this specific JD).*
2. **The Resume:** The candidate's factual work history (e.g., `ME.md`).

## Core Mandates

### Mandate 1: Zero-Hallucination Policy (Resume Facts)
**This is the highest priority rule regarding the candidate's background.**  
The agent must operate under the **Principle of Using Only Facts**. Every claim about the candidate's past must be directly traceable to the provided resume.

| Permitted (Strictly Factual) | Prohibited (Hallucination/Speculation) |
| :--- | :--- |
| Using achievements/metrics explicitly stated in the resume. | Fabricating achievements, metrics, or outcomes not in the resume. |
| Using specific skills and tool names listed in the resume. | Speculating with phrases like "can also handle [X]" or "probably knows [Y]". |
| Using exact job titles and employment periods as stated. | Over-interpreting or expanding ambiguous expressions. |
| Rephrasing stated achievements for better flow/impact. | Exaggerating, inflating, or misrepresenting the scale of achievements. |

### Mandate 2: Job Description Alignment (The "Mail/Pitch" Rule)
**Every generated application email, cover letter, or PR text must be strictly based on the user-provided Job Description.**

- **No Generic Templates:** The output must not read like a generic cover letter. It must explicitly reference the company name, the specific role, and the exact challenges/requirements mentioned in the JD.
- **Keyword Mirroring:** The vocabulary and technical terms used in the JD must be naturally mirrored in the pitch.
- **Relevance Filter:** If an experience in the resume does not help answer the specific needs of the provided JD, it should be minimized or excluded to keep the email focused.
- **Address the "Why":** The motivation section must explicitly answer *why* the candidate wants *this specific role at this specific company* based on the JD's context.

## Gap Management Protocol
When the JD requires skills not present in the resume, handle gaps transparently:
1. **No Experience:** Honestly state "No direct experience in [Skill]".
2. **Tangential Experience:** Clearly state "While I lack direct experience in [Skill], I have extensive experience in [Related Skill]".
3. **Active Learning:** State only verifiable facts (e.g., "Currently completing a certification in [Skill]").

## Execution Workflow

### Phase 1: Information Gathering & JD Parsing
1. **Ingest Job Description (User Provided):** Extract and analyze the specific JD.
   - *Company/Project Context & Mission*
   - *Required & Preferred skills*
   - *Core job duties & daily responsibilities*
   - *Ideal candidate profile & pain points they are trying to solve*
2. **Ingest Resume:** Parse the candidate's factual resume.

### Phase 2: Matching Analysis
1. **Cross-Reference:** Map resume skills against the *specific JD requirements*.
2. **Cite Sources:** Identify the exact section in the resume for every matched JD requirement.
3. **Score Alignment:** Calculate match levels (`High` / `Medium` / `Low` / `Not Applicable`).
4. **Identify Gaps:** Flag missing JD requirements and formulate a coverage strategy.

### Phase 3: PR Text & Email Generation
Generate the analysis and the tailored application texts (Email/Cover Letter + PR variations) based *strictly* on the JD and Resume intersection.

## Standard Output Format: Job Application PR Text & Email

### Job Description Summary (User Provided)
| Item | Details |
|------|---------|
| **Target Company/Project** | [Extracted from JD] |
| **Position** | [Extracted Position Title] |
| **Core Pain Points/Needs** | [What the JD implies they need to solve] |
| **Required Skills** | [List of mandatory requirements from JD] |

### Match Level Evaluation
| JD Requirement | Match Level | Relevant Resume Experience | Source (Resume Reference) |
|----------------|-------------|----------------------------|---------------------------|
| [JD Skill 1]   | High/Med/Low/N/A | [Specific experience]    | [e.g., "Work History > Project X"] |
| [JD Skill 2]   | High/Med/Low/N/A | [Specific experience]    | [e.g., "Skills > Python"] |

### Points to Emphasize (Based on JD)
- [Experience that directly solves the JD's primary pain point]
- [Skill that matches their "Ideal Candidate" profile]

### Gaps & Supplementary Explanations
- **[Missing JD Skill]:** [Honest assessment and coverage strategy]

## Application Email / Cover Letter
*(A complete, ready-to-send email/message to the recruiter/hiring manager. Strictly tailored to the provided JD, referencing the specific company and role. Professional, concise, and impactful.)*

```markdown
**Subject:** Application for [Position Title] - [Candidate Name]

Dear [Hiring Manager Name or "Hiring Team"],

[Opening: State the role applying for and a strong, JD-aligned hook.]

[Body Paragraph 1: Highlight the most relevant resume fact that matches the JD's core requirement.]

[Body Paragraph 2: Highlight a secondary achievement that addresses another JD pain point.]

[Closing: Reiterate enthusiasm for this specific company/project based on the JD context, and call to action.]

Best regards,
[Candidate Name]
[Contact Info]
```

## PR Text (Platform/Portal Variations)

### Ultra-short version (~100 characters)
*(One-sentence pitch answering the JD's main need.)*
[Generated Text]

### Short version (~200 characters)
*(Compact summary for chat/SNS, linking a resume fact to the JD.)*
[Generated Text]

### Standard version (400-600 characters)
*(Structured PR for application forms, using STAR method aligned with JD.)*
[Generated Text]

### Detailed version (800-1000 characters)
*(Comprehensive breakdown of achievements mapped directly to the JD's responsibilities.)*
[Generated Text]
