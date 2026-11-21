---
name: phd-methods
description: "Research work for Nikhil Sehgal's PhD applications, done by the rules and methods of his PhD system on disk. Use when asked to build a prototype study for a PhD programme, to run a study step from a BRIEF.md, or to do a literature review, deep research brief, source comparison or long PDF read for one of his applications."
---

# PhD methods (Claude Science side)

The methods live on disk in Nikhil's PhD system. This skill only says where they are and how to
run them here. Read the files every time; never work from memory of an earlier session.

## 1. Read first, in this order

1. `D:\PHD Applications\phd-system-v2\profile\candidate.md`: the only source of facts about Nikhil.
   Its "Hard rules" section is binding.
2. `D:\PHD Applications\phd-system-v2\profile\writing-standards.md`.
3. `D:\PHD Applications\phd-system-v2\methods\verification.md`: the status labels you must use.
4. The method file for the task (table below). For a study, also the programme's
   `prototype\BRIEF.md` and, if there is one, `prototype\PLAN.md` and `prototype\HANDBACK.md`.

If a file cannot be read, stop and tell Nikhil which folder access is missing (step 2 of
`D:\PHD Applications\phd-system-v2\claude-science\INSTALL.md`). Do not continue from memory.

If you are not running as the PHD_RESEARCH profile, ask Nikhil to switch to it
(`host.agents.switch("PHD_RESEARCH")`, see the `customize` skill) before you start a study.

## 2. Task to method

Method paths are relative to `D:\PHD Applications\phd-system-v2`. Outputs are relative to
the programme folder.

| Task | Follow | Tools to use here | Output |
|---|---|---|---|
| Prototype study, or one step of it | `runbooks\study.md` | Python or R in the study's conda environment; `figure-style` for every figure, so all studies share one look; `figure-composer` for multi-panel figures; `paper-narrative` on the note and figures at S4 | `_publish\<repo>\` and `prototype\HANDBACK.md` |
| Literature review, state of the art, a professor's publications | `methods\literature-review.md` | the `literature-review` skill's `search_openalex` and `crossref_lookup`, for retrieval only | `research\<slug>.md` and `research\<slug>.provenance.md` |
| Deep research on one question | `methods\deep-research.md` (its plan step is a checkpoint) | as above | as above |
| Compare methods, datasets or frameworks | `methods\source-comparison.md` | as above | `research\<slug>.md` |
| Read a long PDF | `methods\pdf-extraction.md` | `pdf-explore` | notes in `research\` |

The method file sets the steps and the output format. A bundled skill supplies tools only: where
its workflow and the method file differ, the method file wins. Everything you write is a draft
for Claude Code to review before it reaches a deliverable.

## 3. Rules for this app

- Write only inside `D:\PHD Applications\programs\<Programme>\`. A result kept only as a Claude
  Science artifact never reaches Claude Code.
- No git: the sandbox cannot write `.git`. List the commits you need in `HANDBACK.md`, under "For
  Claude Code". S1 does not start until Claude Code has committed the signed analysis plan.
- Never push, deploy, post, email or contact anyone.
- One conda environment per study, named after the repo, with the packages in its
  `pyproject.toml`. CPU only: this PC has no working GPU. No remote compute without Nikhil's go.
- Facts about Nikhil come only from `candidate.md`. Do not save them to memory.
- At every checkpoint, stop with `ask_user` and wait. Quote his answer and the date in
  `HANDBACK.md`.
- If a data domain is blocked, list it in `HANDBACK.md`: Claude Code can fetch the file into the
  repo's `local\` folder.

## 4. Before every handback: export the reviewer findings

In the `repl` tool:

```python
import json, os
os.makedirs("handoff", exist_ok=True)
json.dump(host.findings(), open("handoff/findings.json", "w"), indent=1, default=str)
```

Then, in a `python` cell, read `handoff/findings.json` and write each finding into the "Claude
Science reviewer findings" table of `HANDBACK.md`, with what you did about it. Translate each
verdict into the labels of `verification.md`: warn is `[verify]`, fail is CORRECTED or DO NOT
CITE, inconclusive is UNRESOLVED. A pass supports a label; it is not VERIFIED without a source
link.
