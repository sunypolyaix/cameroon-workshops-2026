---
filename: live-examples
title: First Steps — Live Examples: From Interest to a Question
description: Two worked examples of the Socratic question-sharpening method from the workshop — Manga (University of Buea) and Brice (Université de Yaoundé I) — showing the full dialogue and the research question each arrived at.
author: Steven M. Schneider
date: 2026-06-28
type: artifact
status: final
project: SUNY Poly AIX Research Workshop
companion: prompts.md
tags:
  - live-examples
  - question-sharpening
  - buea
  - yaounde
  - cameroon-2026
---

# Live Examples — From Interest to a Question

These are real exchanges from the workshop session. The AI was configured with one instruction: ask one question at a time, do not propose a topic. Each student arrived at a specific, testable research question in under five minutes.

The prompt used to configure the AI:
> "Don't propose a topic. Ask me one question at a time to sharpen my interest into a specific, answerable research question."

---

## Manga — University of Buea, Computer Science

**Starting interest:** Web scalability, edge computing, and real-time systems.

| Speaker | Message |
|---------|---------|
| Manga | Web scalability, edge & real-time systems — serverless + streams. |
| Claude | Broad! Which pulls you most — scaling, or the real-time part? |
| Manga | Real-time streaming — but it must scale under bursty load. |
| Claude | When it breaks, what fails first — latency, cost, or correctness? |
| Manga | Latency — serverless cold-starts right when bursts hit. |

**The question Manga arrived at — Claude only asked:**

> Can predictive pre-warming cut p95 latency for bursty stream-processing workloads, versus default serverless autoscaling?

**Why this is a research question:** It is specific (p95 latency), testable (predictive pre-warming vs. baseline), and bounded (bursty stream-processing workloads). Every word came from Manga's answers, not from the AI.

---

## Brice — Université de Yaoundé I, Electrical Engineering

**Starting interest:** Using AI to improve the Cameroon RIS–RIN interconnection.

*Intérêt de départ : utiliser l'IA pour améliorer l'interconnexion RIS–RIN du Cameroun.*

| Speaker | Message |
|---------|---------|
| Brice | AI to make Cameroon's RIS–RIN interconnection more stable & efficient. |
| Claude | Broad! Stability or efficiency — what pulls you most? |
| Brice | Stability — holding frequency in range when the grids connect. |
| Claude | Which lever — forecasting or control? And what would you measure? |
| Brice | Forecasting — I want to predict the load drop before it happens. |

**The question Brice arrived at — Claude only asked:**

> Can LSTM load-forecasting reduce frequency deviation after RIS–RIN interconnection, versus the baseline controller?

*La prévision LSTM peut-elle réduire l'écart de fréquence après l'interconnexion RIS–RIN, par rapport au contrôleur de référence ?*

**Why this is a research question:** It names the method (LSTM), the outcome (frequency deviation), the context (RIS–RIN interconnection), and has a comparison condition (baseline controller). Brice can now go directly to Move 2 — mapping search terms.

---

## What These Examples Show

**The AI asked five questions across both sessions.** It did not know anything about serverless computing or power grid interconnection that Manga and Brice didn't already know. It asked. They answered. The questions are genuinely theirs.

**The method works because asking is structurally different from telling.** When the AI tells you your research question, you have received an output. When you answer five narrowing questions, you have done the cognitive work of narrowing — the AI just held the structure.

**The questions are now the entry point for Move 2** (orienting to the field). Manga's question maps to: serverless computing, cold-start latency, stream processing, predictive scaling. Brice's maps to: LSTM, load forecasting, frequency stability, power grid interconnection, Cameroon/Central Africa energy systems.

---

## Try It Yourself

Use this prompt with any AI tool (Gemini, Claude, ChatGPT):

> "Don't propose a topic. Ask me one question at a time to sharpen my interest into a specific, answerable research question."

> « Ne propose pas de sujet. Pose-moi une question à la fois pour affiner mon intérêt en une question de recherche précise et répondable. »

It takes 5–10 minutes. The question you arrive at will be yours.
