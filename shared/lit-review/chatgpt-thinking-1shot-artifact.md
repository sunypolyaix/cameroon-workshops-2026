# Literature Review Framework: Interconnection of Cameroon’s Northern Interconnected Grid (NIG) with the Chad National Power Grid

## Working Title

**Literature Review Framework for the Interconnection of Cameroon’s Northern Interconnected Grid with the Chad National Power Grid Using Power-System Simulation and AI-Based Optimization**

---

## 1. Background and Problem Context

The proposed Cameroon–Chad power interconnection is not only a transmission expansion project. It is a **regional power-system integration problem** involving load-flow feasibility, voltage stability, frequency control, cross-border electricity trade, reliability, and institutional coordination.

The World Bank describes the project objectives as interconnecting Cameroon’s Southern and Northern power systems, enabling electricity trade between Cameroon and Chad, and increasing electricity access in N’Djamena. Recent project descriptions indicate that the broader Cameroon–Chad interconnection involves substantial high-voltage infrastructure, including transmission reinforcements in Cameroon and a cross-border link toward Chad. Enerdata reports that the project includes about **1,556 km of new transmission lines**, with a second phase involving approximately **800 km of lines** and a planned export of about **100 MW from Cameroon to Chad**. AfDB project information similarly frames the project as a means to interconnect generation and transmission infrastructure, reduce production costs, and improve electricity access in both countries.

For this study, the central technical issue is the identification of the **most suitable busbar or set of busbars** on the Cameroon Northern Interconnected Grid for interconnection with Chad, under criteria such as:

- minimum active and reactive power losses;
- acceptable bus voltage magnitudes;
- acceptable system frequency behavior;
- adequate static, dynamic, and transient stability;
- economic feasibility;
- reliability and operational security;
- strategic value for regional electricity trade.

A key methodological caution is that the “best busbar” cannot be determined by load-flow loss minimization alone. A technically attractive busbar under steady-state Newton–Raphson load flow may become weak under contingency, short-circuit, voltage-collapse, or frequency-disturbance conditions. The literature review should therefore treat busbar selection as a **multi-criteria planning and operation problem**, not a single-objective power-loss problem.

---

## 2. Regional Grid Interconnection and Power-Pool Integration

Regional interconnection is widely treated in the literature as a way to improve generation adequacy, reduce reserve requirements, enable power exchange, and improve reliability. In Africa, this logic is embedded in regional power-pool initiatives. The Central African Power Pool / Pool Énergétique de l’Afrique Centrale provides documents on intergovernmental agreements, interconnected-grid operating codes, and regional energy strategy, indicating that cross-border interconnection is an institutional as well as technical undertaking.

Technical guidelines for African grid interconnections emphasize the need for control areas, scheduled interchanges, operating rules, grid-code compliance, and continuous updating of interconnected power-system plans. This is directly relevant because Cameroon and Chad will need coordinated operational procedures for active-power exchange, reactive-power support, protection coordination, disturbance response, and emergency control.

Studies on other African power pools also show that cross-border interconnections are rarely neutral additions to a grid. A load-flow study on Southern African Power Pool interconnections compares HVAC, HVDC, and FACTS-based options and highlights the importance of transmission technology choice for long-distance power exchange, losses, and controllability. Although the Cameroon–Chad scheme is not the Southern African Power Pool, the methodological implication is useful: **interconnection planning should compare alternatives**, including network reinforcement, compensation devices, reactive-power planning, and possibly controllable interconnection technologies where justified.

### Relevance to This Study

This theme supports a review section arguing that the Cameroon–Chad interconnection should be assessed through:

1. **Technical feasibility**: voltage, losses, stability, transfer capacity;
2. **Operational feasibility**: control areas, dispatch coordination, protection, frequency regulation;
3. **Economic feasibility**: capital cost, loss reduction, reduced generation cost, reliability value;
4. **Strategic feasibility**: regional trade, energy security, access expansion, resilience.

---

## 3. The Cameroon Northern Interconnected Grid as a Weak-Grid Planning Case

The Northern Interconnected Grid of Cameroon is a relatively weak and stressed system compared with large meshed transmission networks. Recent literature on the NIG identifies challenges linked to rising demand, hydrological constraints at Lagdo, load shedding, voltage issues, renewable integration, and the need for stability studies.

