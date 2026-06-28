---
filename: workflow
title: AI-First Literature Review — Five-Step Workflow
description: The complete five-step live demo workflow for AI-assisted literature review — from seed bibliography through Zotero verification, NotebookLM synthesis, and per-paper grounded note extraction.
author: Steven M. Schneider
date: 2026-06-28
type: workflow
status: final
project: SUNY Poly AIX Research Workshop
companion: toolkit.md
tags:
  - workflow
  - literature-review
  - zotero
  - notebooklm
  - gemini
  - cameroon-2026
---

# Five-Step Workflow — AI-First Literature Review

*Eight minutes, start to finish.*

This workflow covers the bibliographic and identification phase of literature research — what the field sometimes loosely calls a "literature review." It is more precisely described as: finding papers, screening them, extracting structured notes, and synthesizing across them. The actual literature review — the original argument about what is absent from the field — comes after this workflow, not from it.

---

## Step 1 — Prompt → Seed Bibliography

**Time:** ~1 minute  
**Tool:** Gemini (or any LLM)  
**Status:** Already demonstrated

One well-formed prompt gets you 20–30 candidate references. Ask for output as a `.bib` file — this imports directly into Zotero without copy-paste.

**What to ask for:**
- References relevant to your specific research question
- Output format: BibTeX (`.bib`)
- Request the model flag any items it is uncertain about

**Critical framing:** This is a *seed* bibliography, not a bibliography. Every item needs verification before you cite it. The model does not have access to your library's holdings. It does not know what was published last month. It will occasionally confabulate — producing plausible-looking but nonexistent references.

**Run two models:** Ask Gemini and one other (Claude, ChatGPT). Import both as separate Zotero collections with a tag indicating the source model. The ~7% overlap rate between models means the union of both lists is substantially richer than either alone.

---

## Step 2 — Import .bib → Zotero → Verify → Attach PDFs

**Time:** ~2 minutes  
**Tool:** Zotero Desktop  
**Status:** Live demo

```
File → Import → BibTeX (.bib file from Step 1)
```

The entire bibliography lands as a Zotero collection. Now verify each item:

1. **DOI first** — click the DOI link. Does it resolve to the paper the citation describes?
2. **URL second** — if no DOI, try the URL.
3. **Title search third** — search Google Scholar for the exact title.

For each verified paper:
- Right-click → Find Available PDF (works for open-access papers)
- For paywalled papers: check your institutional access, then try Unpaywall or the author's ResearchGate page

**What to track:**
- Items that resolve correctly: verified, add PDF
- Items that don't resolve: flag as confabulated, delete
- Your confabulation rate (items that don't resolve ÷ total items) is worth noting — it varies significantly by topic and model

**Expected rate:** on a well-scoped technical topic, 60–80% of items will resolve to real, accessible papers.

---

## Step 3 — Upload PDFs to NotebookLM → "Brain Dead" Synthesis

**Time:** ~2 minutes  
**Tool:** NotebookLM (https://notebooklm.google.com)  
**Status:** Live demo

1. Open NotebookLM, create a new notebook
2. Upload 3–5 verified PDFs from your Zotero library (export to a local folder first)
3. NotebookLM synthesizes across all sources automatically — no prompting skill required

**What you get:** A summary of what the papers collectively say, with citations pinned to specific passages. Ask follow-up questions and it answers from your sources, not from its training data.

**The ceiling:** This is fast and genuinely useful. It is not a warranted literature review.

NotebookLM summarizes *presence* — what the papers say. It does not argue about *absence* — what the field has not done. It has no standpoint outside the documents. It cannot make a gap claim. It cannot identify what is missing from a field. That requires a researcher who stands outside the corpus — and that is you.

Use NotebookLM as a reading aid and orientation tool, not as a replacement for your own synthesis.

---

## Step 4 — Export PDFs → Paper Extractor Gem → Grounded Notes

**Time:** ~2 minutes  
**Tool:** Gemini with Paper Extractor Gem  
**Status:** Live demo — Gem pre-loaded

The Paper Extractor Gem produces a structured note for each paper, grounded in the actual document:

- **Argument:** What claim does this paper make?
- **Methods:** How does it make that claim?
- **Key findings:** What did it find?
- **Relevance:** How does it connect to your research question?
- **Quotable passage:** One passage worth quoting directly
- **DOI anchor:** For citation

**How to use it:**
1. Export 3–5 verified PDFs from Zotero to a local folder
2. Open Gemini with the Paper Extractor Gem active
3. Upload one PDF at a time; run the extraction prompt

**Why this is different from Step 3:** NotebookLM synthesizes *across* papers. The Paper Extractor Gem extracts *per paper*. You need both: orientation (Step 3) and granular notes (Step 4).

**The Gem instructions** are in the shared Drive folder for this workshop. Copy them into your own Gemini session to replicate this step on your own papers.

---

## Step 5 — Handoff — Replicate It Yourself

**Time:** ~1 minute  
**Status:** Share Drive link

Everything from the demo is in the shared Google Drive folder:

- The `.bib` files from both models (Gemini and Claude)
- The Zotero export of verified papers
- The extracted notes from Step 4
- The Paper Extractor Gem instructions

**Replication is the point.** The workflow takes about 8 minutes on a well-scoped topic. The bottleneck is Step 2 (verification) — and that bottleneck is intentional. Every item you verify is an item you have read enough to know is real. That is not friction to remove; that is the minimum due diligence that stands between a seed bibliography and a citable one.

---

## What This Workflow Is — and Isn't

| This workflow produces | This workflow does not produce |
|----------------------|-------------------------------|
| A seed bibliography (Step 1) | A final citable bibliography |
| A verified paper set (Step 2) | A complete literature review |
| A synthesis of what papers say (Step 3) | An argument about what is absent |
| Structured per-paper notes (Step 4) | Your original gap claim |

The gap claim — the argument that something is missing from the field that your research will address — comes after this workflow. It requires a researcher who stands outside the corpus. Steps 1–4 give you organized material to think with. The thinking is yours.
