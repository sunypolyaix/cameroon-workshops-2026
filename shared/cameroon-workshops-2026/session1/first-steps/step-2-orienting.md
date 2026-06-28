---
filename: step-2-orienting
title: First Steps — Step 2: Orienting to the Field
description: The five-move workflow for building an organized literature base inside a persistent AI workspace — setup, mapping, gathering, building the corpus, and interrogating it.
author: Steven M. Schneider
date: 2026-06-28
type: workflow
status: final
project: SUNY Poly AIX Research Workshop
companion: prompts.md
tags:
  - workflow
  - literature-review
  - research-methods
  - ai-workspace
  - cameroon-2026
---

# Step 2 — Orienting to the Field

*S'orienter dans le domaine*

All five moves happen inside a single AI workspace session or Project. The workspace becomes a persistent research environment — not a one-off chat, a configured instrument for the thesis.

---

## Move 1 — Set Up the Workspace

**What you do:** Create one project or session for the whole thesis. Write project instructions that ground every subsequent interaction.

**The goal:** Every chat starts with your question in context. The AI is told how to behave before it does anything else.

**Project instructions template:**

> "This project supports my thesis: [question]. Be my critical reading partner. Use only sources I upload — never invent citations. Flag what you're unsure of."

**Tool options:**
- **Claude Projects** (paid tier) — persistent instructions, persistent uploaded documents
- **Gemini** (free tier) — paste the instructions block at the start of each session; keep a Google Doc with your running context to paste back in
- **NotebookLM** — not for this move, but ideal for Move 4

---

## Move 2 — Map Search Terms

**What you do:** Ask the AI to decompose your question into searchable components.

**What you get:** Synonyms for each core concept, 5 ready-to-paste query strings for Google Scholar / arXiv / IEEE Xplore, and a list of subfields and venues to search.

**Why this matters:** Different databases use different vocabulary. A query that returns 200 results on Google Scholar may return 3 on IEEE Xplore if you don't adapt the terminology.

**The prompt (see prompts.md for bilingual version):**

> "Break my question into core concepts. Give me synonyms and 5 query strings ready to paste into Google Scholar and arXiv. Name the subfields and key venues where this work typically appears."

---

## Move 3 — Gather Sources

**What you do:** Run those queries yourself, in the actual databases.

**This move belongs to you.** The AI cannot fetch papers and should not pretend to. It does not know what your library has access to. It does not know what was published last month.

**Where to search:**
- Google Scholar — broad, good for snowballing via "cited by" and "related articles"
- arXiv — preprints in CS, physics, engineering, economics
- IEEE Xplore — electrical engineering, power systems, computer science
- Semantic Scholar — strong on citation graphs
- Your institutional library — check what full-text access you have

**Snowball outward:** for every paper you keep, check its reference list and its "cited by" list. The most-cited papers in your specific question space will surface quickly.

**Output:** A set of PDFs, downloaded and organized. You judge which are relevant — that judgment is yours.

---

## Move 4 — Build the Set

**What you do:** Upload what you gathered into your AI workspace as knowledge.

**What changes:** The AI is now grounded in your actual sources, not its training data. Every answer it gives can be traced back to a document you selected and uploaded.

**The prompt:**

> "Here are the papers I gathered. For each: problem, method, key result, limitation in 3 lines. Then name the 5 most central to my question, and why."

**Tool note:** NotebookLM is purpose-built for this move. Upload PDFs, get a synthesis grounded in your sources, with citations pinned to specific passages. Use it alongside your main workspace, not instead of it.

---

## Move 5 — Interrogate and Keep a Living Log

**What you do:** Ask the AI to compare your sources and surface where they disagree or leave gaps. Keep a running log in your workspace — update it as new papers arrive.

**The prompt:**

> "Build a table comparing these papers by method, workload type, key metric, and limitation. Where do they disagree? What hasn't been tested yet for [your specific context]?"

**The living log:** A document (in your Project, in a Google Doc, in Obsidian) that accumulates your observations across sessions. Not a summary — a record of your thinking as it develops.

**Guardrails:**
- Claude and Gemini can invent references. Trust only sources you uploaded or verified yourself.
- You decide what is relevant and where the gap is. The AI maps presence; you identify absence.
- Check every factual claim against the actual paper before you write it into your thesis.

---

## Quick Reference

| Move | Who | Tool |
|------|-----|------|
| 1 — Set up workspace | You | Claude Project / Gemini session |
| 2 — Map search terms | AI | Any LLM |
| 3 — Gather sources | **You** | Google Scholar, IEEE Xplore, library |
| 4 — Build the set | You + AI | NotebookLM, Claude Project |
| 5 — Interrogate + log | AI + You | Claude Project, Gemini + Google Doc |