A 2024 study on power-flow optimization in Northern Cameroon’s Interconnected Grid used the **Newton–Raphson method in MATLAB** and simulated outage scenarios to evaluate grid performance. It emphasizes that power-flow analysis provides bus voltage magnitudes, voltage angles, active and reactive power flows, and information needed for planning new facilities and reducing losses.

This is highly relevant because the busbar-selection problem begins with conventional load-flow analysis. However, the literature review should not stop there. The NIG’s structural weakness means that each candidate busbar should be evaluated under:

- base-case load flow;
- peak-load and low-load scenarios;
- N-1 line or transformer contingencies;
- generation loss scenarios;
- Chad import/export variation;
- renewable generation variability;
- reactive-power shortage;
- short-circuit and protection constraints;
- transient and small-signal stability events.

### Relevance to This Study

This theme justifies using a **multi-scenario simulation framework**. A single base-case load-flow result may understate risk. The selected busbar must remain acceptable under credible operating conditions, not merely under normal conditions.

---

## 4. Load-Flow Analysis, Busbar Selection, and Power-Loss Minimization

The classical entry point for interconnection studies is **power-flow analysis**, usually using Newton–Raphson, Gauss–Seidel, fast-decoupled load flow, or continuation power flow. For a transmission interconnection, the important outputs are:

| Output | Importance for Busbar Selection |
|---|---|
| Bus voltage magnitude | Identifies undervoltage or overvoltage risk |
| Bus voltage angle | Indicates angular separation and transfer stress |
| Line active/reactive power flow | Shows loading and congestion |
| Active power loss | Used for efficiency comparison |
| Reactive power loss | Indicates voltage-support burden |
| Transformer loading | Detects overload constraints |
| Voltage stability index | Identifies weak buses |
| Available transfer capability | Measures feasible export/import level |

The busbar yielding the lowest losses is often not the same as the busbar with the best voltage stability margin. Therefore, literature on **optimal power flow (OPF)** is important. OPF allows the researcher to optimize an objective function such as loss minimization, voltage deviation minimization, generation cost minimization, or stability-index improvement while respecting equality and inequality constraints.

Recent OPF literature emphasizes that OPF remains central to power-system operation and market-clearing tools, but is nonlinear and computationally demanding, especially for AC formulations. Metaheuristic OPF studies commonly include objectives such as fuel cost, voltage deviation, voltage stability index, active losses, and reactive losses.

### Possible Optimization Formulation

Busbar selection may be formulated as a constrained optimization problem:

```text
Minimize:
F = w1(P_loss) + w2(Q_loss) + w3Σ|Vi - Vref| + w4C + w5R
```

Where:

- `P_loss` = active power losses;
- `Q_loss` = reactive power losses;
- `Vi` = bus voltage magnitude;
- `C` = investment or operating cost indicator;
- `R` = reliability or risk penalty;
- `w1, w2, w3, w4, w5` = weights reflecting planning priorities.

A stricter formulation would impose limits instead of only adding penalties:

```text
Vmin ≤ Vi ≤ Vmax
fmin ≤ f ≤ fmax
Sline ≤ Srated
Pexport ≤ ATC
```

This gives the literature review a direct bridge from prior OPF work to the busbar-selection problem.

---

## 5. Voltage Stability and Reactive-Power Adequacy

Voltage stability is central for long radial or weakly meshed systems. Interconnecting Chad to the NIG may increase loading, alter reactive-power flows, and deepen voltage drops if compensation and reinforcement are inadequate. Literature on voltage-profile improvement in African systems is relevant because voltage collapse is often associated with heavily loaded corridors, reactive-power deficiencies, and poor voltage control.

Machine-learning methods are also increasingly used for voltage-stability assessment because traditional methods can become computationally heavy when many scenarios must be evaluated. Recent studies use models such as linear regression, random forest, gradient boosting, and support vector machines to predict voltage-stability indices under varying load levels.

### Relevance to This Study

The literature suggests that candidate busbars should be ranked not only by loss reduction but also by:

- voltage deviation index;
- voltage stability margin;
- Fast Voltage Stability Index, L-index, or similar indicators;
- reactive-power reserve;
- sensitivity of voltage to active and reactive load changes;
- performance after loss of a major generator, line, or transformer;
- need for shunt capacitors, reactors, SVC, STATCOM, or transformer tap changes.

