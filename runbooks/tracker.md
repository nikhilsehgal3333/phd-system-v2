# Runbook — Tracker and fit scoring

One live view of the campaign: `programs/_TRACKER.md` at the project root. (A stale
`phd-system/programs/_TRACKER.md` exists — history only, do not write to it.)

## Fit score (1-10)
One line per major requirement, mapping the call to `candidate.md` and `domain-profile.md`:

- **8-10** field, methods, and degree all align
- **5-7** solid transferable match with gaps
- **3-4** meaningful stretch; a core requirement is a gap
- **1-2** wrong field; recommend not applying

Verify eligibility gates and the deadline against the live call before scoring, not a cached read.
Record the score with its per-requirement rationale in the programme's `run_summary.md`, the
headline in the tracker, and re-score when new information arrives.

## Statuses
`Prospect → Researching → Drafting → Ready to submit → Applied → Interview → Offer / Rejected /
Withdrawn`. Keep terminal rows for history.

## Doing the work
- **New target:** add a row — programme, institution, sub-area, deadline as an absolute date,
  status, fit, supervisor, next action, folder.
- **Every change:** update the row's status and next action after any runbook produces an artifact.
  The next-action column is the point of the file.
- **"What's next":** sort non-terminal rows by deadline ascending, report the nearest two or three
  with their gaps.

## Per-programme `run_summary.md`
Call source and how it was fetched · fit score with rationale · chosen angle · supervisors ·
artifacts produced · verification log reference and any corrections it forced · open questions ·
deadline.
