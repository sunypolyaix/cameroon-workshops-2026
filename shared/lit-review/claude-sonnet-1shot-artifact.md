# Literature Review: Interconnection of the Northern Interconnected Grid (NIG) of Cameroon with the Chad National Power Grid

**Focus:** Busbar optimization, power loss minimization, voltage and frequency stability, and AI-driven solutions  
**Prepared for:** Research study on technical, economic, and strategic challenges of NIG–Chad grid interconnection  
**Date:** June 2026

---

## 1. Introduction and Research Context

The electrification deficit in Sub-Saharan Africa remains one of the most pressing development challenges of the 21st century. Against this backdrop, cross-border power interconnections have emerged as a strategic lever for improving energy access, grid stability, and regional economic integration. This literature review surveys the body of knowledge relevant to studying the interconnection of Cameroon's Northern Interconnected Grid (NIG) with Chad's National Power Grid, with particular attention to: (1) the current state of each grid and the interconnection project; (2) regional energy integration frameworks; (3) power flow analysis and busbar optimization methods; (4) voltage and frequency stability in interconnected systems; (5) economic and strategic dimensions; and (6) artificial intelligence tools applicable to power system analysis and optimization.

The study's central technical objective—identifying busbars that yield minimal power losses, adequate voltage levels, and frequency within acceptable limits—situates it at the intersection of classical power engineering and modern AI-assisted grid analysis.

---

## 2. Cameroon's Northern Interconnected Grid (NIG): Current State and Challenges

### 2.1 Generation Profile and Infrastructure

Cameroon operates two major interconnected grids: the Southern Interconnected Network (SIN) and the Northern Interconnected Grid (NIG). The SIN dominates national generation, housing approximately 98% of the country's hydroelectric output from a technically exploitable potential of 83 TWh/year. The NIG, by contrast, draws primarily from the Lagdo hydroelectric plant on the Benue River, which forms the backbone of power supply for the Adamawa, North, and Far North regions (Optimizing Power Flow in Northern Cameroon's Interconnected Grid, SCIRP, 2024).

Despite its modest installed capacity, the NIG zone has a technically exploitable hydropower potential of approximately 7.5 TWh/year, which—if developed—could not only relieve energy poverty in northern Cameroon but also underwrite sustainable electricity exports to Chad and Nigeria (ResearchGate, 2024). However, seasonal variability severely constrains the Lagdo plant's output: accessibility of generation improved from 85% in 2021 to 97.5% in 2022, yet insufficient water levels during the first seven months of the year consistently limit production (Che et al., 2025, *Journal of Control Science and Engineering*, Wiley).

### 2.2 Recent Developments: Solar Injection and the Interconnection Announcement

To alleviate chronic shortfalls, Cameroon has begun injecting renewable energy into the NIG. In September 2022, solar PV and solar-thermal solutions were commissioned alongside an improvement in Lagdo's water availability. By September 2023, the Maroua and Guider solar power stations—with a combined capacity of 36 MWp and 20 MW/19 MWh battery storage—were injected into the NIG (Che et al., 2025). These developments introduce new stability considerations, as intermittent renewable sources interact with the existing synchronous generation.

Critically for this study, on 22 November 2023 the Cameroonian government officially announced the launch of a project to interconnect Cameroon and Chad's electricity networks (Che et al., 2025), building on earlier feasibility and environmental assessments dating to 2007 (AfDB ESIA, 2017).

### 2.3 Power Flow Studies on the NIG

The most directly relevant recent work is Che et al. (2025), a transient stability analysis of the NIG, and the 2024 paper "Optimizing Power Flow in Northern Cameroon's Interconnected Grid" (SCIRP). The latter applies the Newton-Raphson method in MATLAB to model and solve power flow equations for the NIG, simulating outage scenarios and identifying critical nodes. The study reported a power demand of 65.818 MW, generated active power of 68.925 MW, and real power losses of 3.106 MW under baseline conditions—data that provides a quantitative baseline directly applicable to modeling the impact of Chad grid interconnection.

