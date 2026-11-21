# Removed rules — full record

Every rule cut from v1, with the question it failed. Nothing here was deleted from the live system;
v1 is untouched and this is the record of what v2 leaves out.

**Q1** — I would already do this without being told.
**Q2** — It corrects a weakness current models no longer have.
**Q3** — It conflicts with something else in the system.
**DUP** — True and kept, but stated once in v2 instead of in five to ten places.

---

## Q3 — Conflicts (7)

| # | Source | Rule | Why removed |
|---|---|---|---|
| 1 | `runbooks/motivation-letter.md` | Describe the MBA thesis as "regression + survey" | Factually superseded. `candidate.md` says the description was corrected to cost modelling plus LDA thematic analysis and that this "supersedes the earlier regression + survey description". A live fabrication risk sitting in a drafting instruction. Fixed in v2. |
| 2 | `runbooks/academic-cv.md`, `skills/phd-cv` | Academic CV is the default deliverable; set `academic: true` | Contradicts the standing preference (memory `resume-format-preference`, set 2026-06-25, reaffirmed 2026-08-10) for a corporate resume on every application. v1 carried the preference as a note bolted onto a runbook that still taught the opposite. v2 rewrites the runbook corporate-first. |
| 3 | `skills/phd-proposal` | Render via `generate_proposal.js` | The proposal runbook makes `md2docx.cjs` canonical and `generate_proposal.js` the alternative. Two entry points for one artifact. v2 names one renderer per artifact. |
| 4 | `skills/phd-cv` | Render via jobflow `generate-cv.mjs` | Same conflict: the runbook and toolkit make `cv-generator.cjs` canonical. |
| 5 | `AGENTS.md` §7 | "Opus 4.8", "Sonnet 4.6", "default the whole agent to Opus 4.8" | Stale model names. v2 states the delegation boundary (what may be handed off) without pinning version numbers that expire. |
| 6 | `toolkit.md` | claude-scholar clones live "under `programs/<Programme>/claude-scholar`" | Wrong path — the clones are under `Norway/` and `TUM/`. Compounded by every `/ars-*` and `/kb-*` command being referenced inline as if available when neither repo is installed in the active skills directory. v2 demotes both to one clearly-marked optional section. |
| 7 | memory `campaign-state` | Snapshot of active applications and next actions | Superseded and self-contradicting: it names `programs/_TRACKER.md` as authoritative, and its own deadlines (2026-06-30, 07-15, 08-02) have all passed. Deleted from memory; copy preserved in this folder. |

## Q1 — Would do without being told (23)

