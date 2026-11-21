# Method — Source comparison matrix (adapted from Feynman `/compare`)

Puts several sources, options, or frameworks side by side and says plainly where they agree, where
they conflict, and where nobody actually knows. Use it for competing theoretical frameworks or
methods for the proposal, shortlisted programmes or funding schemes, rival datasets, and any place
the literature is split and the proposal has to take a side.

Slug: lowercase, hyphens, at most five words.

## Steps
1. **Plan.** Which sources enter the comparison, which dimensions they are judged on, what the
   output looks like. Write it to `programs/<Programme>/research/.plans/<slug>.md`, summarise in
   two lines, and continue without waiting.
2. **Gather.** `WebSearch` and `WebFetch`, source-quality tiers per
   `phd-system/methods/literature-review.md` §3. Delegate to `phd-research` only when the set is
   broad. Read each source before characterising it.
3. **Build the matrix.** Columns: source · key claim · evidence type · caveats · confidence.
   Every row carries a status label from `phd-system/methods/verification.md`.
4. **Separate the three states.** Agreement, disagreement, and uncertainty are distinct findings.
   Say which is which. A dimension where two sources merely use different words for the same thing
   is agreement, and saying otherwise manufactures a debate that does not exist.
5. **Verify.** Every source URL resolves and supports the claim in its row. Run
   `phd-system/methods/critique.md` when the comparison will carry a proposal decision.
6. **Deliver.** One file: `programs/<Programme>/research/<slug>-comparison.md`, ending in a Sources
   section with a direct URL for every source used.

Charts only when the comparison is quantitative and every number is source-backed. Otherwise the
table is the artifact. A Mermaid diagram is worth drawing for structural or architectural
comparisons where the structure itself is the finding.

When the comparison decides how Nikkhil frames his question, it is a finding like any other: it
takes a checkpoint before it hardens into the proposal.
