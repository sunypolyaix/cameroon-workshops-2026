# Claude vs ChatGPT Literature Review Diff

## Scope
Compared `claude-sonnet-1shot-artifact.md` vs `chatgpt-thinking-1shot-artifact.md`, and `claude-sonnet-1shot-bib.bib` vs `chatgpt-thinking-1shot-bib.bib`.

## Artifact metrics

| Metric | Claude | ChatGPT | Difference |
|---|---:|---:|---:|
| Words | 4224 | 3602 | +622 |
| Characters | 31673 | 29140 | +2533 |
| Headings | 38 | 45 | -7 |
| H2 sections | 13 | 19 | -6 |
| H3 subsections | 24 | 25 | -1 |
| Bullet lines | 0 | 108 | -108 |
| Numbered-list lines | 30 | 28 | +2 |
| Markdown table rows | 0 | 41 | -41 |
| Bolded terms | 8 | 34 | -26 |
| Concept-lexicon hits | 63 | 57 | +6 |

## Bibliography metrics

- Claude references: 25
- ChatGPT references: 20
- Strict common references: 3
- Claude-only references: 22
- ChatGPT-only references: 17
- Combined strict-disparate references: 39


Strict common references:

- Investigation of the Stability of the Cameroon Northern Interconnected Grid (NIG): A Transient Analysis (`Che2025` / `che2025nigtransientanalysis`; matched by doi,url,title)
- Optimizing Power Flow in Northern Cameroon's Interconnected Grid: Challenges and Solutions (`Ndoumbe2024` / `ndoumbe2024optimizingpowerflow`; matched by doi,url,title)
- Leveraging Power Grid Topology in Machine Learning Assisted Optimal Power Flow (`Falconer2021` / `falconer2022leveragingtopologyopf`; matched by title)

## Interpretation

Claude is longer and more narrative, with broader regional-development framing and more Cameroon/Chad policy context. ChatGPT is shorter but more structured, method-oriented, tabular, and explicit about candidate-busbar evaluation criteria, standards, and modeling workflow.

## 25-word summaries

- Only Claude: You would see a regionally grounded, development-heavy literature review with broad AI coverage, but less explicit operational modeling structure and validation criteria.

- Only ChatGPT: You would see a sharper simulation framework for busbar selection, losses, voltage, frequency, grid-code limits, and economics, but less regional contextual depth.