For the NIG–Chad interconnection, voltage stability may become one of the decisive criteria because the export path is likely to be long and may pass through relatively weak transmission infrastructure.

---

## 6. Frequency Stability, Load-Frequency Control, and Disturbance Response

Frequency stability concerns the ability of the interconnected system to maintain balance between generation and load after disturbances. In a cross-border interconnection, frequency behavior depends on generator inertia, governor response, spinning reserve, load damping, protection settings, and control-area coordination.

Recent AI-based frequency-stability research shows that explainable machine learning can help identify variables affecting frequency indicators such as rate of change of frequency and frequency nadir. Literature on cross-area interconnector flows also shows that interconnector operation can either support or disturb frequency stability depending on ramping limits and control mode.

Even if the Cameroon–Chad interconnection is HVAC rather than HVDC, the key insight remains relevant: **cross-border power transfer changes frequency-control obligations**. If Chad imports significant power from Cameroon, a disturbance in either country may propagate unless there are clear control-area rules, protection coordination, and reserve-sharing arrangements.

### Relevance to This Study

The review should examine:

- acceptable frequency bands under the applicable grid codes;
- governor response and primary frequency control;
- automatic generation control, if available;
- load-frequency control between Cameroon and Chad;
- effect of sudden loss of the interconnector;
- effect of sudden loss of generation in Cameroon;
- under-frequency load shedding;
- rate-of-change-of-frequency protection;
- reserve requirements for scheduled exports.

A methodological warning is important: **frequency cannot be fully assessed from static load-flow analysis**. It requires dynamic simulation or at least simplified swing-equation and load-frequency-control modeling.

---

## 7. Grid Codes, Standards, and Operational Limits

The study must define “acceptable limits” from applicable standards rather than arbitrary assumptions. For Cameroon and Chad, the most relevant sources would include:

- Cameroon transmission and distribution codes, if accessible through ARSEL, SONATREL, or ENEO;
- Chad electricity-sector regulations and utility requirements;
- Central African Power Pool operating code;
- AFSEC / IEC interconnection guidelines;
- project-specific technical specifications from World Bank or AfDB documents.

The Central African Power Pool makes available an operating code for interconnected electrical networks in Central Africa, which should be treated as a priority source for this study. AFSEC technical guidelines also emphasize grid-code compliance, operating coordination, and planned interconnection governance.

### Relevance to This Study

The literature review should avoid vague language such as “voltage must be normal” or “frequency must be stable.” Instead, it should state the selected limits.

| Parameter | Literature-Review Issue |
|---|---|
| Voltage magnitude | Define permissible transmission-bus operating range from applicable grid code |
| Frequency | Define normal, alert, emergency, and collapse ranges |
| Thermal loading | Use line and transformer ratings |
| Short-circuit level | Ensure breaker and protection compatibility |
| Power factor | Assess reactive-power obligations at point of interconnection |
| Reliability | Define N-1 or other security criterion |
| Power quality | Consider harmonics, flicker, voltage unbalance if relevant |

Where local grid-code data are unavailable, the review can use IEC/AFSEC/CAPP guidance provisionally, but the thesis should later replace generic limits with Cameroon–Chad-specific requirements.

---

## 8. Economic and Strategic Dimensions

The economic literature on interconnection typically considers capital cost, operating cost, loss reduction, reliability improvement, avoided unserved energy, generation-cost savings, and regional trade benefits. World Bank project documents identify electricity trade and improved access in N’Djamena as explicit development objectives. AfDB also frames the interconnection as a way to reduce production costs and electrify communities along the interconnection corridor.

However, economic feasibility is vulnerable to project execution risk. Recent reporting on the PIRECT project indicates a funding gap affecting implementation progress, which means the literature review should treat financing and sequencing as part of the strategic challenge rather than as external background.

### Relevance to This Study

Economic assessment should include:

- cost of each busbar interconnection alternative;
- line length from candidate busbar to Chad border or load center;
- substation expansion cost;
- reactive compensation cost;
- protection and control upgrades;
- energy-loss cost;
- reliability benefit;
- avoided diesel generation in Chad;
- value of increased energy access;
- sensitivity to export volume, demand growth, fuel prices, and hydrology.