An earlier study on optimal energy scheduling for the NIG (Sustainable Energy Research, Springer, 2023) addressed load shedding solutions through optimal scheduling of hybrid resources, noting that the geographic proximity of the NIG to the Sahel gives it disproportionate solar resource endowment compared to southern Cameroon. These papers collectively define the current technical frontier of NIG analysis and establish the methodological precedents for the proposed research.

---

## 3. Chad's National Power Grid: Deficit, Infrastructure, and Trajectory

### 3.1 Scale of the Energy Access Crisis

Chad presents one of the most acute electricity access deficits globally. National electricity access stood at approximately 12% in 2023, a figure that masks severe urban-rural disparity: urban access reached 48.1%, while rural access collapsed to just 0.4% (Africa Energy Portal, 2023). Installed capacity has remained broadly stagnant at roughly 285 MW from 2015 to 2023, wholly inadequate for a growing population in a large-territory landlocked state.

The national utility, the Société Nationale d'Electricité du Tchad (SNE), is characterized in multiple reports as technically, commercially, and financially deficient. Its transmission infrastructure is described as "virtually nonexistent across Chad," its generation assets as "mostly old and decaying," and its pricing structure as regressive—tariffs among the highest in the region that do not translate into investment in network improvement (Columbia University Energy Policy, 2024). The AfDB's Phase 2 Electricity Sector Support Project (PASET-2) acknowledges that these constraints directly undermine Chad's economic diversification and regional stability prospects.

### 3.2 Energy Policy Targets and Renewable Potential

Despite this crisis, Chad holds significant untapped renewable energy potential. Its Sahelian geography yields exceptional solar irradiation, and the African Development Bank's Desert-to-Power initiative identified Chad as a priority country for solar-led electrification. The Desert-to-Power Roadmap (AfDB, 2020) projected the Cameroon–Chad interconnection link becoming operational by 2024–2025, and noted that integrating 702 MW of solar capacity in Chad without thermal backup would require either extension of the interconnection with Cameroon or additional grid development.

Chad's government has set a 30% electricity access target by 2023 (unmet) and 53% by 2030, with a 20% rural access target—ambitions that are only achievable through a combination of grid extension, off-grid solutions, and, crucially, cross-border power imports from Cameroon.

---

## 4. The Cameroon–Chad Power Interconnection Project

### 4.1 Project Origins and Institutional Framework

The Chad–Cameroon 225 kV Electrical Grid Interconnection Project dates to an October 2007 agreement, with Environmental and Social Impact Assessments (ESIAs) prepared in May 2017 under the African Development Bank's Integrated Safeguards System for Category 1 projects (AfDB, 2017). The project encompasses: (1) construction of a 225 kV high-voltage transmission line, and (2) rural electrification components in both countries.

The World Bank's June 2020 Appraisal Document (P168185) formalized the current project structure, with three interlinked development objectives: (i) interconnecting the Southern and Northern power systems of Cameroon; (ii) enabling electricity trade between Cameroon and Chad; and (iii) improving electricity access in N'Djamena (World Bank, 2020). This document remains a foundational reference for the project's technical scope, cost structure, and institutional arrangements.

### 4.2 Technical Scope and Significance

The interconnection is designed as a 225 kV high-voltage AC (HVAC) transmission corridor. Its construction involves new substations and busbars on both sides of the border, making busbar optimization—a central focus of the proposed research—directly pertinent to real infrastructure decisions. The route traverses challenging terrain in northern Cameroon and southern Chad, raising issues of line losses over long distances, reactive power compensation, and voltage profile management at receiving-end buses. These are precisely the parameters the proposed study aims to optimize.

---

## 5. Regional Power Integration in Central Africa

### 5.1 African Power Pools: Overview

Five regional power pools operate across Africa: the Southern African Power Pool (SAPP, established 1995), the West African Power Pool (WAPP, 2000), the Central African Power Pool (CAPP, 2003), and the Eastern Africa Power Pool (EAPP, 2005). Their collective mission is to improve generation capacity, enable cross-border electricity trade, and reduce per-unit energy costs through shared infrastructure (Engineering News, 2026).

