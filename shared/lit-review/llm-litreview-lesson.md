---
title: LLMs Automate the Part of a Literature Review That Isn't the Hard Part
date: 2026-06-24
type: lesson
status: draft
project: sunypolyaix
audience: workshop participants — graduate researchers, faculty
model: claude-sonnet-4-6
tags:
  - lit-review
  - llm
  - zotero
  - research-methods
  - workshop
  - ai-tools-for-research
  - grounded-synthesis
  - prompt-engineering
evidence_base:
  - claude-sonnet-1shot-artifact.md
  - chatgpt-thinking-1shot-artifact.md
  - claude-sonnet-1shot-bib.bib
  - chatgpt-thinking-1shot-bib.bib
  - chatgpt-thinking-diff.md
  - claude-sonnet-diff.md
  - three-versions-compared.md
zotero_group: https://www.zotero.org/groups/6596845/ai-tools-for-research
---

# Lesson: LLMs Automate the Part of a Literature Review That Isn't the Hard Part

*Developed from a comparative experiment: Claude Sonnet 4.6 vs ChatGPT o1 on a 1-shot literature review prompt, read alongside a three-model comparison (Haiku / Opus / Sonnet) on LLM-assisted lit review methods.*

---

## The Thesis

LLMs are excellent at literature review. They cannot do literature analysis. These are not the same activity, and conflating them is the central mistake in how people deploy these tools — and in most of what the LLM-lit-review literature recommends.

**Literature review** is the labor: find papers, screen them, extract claims, organize and summarize. LLMs are genuinely, impressively good at this. They save 60–80 hours of volume work on a well-scoped topic. The tools are fabulous.

**Literature analysis** is the thinking: identify what's missing, see what's assumed, notice what two frameworks can't simultaneously be true, make the conceptual move the literature hasn't made. LLMs cannot do this — not because they're imperfect at it, but structurally, because they are trained on what exists and analysis requires seeing what doesn't.

That boundary holds regardless of which model you use and regardless of how you prompt it. It is not a prompt engineering problem.

---

## Why the Boundary Is Structural

Three reasons, each independent:

**Gaps are defined by absence.** An LLM can notice disagreement — two conflicting claims both appear in training data. It cannot notice silence. The question "what has this literature failed to ask?" requires standing outside the corpus. The model lives inside it.

**Analysis extrapolates; LLMs interpolate.** Novel synthesis means moving to a position the existing literature hasn't occupied — the assumption neither framework questions, the reframing that would dissolve a stale debate. LLMs generate by interpolation within their training distribution. Interpolation is useful. It is not the same operation as extrapolation.

**Coherence erases tension.** LLMs smooth contradiction into synthesis. But the intellectual work often lives in the incommensurability — "these two frameworks cannot both be right about X, and that tells us something about what each is carrying." The model is constitutively disposed to resolve tension rather than hold it.

An LLM given your assembled corpus will produce plausible-sounding synthesis. That synthesis will be a smooth interpolation of the existing literature — competent summary that a federal funder or dissertation committee will immediately recognize as not having an argument. The model will not produce the sentence "what both literatures fail to see is X" because it has no mechanism for identifying X. You do.

---

## What the Comparative Experiment Adds

The Claude vs ChatGPT experiment — and the three-model comparison — is a valuable lesson in its own right, though it's distinct from the structural point above.

It reveals: the same prompt produces fundamentally different artifact types across models. Claude Sonnet interpreted "help me develop a literature review" as a writing task and produced 4,224 words of narrative prose. ChatGPT o1 interpreted it as a planning task and produced a scaffolded research framework with 108 bullet lines and 41 table rows. Both coherent; neither what the other produced.

The three-model comparison sharpens this: Haiku saw a survey task (57 references, comprehensive), Opus saw a decision-support task (26 references, high-signal), Sonnet saw a navigation task (balanced, hedged). The differences are systematic — each model's choices hang together internally — not random variation.

And the bibliography finding: only 3 of 42 references shared between Claude and ChatGPT (~7%). Both cited real papers. The non-overlap isn't hallucination; it's corpus selection bias — each model drawing from a different slice of parametric memory, filtered through its interpretation of the task.

These findings matter for how you use the tools in the review phases: specify the artifact type explicitly, run two models to see the interpretation space, treat any generated bibliography as a seed to verify and extend rather than coverage to trust. They are also a reminder that "prompt engineering" is real — you can close some of the interpretation gap with better specifications.

