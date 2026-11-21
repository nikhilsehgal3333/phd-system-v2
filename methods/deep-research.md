# Method — Deep research brief (adapted from Feynman `/deepresearch`)

A source-heavy investigation that ends in a cited brief with a provenance record. Use it for the
proposal's evidence base (Stage 1), for a regulatory or methodological question the proposal leans
on, and for any question where being wrong would be expensive. For mapping a field or a supervisor's
corpus use `phd-system/methods/literature-review.md` instead; for weighing options against each
other use `phd-system/methods/source-comparison.md`.

This is an execution method. Running it means creating files, not describing the protocol.

Slug: lowercase, hyphens, no filler words, at most five words.

## Artifacts every run leaves on disk
```
programs/<Programme>/research/.plans/<slug>.md
programs/<Programme>/research/.drafts/<slug>-draft.md
programs/<Programme>/research/.drafts/<slug>-cited.md
programs/<Programme>/research/<slug>.md
programs/<Programme>/research/<slug>.provenance.md
```
Once the plan is approved, a run always ends in a written brief. If a capability fails, continue in
degraded mode, write the partial brief, and mark it `Verification: BLOCKED` with the checks that
could not run. Never finish an approved run with chat only.

## 1. Plan → CHECKPOINT
Write `programs/<Programme>/research/.plans/<slug>.md` first: key questions, evidence needed, the
scale decision, a task ledger, a verification log, and a decision log.

Then stop. Summarise the plan and ask for explicit sign-off before searching, fetching, delegating,
drafting, or delivering. This is canon rule 2, not a formality — a deep run pointed at the wrong
question is expensive. If Nikkhil wants changes, update the plan file and ask again.

## 2. Scale
Decide before assigning owners.

**Lead-owned direct search** for a single fact, a narrow question, or anything answerable in three
to ten tool calls. A "what is X" question is always direct. Do not inflate an explainer into a
multi-agent survey.

**Delegate to `phd-research`** only when decomposition genuinely helps: two workers for a head-to-
head comparison, three or four for a broad multi-faceted sweep. Give each worker its own brief file
(`<slug>-T1.md`) and keep the task strings in the `Agent` call short — the brief lives in the file,
not in the call.

## 3. Gather
`WebSearch` to search, `WebFetch` to fetch. In direct mode run at least three distinct queries from
different angles before drafting, and record the exact terms used in
`.drafts/<slug>-research-direct.md`.

Source quality tiers and the "URL or it did not happen" rule are in
`phd-system/methods/literature-review.md` §3 and apply here unchanged.

Never describe the contents of a source you did not open. Noting that a source exists is fine;
characterising what it says from its title is not.

After gathering, update the plan's ledger and verification log. If a line of research failed,
record exactly what failed and continue to a partial draft.

## 4. Draft
Write the brief yourself. Do not delegate synthesis — this is where the argument gets made, and it
is the step that has to survive a supervisor reading it.

To `.drafts/<slug>-draft.md`: executive summary, findings by question or theme, evidence-backed
caveats and disagreements, open questions. No invented sources, results, figures, benchmarks, or
tables.

Before citing, sweep the draft: every critical claim, number, date, and statutory section maps to a
source URL, a research note, or a file path. Remove or downgrade whatever does not. Mark inferences
as inferences.

## 5. Cite
Copy the draft to `.drafts/<slug>-cited.md` with inline citations and a Sources section. Rules:
every factual claim gets at least one citation; no orphan citations and no orphan sources; hedged
statements and opinions do not need one. A citation is valid only when the source supports the
specific number or conclusion attached to it, not merely the same topic.

Verify every URL resolves. Dead link: find the archived or updated version, and if there is none,
remove the source and every claim that rested on it alone.

Delegate this to `phd-verify` for a long draft. Run it inline for a short one.

## 6. Review
Run `phd-system/methods/critique.md` against the cited draft. Fix every **FATAL** before delivery
and run one more pass over the fixes. **MAJOR** goes into Open Questions. **MINOR** is accepted.

When applying fixes, use small edits for one to three corrections; for a section rewrite or more
than three substantive fixes, write a corrected full file to `.drafts/<slug>-revised.md` instead.

**Then prove the fixes landed.** Grep the file for the wording you removed and for the wording you
put in its place. If an edit failed, say so and retry — never write "fixed" into a provenance
record on the strength of having issued the edit.

## 7. Deliver
Final candidate is `<slug>-revised.md` if it exists, otherwise `<slug>-cited.md`. Copy it to
`programs/<Programme>/research/<slug>.md` and write the sidecar:

```markdown
# Provenance: <topic>

- **Date:**
- **Prompted by:**
- **Rounds:**
- **Sources consulted / accepted / rejected:**
- **Verification:** PASS | PASS WITH NOTES | BLOCKED
- **Plan:** programs/<Programme>/research/.plans/<slug>.md
- **Research files:**
```

Corrections and the load-bearing finding also go to `programs/<Programme>/verification_log.md`.
Confirm on disk that both files exist, then report briefly: the brief, the provenance, and anything
left blocked.
