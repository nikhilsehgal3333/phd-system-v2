# Toolkit — renderers and tools

## Renderers (house style, Arial) — one per artifact, no alternatives

| Artifact | Call |
|---|---|
| Proposal, any markdown | `node "D:/Resume/Agent Skill/md2docx.cjs" proposal <src>.md <out>.docx` — run from `D:/Resume/Agent Skill` so `docx` resolves. Kinds: `proposal` (justified, hanging-indent refs) · `letter` · `cv` |
| CV / resume | `cv-generator.cjs` → `generateCV(data)`. `academic: false` is the default (see `phd-system/runbooks/cv.md`) |
| Cover / motivation letter | `cv-generator.cjs` → `generateCoverLetter(data)` |

**Working template for both CV and letter:** `D:/Resume/Agent Skill/_gen_inn_house.cjs` — clone it
and edit its `cv` / `letter` objects. Recent reference builds live in the programme folders
(`render_lund.cjs`, `render_tub_aic_cv.cjs`).

## Source documents
- `D:/Resume/Agent Skill/Nikkhil_Sehgal_Master_Prompt_v4.md` — full experience inventory and bullet
  banks. The CV default draws from here.
- `D:/Resume/Agent Skill/INN_INSEPP_PhD_Proposal.md` — proposal structure exemplar.
- `D:/Resume/Agent Skill/humanizer/SKILL.md` — mechanical AI-tell removal. Never its "Personality
  and Soul" section on a formal document.

## Search and fetch
- **find-contact** (built-in skill) — best single-person email lookup.
- **gooseworks** (built-in skill) — people, web, LinkedIn, company search.
- **WebSearch / WebFetch** — the default for verification passes. Cite the URL in the log.
- **CloakBrowser** (`D:/Agent/GIthub/CloakBrowser`) — stealth fetch for JS-heavy or blocked call
  pages. **browser-harness** (`D:/Agent/GIthub/browser-harness`) — CDP control of a running Chrome
  for interactive portals.

## Optional power-ups (not installed — do not reference their commands as if live)
`claude-scholar` (`D:/Agent/GIthub/claude-scholar`) and `academic-research-skills`
(`D:/Agent/GIthub/academic-research-skills`) add literature-review, citation-verification, and
reviewer slash commands. Neither is installed in the active skills directory, so every `/ars-*` and
`/kb-*` command is currently unavailable; the runbooks are written to work without them. Install
per each repo's README if wanted. `notebooklm-py` (`D:/Agent/GIthub/notebooklm-py`) can bulk-digest
a supervisor's papers; it needs `.env` auth.

Deliberately unused: `autoresearch` (LLM training loop), `researchpooler` (superseded), `caveman`
(token compression, harmful to prose), `gstack` (software team roles).

## Per-CLI entry points
Claude Code reads `CLAUDE.md`; Gemini CLI reads `GEMINI.md`; OpenCode, Codex, Cursor and the rest
read `AGENTS.md` directly. All of them point at `AGENTS.md` — keep logic there.

Claude Science (the desktop app) uses the `PHD_RESEARCH` profile and the `phd-methods` skill,
installed from `phd-system/claude-science/` (see its `INSTALL.md`). Both point back at the
methods and runbooks here.
