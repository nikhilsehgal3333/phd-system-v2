# Method — Literature review (adapted from Feynman `/lit`)

Two modes, one machinery. **Topic mode** maps a field: what is settled, what is contested, where
the gap sits. **Corpus mode** maps a person or group: their publication record, how their questions
moved over time, and which papers turned the corpus. Corpus mode is the engine behind the
supervisor digest in `phd-system/runbooks/supervisor-outreach.md` — run it there rather than
re-deriving a reading of the group by hand.

Everything this method produces is a finding, so everything is labelled per
`phd-system/methods/verification.md`. A literature review that ships unlabelled claims has failed,
however well it reads.

Slug: lowercase, hyphens, no filler words, at most five words. One slug per run, used for every
file.

## 1. Plan
Write `programs/<Programme>/research/.plans/<slug>.md` before searching: the key questions, the
source types worth searching (journals, working papers, faculty pages, regulator sites, repos), the
period that matters, the expected sections, and a task ledger. Summarise it in two or three lines
and continue — this is evidence-gathering, not a deliverable, so it does not take a checkpoint of
its own. The findings it produces will meet one later.

Decide the mode here. An input that names a lab, a professor, an institution page, or an author
profile is corpus mode.

## 2. Identity first (corpus mode only)
The lead session owns this step; do not delegate it. Resolve who the person actually is before
reading anything they wrote: current title and rank, current institution, whether they still
supervise. This is check 4 of `verification.md` and it is where the Hamburg pass produced ten
corrections on one supervisor.

Then collect the reachable publication list into
`programs/<Programme>/research/<slug>-publications.md`: title, year, venue, DOI or URL, and the
gaps you could not close. Prefer the group's own publication page, the author's profile, and
publisher or repository pages. State the gaps rather than filling them by inference.

## 3. Gather
Search with `WebSearch`; fetch with `WebFetch`. Open with two to four queries from different
angles rather than one query refined repeatedly — definition and history, mechanism, current state
and criticism. Then narrow using the terminology and names the first round surfaced.

Delegate to `phd-research` only when the sweep is wide enough to pay for a cold start; a narrow
question is faster and more accurate run inline. Notes go to
`programs/<Programme>/research/.drafts/<slug>-research-*.md`.

Never silently drop an assigned question. Mark it `done`, `blocked`, or `superseded`.

**Source quality.** Prefer peer-reviewed work, official documentation, primary datasets, statutes
and regulator publications, and reputable journalism. Accept well-cited secondary sources with the
caveat attached. Deprioritise undated blogs, listicles, and aggregators. Reject anything with no
author and no date. When the first round returns mostly low-grade sources, re-search against named
authoritative domains instead of settling.

## 4. Synthesise
Separate **consensus**, **disagreement**, and **open question** — these are three different things
and collapsing them is how a proposal ends up claiming a settled field that is not settled. The
open questions are the ones that matter: they are where Nikkhil's question has to live.

Corpus mode additionally produces three to five research trajectories across the corpus, and the
three to five papers that most changed its direction. Rank those by contrastive originality,
method strength, and relation to prior work, never by author prestige or citation count alone.

Use a table for comparisons and a Mermaid diagram for a taxonomy or a trajectory map only when the
structure is source-supported and it changes a decision. No invented figures, numbers, or tables.

## 5. Verify
Run the five checks in `phd-system/methods/verification.md` over the draft, then the severity pass
in `phd-system/methods/critique.md`. Delegate to `phd-verify` for a long draft; run it inline for a
short one. Fix every **FATAL** before the review is used for anything. Carry **MAJOR** into Open
Questions. Accept **MINOR**.

Every claim carries a status label and a link. Anything still `[verify]` at the end is cut or
rewritten as an explicit open question.

## 6. Deliver
Final review to `programs/<Programme>/research/<slug>.md`. Provenance sidecar beside it as
`<slug>.provenance.md`: date, what prompted the run, sources consulted against sources accepted
against sources rejected, verification status, the intermediate files used, and for corpus mode the
publication-log path and the gaps still open. Corrections go to
`programs/<Programme>/verification_log.md` where the rest of the campaign will find them.

Confirm both files exist on disk before reporting the run complete. A cited draft is not a
delivered review.

Verified reference sets that outlive this application belong in
`phd-system/profile/domain-profile.md` under the domain that owns them, with the date, so the next
programme reuses the work.
