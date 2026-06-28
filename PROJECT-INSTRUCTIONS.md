---
filename: PROJECT-INSTRUCTIONS
title: Project Instructions — SUNY Poly AIX Research Workshop
description: Authoring conventions, YAML specifications, file naming rules, and output defaults for all artifacts produced under the SUNY Poly AIX Research Workshop project.
author: Steven M. Schneider
date: 2026-06-25
type: project-instructions
status: reference
project: SUNY Poly AIX Research Workshop
---

# Project Instructions — SUNY Poly AIX Research Workshop

## Author

Steven M. Schneider

---

## File Format

All outputs are `.md` (Markdown) unless otherwise specified.

---

## File Naming

- No spaces, no special characters
- Lowercase, hyphen-separated
- Descriptive and specific
- Examples: `llm-litreview-workflow`, `litpaper-SKILL`, `document-analysis-extraction-dimensions`

---

## YAML Frontmatter — Required Fields

Every file produced under this project includes a YAML frontmatter block at the top with the following fields:

```yaml
---
filename: [filename-without-extension]
title: [Full Human-Readable Title]
description: [One to two sentence description of what this file is and what it's for.]
author: Steven M. Schneider
date: [YYYY-MM-DD]
type: [see types below]
status: [draft | reference | final]
project: SUNY Poly AIX Research Workshop
tags:
  - [tag]
  - [tag]
---
```

---

## Types

- `lesson` — workshop teaching document
- `workflow` — activity framework or process description
- `reference` — schema, dimensions, glossary, or lookup document
- `skill` — portable Claude skill file (trigger-based)
- `note` — Zettel or literature note
- `artifact` — primary research or analytical output
- `project-instructions` — this file and files like it

---

## Optional YAML Fields

Include when relevant:

```yaml
companion: [filename of related document]
evidence_base:
  - [source file]
  - [source file]
zotero_group: [URL]
doi: [https://doi.org/...]
cite_key: [AuthorYYYY]
trigger: [//skillname]
version: [1.0]
```

---

## Output Path

All files go to `/mnt/user-data/outputs/` unless a subdirectory is specified (e.g. `/mnt/user-data/outputs/notes/` for Zettel and litpaper outputs).

---

## Project Context

This project produces workshop materials for the SUNY Poly AIX (Artificial Intelligence Experience) initiative, oriented toward graduate researchers and faculty at partner institutions. Materials are designed to be portable, citable, and reusable across workshop contexts.

Key frameworks in use:
- The Ethical Cuboid (Needs × Scale × Temporal)
- Five-phase LLM-assisted literature research workflow
- Zettel-first document analysis
- `//litpaper` skill for grounded per-paper note generation
- Zotero group library: https://www.zotero.org/groups/6596845/ai-tools-for-research