The World Bank has estimated that regional power trade could reduce electricity system costs across Africa by 10–30% through shared infrastructure and better utilization of generation assets—a transformative prospect for a continent where electricity prices are among the highest in the developing world (Energy Transition Africa, 2026).

### 5.2 CAPP: Potential and Constraints

The Central African Power Pool (CAPP) aims to leverage the Congo Basin's vast hydropower potential and cross-border renewable sharing. However, its implementation has faced serious structural obstacles: a lack of grid interconnections for cross-border electricity trade, poor incentives for private sector participation, inadequate reliable data, financial uncertainties, and absence of a regional electricity trading framework (ScienceDirect, 2021). Member states have shown insufficient involvement in regional integration due to concerns about impacts on national energy policies.

These constraints are directly relevant to the NIG–Chad interconnection, which operates within the CAPP institutional environment. The proposed research should account for CAPP governance structures, as regulatory harmonization is a prerequisite for sustained cross-border trade.

### 5.3 Lessons from SAPP and WAPP

The Southern African Power Pool remains the continent's most advanced regional electricity market, with an institutional framework, grid interconnection density, and transparent electricity market that enable efficient trading. Yet even SAPP traded only 7.7 TWh in 2023 against total demand of 344 TWh—roughly 2%—with 80% of trade via bilateral contracts (African Energy Chamber, 2026). This underscores that interconnection infrastructure alone is insufficient; market design, tariff harmonization, and utility financial health are equally critical. The WAPP's experience in West Africa, where grid links remain incomplete and regulatory fragmentation constrains growth, offers a cautionary parallel for the CAPP context.

---

## 6. Power Flow Analysis and Busbar Optimization

### 6.1 Load Flow Methods

Load flow (or power flow) analysis is the computational foundation of transmission planning. It determines voltage magnitudes and angles at each bus, and real and reactive power flows on each line, under given load and generation conditions—forming the basis for assessing power losses and voltage profiles (Academia, 2026).

The Newton-Raphson (NR) method is the standard for complex, heavily loaded systems. It exhibits fast quadratic convergence and handles P-V bus constraints naturally, making it preferred for large interconnected networks over simpler methods such as Gauss-Seidel (Power Loss Minimization of Distribution Network, arXiv, 2023). NR's Jacobian-based linearization handles nonlinear power balance equations iteratively, with convergence typically achieved in 4–6 iterations for well-conditioned systems. Its limitations—complex programming, large memory requirements, sensitivity to initial conditions—are well-documented but manageable with modern simulation environments such as MATLAB or PowerWorld Simulator.

The application of the NR method to African grids is established. Mgonja et al. applied it to the Tanzanian 330 kV network, demonstrating that voltage magnitudes and phase angles can be resolved to within operating limits when network parameters are accurately represented. A parallel study on the Nigerian 330 kV grid (PMC, 2021) demonstrated the sensitivity of NR convergence to bus numbering strategies—a methodological consideration directly applicable to constructing the NIG–Chad admittance matrix.

### 6.2 Optimal Power Flow (OPF)

Optimal Power Flow (OPF) extends classical load flow by incorporating objective functions—typically minimizing generation cost, transmission losses, or voltage deviations—subject to power balance, thermal, and voltage constraints. OPF is the mathematical framework most directly suited to the proposed study's goal of identifying busbars that minimize power losses while maintaining voltage and frequency within limits.

Penalty function approaches within the NR framework allow soft enforcement of line MVA limits and bus voltage constraints, providing a tractable solution for constrained OPF in transmission networks (PowerWorld, Newton-based OPF). The objective function for loss minimization in a distribution/transmission context is typically formulated as minimizing the sum of I²R losses across all branches, subject to bus voltage bounds (Vmin ≤ Vi ≤ Vmax) and line flow constraints (Flowk ≤ Flowk_max) (arXiv, Particle Swarm Optimization for Capacitor Placement, 2023).

### 6.3 Busbar Selection and Sensitivity Analysis

