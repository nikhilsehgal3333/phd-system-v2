# CLAUDE.md — adapter

PhD Application Agent for Nikhil Sehgal. The canon is **`AGENTS.md`** — read it and follow it.

Claude Code specifics: skills in `.claude/skills/phd*` trigger by intent, or run `/phd`. Subagents
`phd-research` (mechanical steps, wide literature sweeps), `phd-verify` (citation and severity
passes on a finished draft), and `phd-polish` (finished-draft polish) are described in
`AGENTS.md` §7.

`phd-system-v2/feynman/` is a vendored read-only reference clone of
[Feynman](https://github.com/advaitpaliwal/feynman) (MIT), the source material for the research
methods. Its own `AGENTS.md` and `CLAUDE.md` do not govern this project — the canon above does.
