# Runbook — CV / resume

**Default deliverable: the corporate resume built from the Master Prompt**
(`D:/Resume/Agent Skill/Nikkhil_Sehgal_Master_Prompt_v4.md`), for every application. This is
Nikkhil's standing preference, set 2026-06-25 and reaffirmed 2026-08-10 for an explicitly academic
call. Do not re-litigate it each time.

Build with `cv-generator.cjs` (`generateCV`) and **`academic: false`** — corporate ordering:
profile → professional experience → skills → education. Honour the Master Prompt's hard rules
(KarbonWise as two entries; Python listed only for KarbonWise-Previous; reverse chronological).
Reference build: `programs/Lund-LUCSUS-DisorderlyTransitions/render_lund.cjs`.

## Angling a corporate resume at an academic target
Do this rather than switching layout:
- Thesis title **and methods** inside the Education entry.
- An explicit qualitative-methods line in Skills.
- A RESEARCH block via `extras` — it renders after Education when `academic: false`.

For a traditional academic committee, offer the academic layout **once** with the caveat that a
corporate resume can read off-register, then build corporate unless he says otherwise.

## Academic layout (only when asked)
Set `academic: true` so Education and Research lead. Order: Education → Research (thesis: question,
method, finding; GRI multi-country research) → Relevant experience → Presentations (GRI at the
Bombay, Colombo, and Dhaka stock exchanges) → Skills and methods → Certifications → Languages.

## Method
1. Map the call's emphasis (finance / policy / carbon-LCA / data / governance) to `candidate.md`;
   choose the angle from `domain-profile.md`.
   → CHECKPOINT if the required degree, field, or quantitative level is a stretch.
2. Draft bullets from the Master Prompt banks, tailored rather than pasted. Cover each important
   requirement at least once. Most relevant roles carry four to six bullets, supporting roles three.
   Never pad an irrelevant role. First drafts may be delegated to `phd-research`, then reviewed
   here against `candidate.md`.
3. Verify every claim against `candidate.md` and canon §5 — no invented publications, teaching, or
   tools, and never upgrade the LCA toolchain to match a call.
4. Render into `programs/<Programme>/Nikkhil_Sehgal_CV_<Programme>.docx`. Schema:
   `{ name, contact:{location,phone,email,linkedin}, profile,
   experience:[{company,dates,title,bullets[]}], education:[{degree,dates,institution,details[]}],
   extras:[{label,bullets[]}], skills:[{category,items}], certifications:[], languages:[], footer,
   academic:false }`. Working template: `D:/Resume/Agent Skill/_gen_inn_house.cjs`. Update the
   tracker.

Measure page count in Word before calling it done — two pages unless the call says otherwise.
