# Claude vs ChatGPT — 1-Shot Literature Review Diff
**Prompt:** Cameroon–Chad NIG interconnection literature review  
**Claude model:** claude-sonnet-4-6  
**ChatGPT model:** o1 (thinking mode)

---

## Artifact Comparison

| Metric | Claude | ChatGPT |
|---|---|---|
| Words | 4,018 | 3,784 |
| H2 sections | 13 | 18 |
| H3 subsections | 24 | 25 |
| Bullet points | 0 | 108 |
| Bold terms (named concepts) | 8 | 34 |
| Format | Continuous prose | Scaffolded outline |

Claude produced a **draft literature review** — narrative, publishable-ready prose organized into 12 thematic sections. ChatGPT produced a **planning framework** — research questions, annotated literature map, methodology hints, and suggested structure, all heavily bulleted. Similar word count; fundamentally different artifact type.

---

## Bibliography Comparison

| Metric | Claude | ChatGPT |
|---|---|---|
| Total refs | 25 | 20 |
| Shared | 3 | 3 |
| Model-only | 22 | 17 |

Only **3 papers in common** out of 42 total unique references (~7% overlap).

### Shared references
1. *Investigation of the Stability of the Cameroon NIG* — `10.1155/jcse/2524618`
2. *Optimizing Power Flow in Northern Cameroon's Interconnected Grid* — `10.4236/jpee.2024.129005`
3. *Leveraging Power Grid Topology in ML-Assisted Optimal Power Flow* — title match

### Claude-only emphasis
- AI/ML power systems: PowRL, GridMind, GNNs, gradient boosting on edge devices
- FACTS device placement
- Load-flow case studies (Tanzania, radial networks)
- CAPP/African power pool policy analysis
- Chad energy politics and oil sector

### ChatGPT-only emphasis
- World Bank project documentation (5 separate Cameroon–Chad project status reports)
- African grid interconnection standards and codes
- Ethiopian grid stability studies as comparators
- Metaheuristic OPF algorithms (PSO, GA, etc.)
- HVDC cross-area frequency interaction papers

---

## 25-Word Summaries

**Read only Claude →**  
Dense, AI-forward narrative review. Strong on cutting-edge ML tools and African energy politics. Reads as a near-final draft, not a scaffold.

**Read only ChatGPT →**  
Structured research blueprint with WB project docs, metaheuristic methods, and Ethiopian comparators. Heavy on planning scaffolding, light on prose depth.
