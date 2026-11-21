# Runbook: Prototype study

Every application carries a small study, built alongside the package, that shows a professor the
kind of research Nikhil does (his decision of 17 Nov 2026). The test is alignment with the group's
actual work. Where that is not possible, the study is a proof of concept on the professor's topic,
built with one of Nikhil's own methods. **The package comes first:** a study never delays a
required document.

This runbook is written from the seven studies built so far (`programs/_PORTFOLIO.md`). The model
run is `programs/MPI-GEA-Kornhuber-EconImpacts/` (`prototype/PLAN.md` and `NEXT_SESSION.md`).

## 1. Who does what

| Work | Runs in |
|---|---|
| Design, brief, git commits, clean re-run, verification pass, committee test, STE version, PDF, publishing, letters and CV | **Claude Code** (this system) |
| Analysis plan draft, scaffold, data fetch and lock, anchor, analysis, figures, note, README, site, handback | **Claude Science**, as the `PHD_RESEARCH` profile (setup: `phd-system/claude-science/INSTALL.md`) |

Checkpoints are Nikhil's, in whichever app he is using; his words are recorded in `HANDBACK.md`.

Fallback when Claude Science is not available or cannot reach a source: the build runs here, with
`phd-research` for the mechanical steps (fetch and lock, scaffold, tests). Where a step names
`phd-research` or `phd-verify` and the session has not loaded them (a session started in
`phd-system-v2` does not), run that step inline.

Claude Science reads the system folder (`D:\PHD Applications\phd-system-v2`) read-only and writes
only inside `D:\PHD Applications\programs\<Programme>\`. Its
sandbox cannot write `.git`, so Claude Code makes every commit. The two apps share files, never
memory: `prototype/BRIEF.md` goes in, `prototype/HANDBACK.md` comes back.

## 2. Folder layout

```
programs/<Programme>/
  prototype/BRIEF.md      the design and its limits, signed by Nikhil (Claude Code writes it)
  prototype/PLAN.md       the detailed plan, for M and L studies
  prototype/HANDBACK.md   state, files and claims register (Claude Science keeps it current)
  _publish/<repo>/        the public repository; its local/ folder is git-ignored
  research/               private: walkthrough, STE version, critique; never pushed
  verification_log.md     gains a "Prototype study" section
