---
name: phd-lit
description: >-
  Run a literature review, a deep research brief, or a source comparison for Nikhil Sehgal's PhD
  work, with every finding labelled and a provenance record written. Also runs corpus mode over a
  named lab, professor, or author to map their publication trajectory. Use when asked for a
  "literature review", "state of the art", "deep research on <topic>", "what has <professor>
  published", "compare these frameworks", or to build a proposal's evidence base.
---

Read `AGENTS.md`, then pick the method:

- Mapping a field, or a named lab / professor / author → `phd-system/methods/literature-review.md`
  (corpus mode for a person or group).
- A single question the proposal leans on, where being wrong is expensive →
  `phd-system/methods/deep-research.md`. Its plan step takes a **→ CHECKPOINT**.
- Weighing frameworks, methods, datasets, or programmes against each other →
  `phd-system/methods/source-comparison.md`.
- Reading a call PDF or a paper that spans pages → `phd-system/methods/pdf-extraction.md`.

Confirm the target programme first so output lands in `programs/<Programme>/research/`. Every
finding carries a status label from `phd-system/methods/verification.md`; nothing reaches Nikhil
or a deliverable as unmarked fact. Delegate wide sweeps to `phd-research`, keep narrow ones inline.