Identifying optimal busbars for interconnection requires sensitivity analysis to locate buses with maximum voltage sensitivity to load variations—so-called "weak buses." The dV/dQ sensitivity index is widely used to rank buses by their vulnerability to voltage collapse, directing reactive power compensation and interconnection point selection to locations where intervention yields maximum loss reduction (Springer, TLBO-FACTS placement, 2021).

Bus splitting and topology reconfiguration have been investigated through reinforcement learning and graph neural networks (arXiv, Transferable Graph Learning for Busbar Splitting, 2025), establishing that AI-assisted topology optimization can significantly reduce congestion and losses beyond what static NR-based OPF achieves.

---

## 7. Voltage Stability in Interconnected Systems

### 7.1 Voltage Stability Fundamentals

Voltage stability refers to a power system's ability to maintain acceptable voltage at all buses under normal operating conditions and after disturbances. Long high-voltage transmission corridors—such as the proposed 225 kV NIG–Chad line—are particularly susceptible to voltage collapse at receiving-end buses due to reactive power deficit and line charging. IEEE and CIGRE's joint 2023 evaluation of voltage stability assessment methodologies in transmission systems remains the authoritative technical reference for this domain.

### 7.2 Renewable Integration and Voltage Dynamics

The integration of solar PV (as at Maroua and Guider in the NIG) introduces inverter-based generation that, unlike synchronous machines, does not inherently provide reactive power support or inertia. This weakens the short-circuit ratio at connection buses, exacerbating voltage instability in low-inertia conditions (Frontiers in Energy Research, 2025). Grid-forming (GFM) inverter controls—including virtual synchronous machine emulation and droop control—are emerging mitigation strategies, though accurate reactive power sharing remains difficult over impedance-mismatched lines.

For the NIG–Chad corridor, voltage stability modeling must account for: (a) the long transmission distance from Lagdo or the border substation to N'Djamena; (b) the low short-circuit capacity of the Chadian receiving network; and (c) the planned injection of solar generation on both sides. FACTS devices (SVCs, STATCOMs) are the primary technology for reactive power compensation along such corridors, and their optimal placement using metaheuristic optimization (Teaching Learning Based Optimization, Genetic Algorithms, Particle Swarm Optimization) is an active research area.

---

## 8. Frequency Control and Load-Frequency Management

### 8.1 Frequency Regulation in Multi-Area Systems

When two power systems are interconnected via a tie-line, their frequencies become coupled. Disturbances in one area propagate to the other, and load-frequency control (LFC) must coordinate across the interconnection to restore nominal frequency (50 Hz in both Cameroon and Chad) and regulate tie-line power. The literature on LFC has matured considerably with renewable integration: Muduli et al. (2024) document that high renewable penetration creates coupled voltage–frequency regulation needs where fluctuations in one parameter directly influence the other in multi-area networks.

### 8.2 Advanced Control Strategies

Model Predictive Controllers (MPC) have demonstrated significant improvements in frequency deviation management in renewable-integrated multi-area systems. The Leader Harris Hawks Optimization-based MPC (MPC-LHHO) reduced frequency deviation undershoot by 67.45% and voltage settling time by 91.11% compared to conventional PI controllers in a deregulated six-GENCO/six-DISCO network (Scientific Reports, 2025). Auxiliary devices—Unified Power Flow Controllers (UPFC) and grid-connected electric vehicles (EVs)—further enhanced robustness under stochastic renewable scenarios.

For the NIG–Chad system, LFC design is complicated by: (a) the limited inertia of Chad's largely diesel-based generation; (b) the seasonal variability of Lagdo's hydro output; and (c) the potential for large frequency excursions following loss of the tie-line (N-1 contingency). The proposed study should model frequency response under contingency scenarios alongside steady-state power flow optimization.

---

## 9. Artificial Intelligence Tools for Power System Analysis

### 9.1 AI-Assisted Power Flow and Optimal Power Flow