```

## 3. D: design (Claude Code) → CHECKPOINT

Read `call.md`, the supervisor digest and `programs/_PORTFOLIO.md`. Then make four decisions.

1. **What to build**, from the group's method (table below). Name the anchor: the one published
   result of the group that the study re-runs or builds on. Check its citation
   (`verification.md` check 1) and check that it has not been retracted.
2. **Which question.** Offer two to four framed options tied to the anchor. Nikhil chooses and
   words the question (canon rule 1).
3. **Size**, from the build days left once the package is safe (table below).
4. **Channel**, from what the call accepts: a link in the letter and CV (repo and site), an upload
   (`NOTE.pdf` as a writing sample), or interview material. Interview material stays private.

Form, size and channel are the agent's call, each with a one-line reason; Nikhil can overrule
them. Write `prototype/BRIEF.md` from §7. M and L studies also get `prototype/PLAN.md`, on the
pattern of the model run. List any code to reuse from an earlier study, so that Nikhil can give
Claude Science read access to that repo.
→ CHECKPOINT: the four decisions and the brief.

| The group's work centres on | Build | Done before as |
|---|---|---|
| A published quantitative result on open data | Open re-run of the result, then one extension set in advance (more years, another region) | breadbasket-waves |
| A general claim (for example, that compound shocks cost more than the sum of their parts) | Exact reproduction of an anchor paper, then a pre-registered test of the claim | compound-climate-damages |
| A model (material flow, energy system, agent-based) | A small module that changes one assumption of the model and measures the effect | dk-wind-dmfa |
| An instrument that practitioners use (a risk register, a rating, a score) | What the instrument's numbers mean, checked against public outcome data | sector-likelihood-register |
| Events and early warning | Backtests of single historical cases on public data | days-of-warning |
| Policy, labour or governance, studied in the field | Desk study of public documents, with a coding frame fixed before coding | oilpalm-labour-paperwork |
| Applied energy or infrastructure questions | Desk calculations: first-order sums and joins on public sources | splash-pool-flexibility |
| None of these, or no open data | Fallback: one of Nikhil's own methods on the professor's topic (cost modelling, LDA topic analysis, disclosure-document analysis) | his Master's thesis |

| Size | Build days | Scope |
|---|---|---|
| S | 1-2 | One question, one dataset, one or two figures, a note of about 2 pages |
| M | 3-5 | Anchor plus one pre-registered extension, a note of up to 4 pages, README, site |
| L | more than 5 | Anchor plus two or three linked parts, released one part at a time (v0.1, v0.2, ...) |

## 4. Steps and checkpoints

| Step | Runs in | Work | Ends at |
|---|---|---|---|
| S0 | Claude Science | Check the open items in the brief (data endpoints, licences, retractions, anchor numbers). Write `_publish/<repo>/ANALYSIS_PLAN.md` | **CP0: Nikhil signs the analysis plan.** Claude Code runs `git init` and commits the plan as the first commit, before S1 starts |
| S1 | Claude Science | Scaffold the repo; fetch and lock the data; tests | Tests pass |
| S2 | Claude Science | Reproduce the anchor exactly, or pass the face-validity test the plan sets | **CP1: anchor and face validity** (M and L). Claude Code commits |
| S3 | Claude Science | The registered analysis, checks and figures, with exploratory work kept apart | Results and manifest |
| S4 | Claude Science | `NOTE.md`, README, site, final `HANDBACK.md` | Handback |
| S5 | Claude Code | §6: commit, clean re-run, verification pass, committee test, STE version, walkthrough | **CP2: Nikhil reads the note beside the verification log** |
| CP3 | Claude Code | Only on Nikhil's go: create the repo, push, deploy; portfolio row; tracker; links in the letter and CV | Public |

S studies may merge S0 with S1 and S2 with S3, but CP0 and CP2 always hold. Every checkpoint is a
stop: the next step starts only on Nikhil's word. Claude Science updates `HANDBACK.md` at every
checkpoint, not only at the end, and lists there the commits it needs.

## 5. Design standards (every study)

These make the studies one body of work with one method, whichever app built them.

1. **Plan before results.** `ANALYSIS_PLAN.md` fixes the question, hypotheses, definitions,
   specifications, decision rules, the multiple-testing rule and what counts as support. It is
   signed at CP0 and committed before any result. Later changes go to `DEVIATIONS.md` with the
   date and the reason, and the note cites the plan's commit hash. For a document or text study,
   the same rule fixes the corpus, the coding frame or the topic-model settings (the rule for k,
   the seed, the preprocessing).
2. **Anchor first.** Reproduce a published number exactly, or pass a face-validity test stated in
   the plan, before any extension.
3. **Locked data.** Every source goes in `data/sources.csv` (URL, access date, licence, citation),
   with SHA-256 hashes in `data/lock.csv`. Material with an unclear licence stays in `local/`, and
   only numbers computed from it are published. Code without a licence is re-implemented from the
   paper, never copied. Check every cited work for retraction before using it.
4. **Registered and exploratory kept apart** in code, results, note and letters. A post hoc result
   is a lead, never evidence.
5. **Every null comes with its power** (the minimum detectable effect, or an interval). When the
   main result is null, the note leads with the null.
6. **Checks that fit the method:** robustness specifications, placebos, and permutation or
   randomisation inference where they apply. For a desk study: a second reading of the coded
   documents, and a source for every figure.
7. **Reproducible.** One command rebuilds every result from the locked data (`run_all.py
   --offline`). Tests cover the anchor targets, data integrity and text integrity (no em dash, no
   old double-k spelling of Nikhil's name, no co-author line). Every number in the README, note
   and site is written from `results/manifest.json`. Two offline runs give identical files.
8. **Honest framing.** The README opens with what the study is and what it is not: an independent
   study by Nikhil Sehgal on public data, not an output of the group, institution or company it
   names, and, where it applies, not new science and not a forecast. The note ends with its limits
   and with what a PhD would add.

## 6. After the handback (S5, Claude Code)

1. **Commit** with Nikhil Sehgal as the only author: no co-author line and no AI note.
2. **Clean re-run** in the repo's own environment (`uv`) from the locked data. Compare it with the
   manifest and report every difference.
3. **Verification pass** (`phd-system/methods/verification.md`) over the note, README, site and
   claims register, written to `verification_log.md` under "Prototype study". For a long note use
   `phd-verify` as the cold reader. Claude Science's reviewer verdicts are inputs, not the
   verdict: a pass supports a label but never replaces the source check; warn becomes
   `[verify]`; fail becomes CORRECTED or DO NOT CITE; inconclusive becomes UNRESOLVED.
4. **Committee test** (`phd-system/methods/critique.md`) on the note, to
   `research/<slug>-critique.md`. If the argument fails, use `methods/argument-structure.md`.
5. **For Nikhil:** a plain-English STE version (`research/<slug>-STE.md`, ASD-STE100, linted) and a
   walkthrough with the likely interview questions.
6. → CHECKPOINT CP2. Text fixes happen here. Fixes that need new analysis go back to Claude
   Science as a "Revision" section added to `BRIEF.md`.
7. **CP3, only on Nikhil's go:** create the repo, push, deploy. When the site sits in a subfolder,
   keep a root `vercel.json` and a `.vercelignore` that uploads only `site/` and `vercel.json`.
   Add the row to `programs/_PORTFOLIO.md`, update the tracker, and link the study in the letter
   and CV. A letter says only what the "A letter may say" column of the claims register allows.

## 7. Templates

### `prototype/BRIEF.md`

```markdown
# BRIEF: <study title>
Version <n>, <date>. Signed by Nikhil at D on <date>: "<his words>".

