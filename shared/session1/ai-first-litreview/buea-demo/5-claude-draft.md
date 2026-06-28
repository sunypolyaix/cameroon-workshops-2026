# 5-claude-draft.md — Literature Review Draft

## Tool
Claude (claude.ai)

## Inputs provided
- `1-perplexity.md` — literature framework and suggested structure
- `3-gemini.md` — comparative source analysis and gap identification
- `4-notebooklm.md` — targeted interrogation notes and key facts

## Prompt

> Using the Perplexity framework, the Gemini gap analysis, and the NotebookLM notes, draft the literature review section for this thesis. Ground every claim in the three sources I have uploaded. Flag anything that needs a citation I haven't provided yet.

---

## Draft Literature Review

### The Cameroon–Chad Interconnection: A Review of the Technical, Economic, and Strategic Literature

#### 1. Introduction

The interconnection of national power grids has emerged as a central strategy for addressing energy poverty, enabling renewable integration, and reducing the cost of electricity supply across the African continent. The proposed interconnection of Cameroon's Northern Interconnected Grid (NIG) with the Chad National Power Grid represents a concrete instantiation of this regional imperative — one that demands analysis at the technical, economic, and strategic levels simultaneously. This review surveys the existing literature across these three dimensions, identifies where the literature converges, where it diverges, and where it leaves a gap that the present study is positioned to fill.

#### 2. Chad's Energy Context and the Case for Cross-Border Supply

The baseline condition that motivates this study is documented clearly by Kelly et al. (2023), whose techno-economic analysis of hybrid energy systems in Chad establishes that the country's National Electricity Company (NEC) supplies grid electricity to only 7 of its 23 administrative regions, with all generation sourced exclusively from diesel thermal plants. The national electrification rate stands at approximately 11% for urban populations and 2% for rural populations. The Cost of Energy (COE) for Chad's existing thermal supply is 0.400 USD/kWh — a figure Kelly et al. use as the economic benchmark against which alternative generation strategies are evaluated. Their analysis demonstrates that hybrid PV/diesel/battery configurations can achieve COE values as low as 0.367 USD/kWh in some regions, establishing that alternatives to thermal-only generation are not only technically feasible but economically competitive within Chad's own borders.

What Kelly et al. do not examine is the possibility of importing electricity from a neighboring grid. Their study is bounded to off-grid, autonomous hybrid systems — a design choice that leaves the cross-border interconnection option unexamined. The present study takes up precisely the question Kelly et al. set aside: whether the NIG can serve as a supply source for Chad's northern regions, and at which interconnection point the transfer can be achieved with minimal losses.

#### 3. Regional Interconnection as an Energy Strategy in Africa

The broader literature on African grid interconnection provides the strategic context for evaluating the NIG–Chad corridor. Wu et al. (2017) offer the most directly relevant regional analysis, mapping wind and solar energy potential across 21 countries in the Southern African Power Pool (SAPP) and Eastern Africa Power Pool (EAPP) using the Multicriteria Analysis for Planning Renewable Energy (MapRE) framework. Their central finding is that the most competitive renewable resources are spatially heterogeneous — distributed unevenly across countries — which makes regional interconnection not merely desirable but necessary for cost-effective low-carbon development. In their modeled scenarios, strategic interconnections reduced SAPP-wide conventional generation capacity requirements by approximately 9.5%, producing system cost savings of 6–20% depending on the avoided technology.

Critically, Wu et al. introduce the concept of "no-regrets" interconnection zones — sites that are simultaneously low-cost, low-environmental-impact, and accessible — as the appropriate target for transmission planning. This multicriteria framing is directly applicable to the busbar selection problem at the heart of the present study: a no-regrets busbar for the NIG–Chad interconnection would minimize active power losses while maintaining voltage and frequency within acceptable limits, connect to existing transmission infrastructure with minimal extension, and remain viable under multiple load scenarios.

A significant limitation of Wu et al. for the present purposes is geographic: their analysis covers SAPP and EAPP countries and largely omits Central Africa. Cameroon and Chad fall outside the study region. The present study therefore applies the analytical logic of Wu et al. — multicriteria site selection integrated with system-level cost analysis — to a corridor those authors did not examine.

#### 4. Transmission Technology and Hardware for Cross-Border Interconnection

Imdadullah et al. (2021) provide a comprehensive global review of power grid interconnection technologies, covering AC synchronous interconnection, LCC-HVDC, VSC-HVDC (including MMC variants and HVDC Light), Variable Frequency Transformers (VFT), and the emerging Flexible Asynchronous AC Link (FASAL) system. Their analysis establishes that for long-distance bulk power transfer — the likely requirement of a Cameroon-Chad corridor spanning several hundred kilometers — LCC-HVDC remains the mature, low-loss, high-reliability choice, while VSC-HVDC is preferred where grid strength at the receiving end is limited or where black-start capability is required.

Imdadullah et al. operate at a level of abstraction that is useful for technology selection but insufficient for site-specific engineering decisions. Their review does not address the busbar-level analysis required to determine where on the NIG the interconnection point should be located, nor does it examine the Central African grid context. The present study moves from the technology selection level addressed by Imdadullah et al. to the physical analysis of candidate interconnection points — specifically the comparison of busbars on the NIG in terms of their projected power losses, voltage profiles, and frequency behavior under interconnected operating conditions.

#### 5. The Role of Artificial Intelligence in Grid Optimization

Across all three reviewed sources, AI-based optimization is notable primarily by its absence. Kelly et al. employ HOMER, a simulation and optimization platform that performs techno-economic design but does not use machine learning. Wu et al. apply linear programming for wind zone selection within the MapRE framework. Imdadullah et al. mention machine learning as a future research direction for smart grid development but do not apply it to the interconnection design problem. None of the three papers use neural networks, genetic algorithms, particle swarm optimization, fuzzy multicriteria decision-making, or hybrid AI methods for busbar selection or interconnection optimization.

This gap is methodologically significant. The busbar selection problem is inherently multicriteria and uncertain: candidate busbars must be ranked against multiple simultaneous objectives (loss minimization, voltage adequacy, frequency stability) under variable load conditions and with imperfect data. These are precisely the conditions under which AI-based decision support offers advantages over classical methods. The present study proposes to fill this methodological gap by incorporating AI tools into the busbar ranking and interconnection optimization workflow.

#### 6. Summary of Gaps and Research Contribution

The review of existing literature reveals three interlocking gaps that define the contribution of the present study:

**Geographic gap:** The African interconnection literature (Wu et al.) focuses on Southern and Eastern Africa; the Chad-specific literature (Kelly et al.) focuses on off-grid hybrid generation. No existing study addresses the specific Cameroon-Chad interconnection corridor.

**Technical gap:** Neither the regional planning literature nor the hardware review literature (Imdadullah et al.) resolves the busbar-level engineering question — the physical location on the NIG at which cross-border connection should be made to minimize losses and maintain power quality.

**Methodological gap:** AI-based multicriteria optimization has not been applied to the busbar selection problem in the Central African context, despite its demonstrated potential in comparable grid planning problems elsewhere.

The present study addresses all three gaps by applying AI-assisted multicriteria analysis to the specific problem of busbar selection for the NIG–Chad interconnection, grounded in the regional strategic logic established by Wu et al. and the hardware and load context provided by Imdadullah et al. and Kelly et al.

---

*[Citations requiring additional sources are flagged for follow-up: frequency stability standards for CEMAC regional grid; HVDC cost benchmarks for Sub-Saharan Africa; Cameroon NIG technical specifications.]*
