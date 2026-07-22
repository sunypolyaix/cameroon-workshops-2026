---
title: "pdf2md — Onboarding & Synthesis Brief"
date: 2026-07-17
project: tdac-ac
type: artifact
artifact_type: handoff-brief
status: draft
version: v1
companion:
  - 2026-05-26-literature-review-workflow.md
  - document-analysis-extraction-dimensions.md
  - task-specificiation-meta-lit-review.md
references: pdf-llm-sources.bib
tags: pdf2md, pdf-to-markdown, extraction, rag, pipeline, recipe, evaluation, paperqa2, elicit, tdac-ac
source: claude-conversation (pdf2md1–3), five project docs, pdf-llm-sources.bib, live web search 2026-07-17
---

# pdf2md — Onboarding & Synthesis Brief

For colleagues considering joining the **pdf2md** group. pdf2md owns **Stage 4** of the lit-review pipeline (PDF → text/markdown). Everything downstream — synthesis, zettels, model-in-the-loop inference — reasons over whatever this stage produces, so its fidelity is a hard ceiling on the whole program.

This brief answers three questions, then adds a synthesis and an outline for a toolkit paper:

1. **What is a PDF** — why do we have it, and what was it optimized for?
2. **What are the primary challenges** in transforming PDFs (especially, but not exclusively, scientific and research papers) into structured markdown we can probe deeply with an LLM — and what is the **state of the art**, in both open-source (free to install) and paid services?
3. **What would a pipeline look like for us to build** — one that converts a directory of PDFs according to a *recipe* (specifying process, techniques, and evaluation metric) and yields a set of `.md` documents with YAML frontmatter that identifies the recipe and reports the evaluation metrics?

The three sections below answer these in turn.

---

## Q1 · What PDF is, why we have it, and what it was optimized for

### Q1.1 · Origins and optimization target

PDF (Adobe, 1993) was optimized for one thing: a **fixed visual rendering that looks identical on any system** — print fidelity, layout preservation, tamper-resistance. It solved a real 1990s pain: send a document to anyone, on any OS, and it displays the same. For legal, finance, HR, and government workflows where appearance and non-repudiation matter, that was genuinely valuable.

### Q1.2 · How it escaped its scope — the lock-in

PDF escaped its intended scope. Because it was already standardized and embedded in a million workflows, PDF became the default transmission format for *everything* crossing organizational boundaries — contracts, regulations, medical records, court filings, and academic papers. The lock-in mechanism: Adobe bundled a free Reader (installed base), then had the format ratified as **ISO 32000 (2008)**, which lent it the veneer of a neutral open standard while Adobe's implementation stayed the reference. Institutions stopped investing in semantic document standards — why build extractable, re-purposable data infrastructure when you can "just PDF it"? Switching costs are now astronomical: trillions of documents already exist in the format.

### Q1.3 · Why it matters for us

PDF encodes *visual layout*, not *semantic structure*. There is no tag that says "this is a heading," "this is a table," "read this column first," or "this claim is the novel contribution vs. background." That absence is the root of every problem in the next section. The critique is not new — Jakob Nielsen argued PDFs were unfit for on-screen reading in 1996 and reconfirmed it in 2020 — and the LLM/machine-reading critique that emerged in the 2022–2024 RAG era is rediscovering the same complaint from the other end. The `llms.txt` proposal (authors publish a parallel machine-readable summary) is one response.

---

## Q2 · The conversion challenge, and the state of the art

### Q2.1 · Extraction challenges (acute for scientific / archive papers)

Tables flatten into garbled text (the semantic grid — which cell belongs to which row/column — is lost). Multi-column layouts interleave into arbitrary reading order. Figures and charts are not extractable data, only images. Footnotes, captions, and body text are undifferentiated. Equations need special handling. Scanned/older PDFs have no text layer at all and require OCR.

### Q2.2 · The interpretive ceiling

Even *perfect* text extraction loses something a parser can never recover: which findings are the paper's novel contribution vs. background, which claims are tentative vs. confident, where the real limitations sit. That interpretive scaffolding lived in the reader's head during active reading — it was never encoded in the PDF. So "de-PDFing" cleanly solves the mechanical layer; it does not solve the interpretive one. Downstream models reason over a flattened representation, and that uncertainty has to be accounted for in what we claim. This is measurable: benchmarking PDF/PPTX→markdown ingestion shows text is reliably extracted but significant information is lost from charts and diagrams specifically [@simmeringMeetYourNew2025], and LLM summaries drawn from papers were found ~5× more likely to overgeneralize conclusions than human summaries (Peters & Chin-Yee) — even "successful" extraction can fail downstream.

