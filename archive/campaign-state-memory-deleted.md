---
name: campaign-state
description: "Snapshot of active applications and next actions (context save, as of 2026-06-25)"
metadata: 
  node_type: memory
  type: project
  originSessionId: 2fa5971e-e6b7-4db5-94af-3865efe77fd3
---

Context save from the 2026-06-25 session. Live PhD status lives in `programs/_TRACKER.md` (the
authoritative source — read it); this is the quick-resume snapshot plus the items not in that tracker.

## Active applications and immediate next action
- **Bayreuth LignUp** (Dr.-Ing., LCA of lignin) — deadline **2026-06-30**. Letter + CV ready and
  truthfulness-fixed (OneClick LCA, no "DAX", em-dash clean); thesis summary, supervisors.md, email to
  Helbig, submission_checklist all done. **Next: scan certificates/transcripts, submit via UBT portal
  (keyword "ÖRT LignUp").** Folder: `phd-system/programs/Bayreuth-LignUp/`.
- **ETH NCCR CLIM+** (Position 2, circular economy × climate resilience) — deadline **2026-06-30**
  (rolling). `proposal_NCCR_ClimPlus.md` + `research_statement_NCCR_ClimPlus.md` drafted; Pfeffer
  citation fixed (journal = Environmental Innovation and Societal Transitions). **Next: letter + CV in
  that folder STILL target the old ACHIEVE position — re-point them to Clim+; add 2 referees; render
  proposal to docx if wanted.** Folder: `phd-system/programs/ETH-CircularEconomy/`.
- **Maastricht** (Sustainable, Long-term Investment Decisions, ID 3279) — deadline **2026-07-15**.
  Full set done: academic CV + **corporate resume**, motivation letter, research_statement (GRI
  cross-framework angle), supervisors.md, email_draft (Pownall = r.pownall@maastrichtuniversity.nl,
  high confidence). **Next: confirm Wiehenkamp's Effctl email, your review, submit via portal.**
- **TUI Cruises — Qualitäts-/Prozessmanagement (CORPORATE, not a PhD; not in the PhD tracker)** —
  German Lebenslauf done (`corporate-applications/TUI-Cruises-QM/`), positioned around ISO 14001 +
  process/controls + Schulungen + audit-prep; ISO 9001/auditor framed as Weiterbildung (not claimed).
  **Next: German Anschreiben (pending), confirm Hamburg relocation (footer assumes yes), attach Zeugnisse.**
- **INN/INSEPP** (flagship, fit 8.5) — deadline **2026-08-02**. Strongest bet; still pending docs.
- **Linnaeus timber connections** — **declined** (fit 2.5; FEM/structural-engineering requirements
  outside profile). **TUM / Goethe / Linz (older)** — see tracker; confirm submitted.

## Durable decisions made this session (also captured elsewhere)
- **Default CV deliverable is now the corporate resume from the Master Prompt**, not the academic CV
  (see [[resume-format-preference]]; `academic-cv.md` updated). Build with `cv-generator.cjs`,
  `academic:false`. Reference build: `Maastricht-SustainableFinance/render_maastricht_resume.js`.
- **Multi-perspective scan** added as an optional, guard-railed method
  (`phd-system/methods/multi-perspective-scan.md`), wired into AGENTS.md §5/§8, toolkit, and the
  proposal/tracker/supervisor runbooks. Outputs are hypotheses, never citable evidence; never picks the RQ.
- **Thesis description corrected** everywhere to mixed-methods cost modelling + Latent Dirichlet
  Allocation (not "regression + survey"); `candidate.md` updated.
- LCA tools: OneClick LCA only (see [[lca-tools-truthfulness]]).