But none of that touches the structural argument. You cannot prompt your way to analysis. You cannot choose the right model for it. The boundary is the same regardless.

---

## The Workflow Implication

**Phases 1–3: Search, screen, extract — use the models**

Use an LLM to produce a seed bibliography and narrative orientation. Verify every citation. Run a real database search (Scopus, WoS, Google Scholar) anchored to this seed — the LLM drafts Boolean strings well, but the search runs in a real database. Use the LLM to extract structured fields from abstracts and PDFs once you have your verified corpus. Human spot-checks every cell.

**Phase 4: Analysis — yours**

Read the organized corpus. Think. Write. The LLM cannot do this phase. It can draft passages once you know what you're arguing — give it your thesis sentence and the papers you want synthesized, and it will produce good prose. But it cannot find the thesis. This phase takes 60–100 hours on a serious research question. There is no shortcut.

**Phase 5: Supporting materials — use the models again**

Appendices, citation formatting, reference maps, passage-level drafting within frames you have established.

---

## Summary

The tools are fabulous. Use them hard for Phases 1–3 and 5. Doing so frees the time and cognitive space for Phase 4 — which is where the research actually lives.

The boundary is: **LLMs give you organized material to think with. The thinking is yours.** That is not a limitation to work around. It is the condition of doing research.

---

## Building a Verified Corpus via Zotero

The problem: an LLM gives you a bibliography of 20–25 references. Some are real. Some have errors. Some are behind paywalls. You need a verified local corpus of PDFs before you can do anything grounded with the literature.

The technique: treat the model-generated `.bib` file as a structured import, not a reading list — and use Zotero as the bridge between the model's output and a corpus you actually control.

*[Live demo: Zotero desktop app, group library at zotero.org/groups/6596845/ai-tools-for-research, tag structure, PDF attachment workflow.]*

### What a Good Model-Generated .bib Gives You

A well-prompted model will produce a `.bib` file with the following fields populated:

- **`doi`** — your most reliable hook; resolves directly to the publisher page
- **`url`** — direct link, sometimes to the PDF, sometimes to the abstract page
- **`note`** — content summary the model generated while writing; useful for triage before you've read anything
- **`keywords`** — tag with the model name (e.g., `keywords = {claude}`) so collections from multiple models are filterable after import

### Step 1: Import the .bib into Zotero

`File > Import > BibTeX (.bib)` — Zotero creates a collection from the file. All entries land as items with metadata. Most will not yet have PDFs attached.

If you ran two models, import both. They land as separate collections with different keyword tags. You can now see the full combined bibliography, the overlap, and the model-only entries in one interface.

### Step 2: Click Through to Verify and Download

*[Live demo: clicking through each item, using Zotero's Find PDF, navigating to publisher pages, saving PDFs to desktop, attaching to Zotero records.]*

For each item, in order of reliability:

**DOI present:** Right-click > Find Available PDF. Zotero's resolver finds open-access versions automatically for many papers. If it comes back empty, click the DOI, go to the publisher page, download from there (institutional access) or check for a green open-access version.

**arXiv eprint:** The URL goes directly to the PDF. Free and reliable. Download and attach.

**URL only:** Navigate to it. Check whether it resolves to an actual document. Some model-generated URLs are constructed plausibly but don't exist — a 404 is a signal to search the title directly in Google Scholar before discarding the entry.

**Author listed as "Anonymous":** The model generated the entry from partial information. Search by title. Sometimes the paper is real and the model didn't have the authors. Sometimes it isn't. Either way, verify before discarding.

Use the model's `note` field to triage your download queue: papers with direct methodological relevance first, background framing later. You're building a reading order as you verify.

### Step 3: What You End Up With

A Zotero collection of verified items with PDFs attached, tagged by source model. Typically 60–80% of a well-generated bibliography survives verification as real, accessible papers. The 20–40% that don't — wrong DOIs, plausible-but-nonexistent URLs, anonymous entries that don't resolve — is your hallucination and confabulation rate for the session. Worth noting.

Export the attached PDFs as files to a local folder. You now have a verified corpus.

### Step 4: Upload the Corpus to the LLM for Grounded Synthesis

Upload the PDF files together with the original `.bib` file. The `.bib` supplies structured metadata (authors, DOIs, your note summaries); the PDFs supply the actual content. The model is no longer generating from parametric memory — it is reading documents you have verified exist.

Prompt for per-paper outputs, not a single synthesis pass. For each paper, ask for a structured note: what it argues, its methods, its key findings, its relevance to your research question, and the DOI formatted as a citation anchor.

Save each note as a `.md` file named by the cite key (`Che2025.md`, `Ndoumbe2024.md`). Each note carries the DOI inline.

### Step 5: Assemble the Notes into a Literature Review

You now have a folder of `.md` notes, each grounded in a verified PDF, each with a DOI citation. The assembly step — grouping by theme, writing transitions, building the argument — is yours. The raw material is accurate, traceable, and organized.

The difference from the 1-shot approach is structural. In the 1-shot, the model cited what it remembered. Here, it reads what you verified. Citations point to documents you hold. Every claim is checkable against the source PDF.

---

## The `//litpaper` Skill

The workflow above can be packaged as a portable skill file — a plain `.md` document containing prompting instructions that any researcher can drop into their own Claude session or Cowork setup and immediately use.

*[Live demo: opening the skill file, showing the trigger, running it against an uploaded PDF.]*

The skill below is self-contained. Copy it, save it as `litpaper-SKILL.md`, share it, import it. It gives anyone in the workshop the same grounded note-generation workflow without having to reconstruct the prompting logic from scratch.

---

```markdown
---
name: litpaper
version: 1.0
trigger: "//litpaper"
type: artifact
artifact_type: skill
project: lit-review
date: 2026-06-24
status: reference
description: >
  Processes one uploaded PDF (with optional .bib entry) and generates a
  structured literature note as a .md file with DOI citation anchor, methods
  summary, key findings, and relevance statement. Use during Phase 3 of a
  grounded lit review workflow — after the corpus is verified in Zotero and
  PDFs are exported. One call per paper. Output is ready to assemble into a
  literature review.
---

# litpaper skill

When I type `//litpaper`, process the uploaded PDF (and any accompanying .bib
metadata) and generate one structured `.md` note for this paper.

