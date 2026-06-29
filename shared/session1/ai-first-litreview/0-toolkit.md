---
layout: default
title: "AI Research Toolkit"
---

# 0-toolkit.md — Your AI Research Toolkit

Before running the pipeline, set up your browser. This takes about ten minutes and only needs to be done once.

---

## Zotero

Zotero is your reference manager — it captures sources, stores PDFs, and exports bibliographies. Set it up first; everything else builds on it.

- <a href="../zotero-setup-guide" target="_blank" rel="noopener">Zotero Setup Guide ↗</a> — Installation, Google Drive integration, and folder structure
- <a href="../zotero-prompt-customizer.html" target="_blank" rel="noopener">Zotero Prompt Customizer ↗</a> — Generate custom export prompts for your research question

---

## Browser Extensions

Install these in Chrome. All are free.

| Extension | What it does | Install |
|-----------|-------------|---------|
| **Zotero Connector** | Captures sources from any browser page into Zotero | zotero.org/download |
| **Claude Conversation Exporter** | Exports Claude conversations as Markdown | Chrome Web Store |
| **Claude QoL** (Export, Fork, Search) | Fork conversations, search within sessions | Chrome Web Store |
| **Claude Usage Tracker** | Shows your token usage against plan limits | Chrome Web Store |
| **ChatGPT Exporter** | Exports ChatGPT conversations as Markdown | Chrome Web Store |
| **Gemini Chat Exporter** | Exports Gemini conversations as PDF, Text, or CSV | Chrome Web Store |
| **Markdown Reader** | Previews .md files natively in the browser | Chrome Web Store |
| **Google Docs Offline** | Keeps your documents editable without internet | Chrome Web Store |

---

## Archive Folder

Create this folder structure in Google Drive now, before you start:

```
/research-archive/
  /claude/
  /chatgpt/
  /gemini/
```

After every substantive conversation: export, name the file something recognizable, drop it in the right folder. You cannot go back to what you didn't save.

---

## The Pipeline You Are About to Run

| Step | Tool | What happens |
|------|------|-------------|
| 1 | Claude | Frame your research question |
| 2 | Perplexity | Discover the literature |
| 3 | Zotero | Capture the sources |
| 4 | Gemini | Read and compare the sources |
| 5 | NotebookLM | Interrogate the sources |
| 6 | Claude | Draft the literature review |

Each step leaves a file. By the end, you have a complete audit trail of your thinking.
