# phd-system v2 — installed

Rewritten instruction set from the 2026-08-14 audit. **Installed and live as of 2026-08-14.**

This folder is the master copy. The live files (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`,
`phd-system/`, `.claude/skills|commands|agents`, `.opencode/command`) are byte-identical to it.
Edit here and re-copy, or edit live and copy back — do not let the two drift.

v1 is preserved in `phd-system-v1-backup/` (22 files). Keep it until a full application has run
end-to-end on v2.

- `archive/audit-report.md` — counts, what changed, side findings, install record. **Read this first.**
- `archive/removed-rules.md` — every removed rule with the reason.
- `AGENTS.md` — the canon. Everything else points at it.
- `methods/verification.md` — new: the mandatory examination of research findings.
- `adapters/` — the skills, command, and subagents, in flat form. Live copies sit in `.claude/`.

`profile/candidate.md` and `profile/domain-profile.md` are data, carried over intact apart from
trimmed headers and one corrected thesis description.

---

## 2026-09-08 — Feynman research methods ported in

Six research methods and one subagent adapted from
[Feynman](https://github.com/advaitpaliwal/feynman) (MIT, Companion Inc.), the open-source AI
research agent. The clone sits at `phd-system-v2/feynman/` as read-only reference; **its own
`AGENTS.md` and `CLAUDE.md` do not govern this project.** Nothing here calls the `feynman` binary
or its alpha tools — every workflow was rewritten against Claude Code's `WebSearch`, `WebFetch`,
and `Agent`, and against this system's `programs/<Programme>/` layout.

| New file | From | Wired into |
|---|---|---|
| `methods/literature-review.md` | `prompts/lit.md` | router; `runbooks/supervisor-outreach.md` §2 (corpus mode); proposal Stage 1 |
| `methods/deep-research.md` | `prompts/deepresearch.md` | router; proposal Stage 1 |
| `methods/source-comparison.md` | `prompts/compare.md` | router; proposal Stage 1 |
| `methods/critique.md` | `prompts/review.md` + `.feynman/agents/reviewer.md` | canon §4 committee test; proposal Stage 4 |
| `methods/argument-structure.md` | `skills/paper-narrative` | router; proposal Stage 4 |
| `methods/pdf-extraction.md` | `skills/pdf-explore` | router; canon §3 intake |
| `adapters/agents/phd-verify.md` | `.feynman/agents/verifier.md` + `reviewer.md` | canon §7 |
| `adapters/skills/phd-lit.md`, `phd-critique.md` | — | intent triggers for the above |

`adapters/agents/phd-research.md` gained the integrity commandments, the wide-then-narrow search
strategy, the source-quality tiers, and the numbered evidence table from Feynman's `researcher`
agent. Its task list and limits are unchanged.

**The one real synthesis.** Feynman grades findings by severity (FATAL / MAJOR / MINOR); this
system labels them by status (VERIFIED / `[verify]` / CORRECTED / UNRESOLVED / DO NOT CITE). They
are orthogonal and now compose: `verification.md` establishes whether a claim is true,
`critique.md` grades what it costs if it is not.

**Not ported** (40 of Feynman's 48 skills): the protein and genomics stack (AlphaFold2, Boltz,
Borzoi, Chai-1, DiffDock, ESMFold, Evo2, LigandMPNN, OpenFold3, ProteinMPNN, scGPT, scvi-tools,
SolubleMPNN), remote compute (Modal, RunPod, SSH, Docker, jobs, endpoints), ML training and
autoresearch loops, figure composition, and Feynman's own product self-knowledge skills.
`alpha-research` and `eli5` were skipped because both require the `feynman alpha` CLI binary.

---

## 2026-11-19: prototype study runbook and Claude Science adapter

`runbooks/study.md` (new) installs the prototype study that goes with every application (Nikhil's
decision of 17 Nov 2026). It is written from the seven studies built so far, which are listed in
the live `programs/_PORTFOLIO.md`. Claude Science (the desktop app) is the build engine.
`claude-science/` holds its profile (`PHD_RESEARCH.profile.md`), its skill (`phd-methods/SKILL.md`)
and the setup steps (`INSTALL.md`). Both point back at the methods and runbooks, so the methods
stay in one place.

| Changed | What |
|---|---|
| `AGENTS.md` | §2 router row; §3 step 3a, study design; §4 study gate; §7 Claude Science; §8 layout |
| `runbooks/study.md` | New |
| `claude-science/` | New; live path `phd-system/claude-science/` |
| `adapters/skills/phd-study.md` | New; live path `.claude/skills/phd-study/SKILL.md` |
| `adapters/skills/phd.md`, `adapters/commands/phd.md` | Study trigger and menu entry |
| `adapters/agents/phd-research.md` | Task 5, mechanical study steps |
| `toolkit.md` | Claude Science entry |

Nikhil works in this folder (v2) only, and Claude Science reads it directly. Synced with the live
copy on 19 Nov 2026, including a lossless merge of the two profile files: `profile/candidate.md`
(live had the 13 Nov additions, among them the LDA correction) and `profile/domain-profile.md`
(live had four domain blocks, v2 the 17 Nov Daimler set). Backups of all four files are in
`archive/profile-backup-2026-11-19/`. The seven adapters that differed only by the old double-k
spelling were copied from live. The two copies are now byte-identical.
