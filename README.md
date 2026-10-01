# Application Writer

> Generates highly targeted, **fact-based** motivation and PR (Public Relations/Pitch) statements — application emails and cover letters — strictly aligned to a verified resume and the specific job description.

The **Application Writer** skill produces tailored pitch variations for job applications that maintain **absolute factual integrity** and strict relevance to the target role. It maps a candidate's verified resume against the user-provided **Job Description (JD)** and generates application emails, cover letters, and PR text variations that mirror the JD's terminology, address the role's core needs, and never fabricate or inflate any candidate fact.

---

## Features

- **Fact-based generation:** Every claim about the candidate is traceable to the provided resume — no hallucinations or speculation.
- **JD alignment:** Output is strictly anchored to the specific job description, referencing the company, role, and exact requirements.
- **Keyword mirroring:** JD vocabulary and technical terms are naturally incorporated into the generated pitches.
- **Gap management:** Missing JD requirements are handled transparently (no experience, tangential experience, or verifiable active learning).
- **Standardized output:** Consistent Job Application PR Text & Email format across all outputs.

---

## Requirements

To execute this skill, the agent **must** receive the following from the user. If the Job Description is missing, the agent must halt and request it.

1. **The Job Description (JD):** The exact text, link, or detailed summary of the target role/company requirements provided by the user. *(Crucial: All generated pitches must be anchored to this specific JD.)*
2. **The Resume:** The candidate's factual work history (e.g., `ME.md`).

---

## License

This skill is distributed under the **MIT License** (see [`LICENSE`](LICENSE)).
