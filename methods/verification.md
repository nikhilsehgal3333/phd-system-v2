# Method — Verification of research findings (mandatory)

Every research finding this agent produces gets examined before Nikkhil sees it and before it
enters a deliverable. A finding is any factual claim about the literature, the law, a dataset, an
institution, or a person. This is not proofreading and not a citation spot-check; it asks whether
the research **holds**.

Two rules sit above the checklist:

- **Nothing is presented as fact without a status and a source.** Label every finding.
- **A correction is reported, not quietly absorbed.** When the pass overturns something already
  drafted or already told to Nikkhil, say so explicitly and say what changes downstream.

## Status labels (use these words)

| Label | Means |
|---|---|
| **VERIFIED** | Checked against a primary or authoritative source, cited with a link. Safe to use. |
| **[verify]** | Plausible, not yet checked. May shape thinking. **Never enters a deliverable.** |
| **CORRECTED** | Was wrong; the log states the old claim, the true one, and the consequence. |
| **UNRESOLVED** | Checked and still uncertain. Describe it rather than pin it, or drop it. |
| **DO NOT CITE** | Could not be found or does not say what it was thought to say. |

## The five checks

### 1. Citation integrity
The work exists; authors, year, journal, volume, pages, and DOI are right; and **it actually
supports the claim attached to it**. Check author lists in full — a four-author paper cited as if
sole-authored misrepresents a supervisor to their own face. Where a piece exists in two versions
(working paper and journal issue, online-first and final), use the citable one and note the other.

### 2. Regulatory and temporal currency
For any law, standard, directive, or framework: is this still true **today**, in this jurisdiction?
Has it been amended, delayed, narrowed, or left on the books but unenforced? Never describe a
regime in the present tense without checking its current state. This check caught an LkSG reporting
duty presented as a live submission system months after the authority stopped reviewing reports and
deactivated the portal.

### 3. Feasibility of the empirical object
Will the data the design depends on **exist in time**? Map the regime's application and first
reporting dates against the PhD's own timeline. A directive applying in 2029 with first reports
covering 2030 cannot be the empirical object of a three-year PhD starting in 2026 — it is a
doctrinal and design object, plus anticipation effects. Catching this before submission is the
difference between an ambitious proposal and an unworkable one.

### 4. People and institutions
Before naming anyone: current title and rank, current institution, whether they still supervise
there, whether the group or team described actually exists, and the email's provenance and
confidence. Verify from the faculty page or their own site, not from inference. A pass on the
Hamburg target produced ten corrections on one supervisor, including her rank and the fact that she
had no team.

### 5. Claim-by-claim sweep of the draft
Walk the finished draft and mark every empirical claim, number, date, statutory section, and
attribution. Each gets a label. Anything still `[verify]` at the end is cut or rewritten as an
explicit open question — it does not ship.

## Output — `programs/<Programme>/verification_log.md`

Head it with the date and what prompted the pass. Then, per item: the claim, its label, the source
as a link, and where the draft was wrong. Group by theme (law, literature, people, design) when
there are many. Two things carry the most weight, so make them visible rather than burying them in
a list:

- **Corrections** — what the draft said, what is true, and what must change because of it.
- **The load-bearing finding** — a pass usually turns up one thing that reshapes the argument. Call
  it out. In the Hamburg pass it was a statute formally in force whose enforcement had been
  publicly abandoned, which was very nearly the natural experiment the draft had claimed could not
  be run.

## When it runs

- **Proposal Stage 1** (evidence base) and **Stage 4** (full draft) — both mandatory.
- **Before any outreach** — supervisor facts and email confidence.
- **Fit scoring** — check eligibility gates and deadlines against the live call, not a cached read.
- **Whenever a finding is reported to Nikkhil**, including mid-conversation. Label it there too.

Verified reference sets belong in `phd-system/profile/domain-profile.md` under the domain that owns them, with
the verification date, so the next application reuses the work instead of repeating it.
