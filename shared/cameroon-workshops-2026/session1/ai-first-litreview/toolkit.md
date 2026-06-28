---
filename: toolkit
title: AI-First Literature Review — Toolkit
description: The five tools needed for the AI-first literature review workflow, with setup links, free-tier notes, and the critical Zotero + Google Drive architecture constraint.
author: Steven M. Schneider
date: 2026-06-28
type: reference
status: final
project: SUNY Poly AIX Research Workshop
companion: workflow.md
tags:
  - toolkit
  - zotero
  - notebooklm
  - gemini
  - tools
  - cameroon-2026
---

# Toolkit — What You Need

*We don't set this up in the session. When you go to do this on your own, here's what you need and where to get it.*

---

## 1. Zotero Desktop

**What it does:** Reference manager. Your verified bibliography lives here. Import `.bib` files from any LLM, manage PDFs, tag by source or model.

**Cost:** Free, open-source.

**Get it:** https://www.zotero.org

**Why Zotero specifically:** It is the only reference manager that gives you full control over your data, works offline, and exports to every citation format. It also receives `.bib` files directly — which is exactly what you ask an LLM to produce.

---

## 2. Zotero Browser Extension (Connector)

**What it does:** One-click save from any database, journal page, or Google Scholar result — captures metadata, abstract, and PDF when available.

**Cost:** Free.

**Get it:** https://www.zotero.org/download/connectors

**Install from:** the same page as the desktop app. Available for Chrome, Firefox, Safari, Edge.

**How to use it:** When you find a paper in Google Scholar, IEEE Xplore, or your library, click the Zotero icon in your browser. The metadata imports automatically. No copy-paste.

---

## 3. NotebookLM

**What it does:** Upload PDFs and get an AI-generated synthesis across all of them. Summaries, Q&A, and an audio overview — all grounded in your specific uploaded sources, not the model's training data.

**Cost:** Free with a Google account.

**Get it:** https://notebooklm.google.com

**The ceiling:** NotebookLM summarizes *presence* — what the papers say. It does not argue about *absence* — what the field hasn't done yet. It is a reading aid, not a research contribution. Use it for Step 3 of the workflow (synthesis), not as a replacement for your own gap analysis.

---

## 4. Gemini

**What it does:** The tool for Step 1 (seed bibliography) and Step 4 (Paper Extractor Gem — grounded per-paper notes). Can also be used for Steps 1–4 from `first-steps`.

**Cost:** Free tier available.

**Get it:** https://gemini.google.com

**Free tier note:** The Paper Extractor Gem workflow runs on Gemini. Upload a PDF directly; Gemini processes the actual document rather than drawing from training memory. This is what makes the notes grounded.

**For the Paper Extractor Gem:** instructions are in the shared Google Drive folder for this workshop. Copy them into your own Gemini session to replicate Step 4.

---

## 5. Google Drive

**What it does:** Stores your verified PDFs and enables sharing with collaborators and your AI workspace.

**Cost:** Free tier (15GB).

**Get it:** https://drive.google.com

**Important:** Keep your Google Drive PDF folder *separate* from your Zotero data folder. See architecture note below.

---

## Architecture Note — Zotero + Google Drive

> **Do not put your Zotero data folder inside Google Drive.**

Zotero stores its library in a SQLite database. Google Drive attempts to sync files while they are open — this causes database corruption. The symptoms appear days later as mysterious library errors.

**Correct architecture:**

1. Let **Zotero Sync** (built into Zotero, free up to 300MB) handle your library metadata — citations, notes, tags, collections.
2. Keep your **PDFs in a separate Google Drive folder** that is *not* inside the Zotero data directory.
3. That Drive folder is also what you share with collaborators and upload to NotebookLM or Gemini.

Your Zotero data directory (where the database lives): `~/Zotero/` on Mac/Linux, `C:\Users\[name]\Zotero\` on Windows. Do not move it into Google Drive, Dropbox, or OneDrive.

---

## Quick Reference

| Tool | Cost | Primary use in workflow |
|------|------|------------------------|
| Zotero Desktop | Free | Store and verify bibliography |
| Zotero Browser Extension | Free | Capture papers from databases |
| NotebookLM | Free | Synthesize verified PDFs |
| Gemini | Free tier | Seed bib + per-paper extraction |
| Google Drive | Free tier | PDF storage + sharing |