A strong research design would compare alternatives using **net present cost**, **benefit–cost ratio**, **levelized cost of transmitted energy**, or **multi-criteria decision analysis**.

---

## 9. Artificial Intelligence for Interconnection Planning and Operation

AI should not be presented as a substitute for power-system engineering. It is better framed as a support layer for simulation, optimization, forecasting, pattern recognition, and decision ranking.

Recent reviews show that AI is being applied in power-system operation, control, planning, stability assessment, protection, predictive maintenance, load forecasting, and optimal power flow. Machine-learning-assisted OPF is an active research area because AC OPF is nonlinear and computationally intensive; ML can be used to approximate optimal solutions, predict active constraints, or accelerate repeated scenario analysis.

Metaheuristic algorithms such as genetic algorithms, particle swarm optimization, grey wolf optimizer, ant colony methods, and hybrid algorithms are often used in power-system optimization where objective functions are nonlinear, nonconvex, or multi-objective. Reviews of metaheuristic optimization in power systems emphasize their usefulness when information is sparse or the search space is complex.

### AI Roles Suitable for This Project

| AI Tool Category | Possible Use in This Study |
|---|---|
| Supervised ML | Predict losses, voltage violations, or stability margins from operating scenarios |
| Reinforcement learning | Explore control actions for voltage support or dispatch under uncertainty |
| Metaheuristics | Rank candidate busbars under multi-objective criteria |
| Neural networks / graph neural networks | Learn grid-topology-sensitive OPF approximations |
| Explainable AI | Identify which buses, loads, lines, or generation patterns drive instability |
| Clustering | Group operating scenarios into normal, stressed, and emergency states |
| Forecasting models | Estimate future load growth in northern Cameroon and Chad |
| Multi-criteria decision tools | Combine technical, economic, and strategic indicators |

A defensible AI-based approach would be:

1. build a validated physical grid model;
2. run many load-flow and stability simulations;
3. generate a scenario dataset;
4. train AI models to classify or predict risky operating states;
5. use optimization algorithms to identify the best interconnection busbar;
6. validate AI results against conventional power-system simulation.

This is stronger than simply applying an AI algorithm directly to an unvalidated grid model.

---

## 10. Proposed Conceptual Framework

```text
Candidate busbars
      ↓
Power-flow simulation
      ↓
Voltage profile, losses, line loading
      ↓
Contingency and stability analysis
      ↓
Frequency response, voltage stability, transient stability
      ↓
Economic and strategic evaluation
      ↓
AI / multi-objective optimization
      ↓
Ranking of best interconnection busbar(s)
```

The dependent decision variable is the **optimal busbar or interconnection point**.

The evaluation criteria are:

- active power loss;
- reactive power loss;
- voltage deviation;
- line and transformer loading;
- voltage stability margin;
- frequency stability;
- reliability under N-1 contingencies;
- cost of implementation;
- regional trade benefit;
- environmental and access benefits.

---

## 11. Suggested Literature-Review Structure

### 11.1 Introduction to Cross-Border Power Interconnection

Discuss the rationale for regional interconnection, especially in Africa and Central Africa. Cover power pools, electricity trade, energy access, generation-cost reduction, and reliability.

### 11.2 Overview of the Cameroon and Chad Power Systems

Cover Cameroon’s Southern and Northern Interconnected Grids, Chad’s national grid and N’Djamena demand center, SONATREL, ENEO, SNE, CAPP/PEAC, and project objectives.

### 11.3 Technical Characteristics of the NIG

Review NIG topology, generation sources, load centers, voltage levels, known operational issues, load shedding, hydrological constraints, and previous studies on NIG load flow and stability.

### 11.4 Power-Flow and Optimal-Power-Flow Methods

Review Newton–Raphson load flow, AC OPF, loss minimization, voltage deviation minimization, reactive-power planning, and multi-objective optimization.

### 11.5 Voltage Stability and Reactive-Power Compensation

Review voltage stability indices, weak-bus identification, continuation power flow, reactive-power reserves, FACTS devices, capacitor banks, reactors, tap-changing transformers, SVC, and STATCOM.

### 11.6 Frequency Stability and Dynamic Performance

