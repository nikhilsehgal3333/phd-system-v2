# Method — Adversarial critique (adapted from Feynman `/review`)

The pass that tries to break the work before a selection committee does. `verification.md` asks
*is this true*. This asks *does the argument survive a hostile reader* — and grades what it finds
by severity, so the difference between "this sinks the proposal" and "this is a wording nit" is
visible instead of buried in a list.

Run it on a proposal draft, a motivation letter, a literature review, a supervisor digest, or an
external paper Nikkhil needs a read on. It is the mechanism behind the committee test in canon §4.

Two standing rules: **every weakness quotes the passage it is about**, and **no vague praise** — a
strength that cannot name its evidence is not a strength.

## Severity
| Grade | Means | Disposition |
|---|---|---|
| **FATAL** | The claim is unsupported, false, or the design cannot work. It would end the application. | Fix before the artifact goes anywhere. Re-run the pass over the fix. |
| **MAJOR** | A real weakness a reviewer will raise. Not disqualifying, not ignorable. | Fix, or surface it as an acknowledged limitation. Never leave it silent. |
| **MINOR** | Wording, ordering, polish. | Accept or fix at leisure. |

## What to look for
- Claims that outrun their evidence, and conclusions phrased more strongly than the data allows
- Empirical objects that cannot exist in time — data that will not have been reported yet, a regime
  that applies after the PhD ends (check 3 of `verification.md`, the most common fatal error here)
- Missing method detail: how the sample is drawn, what the identification strategy actually is,
  what the counterfactual is
- Weak positioning against prior work, or a novelty claim the literature already answered
- Single-source critical claims
- Sections, paragraphs, or citations surviving from an earlier draft with nothing now supporting
  them
- Notation and terminology drift; the same construct under two names
- "Verified" or "confirmed" written where no check was actually performed
- Anything suspiciously clean: ask what produced it
- Register breaches against `phd-system/profile/writing-standards.md`, and claims unsupported by
  `phd-system/profile/candidate.md` or tripping canon §5

Keep going after the first serious problem. The first one found is rarely the worst one present.

## Output
Write to `programs/<Programme>/research/<slug>-critique.md`, in two parts.

**Part 1 — structured review**
```markdown
## Summary
What the artifact argues, in one or two paragraphs.

## Strengths
- [S1] ... (naming the passage that earns it)

## Weaknesses
- [W1] **FATAL:** ...
- [W2] **MAJOR:** ...
- [W3] **MINOR:** ...

## Questions a committee will ask
- [Q1] ...

## Verdict
Revision risk and evidence quality. Never predict an admission or acceptance outcome.

## Revision plan
Prioritised concrete steps, one per weakness.
```

**Part 2 — inline annotations.** Quote the exact text, then annotate it with the ID from Part 1:

```markdown
> "The reform provides a natural experiment for identifying the effect."
**[W1] FATAL:** First reports under the regime cover 2030; a PhD starting 2026 cannot observe them.
The object is doctrinal plus anticipation effects. Reframe or change the empirical object.
```

Close with a Sources section listing every URL consulted during the critique.

## Running it
Lead-owned by default. Delegate to `phd-verify` when the artifact is long enough that a cold read
is an advantage rather than a cost — a fresh reader catches drift the drafter cannot see.

For an external artifact (a paper, a call document), read the source directly first and record
evidence notes in `programs/<Programme>/research/.drafts/<slug>-critique-evidence.md` before
writing the critique: quoted claims, observed methods, reported numbers, every path and URL
inspected. If a PDF will not parse, say so, mark those sections `Verification: BLOCKED`, and still
write the critique. A blocked check is not the same as a weakness, and the two must never be
reported as though they were.

Never end a critique run with chat only. The file exists or the pass did not happen.