The traditional deterministic formulations (NR, fast decoupled) are increasingly constrained by nonlinearities introduced by power electronic converters and distributed resources. AI-assisted power flow methods extend classical formulations by incorporating data-driven learning capable of capturing nonlinear relationships (AJIS Research, 2025). Machine learning assisted OPF—using fully connected neural networks, convolutional neural networks (CNNs), and graph neural networks (GNNs)—aims to reduce computational complexity by moving expensive optimization offline to training, enabling real-time deployment (Falconer & Mones, arXiv, 2021).

GNNs are particularly promising for power flow because they exploit the topological structure of the grid graph, outperforming topology-agnostic fully connected networks on systems with varying configurations—a key feature for studying the NIG pre- and post-interconnection (arXiv, Leveraging Power Grid Topology in ML-Assisted OPF, 2021).

### 9.2 Reinforcement Learning for Grid Topology Optimization

Reinforcement learning (RL) has emerged as a powerful tool for power network reconfiguration and congestion management. The L2RPN (Learning to Run a Power Network) benchmark has catalyzed research into RL agents that optimize bus splitting and line switching to minimize losses and prevent cascading failures. PowRL (AAAI, 2023) demonstrated that RL-based topology management outperforms both rule-based and classic optimization approaches under contingency conditions. A 2025 survey by van der Sar et al. (arXiv) comprehensively reviews RL methods for power grid topology optimization, identifying key challenges including sample efficiency, safety constraints, and transfer across network configurations.

For the NIG–Chad study, RL-based approaches could be used to identify optimal busbar configurations that minimize losses under varying load and generation scenarios, including seasonal variation at Lagdo and intermittent solar injection.

### 9.3 Large Language Models and AI Orchestration in Grid Studies

The emerging "Grid-Mind" framework (arXiv, 2025) employs LLM-orchestrated multi-fidelity agents for automated connection impact assessment, combining natural language interfaces with power flow simulation engines. While not yet operationalized in Sub-Saharan African contexts, this represents the frontier of AI integration in grid planning studies and is relevant as a methodological reference.

### 9.4 AI for Grid Modernization in Sub-Saharan Africa

Smart grid fault detection using gradient boosting has been validated for sub-Saharan African conditions, demonstrating that AI-enhanced systems can enable predictive demand-response, improve generator scheduling, and reduce overproduction (WJAETS, 2025). Critically, gradient boosting models—lighter than deep learning architectures—can be deployed on edge devices, reducing dependency on centralized infrastructure. Machine learning can also map energy demand more accurately than traditional surveys, addressing the data scarcity that has historically impeded grid planning in Chad and northern Cameroon (UK Research and Innovation Energy Catalyst, 2025).

---

## 10. Economic and Strategic Dimensions

### 10.1 Cost-Benefit Framework for Cross-Border Interconnection

The economic case for the NIG–Chad interconnection rests on several pillars: (a) avoided cost of diesel generation in Chad (estimated among the highest per-kWh costs in the region); (b) revenue from electricity exports for Cameroon; (c) regional multiplier effects from improved energy access; and (d) facilitation of larger renewable energy projects with multi-country offtake. The World Bank has consistently argued that regional power trade reduces system costs by 10–30% through economies of scale and optimized use of generation assets.

However, financial sustainability requires creditworthy offtakers, transparent tariff structures, and harmonized regulatory frameworks—conditions that are presently weak in both countries' power sectors. SNE's chronic financial underperformance is a principal risk factor: without utility viability, cross-border trade agreements remain political instruments without commercial foundations (Energy Transition Africa, 2026).

### 10.2 Strategic and Geopolitical Considerations

The NIG–Chad interconnection carries strategic dimensions beyond pure economics. Chad's geographic isolation as a landlocked Sahelian state makes energy security a national security issue. The interconnection reduces Chad's dependence on oil-fired diesel generation, diversifies its energy supply, and strengthens bilateral ties with Cameroon within the ECCAS (Economic Community of Central African States) framework. The Desert-to-Power initiative's roadmap explicitly positions the link with Cameroon as a prerequisite for scaling solar integration in Chad at the 700+ MW level (AfDB, 2020).