### Q2.3 · How you measure it

There is no single metric. The reference benchmark is **OmniDocBench** (CVPR 2025; 1,600+ annotated pages, edit-distance for text, TEDS for tables, explicit reading-order and formula scoring). Accuracy splits three ways — *words right*, *structure preserved*, *intent captured* — and a tool can pass one while failing another. Two design cautions from recent benchmarks: presentation-only variance (line breaks, list segmentation, alternative table renderings) is largely irrelevant downstream and over-penalizes tools, so unit-test-style checks that target concrete failure modes are fairer than raw edit distance [@rigalBenchmarkingVisionLanguageModels2026]; and the most decision-useful measure is **downstream-task parity** (does the markdown answer questions as well as the source?). The strongest evidence we have [@santosPDFRAGReadyEvaluating2026] compared Docling, MinerU, Marker, and DeepSeek OCR across 21 configurations on a domain corpus. Two baselines bounded the results: a naïve PDF loader at **86.2%** QA accuracy and hand-curated markdown at **91.3%**. **The core finding overturns the intuitive ceiling.** Docling with hierarchy-aware splitting and image descriptions reached **94.1%** — beating manual curation. It did so because data-prep dominated: chunking strategy and metadata enrichment contributed more to accuracy than the converter choice. An exploratory GraphRAG variant actually *underperformed* basic RAG (82%). The lesson for our recipe: the converter is necessary, but it is not where most of the accuracy lives — chunking and metadata are.

### Q2.4 · State of the art — open source (free to install)

| Tool | Strength | Notes |
|---|---|---|
| **MinerU** (OpenDataLab) | Complex academic papers, CJK, formulas | v2.5 is now a VLM-based parser; outputs MD + JSON; broad hardware support |
| **Docling** (IBM) | Structured output, research docs | First-class LlamaIndex / LangChain integration; self-hostable |
| **Marker** | Fast, JSON schema extraction | Benchmarks competitively vs. paid services; fully open, self-hostable |
| **MarkItDown** (Microsoft), **PyMuPDF4LLM** | Lightweight, many formats | Good defaults; PyMuPDF4LLM auto-OCRs scans (weaker on handwriting) |
| **Pandoc** | Generalist (40+ formats) | *Not* purpose-built for PDF→MD; strips structure — avoid for this |

The clear 2025–2026 trend is **vision-language parsers** that render each page as an image and let a multimodal model read layout, tables, and reading order.

### Q2.5 · State of the art — paid services

| Service | Approach | Best for | Approx. cost |
|---|---|---|---|
| **Mistral OCR 3** | OCR → markdown model | Cheap, high-volume, multilingual; you chunk/embed downstream | ~$1–2 / 1,000 pages (≈$1 batch) |
| **LlamaParse** (LlamaCloud) | VLM parser, LlamaIndex-native | RAG pipelines; layout bounding boxes; multiple output formats | credit-based (~$1 / 1,000 credits); Agentic Plus up to ~$0.09/page |
| **Reducto** | Multi-pass CV + OCR + VLM, agentic | Complex/dense tables (~99–100%), reviewable provenance; SOC2/HIPAA, on-prem | from ~$0.015 / page |
| **Unstructured** | Layout-aware + RAG chunking | Broad format coverage; pipeline integration | from ~$1 / 1,000 pages |
| **Mathpix** | Math/STEM OCR | Equations, LaTeX-heavy papers | usage-based |
| **AWS Textract · Azure Doc Intelligence · Google Document AI** | Form/table specialists | Forms, receipts, IDs; confidence scores + bounding boxes; Google leads handwriting | from ~$1.50 / 1,000 pages |

Effective cost spans roughly free → ~$0.09 / page depending on mode. Vendor pricing and tiers shift frequently, so verify current numbers before procurement — and test on *our* documents rather than trusting vendor benchmarks (the same caution as for open-source tools).

### Q2.6 · A different category — retrieval / synthesis frameworks (PaperQA2, Elicit)