Review load-frequency control, primary and secondary reserves, governor response, frequency nadir, RoCoF, interconnector trip events, and emergency control.

### 11.7 Economic and Strategic Assessment

Review cost-benefit analysis, avoided cost of generation, reliability value, loss cost, regional power trade, electrification benefits, and financing constraints.

### 11.8 AI and Intelligent Optimization Tools

Review supervised learning, metaheuristics, reinforcement learning, explainable AI, graph neural networks, scenario generation, and AI-assisted OPF.

### 11.9 Research Gap

Show that existing work addresses parts of the problem—NIG load flow, grid interconnection, OPF, AI for stability—but not a complete integrated framework for selecting the optimal Cameroon–Chad interconnection busbar under technical, economic, and strategic criteria.

---

## 12. Possible Research Gap Statement

Existing studies on the Northern Interconnected Grid of Cameroon have examined load flow, load shedding, renewable integration, and emerging stability issues. Regional documents and project appraisals justify the Cameroon–Chad interconnection as a strategic electricity-trade and access-improvement project. However, there is limited published work that integrates **busbar-level interconnection selection**, **loss minimization**, **voltage and frequency stability**, **economic feasibility**, and **AI-based multi-objective optimization** for the specific case of the NIG–Chad interconnection. This study therefore addresses a gap by developing and validating a decision-support framework for identifying the most technically secure, economically viable, and strategically beneficial interconnection busbar between the NIG and the Chad National Power Grid.

---

## 13. Suggested Research Questions

1. **Which candidate busbars on the Cameroon NIG provide the lowest active and reactive power losses for interconnection with the Chad National Power Grid?**

2. **How does each candidate busbar affect voltage profiles under normal, peak-load, low-load, and contingency conditions?**

3. **What is the impact of Cameroon–Chad power exchange on system frequency stability and disturbance response?**

4. **Which technical reinforcements are required to maintain voltage and frequency within acceptable limits?**

5. **How can AI-based optimization improve the ranking of interconnection alternatives compared with conventional load-flow-only assessment?**

6. **Which interconnection option provides the best compromise among technical performance, economic cost, reliability, and strategic regional value?**

---

## 14. Recommended Methodology Implied by the Literature

### 14.1 Data Collection

- bus data;
- generator data;
- transformer data;
- transmission-line parameters;
- load profiles;
- projected Chad import demand;
- protection and operating limits;
- cost data.

### 14.2 Network Modeling

- model the NIG;
- model the relevant Chad grid section;
- represent candidate interconnection busbars;
- validate the base case against known operating data.

### 14.3 Load-Flow Analysis

- Newton–Raphson AC load flow;
- base-case and scenario simulation;
- loss and voltage-profile comparison.

### 14.4 Contingency Analysis

- N-1 line outage;
- transformer outage;
- generator outage;
- interconnector outage.

### 14.5 Voltage Stability Analysis

- PV curves;
- QV curves;
- voltage stability indices;
- reactive compensation requirements.

### 14.6 Frequency and Dynamic Analysis

- generator dynamic models;
- disturbance simulation;
- frequency nadir;
- RoCoF;
- settling time;
- reserve adequacy.

### 14.7 Economic Analysis

- investment cost;
- loss cost;
- avoided generation cost;
- reliability benefit;
- sensitivity analysis.

### 14.8 AI-Based Optimization

- train predictive model on simulation scenarios;
- apply multi-objective optimizer;
- rank candidate busbars;
- validate recommended solution using conventional simulation.

---

## 15. Preliminary Annotated Literature Map

| Literature Area | Key Contribution | Use in This Study |
|---|---|---|
| World Bank Cameroon–Chad project documents | Defines project objectives: interconnect Cameroon systems, enable trade, improve N’Djamena access | Establishes project rationale and policy context |
| AfDB Cameroon–Chad project sources | Frames interconnection as cost-reduction and access-expansion project | Supports economic and strategic justification |
| NIG power-flow studies | Uses Newton–Raphson load flow and outage scenarios for the NIG | Provides direct methodological precedent for NIG modeling |
| NIG stability studies | Identify NIG instability and need for transient-stability assessment | Justifies dynamic analysis beyond load flow |
| AFSEC African interconnection guidelines | Emphasize grid-code compliance, control areas, and coordinated operation | Support operating-limit and governance framework |
| CAPP/PEAC documents | Provide Central African regional interconnection and operating-code context | Anchor the study in regional power-pool rules |
| OPF and ML-OPF literature | Shows OPF and AI methods for solving constrained grid optimization problems | Supports AI-based busbar-selection framework |
| AI for stability and control | Reviews AI use in stability, control, protection, and planning | Supports AI component of the project |
| Explainable AI for frequency stability | Uses XAI to identify drivers of frequency risk | Supports interpretable AI for frequency assessment |
| Metaheuristic OPF literature | Optimizes losses, voltage deviation, stability indices, and cost | Supports multi-objective optimization of candidate busbars |

