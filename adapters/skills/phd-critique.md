---
name: phd-critique
description: >-
  Verify and stress-test a finished PhD artifact for Nikhil Sehgal — check every citation resolves
  and supports its claim, then grade the weaknesses FATAL / MAJOR / MINOR with a revision plan. Use
  when asked to "check my proposal", "verify these sources", "critique this draft", "what would a
  committee say", "review this paper", or before anything is submitted or sent.
---

Read `AGENTS.md`, then run both passes:

1. `phd-system/methods/verification.md` — the five checks, and a status label on every claim.
2. `phd-system/methods/critique.md` — severity grading, quoted passages, revision plan.

Fix every **FATAL** before the artifact goes anywhere, then re-run the pass over the fix. **MAJOR**
is fixed or surfaced as an acknowledged limitation, never left silent. **MINOR** is accepted.

Corrections go to `programs/<Programme>/verification_log.md` stated plainly: what the draft said,
what is true, what changes downstream. Prove applied fixes landed by grepping for the old and new
wording — never report a fix on the strength of having issued the edit.

Delegate to the `phd-verify` subagent for a long draft, where a cold reader catches drift the
drafter cannot see. Run it inline for a short one. If the argument itself is what fails rather than
the evidence, switch to `phd-system/methods/argument-structure.md`.
