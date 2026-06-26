---
filename: litreview-talk-outline
title: "AI First: Using LLMs to Build a Literature Review Workflow"
description: Talk outline for the AIX workshop session on LLM-assisted literature review. Opens with a live student research topic, demonstrates a 4-step workflow in ~8 minutes, and closes with a replicable Google Drive handoff.
author: Steven M. Schneider
date: 2026-06-25
type: workflow
status: draft
project: SUNY Poly AIX Research Workshop
tags:
  - lit-review
  - llm
  - zotero
  - workflow
  - workshop
  - demo
  - cameroon-chad
  - litpaper
companion: llm-litreview-lesson.md
version: 1.0
---

# Talk Outline: AI First — Using LLMs to Build a Literature Review Workflow

---

## Opening: A Student's Research Topic

> *"Interconnection of the Northern Interconnected Grid (NIG) [Cameroon] with the Chad National Power Grid — determining the busbars that will yield minimal power losses, adequate voltage levels, and frequency within acceptable limits, leveraging artificial intelligence tools to propose innovative and sustainable solutions."*

Real topic. Real student. Real problem.

The first thing everyone tells you to do is a literature review.

I'm an **AI First** person. So my first step was: ask AI.

---

## What I Got Back

I asked two models — Claude and ChatGPT — the same prompt.

*[Show outputs side by side or in sequence — brief.]*

A few things worth noticing:

- Same prompt. Completely different artifact types. One wrote an essay. One built a planning scaffold.
- Both returned bibliographies. Only ~7% overlap in references — same topic, different slices of scientific memory.
- Both are useful. Neither is a literature review.

**The point:** what you get from a single prompt is a starting point, not a destination. LLMs are fabulous at this process — but it's a process, not a prompt.

---

## What LLMs Are Actually Good For (30 seconds)

- Helping you understand what the scientific literature says about your topic
- Summarizing trends, history, and frameworks
- Identifying a framework to study and explore
- Applying that framework to identify gaps and opportunities
- Helping you decide which sources to read closely
- Tracking your observations as you do close readings
- Integrating those observations into your literature synthesis

**None of that happens in one prompt. It's a workflow.**

I have that workflow documented — *[gesture to handout / Google Drive]* — but today I'm going to show you five steps in eight minutes.

---

## Toolkit

*We're not setting this up now. When you go to do this on your own, here's what you need.*

**Zotero Desktop**
Free, open-source reference manager. Your verified bibliography lives here. zotero.org.

**Zotero Browser Extension**
One-click save from any database, journal page, or Google Scholar result — metadata, abstract, and PDF when available. Install from the same page as the desktop app.

**NotebookLM** (Google)
Upload PDFs and get an instant AI-generated synthesis across all of them. notebooklm.google.com — free with a Google account.

**Gemini** (Google)
Where the seed bibliography and the Paper Extractor Gem run. gemini.google.com.

**Google Drive**
Where your papers live, and how you share them.

*A note on Zotero + Google Drive:* don't put your Zotero data folder inside Google Drive. Zotero runs on a SQLite database that Drive will try to sync while Zotero has it open — that causes corruption. The correct architecture: let **Zotero Sync** (built-in, free) handle your library metadata. Keep your PDFs in a **separate Google Drive folder** alongside your Zotero library, not inside it. That folder is also what you share with collaborators.

---

## The Five Steps (~8 minutes)

### Step 1: Prompt → Seed Bibliography
*[Already demoed — show output]*

- One well-formed prompt gets you 20–30 candidate references
- Export as `.bib` file
- Treat it as a seed, not a bibliography

*Time: ~1 min (shown)*

---

### Step 2: Import `.bib` → Zotero → Verify → Attach PDFs
*[Live demo]*

- `File > Import > BibTeX` — entire bibliography lands as a Zotero collection
- Click through each item: DOI first, URL second, title search third
- Find Available PDF for open-access items; download and attach manually for the rest
- Roughly 60–80% will resolve to real, accessible papers in a well-scoped topic
- What doesn't resolve is your confabulation rate — worth noting

*Time: ~2 min*

---

### Step 3: Upload PDFs to NotebookLM → "Brain Dead" Lit Review
*[Live demo]*

- Open NotebookLM, create a new notebook
- Upload all verified PDFs (3–5 from Zotero)
- NotebookLM reads across all sources and generates a synthesis automatically — no prompting skill required
- What you get: a reasonable summary of what the papers collectively say, with source citations pinned to passages

This is the easy button. It's fast and it's useful.

What it isn't: a warranted literature review. It summarizes presence. It does not argue about absence. It has no standpoint, no gap claim, no theoretical framing. It's a reading aid, not a research contribution.

*Time: ~2 min*

---

### Step 4: Export PDFs → Paper Extractor Gem → Grounded Notes
*[Live demo — Gem pre-loaded]*

- Export 3–5 verified PDFs from Zotero to a local folder
- Upload to Gemini with the Paper Extractor Gem active
- One call per paper: argument, methods, key findings, relevance, quotable passage, DOI anchor
- Output is a structured note grounded in the document, not model memory

*Time: ~2 min*

---

### Step 5: Handoff — Replicate It Yourself
*[Share Google Drive link]*

- All demo papers are in the shared Drive folder
- My `.bib`, my Zotero export, my extracted notes — all there
- The Paper Extractor Gem instructions are in the folder — copy them into your own Gemini session
- Replication is the point

*Time: ~1 min*

---

## Closing

The tools are fabulous. Use them for everything that can be specified — retrieval, organization, extraction, cataloging.

What you cannot hand off: the warrant. Deciding what the gaps mean. Building the argument. That's the research.

But you'll get there faster, and on a firmer foundation, if the organizational work is done right.

*[Reference full workflow document and Google Drive.]*

---

## Materials Referenced

- `llm-litreview-lesson.md` — full workflow documentation
- Google Drive: AIX Research Workbench folder (shared link in session)
- Paper Extractor Gem instructions — in the Drive folder, ready to copy into Gemini

---
