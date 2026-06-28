---
layout: default
title: "Step 4 — NotebookLM"
---

# 4-notebooklm.md — NotebookLM

## Tool
NotebookLM (notebooklm.google.com) · Google

---

## What it is

NotebookLM is a document-grounded AI workspace. You upload sources — PDFs, Google Docs, web URLs, YouTube videos — and the model is constrained to those sources only. It cannot draw from its training data. Every answer it gives is cited to a specific passage in your uploaded documents.

That constraint is the point.

---

## Why it matters here

At this stage in the pipeline you have three papers and a Gemini synthesis. Gemini read everything together and mapped the landscape. NotebookLM lets you interrogate specific claims against specific text — and every time it answers, it tells you exactly where in which paper the answer came from.

After a large-context synthesis like Gemini's, NotebookLM functions as the verification layer. You can ask it something Gemini said and confirm whether the papers actually support it, or where the support is thin.

---

## Key features

**Grounded answers with pinned citations**
Every response links to the exact passage. You can click through to the source text. The model cannot confabulate — if the answer isn't in your sources, it says so.

**Cross-document interrogation**
Ask questions that span multiple papers. NotebookLM searches across all your uploaded sources simultaneously, not one at a time.

**Audio overview**
NotebookLM can generate a podcast-style conversation between two AI hosts summarizing your sources. Useful for orientation, for accessibility, and for students who absorb material better by listening than reading.

**Study guide and briefing document**
Auto-generates structured summaries, FAQs, and timelines from your uploaded sources.

---

## The pedagogical value

Most AI tools expand outward — they connect your question to everything they know. NotebookLM contracts inward — it connects your question only to what you gave it. For research purposes, that is often exactly what you need: a way to stay inside the literature rather than drift beyond it.

---

## Gisèle's notebook

<a href="https://notebooklm.google.com/notebook/93454ab8-7437-4fbd-b698-6d23ccafa211" target="_blank" rel="noopener">Open the NIG–Chad notebook ↗</a>

Five sources loaded: the three reference PDFs from Zotero plus the Perplexity and Gemini outputs.

---

## Audio overview — how it was generated

Format: **Critique** — an expert review of the sources offering constructive feedback.
Length: Default · Language: English · Sources: 5

Focus prompt given to the AI hosts:

> Help me develop a review of literature to begin studying the "Interconnection of the Northern Interconnected Grid (NIG) [Cameroon] with the Chad National Power Grid," to determine the busbars that will yield minimal power losses, adequate voltage levels, and frequency within acceptable limits. This project will focus on analyzing the technical, economic, and strategic challenges of this interconnection with the Chadian grid, leveraging artificial intelligence tools to propose innovative and sustainable solutions to enhance service quality, stability, and reliability of the power system.

The Critique format is particularly useful here: rather than a neutral summary, the hosts evaluate the literature — identifying where coverage is strong, where it is thin, and what a researcher working on this specific problem still needs to find.