| # | Source | Rule | Note |
|---|---|---|---|
| 8 | `AGENTS.md` §8 | "When in doubt, read the runbook end-to-end before acting" | |
| 9 | `AGENTS.md` §0 | "Do not re-derive Nikkhil's identity from scratch" | The pointer to the profile files is kept; the injunction is not. |
| 10 | `AGENTS.md` §1 | "One folder per programme. Never overwrite another programme's folder." | Kept as a layout fact, dropped as a prohibition. |
| 11 | `AGENTS.md` §1 | "If a tool is missing, fall back to the embedded procedure and tell the user" | |
| 12 | `AGENTS.md` §2 | "A single request can chain runbooks" | |
| 13 | `AGENTS.md` §5 | "Self-critique: would a committee find this convincing" | Kept in compressed form as the committee test; the surrounding explanation went. |
| 14 | `runbooks/*` (all five) | "Before you start: read `candidate.md`, `domain-profile.md`, `writing-standards`, `call.md`" | Stated once in canon §0. Five near-identical paragraphs removed. |
| 15 | `runbooks/proposal.md` | "Draft, then pause per section rather than dumping the whole proposal" | Kept in one clause; the rationale went. |
| 16 | `runbooks/proposal.md` | "Cross-check every citation against reality" | Replaced by the verification method, which specifies *how*. |
| 17 | `runbooks/motivation-letter.md` | "No generic 'I am passionate about sustainability' openers" | Covered by the sharper instruction to name the problem and the group. |
| 18 | `runbooks/motivation-letter.md` | "No invented motivation, projects, or affiliations" (as a separate don't) | Folded into the single truthfulness rule. |
| 19 | `runbooks/academic-cv.md` | "Don't reuse the industry CV unchanged" | Moot once the corporate resume is the tailored default. |
| 20 | `runbooks/academic-cv.md` | "Never pad an irrelevant role" | Kept in the bullet-count line. |
| 21 | `runbooks/tracker.md` | "Convert every relative deadline to an absolute date" | Kept as three words in the row spec. |
| 22 | `runbooks/tracker.md` | "Keep terminal-status rows for history; don't delete them" | Kept as four words. |
| 23 | `runbooks/tracker.md` | "This is a campaign tool, not just a file list" | Motivational, not instructional. |
| 24 | `runbooks/supervisor-outreach.md` | "No fabricated familiarity ('I loved your 2021 paper')" | |
| 25 | `runbooks/supervisor-outreach.md` | "Prefer the official faculty-page email when one is listed" | Kept as a clause. |
| 26 | `methods/multi-perspective-scan.md` | Guardrail 1: outputs are hypotheses, not facts | Compressed into one clause; the paragraph of explanation went. |
| 27 | `methods/multi-perspective-scan.md` | Guardrail 2: consensus is not proof, personas share model priors | Same. |
| 28 | `methods/multi-perspective-scan.md` | Guardrail 4: no persona may invent Nikkhil's experience | Same. |
| 29 | `methods/multi-perspective-scan.md` | "Do not use for mechanical steps, or where a single verified source is what's needed" | Kept as one clause. |
| 30 | `toolkit.md` | "Everything degrades gracefully"; "repos are referenced, not copied"; "if the user wants these reconsidered, discuss first" | Three framing statements. |

## Q2 — Corrects a weakness current models no longer have (14)

| # | Source | Rule | Note |
|---|---|---|---|
| 31 | `writing-standards` | No AI vocabulary: "delve", "leverage", "seamless", "underscore", "vibrant" | Older-model vocabulary tics. The register rule that replaces it is stronger and shorter. |
| 32 | `writing-standards` | No copula-avoidance ("serves as") | |
| 33 | `writing-standards` | No false ranges | |
| 34 | `writing-standards` | No curly quotes | |
| 35 | `writing-standards` | No emojis in formal documents | |
| 36 | `writing-standards` | No mechanical boldface | |
| 37 | `writing-standards` | No filler or hedging | Partly contradicts the proposal register rule, which *requires* appropriate hedging ("the evidence suggests"). |
| 38 | `writing-standards` | Anti-AI rule 1: opener diversity, no phrase opens more than two consecutive sentences | Kept only for CV bullets, where it is a real formatting convention. |
| 39 | `writing-standards` | Anti-AI rule 2: length variation across sentences and paragraphs | |
| 40 | `writing-standards` | Anti-AI rule 5: specificity over abstraction | Kept as one line, since it is genuinely load-bearing for proposals. |
| 41 | `writing-standards` | Anti-AI rule 6: varied polish, plainer phrasing in places | |
| 42 | `writing-standards` | Pre-delivery item 6: "read aloud; if it sounds chatty, rewrite" | |
| 43 | `writing-standards` | Verb bank of 18 approved verbs | The formula and the avoid-list are kept; the whitelist is not. |
| 44 | `AGENTS.md` §7 | Per-step model rationale ("mechanical, cheap", "high-volume search") | The boundary is kept, the cost reasoning is not. |

## DUP — Kept, but stated once instead of many times

| Rule | v1 locations | v2 location |
|---|---|---|
| Socratic; never invent, rank, or substitute the research question | CLAUDE.md, GEMINI.md, AGENTS.md §1, proposal runbook (mode line + Stage 0 + hard boundary), skills `phd` and `phd-proposal`, both `/phd` commands, scan guardrail 3 — **10** | canon §1.1 |
| Checkpoints are mandatory | CLAUDE.md, GEMINI.md, AGENTS.md §1, every runbook, skills, commands — **9** | canon §1.2, plus the gates themselves |
| Truthful; never fabricate | AGENTS.md §1, candidate.md, all five runbooks, both agents, three skills — **11** | canon §1.3 and §5 |
| Humanizer mechanical-only, never "Personality and Soul" | AGENTS.md §5, writing-standards ×2, proposal, motivation-letter, supervisor-outreach, phd-motivation skill, phd-polish — **8** | writing-standards, one line |
| Never send outreach autonomously | supervisor-outreach ×2, phd-supervisor skill, phd-research agent — **4** | outreach runbook, one line |
| Power-up references (`/ars-*`, claude-scholar skills) | AGENTS.md §5, proposal Stages 0/1/4, supervisor-outreach ×2, tracker, toolkit ×4, phd-proposal, phd-supervisor — **13** | toolkit, one optional section |

## Not removed but flagged

- **`.commandcode/taste/taste.md`** records (confidence 0.6) that Nikkhil "expects fully autonomous
  end-to-end execution without step-by-step confirmation prompts" — which directly contradicts the
  mandatory checkpoints. He ruled on 2026-08-14 to **keep all checkpoints**. The file belongs to
  CommandCode's own learning system, so it is left alone; the ruling is recorded here and in canon
  §1.2. Note it exists in two copies that can drift.
- **`taste.md`'s** other durable item — a pre-application supervisor-fit inquiry email, kept
  separate from the formal courtesy note — was **promoted** into `runbooks/supervisor-outreach.md`,
  since it has since worked twice (van Veelen at Lund, van der Zee at Hamburg).