These are *not* PDF→MD converters; they wrap parsing inside an agentic retrieval + synthesis loop and hand back *answers*, not markdown you own.
- **PaperQA2** (FutureHouse, open source): point it at a folder of PDFs; it fetches metadata (incl. citation counts and a **retraction check**), parses and caches into a full-text index, then answers with an agentic RAG loop (query expansion, re-ranking, contextual summarization). Reports superhuman results on LitQA2-style tasks. Caveats: token-heavy in agentic mode; moved to CalVer in Dec 2025, so **pin versions**; a Zotero-integrated fork exists.
- **Elicit** (freemium/paid, hosted): indexes ~138M papers via Semantic Scholar, does structured extraction into sortable tables, PRISMA workflows, sentence-level citations, Zotero import. Caveats: academic literature only (no grey literature — a gap for TDAC's broad-source mandate); independent work (Lau et al., 2025) found screening sensitivity fell from a benchmarked **96.9%** to **37.9%** under realistic search strategies. Validate on *our* corpus, not vendor benchmarks.

---

## Q3 · The pipeline we would build

### Q3.1 · Shape

A directory of PDFs **+ a recipe file** in → a set of `.md` files (one per PDF) with YAML frontmatter that records the recipe and the evaluation metrics out. The recipe is the **reproducibility contract**: because PDF→MD is *deterministic once the toolchain and versions are locked*, the same recipe on the same PDF yields byte-identical markdown. We validate the recipe **once** against a hand-built gold-standard set, then trust it at scale.

```
pdf2md/
├── recipes/
│   └── scientific-v1.yaml        ← process · techniques · eval-metric
├── gold/                         ← 20–30 PDFs + hand-curated reference .md
│   └── <name>.pdf + <name>.ref.md
├── in/                           ← corpus to convert
└── out/                          ← one .md per PDF, YAML-tagged
```

### Q3.2 · The recipe — what the operator specifies

**`scientific-v1.yaml`:**
```yaml
recipe_id: scientific-v1
process:
  converter: mineru
  converter_version: 2.5.0        # pinned → determinism
  ocr_fallback: true
  chunking: section-aware
techniques:                        # dimensions to characterize per doc
  extract: [headings, tables, reading_order, figures, footnotes, references]
  schema: document-analysis-extraction-dimensions.md   # our draft 8-dim schema
evaluation_metric:
  gold_set: gold/
  structural: {tables_TEDS: true, reading_order: true, headings_F1: true}
  downstream_parity: {task: qa, judge: llm, baseline: curated_md}
  provenance: {record_extractor: true, flag_losses: true}
```

### Q3.3 · Output frontmatter — what each `.md` carries
```yaml
source_pdf: smith2021.pdf
recipe_id: scientific-v1
converter: mineru@2.5.0
converted_at: 2026-07-17
eval:
  structural_fidelity: 0.94       # vs. gold class "born-digital"
  tables_TEDS: 0.88
  downstream_qa_parity: 0.93
  doc_class: born-digital-2col
losses: ["figure 3 not data-extracted", "1 nested table flattened"]
```

This pipeline wouldn't inherit existing principles — the group doesn't have settled ones yet; it would **establish** them. Two to start: *version the recipe* (commit the toolchain, thresholds, and prompts so any run is reproducible), and *ship a structured characterization record with every document*, using the **document-analysis extraction-dimensions** schema as the "techniques" list so each converted doc carries structured metadata, not just prose. The `.bib`/Zotero export handles bibliographic metadata; this frontmatter handles fidelity and provenance.

### Q3.4 · Best-source-first routing (the LaTeX shortcut)

For a scientific corpus, one shortcut is worth building in: for arXiv papers (a large share of what TDAC will cite), skip the PDF entirely and convert from the **LaTeX source**, which preserves structure, labels, sectioning, macros, and authorial intent that PDF extraction distorts or loses — a documented, tooling-backed workflow exists for LaTeX→markdown/JSONL [@verhoeffAIFriendlyLaTeXUsing2026]. The recipe should route by availability: LaTeX source → born-digital PDF → scanned/OCR, best-source-first. On the efficiency side, the newest academic-PDF converters exploit the high n-gram overlap between a PDF and its markdown (copy-from-source decoding, layout-aware editing) to cut conversion latency 40–70% at equal quality [@duanAcceleratingEndtoEndPDF2026; @duanLayoutAwareTextEditing2026] — relevant once we scale to tens of thousands of documents.

---

## Synthesis

PDF→MD is, at the mechanical level, a **solved and deterministic problem** — pick a purpose-built converter, lock the version, and outputs are repeatable. So the group's real deliverables are not "a converter" but: (1) a **validated converter + recipe** chosen by benchmarking two or three candidates on *our own* corpus (vendor benchmarks don't transfer — this is the same cross-model-comparison discipline from `three-versions-compared.md`, applied to tools); (2) an honest **error profile per document class** ("94% structural fidelity on born-digital, 78% on scans"); and (3) explicit acknowledgment that the **interpretive ceiling** is not a parsing bug to fix but a constraint to declare. Frameworks like PaperQA2 and Elicit are attractive because they fold parsing, retrieval, and synthesis together — but they hand back answers we must trust, whereas a converter hands back markdown we own and can audit. That trade — control and auditability vs. convenience and speed — is the central design decision.

