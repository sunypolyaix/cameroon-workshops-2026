---
layout: default
filename: llm-utility
title: AI-First Literature Review — What LLMs Are Actually Good For
description: A precise account of where LLMs add genuine value in a research workflow and where the boundary of human judgment sits — the machine/human distinction applied to literature research.
author: Steven M. Schneider
date: 2026-06-28
type: reference
status: final
project: SUNY Poly AIX Research Workshop
companion: closing.md
tags:
  - llm-utility
  - machine-human
  - literature-review
  - warrant
  - cameroon-2026
---

# What LLMs Are Actually Good For

*Thirty seconds. Here is the honest list.*

---

## The List

| | Task |
|---|---|
| ✦ Machine | Helping you understand what the scientific literature says about your topic |
| ✦ Machine | Summarizing trends, history, and established frameworks |
| ✦ Machine | Identifying frameworks worth studying and exploring |
| ✧ Human | Applying a framework to identify gaps and opportunities |
| ✦ Machine | Helping you decide which sources to read closely |
| ✦ Machine | Tracking your observations as you do close readings |
| ✧ Human | Integrating those observations into your literature synthesis |

None of that happens in one prompt. It is a workflow.

---

## The Structural Distinction

### Machine labor — Find · Screen · Extract · Organize

LLMs save 60–80 hours of volume work on a well-scoped research topic. They are genuinely good at retrieval-oriented tasks: finding candidate papers, summarizing what papers say, extracting structured information from documents, organizing notes.

The key word is *retrieval*. These tasks involve locating and organizing what exists. They do not require a standpoint outside the corpus.

### Human analysis — Identify · Argue · Synthesize · Warrant

Gap identification, novel synthesis, and theoretical framing require a standpoint *outside* the literature. They require a researcher who can say: *given everything the field has done, here is what it has not done, and here is why that matters.*

LLMs live inside their training corpus. They cannot independently warrant a claim about what is absent. They interpolate — producing outputs consistent with what exists, not outputs that identify what doesn't. A model trained on a field will reproduce the blind spots of that field.

---

## Why This Distinction Matters

It is not a limitation to work around. It is the structural condition that makes your contribution possible.

If an LLM could identify the gap, the gap would already be filled — because the LLM would have been used to fill it by someone else. The genuine research gaps are the ones that require your standpoint, your combination of frameworks, your judgment about what is important.

The tools accelerate your path to the gap. They do not cross it for you.

---

## The Comparison: Same Prompt, Different Model

In the workshop demonstration, the identical one-shot prompt was given to **Claude Sonnet 4.6** and **ChatGPT o1** for the same research topic (Cameroon NIG–Chad power grid interconnection).

| Metric | Claude Sonnet 4.6 | ChatGPT o1 |
|--------|------------------|------------|
| Artifact type | Draft literature review | Planning framework |
| Format | Continuous prose | Scaffolded outline |
| Words | 4,224 | 3,602 |
| Bullet lines | 0 | 108 |
| References | 25 | 20 |
| Shared references | 3 (~7% overlap) | — |

The ~7% reference overlap is not evidence that one model is right and one is wrong. It is evidence of **corpus selection bias** — each model drew from a different slice of its training data, filtered through its interpretation of the task.

Both outputs are useful. Neither is a literature review. Running both and taking the union of the reference lists produces a richer seed bibliography than either alone.

---

## What "Cannot Independently Warrant" Means

Throughout these materials the phrase used is: *LLMs cannot independently warrant* — not simply "cannot."

The distinction is precise. An LLM can produce text that asserts a gap exists. It can produce text that sounds like a gap claim. What it cannot do is provide the epistemic warrant for that claim — the standing to assert that something is genuinely absent from a field, based on a principled examination of what is present.

Warrant comes from the researcher's standpoint, their methodology, their engagement with the primary literature. An LLM's assertion about a gap is a plausible interpolation, not a warranted claim. Your thesis committee will be evaluating the warrant, not just the assertion.