### 10.3 Environmental and Social Considerations

The AfDB Category 1 ESIA (2017) identifies significant environmental and social impacts along the transmission corridor, including land acquisition, community displacement, and ecological disruption. These factors influence both route selection and busbar siting—considerations that intersect with the technical optimization objectives of the proposed study. Sustainable development framing requires that infrastructure decisions optimize not only technical performance but also social equity and environmental impact.

---

## 11. Research Gaps and Positioning of the Proposed Study

The literature review reveals several gaps that the proposed study is positioned to address:

1. **No post-2023 integrated study of the NIG–Chad interconnection** accounting for the actual project announcement, updated NIG parameters (including Maroua and Guider solar plants), and Chad's current grid state. Existing analyses are either pre-project (AfDB ESIA, 2017) or focused on the NIG in isolation.

2. **Busbar-level optimization for the interconnection point has not been published.** Existing NIG power flow studies (SCIRP 2024, Sustainable Energy Research 2023) do not specifically address optimal busbar selection for the cross-border tie-line injection.

3. **AI methods have not been applied to the NIG context.** The broader literature demonstrates the applicability of NR-based OPF, RL, and GNN methods to African transmission grids (Nigeria, Tanzania), but these have not been applied to the NIG or the NIG–Chad corridor.

4. **Integrated technical-economic-strategic analysis is absent.** The World Bank and AfDB project documents focus on financial and development dimensions without the granular power system analysis that this study proposes.

5. **Frequency stability under the interconnection has not been modeled.** Given Chad's low-inertia, diesel-dominated system and the NIG's hydropower variability, LFC co-design for the interconnected system is an open problem.

---

## 12. Conclusion

This review establishes the multi-layered context for studying the NIG–Chad interconnection. The foundational technical challenge—identifying busbars that minimize power losses while maintaining voltage and frequency stability—draws on a mature body of power systems literature centered on Newton-Raphson OPF, sensitivity analysis, voltage stability assessment, and load-frequency control. These classical methods are increasingly augmented by AI tools including graph neural networks, reinforcement learning, and gradient-boosted machine learning models, which offer both computational efficiency and the ability to handle the nonlinearities introduced by renewable energy integration.

The contextual literature reveals an urgent development rationale: Chad's near-total rural electrification deficit, the NIG's untapped export potential, and the enabling framework of CAPP and Desert-to-Power all converge to make this interconnection a high-priority regional infrastructure investment. The proposed study's integration of technical rigor with AI-driven innovation and strategic analysis has the potential to provide actionable guidance for this consequential project.

---

## Key References

*The following are the primary sources identified in this review. A full formatted bibliography in IEEE or APA style should be compiled prior to manuscript submission.*

1. Che, et al. (2025). "Investigation of the Stability of the Cameroon Northern Interconnected Grid (NIG): A Transient Analysis." *Journal of Control Science and Engineering*, Wiley. https://onlinelibrary.wiley.com/doi/10.1155/jcse/2524618

2. Anonymous (2024). "Optimizing Power Flow in Northern Cameroon's Interconnected Grid: Challenges and Solutions." *Scientific Research Publishing (SCIRP)*. https://www.scirp.org/journal/paperinformation?paperid=136049

3. Anonymous (2023). "Optimal energy scheduling method for the North Cameroonian interconnected grid in response to load shedding." *Sustainable Energy Research*, Springer Open. https://sustainenergyres.springeropen.com/articles/10.1186/s40807-023-00084-x

4. World Bank Group (2020). *Cameroon-Chad Power Interconnection Project: Appraisal Document* (P168185). https://documents1.worldbank.org/curated/en/482631592619043723/pdf/Cameroon-and-Chad-Power-Interconnection-Project.pdf

5. African Development Bank (2017). *Multinational – Chad-Cameroon 225 kV Electrical Grid Interconnection: Summary ESIA*. https://www.afdb.org/fileadmin/uploads/afdb/Documents/Environmental-and-Social-Assessments/Multinational...

