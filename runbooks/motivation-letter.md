# Runbook — Motivation letter

Formal, programme-specific. Exemplar:
`Linz University/Nikkhil_Sehgal_MotivationalLetter_ITU_Linz.docx`. If a proposal exists for this
programme, read it — the letter echoes its framing.

1. **Extract the requirements** from the call: prescribed sections or word limits, language (confirm
   if ambiguous), the research group, the specific position.
   → CHECKPOINT if the call prescribes a structure.
2. **Pick the angle** from `domain-profile.md` and the two or three experiences from `candidate.md`
   that most directly evidence readiness for *this* topic.
3. **Draft:**
   - **Opening** — the specific research problem and why it matters now. Not generic enthusiasm.
   - **Why this group, by name** — the supervisor's work, the programme's methods or data, why here.
   - **Why Nikkhil is ready** — the MBA thesis (CSRD financial implications; cost modelling plus LDA
     thematic analysis) and the most relevant roles (TUI CSRD/ESRS, CDP 150+ organisations, GRI
     multi-country research), framed as research preparation rather than job history.
   - **Fit and forward** — how the research advances the group's agenda.
   - **Close** — measured.
4. **Verify** every named fact about the group, the supervisor, and the programme
   (`phd-system/methods/verification.md`) before the draft goes out.
5. **Test it:** could this letter have been sent to another programme? If yes, rewrite.
   → CHECKPOINT: present the draft.
6. **Render.** `cv-generator.cjs` `generateCoverLetter` (block letter, Arial). Schema:
   `{ name, contact:{location,phone,email}, date, subject, salutation, paragraphs:[...], closing,
   outputFilename }`. Working template: `D:/Resume/Agent Skill/_gen_inn_house.cjs` (its `letter`
   object). Save into `programs/<Programme>/` and update the tracker.

No invented motivation, projects, or affiliations.
