# Claude Science: setup for the PhD system

Claude Science (the desktop app) builds the prototype studies and can run literature work. It
reads the methods from your working copy on disk, `D:\PHD Applications\phd-system-v2`, so they
stay in one place: `methods\`, `runbooks\study.md` and `profile\`. This folder holds the two
pointers it needs: the `phd-methods` skill and the `PHD_RESEARCH` profile, which the app calls a
specialist.

Screen names below are taken from the app's interface text (Claude Science 0.1.73).

**Status, 19 Nov 2026:** files written. The six steps under "Once" are Nikhil's, in Claude
Science.

## Once (about 10 minutes)

1. **Create the project.** Claude Science keeps every session inside a project. Click **New
   project** (on first start: **Create your first project**) and fill in:
   - **Name:** `PhD applications`
   - **Description:** `Prototype studies and research briefs for my PhD applications` (this is
     only for you; Claude does not read it)
   - **Instructions for Claude:** paste this block.

   ```text
   This project is Nikhil Sehgal's PhD application research: the prototype study for each application, and research briefs. His PhD system is in D:\PHD Applications\phd-system-v2 (read-only) and his applications are in D:\PHD Applications\programs\.

   Before any work, load the phd-methods skill and follow it. If it is not installed, read D:\PHD Applications\phd-system-v2\claude-science\phd-methods\SKILL.md instead. For a study, use the PhD Research specialist (Session options, Specialist).

   Never run git, and never push, deploy, post or send anything. The research question is Nikhil's. Stop at every checkpoint for his sign-off.
   ```
2. **Open a session** in that project: **New session**.
3. **Remove the old uv folder.** In the message box, click **+** → **Your files**. If
   `C:\Users\sehga\AppData\Roaming\uv\python` is listed, revoke it. It points at a junction: on
   18 Nov it broke new shells and the file-edit tool, and it was still loading on 19 Nov.
4. **Grant the PhD system, read-only.** In the same panel: **Grant folder…** →
   `D:\PHD Applications\phd-system-v2` → **Read-only**.
5. **Install the skill and the specialist.** Paste:

   > Load the customize skill. Then, showing me each item before you write it:
   > 1. Create a skill named phd-methods whose SKILL.md is the exact content of
   >    D:\PHD Applications\phd-system-v2\claude-science\phd-methods\SKILL.md. Keep it as a draft.
   > 2. Create the agent profile (specialist) described in
   >    D:\PHD Applications\phd-system-v2\claude-science\PHD_RESEARCH.profile.md, with full access,
   >    copying the name, display name, description and system prompt exactly.
   > 3. Read back host.skills.list() and host.agents.list() and show me that both exist.

   Approve each card it shows. If it reports that custom skills are turned off, skip the skill:
   the specialist reads the same SKILL.md from disk.
6. **Check.** **Settings** → **Customize**: **PhD Research** is listed under **Specialists**, and
   **phd-methods** under **Skills**.

## Each study

1. **Claude Code:** design the study (`runbooks/study.md` §3). It writes
   `programs\<Programme>\prototype\BRIEF.md` and gives you the start line.
2. **Claude Science:** in the **PhD applications** project, click **New session**, then
   **Session options** beside the message box → **Specialist** → **PhD Research**.
3. **+** → **Your files** → **Grant folder…** → `D:\PHD Applications\programs\<Programme>` →
   **Read & write**. Check that `phd-system-v2` (read-only) is still listed, and grant it again if
   not. If the brief names code to reuse, grant that earlier study's `_publish\<repo>` folder
   **Read-only**.
4. **Paste the start line.** It reads the files, runs S0 and stops at CP0 with a question.
5. **CP0:** read `_publish\<repo>\ANALYSIS_PLAN.md` and give your sign-off. In Claude Code, ask it
   to commit the plan; it gives you a commit hash. In Claude Science: "CP0 signed, plan committed
   as <hash>, continue with S1." CP1 works the same way.
6. **Along the way:** allow the conda environment it asks to create. Allow only the data sites the
   brief lists (they are kept under **Settings** → **Network** → **Allowed domains**). The first
   time it searches literature it asks for an OpenAlex API key: the key is free from an OpenAlex
   account; or leave literature work to Claude Code.
7. **After S4** it writes `prototype\HANDBACK.md` and stops. **Claude Code:** tell it that Claude
   Science has handed back the study. It runs S5 (commit, re-run, verification, critique, STE),
   then CP2 and CP3 with you.
8. **When the study is public,** revoke the programme folder in **+** → **Your files**.

## Keeping the two apps in step

- The methods and the runbook are read live from disk. Edits to them need nothing in Claude
  Science.
- If `phd-methods\SKILL.md` or `PHD_RESEARCH.profile.md` changes, ask Claude Science (customize
  skill) to update that skill or specialist from the file.
- Claude Science keeps its own memory. Facts about Nikhil live only in `candidate.md`.