6. African Development Bank (2024). *Electricity Sector Support Project in Chad – Phase 2 (PASET-2)*. https://www.afdb.org/sites/default/files/documents/projects-and-operations/chad_electricity_sector_support...

7. African Development Bank (2020). *Desert-to-Power Roadmap for Chad*. https://www.afdb.org/sites/default/files/2024/08/23/desert-to-power_dtp_roadmap_for_chad_en_oct2020-v2_en.pdf

8. Columbia University Center on Global Energy Policy (2024). "Oil and the Politics of Energy Access in Chad." https://www.energypolicy.columbia.edu/wp-content/uploads/2024/02/Oil-and-energy-access-in-Chad-Commentary_CGEP_012224.pdf

9. Africa Energy Portal (2023). *Chad Country Profile*. https://africa-energy-portal.org/aep/country/chad

10. Falconer, T. & Mones, L. (2021). "Leveraging Power Grid Topology in Machine Learning Assisted Optimal Power Flow." *arXiv*. https://arxiv.org/pdf/2110.00306

11. Anonymous (2025). "Artificial Intelligence Assisted Power Flow Control, Fault Detection." *AJIS Research*. https://ajisresearch.com/index.php/ajis/article/download/105/103

12. Anonymous (2025). "Transferable Graph Learning for Transmission Congestion Management via Busbar Splitting." *arXiv*. https://arxiv.org/pdf/2510.20591

13. Anonymous (2025). "Optimized smart grid fault detection model using gradient boosting." *WJAETS*. https://journalwjaets.com/sites/default/files/fulltext_pdf/WJAETS-2025-0264.pdf

14. Anonymous (2025). "Grid-Mind: An LLM-Orchestrated Multi-Fidelity Agent for Automated Connection Impact Assessment." *arXiv*. https://arxiv.org/pdf/2602.20683

15. Anonymous (2025). "Optimal voltage and frequency control strategy for renewable-dominated deregulated power network." *Scientific Reports*. https://www.nature.com/articles/s41598-024-84549-z

16. van der Sar, E., et al. (2025). "Optimizing power grid topologies with reinforcement learning: A survey of methods and challenges." *arXiv*. https://arxiv.org/pdf/2504.08210

17. Chauhan, A., et al. (2023). "PowRL: A Reinforcement Learning Framework for Robust Management of Power Networks." *AAAI*. Vol. 37, No. 12, pp. 14757–14764.

18. Anonymous (2021). "Optimal Placement of FACTS Device Considering Voltage Stability and Losses using TLBO." *Journal of The Institution of Engineers (India): Series B*, Springer. https://link.springer.com/article/10.1007/s40031-021-00582-w

19. Mgonja, C.T. (2014). "Load Flow Solution of the Tanzanian Power Network Using Newton-Raphson Method and MATLAB Software." *Academia*.

20. Anonymous (2021). "Investigating the effects of bus numbering in a radial transmission network using load-flow study." *PMC/Heliyon*. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8176315/

21. Anonymous (2021). "Cameroon's hydropower potential and development under the vision of Central African Power Pool (CAPP): A review." *ScienceDirect*. https://www.sciencedirect.com/science/article/abs/pii/S136403212100873X

22. African Energy Chamber (2026). *State of African Energy 2026 Outlook: African Power Pools.* https://energychamber.org/african-power-pools-how-regional-integration-can-strengthen-energy-security/

23. IRENA/AfDB (2017). *Renewable Energy Roadmap for Central Africa.* https://rise.esmap.org/sites/default/files/library/central-african-republic/...

24. UK Research and Innovation / Energy Catalyst (2025). "Unlocking Off-Grid potential: How AI is powering smarter energy solutions across Africa." https://energycatalyst.ukri.org/news/unlocking-off-grid-potential-how-ai-is-powering-smarter-energy-solutions-across-africa/

25. Anonymous (2023). "Power Loss Minimization of Distribution Network using Different Grid Strategies." *arXiv*. https://arxiv.org/pdf/2307.06275

---

*End of Literature Review*
