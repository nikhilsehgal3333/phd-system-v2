# Runbook — Research proposal

Socratic and checkpoint-gated. Structure exemplar:
`D:/Resume/Agent Skill/INN_INSEPP_PhD_Proposal.md`. Read the programme's `call.md` first.

## Stage 0 — Frame
Ask 5-15 short questions, each offering 2-4 framed options rather than open-ended prompts, to
converge on the gap, the central question, the unit of analysis, and the angle that connects to the
target group's research. Surface options; Nikkhil chooses.
→ CHECKPOINT: the research question and angle, in his words, before any drafting.

## Stage 1 — Evidence
Map the field with `phd-system/methods/literature-review.md`, and run
`phd-system/methods/deep-research.md` on any single question the design leans on where being wrong
would be expensive. Where the literature is split and the proposal has to take a side, run
`phd-system/methods/source-comparison.md` — say plainly which state each dimension is in
(agreement, disagreement, nobody knows) rather than flattening the three.

Build the evidence base as claim → source → strength, then run `phd-system/methods/verification.md` over it.
Check regulatory currency and whether the data the design needs will exist inside the PhD timeline
before committing to an empirical object. Verified sets go into `domain-profile.md` for reuse.
→ CHECKPOINT: the framing literature and the gap, with the verification log.

## Stage 2 — Outline
1. Introduction and academic relevance (tied to the programme's focus)
2. Research questions (2-4, interconnected, the last integrative)
3. Theoretical framework (from the `domain-profile.md` theory bank)
4. Methods / work packages (WP1 quant · WP2 qual · WP3 synthesis)
5. Challenges and possibilities, including identification strategy and honest limitations
6. Progress plan (years, months blocked, target working papers and venues)
7. Expected contributions (academic / practical / societal)
8. Candidate qualifications, mapped truthfully from `candidate.md`
9. References

→ CHECKPOINT: outline plus the method design. Identification choices live here — staggered DiD on
phased mandates, PSM, case selection logic.

## Stage 3 — Draft
Section by section, pausing for feedback rather than delivering the whole proposal at once.
→ CHECKPOINT: after the methods section, and again after a complete first draft.

## Stage 4 — Gates
Full verification pass (`phd-system/methods/verification.md`) over the finished draft, then the register pass,
then the committee test as `phd-system/methods/critique.md` — every **FATAL** fixed and re-checked
before the draft moves. If the critique finds the evidence sound but the argument not carrying,
run `phd-system/methods/argument-structure.md`; its revision plan takes its own checkpoint because
restructuring changes what Nikkhil is claiming. Address the top issues; remaining ones become
written acknowledged limitations rather than silent revision loops (cap at two).
→ CHECKPOINT: the draft, the verification log, and the corrections it forced.

## Stage 5 — Render
Write `programs/<Programme>/proposal.md`, then:

```
node "D:/Resume/Agent Skill/md2docx.cjs" proposal "<src>.md" "<out>.docx"
```

Run it from `D:/Resume/Agent Skill` so `docx` resolves. Update `programs/_TRACKER.md`.
→ CHECKPOINT: confirm the rendered document before treating it as final.

## Boundaries
Do not generate the research question or hypotheses. Do not fabricate data, citations, or pilot
results — a proposal proposes, it does not report experiments never run. Keep it honest about what
Nikkhil's background supports.