**Open questions for the group / Steve (unresolved):**
1. **Positioning of PaperQA2 & Elicit** — downstream consumers of our markdown, the retrieval engine we wrap, or baselines we benchmark against? (Opus's earlier insight: running PaperQA2 as a *parallel validation* against the human-assembled corpus turns Month-1 work into a methodological contribution.)
2. **Mandate** — select-and-validate an off-the-shelf converter, build a custom orchestrated pipeline, or both (eval harness + adoption recommendation)?
3. **What the recipe's eval-metric optimizes** — structural fidelity, downstream-task parity, provenance/audit fields, or all three weighted.

---

## Outline — technical / toolkit paper

The paper has two parts: **Part 1** is the convert-and-own-the-markdown approach (pdf2md); **Part 2** is the alternative that extracts knowledge from PDFs *without* producing a markdown artifact at all (pdf2mk — "managed knowledge").

### Part 1 — pdf2md: convert the PDF, own the markdown (~5 pg)

1. **Problem & motivation (~0.5 pg).** PDF as a fixed-layout format with no semantic structure; the interpretive ceiling; why this blocks a literature-grounded, model-in-the-loop program at TDAC scale.
2. **Background (~0.5 pg).** The two critique lineages (usability → machine-reading); deterministic vs. probabilistic pipeline stages (extraction/RAG/graph = deterministic when pinned; LLM generation = probabilistic); why that split defines where to place the human-verification trust boundary.
3. **Landscape & evaluation (~1 pg).** Open-source (MinerU, Docling, Marker, MarkItDown, PyMuPDF4LLM) vs. paid (Mistral OCR, LlamaParse, Reducto) vs. frameworks (PaperQA2, Elicit); OmniDocBench and downstream-parity metrics; the 86.2% / 91.3% / 94.1% loader–manual–best-automated bounds and the finding that chunking + metadata dominate the converter choice.
4. **The recipe-driven pipeline (~1.5 pg).** Architecture (directory + recipe → YAML-tagged `.md`); recipe and frontmatter schemas; the gold-standard set; validate-once-then-lock; integration of the 8-dimension characterization schema; determinism/provenance guarantees.
5. **Evaluation results & recommendation (~1 pg).** Benchmark of the shortlisted converters on our own corpus by document class; error profiles; a build-vs-adopt recommendation.

### Part 2 — pdf2mk (managed knowledge): extract knowledge without the markdown (~2–3 pg)

6. **The alternative model (~1 pg).** Agentic RAG over PDFs (**PaperQA2**) and hosted research assistants (**Elicit**) as a *parallel* path: point the tool at the PDFs, and it parses, indexes, retrieves, and answers with cited responses — you never produce, store, or audit a markdown artifact. What you gain: no MD engineering, built-in retrieval + synthesis, citation grounding. What you give up: the intermediate markdown you can inspect, version, re-chunk, and reuse across any downstream model.
7. **Cost & control tradeoff (~1 pg) — "do we pay for the PDF reads every time?"** *No — not per read.* In both tools, parsing/OCR + embedding a document is a **one-time, cached step**: PaperQA2 builds a persistent local full-text + vector index; Elicit stores your uploads (or queries its pre-built ~138M-paper index). You do **not** re-parse the same PDF for each question. What recurs is **LLM inference per query** — and in agentic mode that is many model calls (search → re-rank → contextual summarize → answer), so it is *token-heavy per question*. So the recurring cost is priced per **question**, not per **read**: PaperQA2 (self-hosted, open source) spends *your own* API tokens on each agentic query; Elicit (hosted) spends *credits/subscription* per search, report, or extraction. Re-indexing (e.g., if you change the embedding model) re-incurs the cheap one-time parse/embed cost, not a per-read charge. **The cost *shape* is the real contrast with Part 1:** convert-to-MD is a one-time cost, after which the markdown is yours to query forever, with any model, at only your own inference cost; pdf2mk folds parse + retrieve + synthesize together but you keep paying per question (and with Elicit you are renting the index).
8. **When pdf2mk beats pdf2md, and vice versa (~0.5–1 pg).** pdf2mk wins for fast, exploratory question-answering over a stable corpus with low audit requirements; pdf2md wins when you need an inspectable, versioned, reusable artifact and full provenance (the TDAC/federal-funder case). The **parallel-validation design**: run PaperQA2 against the human-assembled corpus and score its answers against the pdf2md pipeline — this turns the Month-1 literature review into a miniature of the main TDAC question (AI vs. human analytical output under bounded information), converting a deliverable into a methodological contribution. Governance notes: data-retention and PII implications of sending PDFs to a hosted service; auditability of a rented index vs. an owned markdown corpus.

*Appendix:* recipe files, gold-set construction protocol, per-tool version pins.

---

## Key sources (from `pdf-llm-sources.bib`)

The curated `pdf-llm` set grounds this brief. Where each lands:

- **[@santosPDFRAGReadyEvaluating2026]** — *From PDF to RAG-Ready* (Applied Sciences, 2026). Our primary evaluation evidence: converter comparison by downstream QA accuracy; data-prep dominates. paper outline §3 + eval design. DOI: https://doi.org/10.3390/app16105069
- **[@rigalBenchmarkingVisionLanguageModels2026]** — *Benchmarking VLMs for French PDF-to-Markdown*. Evaluation should discount presentation-only variance; unit-test-style checks. Paper outline §3. DOI: https://doi.org/10.48550/arXiv.2602.11960
- **[@simmeringMeetYourNew2025]** — *Meet Your New Client*. Empirical information-loss on charts/diagrams during PDF/PPTX→MD ingestion; argues for AI-native deliverables. Supports the interpretive-ceiling point. DOI: https://doi.org/10.48550/arXiv.2508.15817
- **[@verhoeffAIFriendlyLaTeXUsing2026]** — *AI-Friendly LaTeX*. Prefer LaTeX source over PDF for arXiv/technical papers; tooling for LaTeX→MD/JSONL. Best-source-first routing in the pipeline section. DOI: https://doi.org/10.48550/arXiv.2605.22923
- **[@duanAcceleratingEndtoEndPDF2026]** — *Copy Lookup Decoding*: efficiency of VLM academic-PDF conversion via copy-from-source. Pipeline scaling; paper outline §4. DOI: https://doi.org/10.1007/978-3-031-97141-9_3
- **[@duanLayoutAwareTextEditing2026]** — *EditTrans*: layout-aware editing to cut conversion latency at equal quality. Pipeline scaling; paper outline §4. DOI: https://doi.org/10.1007/978-3-032-04614-7_13
- **[@saraivaRxivMakerAutomatedTemplate2026]** — *Rxiv-Maker*. Reproducible MD→PDF authoring with executable code; a model for our own recipe-versioned manuscript workflow. Relevant to the toolkit paper's authoring side. DOI: https://doi.org/10.48550/arXiv.2508.00836
- **[@futurehousePaperqaHighAccuracyRAG]** — PaperQA2 (FutureHouse). The agentic-RAG framework in the "frameworks" category; candidate for the parallel-validation study. No DOI (software) — https://github.com/Future-House/paper-qa

*Note:* `pdf-llm-sources.bib` sits in this same folder, alongside this brief, and is Zotero-ready (File → Import). DOI links are listed above; PaperQA2 has no DOI (software — cite the GitHub URL, per the `% NO DOI — URL only` convention). Per the citation conventions in `task-specificiation-meta-lit-review.md`, run a DOI-resolution pass (doi.org or the Crossref API) before final import. The two Springer book-chapter DOIs (`10.1007/…`) are the ones worth confirming first, since chapter DOIs sometimes register later than the arXiv preprint; the arXiv DOIs (`10.48550/…`) and the MDPI DOI resolve on registration.