## What this skill is for

Extracting grounded, citable notes from verified PDFs during Phase 3 of a
literature review. The model reads the actual document — not its memory of the
topic. Output is a `.md` file named by cite key, with DOI embedded, ready to
assemble into a literature review.

Not for: generating bibliographies from scratch (that is Phase 1 work).
Not for: synthesizing across multiple papers (do that manually in Phase 4).

## Inputs expected

- **Required:** one PDF, uploaded to the session
- **Optional:** the `.bib` entry for this paper, pasted into the prompt —
  supplies cite key, DOI, and the model's original note field as context

## Output format

```
---
cite_key: [from .bib if provided, else AuthorYYYY]
title: [full paper title]
authors: [last names, et al. if >3]
year: [YYYY]
doi: [DOI string, formatted as https://doi.org/...]
source: [journal / conference / report series]
type: litpaper
date_noted: [YYYY-MM-DD]
tags:
  - [method or domain tag]
  - [method or domain tag]
  - [topic tag]
relevance: [1–5]/5
---

## Argument

[2–3 sentences: what the paper claims and why it matters to the field.]

## Methods

[2–3 sentences: what data, what approach, what analytical procedure.]

## Key findings

- [finding — stated as a fact, not a summary hedge]
- [finding]
- [finding]

## Relevance to this study

[2–3 sentences: how this paper connects to the researcher's specific question.
Write as if the researcher's topic is known from context. Be specific.]

## Quotable

> "[verbatim quote most likely to be cited]" (p. X)

## Open questions this paper raises

- [genuine unresolved question]
- [genuine unresolved question]
```

## Rules

- Read the PDF. Do not generate from memory. If a claim is not in the document,
  do not include it.
- Every finding must be checkable against the source. No hedging language
  ("suggests," "may indicate") unless the paper itself hedges.
- DOI field must be a resolvable URL. If the .bib entry has a doi field, use it.
  If not, leave it blank rather than guessing.
- Relevance section must reference the researcher's specific question, not the
  paper's topic in general.
- Quotable section: one quote, verbatim, with page number. If no page numbers
  are available (web document), omit rather than approximate.

## Output path

```
/mnt/user-data/outputs/notes/[cite_key].md
```

## Output rule

Output ONLY the file contents. No preamble, no commentary, no explanation.
```

---

*Evidence base: `claude-sonnet-1shot-artifact.md`, `chatgpt-thinking-1shot-artifact.md`, `claude-sonnet-1shot-bib.bib`, `chatgpt-thinking-1shot-bib.bib`, `chatgpt-thinking-diff.md`, `claude-sonnet-diff.md`, `three-versions-compared.md`*
