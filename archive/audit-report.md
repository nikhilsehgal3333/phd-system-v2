# Instruction audit — report

Run 2026-08-14 across every instruction the PhD agent carries: `CLAUDE.md`, `GEMINI.md`,
`AGENTS.md`, five runbooks, three profile files, the methods file, `toolkit.md`, five skills, two
subagents, two slash-command copies, the CommandCode taste files, four memory files, and four
`settings.local.json` files. Each rule was tested against three questions — would the model already
do this untold, does it correct a weakness current models no longer have, does it conflict with
anything else — and anything failing one was removed and recorded in `removed-rules.md`.

v1 is untouched. v2 lives in `phd-system-v2/` and is not installed.

## Counts

Rules counted as discrete directives; data (candidate facts, theory banks, verified citation sets)
is not counted as rules.

| | v1 | v2 |
|---|---|---|
| Rules | ~239 | ~136 |
| Instruction words | 8,150 | 4,912 |
| Instruction words, excluding the new verification method | 8,150 | 4,155 |
| Data words carried over unchanged | 3,646 | 3,618 |
| Files | 20 | 21 |

Instruction text is down **40%** with the new verification method included, **49%** without it.
Removed: 44 rules outright, plus ~55 duplicate statements collapsed into single locations. The
remainder is compression rather than deletion.

Per file:

| File | v1 | v2 |
|---|---|---|
| AGENTS.md | 1,682 | 874 |
| CLAUDE.md | 159 | 45 |
| GEMINI.md | 103 | — (folded into the adapter set) |
| writing standards | 525 | 275 |
| runbooks (5) | 2,501 | 1,615 |
| toolkit.md | 920 | 331 |
| multi-perspective-scan | 693 | 293 |
| skills (5) | 710 | 328 |
| commands (2 copies) | 242 | 57 (one file) |
| subagents (2) | 615 | 337 |
| **methods/verification.md** | — | **757 (new)** |
| candidate.md / domain-profile.md | 3,646 | 3,618 (data, preserved) |

## What changed structurally

**Added — the verification method** (`methods/verification.md`), at Nikkhil's request during the
audit. v1 treated "verify citations" as a one-line gate repeated in several places. v2 makes
examination of research findings a governing rule (canon §1.4) with a mandatory gate (§4) and a
five-check protocol: citation integrity, regulatory and temporal currency, feasibility of the
empirical object, people and institution facts, and a claim-by-claim sweep. Every finding carries a
status label (VERIFIED / [verify] / CORRECTED / UNRESOLVED / DO NOT CITE) and nothing unlabelled
reaches him or a deliverable.

This is not new invention. It codifies what the campaign already did ad hoc and what worked best:
the Hamburg pass caught an LkSG reporting duty described in the present tense months after the
authority stopped enforcing it and dismantled the portal, established that CSDDD cannot be the
empirical object of a PhD ending before the first data exists, and produced ten corrections on one
supervisor. Those three error classes are now checks 2, 3, and 4.

**Fixed — seven conflicts.** The thesis was still described as "regression + survey" in the letter
runbook after being corrected everywhere else; the CV runbook taught the academic layout as default
against a settled preference for the corporate resume; two artifacts had two competing renderers;
model names were stale; toolkit paths were wrong and uninstalled slash commands were referenced as
if live; a memory file had expired. Detail in `removed-rules.md`.

**Collapsed — duplication.** "Never invent the research question" appeared in 10 places, "truthful,
never fabricate" in 11, the humanizer scoping rule in 8, power-up references in 13. Each now appears
once, with adapters pointing rather than restating. This was the single largest source of words.

**Demoted — anti-AI tell lists.** Most of that section targeted older-model tics (delve, leverage,
seamless, copula-avoidance, false ranges, opener diversity, length variation). Kept: no em dashes,
no rule-of-three, no significance inflation, never casualise — genuine standing preferences that
still bind. One item was self-contradictory and removed: "no filler or hedging" against a proposal
register rule that requires appropriate hedging.

## Decisions taken during the audit

- **Checkpoints stay mandatory everywhere.** `.commandcode/taste/taste.md` had learned the opposite
  (autonomous end-to-end runs, confidence 0.6); Nikkhil ruled for checkpoints on 2026-08-14. The
  taste file belongs to CommandCode's learning system and was left alone.
- **The pre-application supervisor-fit inquiry email** was promoted from taste.md into the outreach
  runbook. It has worked twice — van Veelen endorsed the Lund angle and supplied the extended
  project description; van der Zee endorsed the Hamburg direction.
- **Memory:** `campaign-state.md` deleted (expired, and it named the tracker as authoritative);
  copy preserved here. `lca-tools-truthfulness` and `resume-format-preference` kept — both record
  real decisions, and both are now also encoded in the canon so the system does not depend on
  memory recall to stay truthful.

## Side findings (no action taken)

1. **Two `programs/` folders, two trackers.** The live one is `programs/_TRACKER.md` at the project
   root (20 rows, current). `phd-system/programs/_TRACKER.md` holds 2 rows and points at the root
   one as live. Programme folders are split across both. v2 declares the root canonical; the
   folders themselves were left where they are.
2. **Broad permission grants** in `phd-system/.claude/settings.local.json` (~60 entries):
   `PowerShell(Set-Content *)`, `PowerShell(Out-Null *)`, and `Bash(node *)` are effectively
   unrestricted write and execute. Worth narrowing.
3. **No hooks exist anywhere** in the PhD system. All four settings files are permissions-only.
4. **A second, complete instruction system** sits inside `Norway/claude-scholar` — its own
   CLAUDE.md, rules, hooks, agents, commands, skills. Inert (nothing loads it), but it would
   activate if a session started in that directory.
5. **`taste.md` exists in two copies** that can drift apart.
6. **`.opencode/command/phd.md` duplicated `.claude/commands/phd.md`** with slightly different
   wording. v2 ships one text for both.

## Install record — done 2026-08-14

v2 is **live**. v1 was backed up first to `phd-system-v1-backup/` (22 files; the project is not a
git repository, so this is the only rollback path). Then: canon to the project root; `profile`,
`runbooks`, `methods`, `toolkit.md` into `phd-system/`; the five adapters to
`.claude/skills/<name>/SKILL.md`; the command to both `.claude/commands/` and `.opencode/command/`;
the two subagents to `.claude/agents/`. The superseded `runbooks/academic-cv.md` and
`profile/writing-standards-academic.md` were deleted rather than left beside their replacements.

Two defects were caught during installation and fixed in both the live tree and this master:

1. **Broken internal paths.** Compression had left 23 references relative to the wrong base.
   `AGENTS.md` sits at the project root but said `profile/candidate.md`; the runbooks sit in
   `phd-system/runbooks/` but said `methods/verification.md`. Neither resolves. All are now
   root-relative, which is what v1 did and what works from any file. The archive files keep bare v1
   names deliberately, since they describe v1.
2. **Missing `GEMINI.md`.** v2's canon and toolkit both told Gemini CLI to read it, but v2 shipped
   no replacement, so the v1 file would have survived and contradicted the new canon. Written and
   installed.

Verified after install: live tree byte-identical to this master; no references remain to
`academic-cv.md`, `writing-standards-academic.md`, `Opus 4.8`, `Sonnet 4.6`, `generate_proposal.js`,
or `generate-cv.mjs`; all five `SKILL.md` files carry valid frontmatter; every external path
(renderers, Master Prompt, INN exemplar, tracker) resolves. **Still outstanding: the live smoke
test** — start a fresh session and run `/phd` to confirm the agent reads the new canon end to end.
