---
layout: default
title: "Step 2 — Zotero Export"
---

# 2-zotero.md — Zotero Export Stage

## Pipeline Position

```
1-perplexity.md → [2-zotero.md] → 3-gemini.txt
```

This file documents the manual PDF acquisition and Zotero export step that bridges the Perplexity literature discovery stage and the Gemini synthesis stage.

---

## Sources Acquired

Three PDFs were saved deliberately and individually at this stage:

| File | Citation | Source |
|------|----------|--------|
| `Imdadullah_et_al__-_2021_-_Electric_Power_Network_Interconnection...pdf` | Imdadullah, Alamri, Hossain, & Asghar (2021). Electric Power Network Interconnection: A Review on Current Status, Future Prospects and Research Direction. *Electronics*, 10(17), 2179. | MDPI (open access) |
| `Kelly_et_al__-_2023_-_Off_grid_PVDieselWindBatteries_energy_system_options...pdf` | Kelly, Medjo Nouadje, Tonsie Djiela, Tiam Kapen, Tchuen, & Tchinda (2023). Off grid PV/Diesel/Wind/Batteries energy system options for the electrification of isolated regions of Chad. *Heliyon*, 9, e13906. | Elsevier (open access) |
| `Wu_et_al__-_2017_-_Strategic_siting_and_regional_grid_interconnections...pdf` | Wu, Deshmukh, Ndhlukula, Radojicic, Reilly-Moman, Phadke, Kammen, & Callaway (2017). Strategic siting and regional grid interconnections key to low-carbon futures in African countries. *PNAS*, 114(17), E3004–E3012. | PNAS (open access) |

---

## Acquisition Method (This Stage)

PDFs were saved manually — one at a time — directly from publisher or repository pages. This was deliberate: at this scale (three sources), manual acquisition is faster than automation and keeps the pipeline transparent.

The Zotero Connector was used to capture each source while on the publisher page, adding full metadata to the Zotero library. PDFs were then exported from Zotero for upload to Gemini.

---

## Inputs to Gemini (Step 3)

The following files were uploaded together to Gemini for synthesis:

- `1-perplexity.md` — the structured literature review framework from Perplexity, including the original research question
- All three PDFs above

Gemini was prompted to walk through the three sources point by point, identifying overlaps, distinctions, and gaps relative to the Cameroon–Chad NIG interconnection research project.

Output: `3-gemini.txt`

---

## Scaling Note

At this stage, PDF acquisition was manual. At larger scale (10+ sources), the pipeline would shift to:

- Zotero group library with shared folder
- Bulk BibTeX export
- Automated PDF-to-text conversion (e.g., Paul Lee's script)
- Batch upload to Gemini or equivalent large-context model

For now, the manual approach preserves legibility and control over what enters the synthesis stage.