---

## 16. Refined Project Aim

This study aims to determine the technically, economically, and strategically optimal busbar or interconnection point for linking Cameroon’s Northern Interconnected Grid with the Chad National Power Grid. The study will use AC load-flow analysis, contingency analysis, voltage-stability assessment, frequency-stability evaluation, economic assessment, and AI-based multi-objective optimization to identify the interconnection alternative that minimizes power losses, maintains acceptable voltage and frequency performance, improves reliability, and supports sustainable regional electricity trade.

---

## 17. Preliminary Source List

The following sources should be checked, expanded, and formalized into the required citation style for the final literature review:

1. World Bank. *Cameroon–Chad Power Interconnection Project*.  
   <https://documents.worldbank.org/en/publication/documents-reports/documentdetail/482631592619043723>

2. Enerdata. *Cameroon launches its 1,556 km interconnection project with Chad*.  
   <https://www.enerdata.net/publications/daily-energy-news/cameroon-launches-its-1556-km-interconnection-project-chad.html>

3. African Development Bank. *Cameroon–Chad Power Interconnection Project*.  
   <https://mapafrica.afdb.org/en/projects/46002-P-Z1-FA0-072>

4. Central African Power Pool / Pool Énergétique de l’Afrique Centrale. *Documents and operating-code resources*.  
   <https://peac-ac.org/documents/>

5. AFSEC. *Guidelines for the Interconnection of Electricity Networks in Africa*.  
   <https://afsec-africa.org/assets/DownloadFiles/Guids/ptb_AFSEC_Interconnection_%20Guide_No_11_en_WEB.pdf>

6. SCIRP. *Power-flow optimization in Northern Cameroon’s Interconnected Grid*.  
   <https://www.scirp.org/pdf/jpee2024129_51771144.pdf>

7. Wiley / Journal of Control Science and Engineering. *Stability-related study on the Northern Interconnected Grid of Cameroon*.  
   <https://onlinelibrary.wiley.com/doi/epdf/10.1155/jcse/2524618>

8. IEEE. *Machine-learning-assisted optimal power flow literature*.  
   <https://ieeexplore.ieee.org/document/9042547>

9. MDPI Applied Sciences. *Artificial intelligence applications in power systems*.  
   <https://www.mdpi.com/2076-3417/14/14/6214>

10. MDPI Sustainability. *Metaheuristic optimization in power systems*.  
   <https://www.mdpi.com/2071-1050/15/12/9434>

11. Nature Scientific Reports. *Metaheuristic OPF and multi-objective optimization literature*.  
   <https://www.nature.com/articles/s41598-024-58565-y>

12. Cell Patterns. *Explainable AI for frequency stability*.  
   <https://www.cell.com/patterns/fulltext/S2666-3899%2821%2900227-0>

---

## 18. Notes for Further Development

This draft should be treated as a starting framework. Before submission, the literature review should be strengthened by:

- adding peer-reviewed sources from IEEE, Elsevier, Springer, MDPI, Wiley, and Taylor & Francis;
- verifying the most recent project status from World Bank, AfDB, SONATREL, SNE, ARSEL, and CAPP/PEAC;
- replacing provisional operating limits with official Cameroon, Chad, or CAPP grid-code values;
- expanding the Chad grid context, especially N’Djamena demand and existing generation mix;
- adding a formal methodology section with simulation tools such as MATLAB/Simulink, DIgSILENT PowerFactory, ETAP, PSS/E, or pandapower;
- defining exact candidate busbars once system data are available;
- converting the source list into IEEE, APA, or the institution’s required citation format.