Programme: <folder>, tracker row <n>, deadline <date>. Package status: <what is done>.
Reader: <name, rank, group>. Anchor: <citation, DOI> (VERIFIED <date>, not retracted).

## Decisions
1. Build: <form from the method table>, because <reason>.
2. Question, in Nikhil's words: "<question>".
3. Size: <S | M | L>, <n> build days, done by <date>.
4. Channel: <link in letter and CV | upload | interview>. Repo name: <proposal, checked at CP3>.

## Data and materials (checked <date>)
| Source | URL | Licence | Status |
|---|---|---|---|

Local only: <items>. Re-implement, never copy: <items>. Never cite: <retracted works>.
Reuse from earlier studies (Nikhil gives read access): <repo paths and files>.

## Steps
S0 to CP0, S1, S2 to CP1, S3, S4 to handback. Stop at every checkpoint.

## Out of scope
Proposal, letters, CV and emails. Git. Pushing, deploying, posting or sending anything.

## Start line for Claude Science
"Load the phd-methods skill, then build the study in
D:\PHD Applications\programs\<Programme>\prototype\BRIEF.md from S0."
```

### `prototype/HANDBACK.md`

```markdown
# HANDBACK: <study title>, after S<n>, <date>

## State
Steps done. Checkpoint reached. Nikhil's sign-offs, quoted, with dates. Plan commit: <hash>.

## Environment and re-run
Conda environment <name>; packages and versions in <file>. Re-run: <command>, <minutes>.
Tests: <n> pass.

## Files written
<paths, relative to the programme folder>

## Claims register
| # | Claim | Kind | Status | Source or producing file | Registered? | A letter may say |
|---|---|---|---|---|---|---|

Kind: literature, data, institution or result. Literature, data and institution claims carry a
label from verification.md and a link. Results carry [I] and the manifest key or script.
Registered?: yes (plan item), exploratory, or post hoc.

## Deviations
One line per DEVIATIONS.md entry.

## Claude Science reviewer findings
| Claim | Verdict | Evidence | What was done |
|---|---|---|---|

## For Claude Code
Commits to make, with messages. Open items. Licence flags. Anything not checked.
```
