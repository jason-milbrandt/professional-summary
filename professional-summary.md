# Professional Research Summary: Jason A. Milbrandt

> **Status — living document (updated 2026-06-06).** This document aggregates the per-article summaries in `wiki/summaries/` into a synthetic overview of Jason A. Milbrandt's research contributions, intended as a go-to reference for downstream AI-assisted research and publication work. It now covers the **complete processed corpus of 68 papers** (30 Tier 1/2 lead/key-author papers + 38 Tier 3 contributing-author papers). The main narrative (Sections 1–7) covers the Tier 1 and Tier 2 papers — those where Milbrandt drove or substantively shaped the science. Tier 3 papers — where he was a supporting contributor (typically the provider of his microphysics scheme or domain expertise) — are summarized thematically in the **Related Contributions** section (Section 8). Per-summary source files are the authoritative record; this document should not be cited in place of them. Interpretive cross-references not yet verified against a source are tagged `⚠ verify`.

> **How to use this document (for an AI reading it cold):** Sections 1–2 give the author profile and the single intellectual through-line of his career. Section 3 narrates the research arc thematically. Section 4 is a chronological one-line-per-paper table with citation counts. Section 5 is a deeper thematic synthesis. Section 6 records the tier system and how to talk about credit accurately. Section 8 covers the supporting (Tier 3) body of work. The **tier system is the most important framing device**: do not describe Milbrandt as having "developed" or "led" Tier 2/3 work — use "contributed," "co-developed," or "provided the scheme for." When in doubt about any specific factual claim, consult the named summary file in `wiki/summaries/`.

---

## 1. Author Profile

**Jason A. Milbrandt** is a Research Scientist in the Meteorological Research Division of Environment and Climate Change Canada (ECCC). His specialty is **cloud microphysics parameterization for numerical weather prediction (NWP)**. His two defining scientific contributions are:

- **The Milbrandt–Yau (MY) multimoment bulk microphysics scheme** — a six-category (cloud, rain, ice, snow, graupel, hail) bulk scheme with selectable one-, two-, and three-moment options, developed during his doctoral work at McGill University with M. K. Yau. The two-moment configuration (MY2) became the operational microphysics scheme in ECCC's kilometer-scale High Resolution Deterministic Prediction System (HRDPS) when it went operational in November 2014 (Milbrandt et al. 2016), and a two-moment MY option is available in the community WRF model. It is also the cloud-microphysics component of ECCC's coupled air-quality model GEM-MACH (Gong et al. 2015; Makar et al. 2015a,b).

- **The Predicted Particle Properties (P3) scheme** (with H. Morrison) — a conceptually distinct approach that abandons rigid predefined ice categories in favor of one or more "free" ice categories whose physical properties (rime fraction, density, fall speed) evolve continuously via conserved prognostic variables. P3 was implemented operationally in HRDPS as part of ECCC's physics modernization, replacing MY2 (McTaggart-Cowan et al. 2019), and is used in research models including WRF, CM1, and GEM (E3SM adoption ⚠ verify).

His work sits at the interface of fundamental cloud physics, parameterization design, and operational NWP, with a consistent emphasis on the physical fidelity of the hydrometeor size distribution and its consequences for sedimentation, precipitation, storm structure, and surface precipitation type.

**Institutional affiliation:** Environment and Climate Change Canada (ECCC), Meteorological Research Division / Recherche en Prévision Numérique (Dorval, Quebec).
**Primary academic lineage:** Ph.D., McGill University (Dept. of Atmospheric and Oceanic Sciences) under M. K. Yau.
**Contact:** jason.a.milbrandt@gmail.com

---

## 2. The Single Intellectual Through-Line

The entire arc of Milbrandt's research is organized around one question: **how faithfully a bulk microphysics scheme represents the hydrometeor particle size distribution (PSD), and why that fidelity matters for prediction.**

The recurring mathematical object is the **gamma PSD**,
$$N(D) = N_0 D^\alpha e^{-\lambda D},$$
and in particular its **spectral shape (relative dispersion) parameter $\alpha$** (equivalently $\mu$). Conventional bulk schemes held $\alpha$ fixed and prescribed rigid particle categories with fixed densities, mass–diameter ($m$–$D$) relations, and fall speeds. Milbrandt's career is a sustained campaign to **replace fixed assumptions with predicted physical degrees of freedom**:

1. First, predict more **moments** of the PSD (number → reflectivity), letting $\alpha$ evolve (the MY scheme, 2005–2006).
2. Then, predict **particle properties** within a category — bulk density (graupel-density paper, 2013), then the full free-category framework (P3, 2015–2016).
3. Then, add **more predicted moments and phases** back into the property-predicting framework: triple-moment ice (2021), predicted liquid fraction (Cholette et al. 2019), and multiple coexisting free categories (2016; combined for hail in 2025).
4. Throughout, **bring these schemes into operational NWP** (HRDPS, 2016) and adapt them across model scales (Chosson et al. 2014; Jouan et al. 2020) and to explicit surface precipitation-type prediction (freezing rain, ice pellets, wet snow).

Each advance is motivated by a concrete failure of the previous fixed assumption, demonstrated quantitatively, and then either validated against observations or deployed operationally. This is the spine onto which every paper below attaches.

---

## 3. Research Program Overview (chronological arc)

**(a) Applied mesoscale foundations (2001).** The Saguenay flood study established the modeling environment (the Canadian MC2 model + Kong–Yau explicit microphysics), the collaboration (Yau), and the applied-NWP motivation from which the microphysics program grew.

**(b) The Milbrandt–Yau multimoment scheme (2005–2006, Parts I–IV).** A four-part series that built, validated, and characterized the MY scheme: theory of the shape parameter (Part I), three-moment closure and full scheme description (Part II), 3D cloud-resolving demonstration (Part III), and cost–benefit sensitivity analysis (Part IV).

**(c) Validation and theoretical consolidation (2008–2010).** First in-situ aircraft validation against the IMPROVE-2 orographic dataset (Parts I & II, 2008 & 2010) and a comprehensive theoretical treatment of sedimentation errors across all moment configurations (Milbrandt & McTaggart-Cowan 2010).

**(d) Benchmarking and ice-phase diagnosis (2011–2013).** The Morrison–Milbrandt intercomparison (2011) showed even comparable two-moment schemes diverge, with the graupel-vs-hail choice dominant. The snow-category modernization papers (2012) and the prognostic graupel-density paper (2013) progressively fixed the most rigid ice assumptions — the latter explicitly framed as a "paradigm shift toward adding physical degrees of freedom," directly anticipating P3.

**(e) The P3 scheme (2015–2016).** The Predicted Particle Properties scheme (Parts I–III), Milbrandt's most highly cited body of work, replacing fixed ice categories with continuously evolving particle properties, then extending to multiple free categories.

**(f) Operationalization and scale adaptation (2014–2020).** MY2 in operational HRDPS (Milbrandt et al. 2016); scale-adaptive subgrid cloud fraction enabling two-moment schemes at coarse resolution (Chosson et al. 2014) and its application to P3 for global-scale NWP (Jouan et al. 2020); the transition of HRDPS from MY2 to P3 (McTaggart-Cowan et al. 2019).

**(g) Modern P3 extensions (2019–2025).** Triple-moment ice (2021); predicted liquid fraction for mixed-phase particles (Cholette et al. 2019, 2023, 2024, 2025); explicit prediction of freezing rain, ice pellets, and wet snow; and the combined-capability hail study (Milbrandt et al. 2025) that closes the loop on P3's longstanding hail weakness.

---

## 4. Thematic Contributions (Tier 1 & 2)

### 4.1 The spectral shape parameter $\alpha$ — the conceptual seed (MY Part I, 2005a)

**Part I (2005a)** showed quantitatively that $\alpha$ controls the rate of gravitational size sorting (via the ratio of mass- to number-weighted fall speeds) and the accuracy of moment-based microphysical source terms — an incorrect $\alpha$ can produce ~700% errors in radar reflectivity and unrealistic "excessive size sorting." It established a clear scheme-skill hierarchy (three-moment > diagnosed-$\alpha$ two-moment > fixed-$\alpha=3$ > fixed-$\alpha=0$ > single-moment) and introduced a diagnostic relation $\alpha = f(D_m)$ as a low-cost way to capture much of the benefit. (~665 citations.)

### 4.2 Three-moment closure and the MY scheme (Part II, 2005b)

**Part II (2005b)** delivered the first complete bulk scheme to fully prognose $\alpha$ for all precipitating categories, adding a mathematically consistent tendency equation for radar reflectivity (the third moment) across all microphysical process classes. The resulting **six-category scheme with unified one-/two-/three-moment options** is the central artifact of the first half of his career and the ancestor of the operational MY2 component of ECCC's HRDPS. (~556 citations; Parts I+II together exceed 1,200 citations and are standard references for multimoment bulk microphysics.)

### 4.3 3D validation and hail diagnostics (Part III, 2006a)

**Part III (2006a)** produced the first-ever cloud-resolving simulation with a three-moment bulk scheme (the 14 July 2000 Pine Lake, Alberta supercell), reproducing observed storm structure (BWER, hook echo, mesocyclone). It introduced the diagnostic parameters $N_h^*\{D^*\}$ (number concentration of hail larger than $D^*$) and $R_h^*\{D^*\}$ (its surface flux) with observability thresholds, enabling a bulk scheme to report a physically meaningful **maximum hail size** rather than a misleading mean diameter. It also gave a mechanistic account of how $\alpha$ can locally *decrease* in full physics (via advection, sources/sinks, sedimentation) — behavior impossible in fixed/diagnosed-$\alpha$ schemes. (~62 citations.)

### 4.4 Cost–benefit guidance for scheme complexity (Part IV, 2006b)

**Part IV (2006b)** delivered the program's most actionable practical result via controlled sensitivity experiments (all versions of the *same* scheme): the dominant skill gain is from **one-moment → two-moment**, with a smaller incremental gain to three moments for most fields — *except maximum hail size*, which only the full three-moment scheme captures. This underpins the common operational choice of the economical two-moment configuration, and the recognized awkwardness of fixed hydrometeor categories foreshadows P3. (~84 citations.)

### 4.5 Observational validation and sedimentation theory (2008–2010)

- **IMPROVE-2 Part I (Milbrandt et al. 2008)** — first in-situ (aircraft) validation of the MY scheme against the IMPROVE-2 orographic dataset: realistic precipitation pattern and particle sizes (confirming the multimoment thesis observationally) but overpredicted snow mass / underpredicted cloud water; notably *no* leeside overprediction, unlike MM5/Reisner-2. (~40 citations.)
- **Sedimentation errors (Milbrandt & McTaggart-Cowan 2010)** — comprehensive ranking of bulk-scheme moment configurations; the standard two-moment ($M_0$–$M_3$, fixed $m$) configuration performs catastrophically for sedimentation; proposes generalized diagnostic-$m$ and diagnostic $V_k/V_j$ fixes applicable to *any* existing two-moment scheme. Returns to and generalizes the Part I theory. (~110 citations.)
- **IMPROVE-2 Part II (Milbrandt et al. 2010)** — double-moment ≈ triple-moment for the orographic case; *scheme identity matters more than moment count*; identifies the leeside-overprediction mechanism in KY/Reisner-2 (missing latent-heat term + instantaneous melting). Announces forthcoming snow-category modernization. (~52 citations.)

### 4.6 Benchmarking and ice-phase modernization (2011–2013)

- **Morrison–Milbrandt intercomparison (2011)** — idealized WRF supercell; the graupel-vs-hail choice is the dominant inter-scheme difference; drop breakup matters for the MOR cold pool; two-moment schemes do not converge as complexity increases. Most-cited paper of the early corpus. (~210 citations.) This *diagnosed* the dominant ice-phase uncertainty that the 2013 paper then *fixed*.
- **Snow-category modernization (Milbrandt et al. 2012, two papers)** — a 1D snow-melting study (PAAG / "snowmelting", same paper, ~15 citations) identifying the inability of bulk schemes to represent partial melting as a fundamental limitation and proposing a 1D model as a forecaster tool; and the **snow-to-liquid ratio (SLR)** paper (~26 citations) delivering the first explicit SLR prediction from a bulk scheme via new MY2 snow updates ($d_s \approx 2$, faster $V$–$D$, constrained $\lambda_{s,\min}$, reduced capacitance). The SLR feature was deployed operationally in the ECCC experimental system for the **2010 Vancouver Winter Olympics** (Mailhot et al. 2012).
- **Prognostic graupel density (Milbrandt & Morrison 2013)** — adds $B_g = q_g/\rho_g$ as a new prognostic variable, giving density-dependent fall speeds via a Re–$X$ formulation, so a single rimed-ice category can span lightly rimed snow to hail-like ice. Explicitly framed as "part of a paradigm shift... toward adding physical degrees of freedom for a given hydrometeor type." The critical conceptual bridge to P3; $B_g$ is the direct ancestor of P3's rime-volume variable $B_{rim}$. (~62 citations.)

### 4.7 The P3 scheme (2015–2016, Parts I–III)

The **Predicted Particle Properties (P3) scheme** is Milbrandt's most impactful contribution. Combined summary: `Morrison_Milbrandt_2015_2016-P3-summary.md`.

- **Part I (Morrison & Milbrandt 2015a; ~511 citations)** — introduces P3: a single "free" ice category with four conserved prognostic variables (total ice mass $q_i$, number $N_i$, rime mass $q_{rim}$, rime volume $B_{rim}$), allowing the rime mass fraction $F_r = q_{rim}/q_i$ and predicted rime density $\rho_r = q_{rim}/B_{rim}$ to evolve freely. A four-region $m$–$D$ relation and Re–$X$ fall speeds make particle density, size, and fall speed self-consistent. Eliminates all predefined ice categories and the artificial conversion processes between them. Idealized 2D squall-line tests show $F_r$ and $\rho_r$ have *no* simple relationship with local temperature, LWC, or updraft — confirming that transport makes diagnostic approaches unreliable. **Authorship note:** Morrison's first authorship on Parts I & II is nominal; Milbrandt is co-lead (Tier 1), contributing the MY2 framework, the rime-volume budget, and the density-dependent fall-speed approach.
- **Part II (Morrison et al. 2015b; ~211 citations)** — 3D WRF evaluation against two well-observed cases and nine schemes. For a midlatitude squall line, P3 (like MOR-H) reproduces the narrow, intense convective leading edge that graupel-only schemes miss, because it predicts hail-like ($\rho_g > 700$ kg m$^{-3}$) fall speeds in the core. For the IMPROVE-2 orographic case, P3 produces more windward / less leeward precipitation, traceable to predicted enhanced fall speeds for lightly rimed snow — consistent with the IMPROVE-2 observations and the 2008/2010 physical argument. Computationally efficient: faster than MY2, only ~11% slower than WSM6 despite 7 prognostic variables.
- **Part III (Milbrandt & Morrison 2016; ~131 citations)** — Milbrandt first-authored. Extends P3 to $n_{Cat}$ user-specified free categories, eliminating "property dilution" (the blending of distinct ice populations forced into one category). New algorithmic elements: destination-category selection ($\Delta D_{init}$ threshold), inter-category collection (lookup-table double integral), and category merging. Convergence at $n_{Cat} \approx 3$–4 (strong forcing) or 2 (weak); rime splintering requires $n_{Cat} \geq 2$ to be beneficial. The **first multiple-free-category bulk microphysics scheme**.

### 4.8 Modern P3 extensions: moments, phase, and hail (2019–2025)

- **Triple-moment ice (Milbrandt et al. 2021; ~46 citations, Tier 1 lead)** — adds a fifth prognostic variable per ice category, the sixth PSD moment $Z_{i,tot}$ (analogous to reflectivity), letting the shape parameter $\mu$ vary independently of mean size. This removes the artificial 2-mm mean-size limiter and controls size sorting *physically*, producing larger, more realistic mean and maximum hail and reflectivity in idealized CM1 supercell simulations. Applies the three-moment concept from MY05 to the free-category P3 framework. Recommends advecting $Z_{advect}=Z_{i,tot}/Q_{i,tot}$ (per Morrison et al. 2016) to preserve PSD parameters during transport.
- **Predicted liquid fraction (Cholette et al. 2019, Tier 2)** — adds $q_{i,liq}$ (bulk liquid fraction $F_{i,liq}$) so P3 can represent mixed-phase particles explicitly, enabling **wet snow** and **ice pellets** that no standard bulk scheme produces. Milbrandt co-supervised Cholette (PhD) and provided the P3 framework. First of a four-paper Cholette series (2019, 2023, 2024, 2025).
- **Triple-moment + liquid fraction integration (Cholette et al. 2023, Tier 2; ~13 citations)** — combines the two upgrades (up to 6 prognostic variables/category), tested on a real squall line in GEM. Produces stronger cold pools, faster propagation, reduced surface ice, and an explicit, realistic radar bright band. This combined `3MOM_LF` configuration is the operational P3 in HRDPS (exact deployment date ⚠ verify).
- **Secondary ice production for freezing rain (Cholette et al. 2024, Tier 2; ~8 citations)** — Hallett–Mossop rime splintering with two ice categories cuts excessive HRDPS freezing-rain accumulation by up to 98% and matches/beats the empirical Bourgouin diagnostic over 40 winter hindcasts, using only physical prognostic variables. Brackets, with Barszcz et al. (2018), the two-sided sensitivity of explicit freezing-rain prediction.
- **Wet snow in orographic terrain (Cholette et al. 2025, Tier 2; 0 citations, very recent)** — first 3D NWP evaluation of P3's liquid-fraction capability for wet snow, against ICE-POP 2018 (South Korea) retrievals; LF produces wet snow where the standard scheme produces rain, and captures the coast-to-mountain density gradient.
- **Combined hail capabilities (Milbrandt et al. 2025; ~1 citation, Tier 1 lead)** — isolates the effects of predicted liquid fraction (→ smaller surface hail, via $N_{i,tot}$ preservation during melt/shed) and multiple ice categories (→ larger hail, via reduced dilution) on idealized 200-m CM1 supercell hail. Argues the current `LF-2CAT` configuration (triple-moment ice + liquid fraction + two categories) can realistically represent the full hail lifecycle, closing the longstanding P3 hail weakness first flagged by Johnson et al. (2019).

### 4.9 Operational NWP and scale adaptation (2014–2020)

- **HRDPS system paper (Milbrandt et al. 2016; ~152 citations, Tier 1 lead)** — the definitive description and verification of Canada's pan-national 2.5-km operational NWP system (HRDPS, operational November 2014), built on GEM with MY2 microphysics. Documents improved skill over the 10-km RDPS, the hydrometeor "hot start," a moist bias traceable to MY2 (excessive snow sublimation), the −5°C freezing-rain fix to MY2, and the planned transition to P3. The primary reference for the HRDPS-MY2 configuration.
- **Scale-adaptive two-moment microphysics (Chosson et al. 2014, Tier 2; ~29 citations)** — a subgrid cloud/precipitation fraction (SCPF) parameterization plus microphysical sub-time-stepping that lets MY2 work at coarse (15-km) resolution, validated against CALIPSO/CloudSat. Milbrandt is co-developer of the target scheme.
- **P3 for large-scale NWP (Jouan et al. 2020, Tier 2; ~14 citations)** — applies the Chosson SCPF approach to P3 in the 25-km global GEM, the first step toward replacing the decades-old Sundqvist scheme across *all* ECCC model scales with unified P3 microphysics. Milbrandt second author and senior scientist.

### 4.10 Process studies enabled by the schemes (Tier 2)

- **CCN sensitivity of deep convection (Jouan & Milbrandt 2019; ~11 citations)** — uses MY2 in GEM (1 km) to show a squall line's response to CCN acts not only through warm-phase effects but through ice-phase (graupel-riming) pathways; prognostic graupel density and two-moment graupel are necessary to capture it. Directly supports the case for property-based schemes (P3) over category-based ones. Milbrandt supervised and provided the expertise.
- **Melting-snow valley flow (Thériault et al. 2015; ~12 citations)** — semi-idealized 2D WRF of the Whistler/Callaghan Valley 2010 Olympics case; melting-induced cooling is necessary and sufficient for valley-flow reversal, robust across MY2, Thompson, and bin schemes. Builds on the 1D companion Milbrandt et al. (2014). Milbrandt provided MY2 (the control scheme) and snow-melting expertise.

### 4.11 Operational precipitation-type prediction (Tier 2)

- **Freezing-rain diagnosis and fix (Barszcz et al. 2018; ~17 citations)** — identifies excessive rain–graupel collisional freezing in MY2 as the cause of HRDPS freezing-rain *under*prediction; the −5°C threshold fix was implemented operationally. Milbrandt co-supervised and provided microphysics interpretation. (Pairs with Cholette et al. 2024, which addresses the opposite *over*prediction bias.)
- **Predicted graupel density in WDM6 (Park et al. 2024; ~4 citations)** — an independent Korean group ports the Milbrandt & Morrison (2013) density-prediction method into WRF's WDM6 scheme and validates against ICE-POP 2018. Demonstrates the broad adoptability of Milbrandt's density-prediction concept beyond his own schemes. Milbrandt is senior international co-author / originator of the method.

### 4.12 Applied mesoscale NWP — the starting point (2001)

**The Saguenay flood study (Milbrandt & Yau 2001)** — predating the microphysics focus, used MC2 with piecewise PV inversion and factor-separation experiments to decompose the 1996 Saguenay extreme cyclone/precipitation event (upper-level dynamics ~47%, latent heating ~41%, surface baroclinicity ~12%, orography ~24% of regional precipitation). Establishes the tools, collaborator, and applied motivation from which the microphysics program grew. (Citation count not retrieved ⚠ verify.)

---

## 5. Per-Article Contributions — Tier 1 & 2 (chronological)

| Year | Paper (stem) | Tier | One-line contribution | Citations¹ |
|------|--------------|------|-----------------------|-----------|
| 2001 | `Milbrandt_Yau_2001` | T1 | MC2 simulation + PV-inversion/factor-separation diagnosis of the 1996 Saguenay flood. | n/a |
| 2005a | `Milbrandt_Yau_2005a` | T1 | **MY Part I** — theory of the shape parameter $\alpha$; size-sorting & source-term errors; scheme-skill hierarchy; diagnostic $\alpha=f(D_m)$. | ~665 |
| 2005b | `Milbrandt_Yau_2005b` | T1 | **MY Part II** — three-moment closure (predicted reflectivity); full six-category scheme. | ~556 |
| 2006a | `Milbrandt_Yau_2006a` | T1 | **MY Part III** — first 3D three-moment simulation (Pine Lake hailstorm); $N_h^*/R_h^*$ hail diagnostics. | ~62 |
| 2006b | `Milbrandt_Yau_2006b` | T1 | **MY Part IV** — sensitivity tests; one→two moment is the dominant gain; only 3-moment captures max hail size. | ~84 |
| 2008 | `Milbrandt_etal_2008` | T1 | **IMPROVE-2 Part I** — first aircraft validation of MY; realistic sizes, overpredicted snow mass; no leeside overprediction. | ~40 |
| 2010 | `Milbrandt_McTaggart-Cowan_2010` | T1 | **Sedimentation errors** — ranks all moment configs; standard 2-moment fails; proposes diagnostic-$m$ / $V_k/V_j$ fixes. | ~110 |
| 2010 | `Milbrandt_etal_2010` | T1 | **IMPROVE-2 Part II** — scheme identity > moment count for orographic case; leeside-overprediction mechanism. | ~52 |
| 2011 | `Morrison_Milbrandt_2011` | T2 | **MOR vs MY intercomparison** — graupel-vs-hail is the dominant inter-scheme difference; schemes don't converge. | ~210 |
| 2012 | `Milbrandt_etal_2012_snowmelting` (=PAAG) | T1 | **1D snow melting** — partial-melting limitation of bulk schemes; 1D forecaster tool. | ~15 |
| 2012 | `Milbrandt_etal_2012_snowdensity` | T1 | **Snow-to-liquid ratio** — first explicit SLR from a bulk scheme; new MY2 snow updates; Vancouver 2010 deployment. | ~26 |
| 2013 | `Milbrandt_Morrison_2013` | T1 | **Prognostic graupel density** — adds $B_g=q_g/\rho_g$; density-dependent fall speeds; the bridge to P3. | ~62 |
| 2014 | `Chosson_etal_2014` | T2 | **Scale-adaptive MY2** — subgrid cloud/precip fraction + sub-time-stepping; MY2 usable at coarse resolution. | ~29 |
| 2015 | `Theriault_etal_2015` | T2 | **Melting-snow valley flow** — melting cooling necessary & sufficient for valley-flow reversal; MY2 control. | ~12 |
| 2015 | `Morrison_Milbrandt_2015a` | T1 (co-lead) | **P3 Part I** — single free ice category, 4 prognostic vars; properties evolve freely; idealized tests. | ~511 |
| 2015 | `Morrison_etal_2015b` | T1 (co-lead) | **P3 Part II** — 3D WRF vs. obs & 8 schemes; correct convective leading edge & orographic distribution; efficient. | ~211 |
| 2016 | `Milbrandt_Morrison_2016` | T1 | **P3 Part III** — multiple free categories; ends property dilution; first multi-free-category scheme. | ~131 |
| 2016 | `Milbrandt_etal_2016` | T1 | **HRDPS** — description/verification of Canada's operational 2.5-km system (GEM+MY2). | ~152 |
| 2018 | `Barszcz_etal_2018` | T2 | **Freezing-rain fix** — excess rain–graupel collisional freezing; −5°C threshold deployed operationally. | ~17 |
| 2019 | `Cholette_etal_2019` | T2 | **P3 liquid fraction** — adds $q_{i,liq}$; explicit wet snow & ice pellets in P3. | ~28 |
| 2019 | `Jouan_Milbrandt_2019` | T2 | **CCN & ice-phase** — CCN response acts through graupel riming; supports property-based schemes. | ~11 |
| 2020 | `Jouan_etal_2020` | T2 | **P3 for global NWP** — SCPF applied to P3 at 25 km; path to unified ECCC microphysics. | ~14 |
| 2021 | `Milbrandt_etal_2021` | T1 | **Triple-moment ice in P3** — adds $Z_{i,tot}$; $\mu$ free; physical size-sorting control; better hail. | ~46 |
| 2023 | `Cholette_etal_2023` | T2 | **3MOM + LF in P3** — combined upgrades; stronger cold pools, bright band; operational HRDPS config. | ~13 |
| 2024 | `Park_etal_2024` | T2 | **Predicted density in WDM6** — independent port of MM2013 density method to WRF/WDM6; ICE-POP validation. | ~4 |
| 2024 | `Cholette_etal_2024` | T2 | **SIP for freezing rain** — Hallett–Mossop + 2 categories cuts FR bias up to 98%; matches Bourgouin. | ~8 |
| 2025 | `Cholette_etal_2025` | T2 | **Wet snow (orographic)** — first 3D NWP eval of P3 LF for wet snow vs. ICE-POP 2018. | 0 |
| 2025 | `Milbrandt_etal_2025` | T1 | **P3 hail** — LF (smaller hail) vs. multi-category (larger hail); `LF-2CAT` represents full hail lifecycle. | ~1 |

¹ Semantic Scholar, retrieved 2026-05-25 (Parts I–II) and 2026-06-06 (all others); approximate, recheck before citing.

**Combined summaries:** `Milbrandt_Yau_2005ab-summary.md` (Parts I & II), `Milbrandt_Yau_2006ab-summary.md` (Parts III & IV), and `Morrison_Milbrandt_2015_2016-P3-summary.md` (P3 Parts I–III) treat each natural series as a unit.

---

## 6. Synthesis: Significance of the Tier 1 & 2 Work

Across the lead and key-author corpus, a single, coherent, and influential research program emerges, organized around the through-line of Section 2.

**The MY scheme (2005–2006)** is among the most widely adopted multimoment bulk microphysics parameterizations developed in the 2000s — implemented in WRF, in ECCC's operational HRDPS (2014–~2021, before the P3 transition), and in GEM-MACH, and used as a reference scheme in numerous community intercomparisons (e.g., Fan et al. 2017; Han et al. 2019; Johnson et al. 2019). Parts I and II together exceed 1,200 citations and are standard references for the field; Parts III and IV document real-world behavior and provide durable guidance on the complexity–cost trade-off. The recurring scientific theme — that the *shape* of the PSD, not just its mass and number, governs precipitation and storm behavior — both established Milbrandt's reputation and seeded all subsequent work.

**The validation and theory phase (2008–2010)** confronted MY with in-situ aircraft data (IMPROVE-2), confirming the multimoment thesis observationally while exposing the specific deficiencies (overpredicted snow mass, rigid ice categories) that motivated later refinements; the sedimentation paper (~110 citations) generalized the Part I theory into an actionable toolkit for any two-moment scheme.

**The benchmarking-and-modernization phase (2011–2013)** is the conceptual hinge of the career. The 2011 intercomparison *diagnosed* the dominant ice-phase uncertainty (graupel vs. hail); the 2012 snow papers and the 2013 graupel-density paper *fixed* the most rigid ice assumptions and explicitly named the "paradigm shift toward adding physical degrees of freedom" that P3 then realized for all ice particles. The SLR work also marks Milbrandt's first operational deployment of a new scheme feature (Vancouver 2010).

**The P3 scheme (2015–2016)** is the culmination and his most highly cited contribution (Part I alone ~511). It replaces predefined ice categories and their artificial conversions with continuously evolving particle properties (Part I), demonstrates superior, computationally efficient performance against observations and other schemes (Part II), and extends to multiple coexisting free categories (Part III). The physical formulation descends directly from the 2013 graupel-density work ($B_{rim}$ generalizes $B_g$).

**The modern extension phase (2019–2025)** systematically adds back the capabilities that the original property-predicting framework lacked, without reintroducing fixed assumptions: triple-moment ice (2021) for size sorting and hail; predicted liquid fraction (Cholette series) for mixed-phase particles and explicit surface precipitation type; and the combined hail study (2025). In parallel, the **operationalization thread** (HRDPS 2016; Chosson 2014; Jouan 2020; McTaggart-Cowan 2019) carries these schemes from research into daily forecasting across model scales, with the explicit goal of unifying ECCC's microphysics on P3. The two Tier 2 process studies (CCN sensitivity 2019; valley-flow 2015) and the two precipitation-type papers (Barszcz 2018; Park 2024) show the schemes being used as research instruments and adopted by other groups.

The early Saguenay paper (2001) is not central to the microphysics legacy but is valuable context: the tools, collaborator, and applied motivation from which everything else grew.

---

## 7. Authorship Tiers — How to Represent Credit

This document and its source summaries use a three-tier system to keep attributions of intellectual ownership accurate. **Respect it when writing about Milbrandt's work.**

- **Tier 1 — Lead contributor.** First author, or co-first where Milbrandt drove the science on equal footing (e.g., P3 Parts I & II, where Morrison's first authorship is nominal). Full intellectual ownership. *Language:* "Milbrandt developed / led / introduced."
- **Tier 2 — Key co-author.** Substantive intellectual contribution (co-designed the study, supervised the lead researcher, or provided central domain expertise) but not the primary driver. *Language:* "Milbrandt co-developed / co-supervised / contributed the scheme and guided."
- **Tier 3 — Contributing co-author.** Real but supporting role: provided his scheme, ran a model, supplied data, or reviewed. *Language:* "Milbrandt provided the MY/P3 scheme for / contributed expertise to." **Do not** say he "developed" or "led" Tier 3 work.

Sections 1–6 cover Tier 1 & 2. Section 8 covers Tier 3.

---

## 8. Related Contributions (Tier 3)

The 38 papers below are works in which Milbrandt was a **contributing co-author**: his role was to supply his microphysics scheme (MY2 or P3), run or support the GEM/HRDPS modeling component, provide cloud-physics domain expertise, or review the manuscript — **not** to drive the intellectual direction. They reflect his standing as a **microphysics scheme provider and domain expert sought out by other research groups**, both within ECCC and internationally, rather than as a primary investigator. They are grouped thematically; within each group, papers are listed with first author, year, venue, citation count (Semantic Scholar, retrieved 2026-06-06 unless noted), and Milbrandt's specific contribution. Full per-paper summaries are in `wiki/summaries/`.

### 8.1 Microphysics scheme intercomparisons and process studies (9 papers)

Milbrandt's MY2 and/or P3 schemes served as reference schemes in multi-scheme intercomparisons, or his schemes and expertise supported process studies led by others. This is the largest Tier 3 cluster and the clearest evidence of his schemes' role as community tools.

- **Fan et al. (2017)**, *JGR Atmos.*, ~144 — MC3E squall-line cloud-resolving model intercomparison, Part I (convective updrafts); MY2 one of eight schemes.
- **Han et al. (2019)**, *JGR Atmos.*, ~65 — companion Part II (stratiform precipitation); MY2 and P3 among the eight schemes.
- **Johnson et al. (2019)**, *MWR*, ~14 — effects of rimed-ice representation on polarimetric signatures; MY2 and P3 are the primary schemes evaluated. (First identified P3's hail-signature weakness later addressed by Milbrandt et al. 2021, 2025.)
- **Dawson et al. (2016)**, *JAS*, ~20 — buoyancy/dynamic-pressure analysis of the 3 May 1999 OKC tornadic supercell; MY multimoment scheme provided for the simulations.
- **Jensen et al. (2017)**, *JAS*, ~88 — predicting ice-shape evolution (the ISHMAEL scheme); P3 and the 2013 graupel-density paper are key precursors; Milbrandt contributed scientific guidance.
- **Morrison et al. (2016)**, *MWR*, ~17 — advection of coupled hydrometeor quantities (the SFVT method); developed/tested with the P3 and MY schemes Milbrandt provided. (Source of the advected-variable guidance used in Milbrandt et al. 2021.)
- **Paukert et al. (2019)**, *JAMES*, ~38 — three-moment rain representation, developed and tested within the P3 framework Milbrandt provided.
- **Stanford et al. (2019)**, *JAMES*, ~19 — stochastic ice-microphysics framework built on P3; Milbrandt contributed as scheme developer.
- **Morrison et al. (2020)**, *JAMES*, ~378 — major community review, "Confronting the challenge of modeling cloud and precipitation microphysics"; Milbrandt contributed bulk-scheme (P3/MY) expertise. (Highest-cited Tier 3 paper.)

### 8.2 Secondary ice production, HIWC, and mixed-phase cloud observations (4 papers)

Studies — largely tied to ECCC's Convair-580 aircraft and the HAIC-HIWC campaign — of secondary ice production (SIP), high ice water content, and mixed-phase cloud structure, where Milbrandt provided microphysics expertise and his schemes for the modeling components.

- **Korolev et al. (2020)**, *ACP*, ~122 — environmental conditions favorable to secondary ice production; Milbrandt contributed cloud-microphysics expertise (Convair-580 campaign context ⚠ verify aircraft role).
- **Korolev & Milbrandt (2022)**, *GRL*, ~50 — "How are mixed-phase clouds mixed?"; Milbrandt co-contributed to conceptualization, methodology, and writing (data/analysis led by Korolev).
- **Huang et al. (2021)**, *ACP*, ~21 — microphysical processes producing high ice water contents in tropical convection (HAIC-HIWC); P3 one of four schemes evaluated.
- **Qu et al. (2022)**, *ACP*, ~32 — impacts of SIP on tropical-convection microphysics and dynamics; Milbrandt co-conceptualized and co-designed experiments and provided P3/GEM expertise. *(Borderline Tier 2/3 — author-contributions statement notes co-conceptualization; retained as Tier 3.)*

### 8.3 Coupled air-quality / weather modeling — GEM-MACH (4 papers)

Milbrandt provided the MY2 (and later P3) cloud-microphysics component of ECCC's online coupled air-quality model GEM-MACH and the related AQMEII intercomparisons.

- **Gong et al. (2015)**, *Atmos. Environ.*, ~77 — aerosol–cloud–meteorology interaction in fully coupled GEM-MACH; MY double-moment scheme provided.
- **Makar et al. (2015a)**, *Atmos. Environ.*, ~137 — feedbacks between air pollution and weather, Part 1 (effects on weather); GEM-MACH microphysics (MY2) component, AQMEII-2.
- **Makar et al. (2015b)**, *Atmos. Environ.*, ~128 — companion Part 2 (effects on chemistry); same supporting role.
- **Makar et al. (2021)**, *ACP*, ~26 — forest-fire aerosol–weather feedbacks; advised on integrating the aerosol indirect effect within the P3 scheme.

### 8.4 Winter Olympics and WWRP nowcasting / field projects (8 papers)

Milbrandt provided and supported the high-resolution GEM-LAM / HRDPS NWP component (using MY2 microphysics) for a series of World Weather Research Programme field projects and Olympic forecast demonstration projects.

- **Isaac et al. (2012)**, *Pure Appl. Geophys.*, ~64 — SNOW-V10, the Vancouver 2010 Olympics nowcasting project; contributed GEM-LAM NWP capability and microphysics.
- **Mailhot et al. (2012)**, *Pure Appl. Geophys.*, ~47 — the experimental high-resolution forecast system for Vancouver 2010; contributed the MY2 scheme and the SLR diagnostic.
- **Mo et al. (2012)**, *Pure Appl. Geophys.*, ~20 — mid-mountain clouds at Whistler during Vancouver 2010; MY2 used in all nested GEM-LAM configs.
- **Thériault et al. (2012)**, *WAF*, ~22 — processes impacting precipitation phase/intensity during Vancouver 2010; provided MY2 for all GEM-LAM configs.
- **Kiktev et al. (2017)**, *BAMS*, ~19 — FROST-2014, the Sochi Winter Olympics project; provided GEM-LAM at 2.5/1/0.25 km.
- **Joe et al. (2020)**, *BAMS*, citation pending (rate-limited) — Canadian Arctic Weather Science project (Iqaluit); contributed HRDPS/GEM NWP expertise.
- **Joe et al. (2025)**, *BAMS*, 0 (recent) — insights from WWRP nowcasting/mesoscale working-group projects; contributed high-resolution NWP expertise (Vancouver 2010 context ⚠ verify).
- **Taylor et al. (2011)**, *BAMS*, ~25 — the UNSTABLE 2008 severe-thunderstorm/boundary-layer experiment (Alberta); provided the 1-km GEM-LAM with MY2 and NWP support.

### 8.5 Fog, visibility, and instrumentation (6 papers)

Collaborations (chiefly with I. Gultepe and F. Boudala) on fog, ice fog, visibility parameterization, and surface-instrument evaluation, where Milbrandt contributed NWP/GEM context, the MY scheme, or manuscript review.

- **Gultepe & Milbrandt (2007)**, *Pure Appl. Geophys.*, ~108 — warm-fog microphysics + MC2 simulation (FRAM); ran the MC2 model with the MY triple-moment scheme to demonstrate a new fog-visibility parameterization.
- **Gultepe & Milbrandt (2010)**, *JAMC*, ~77 — probabilistic visibility parameterizations; contributed NWP/GEM context (observational analysis led by Gultepe).
- **Gultepe et al. (2014)**, *BAMS*, ~83 — ice fog in the Arctic (FRAM–Ice Fog); contributed GEM context and the MY scheme for the ice-fog prediction section.
- **Boudala et al. (2021)**, *Remote Sensing*, ~9 — performance of surface visibility/ceiling/humidity instruments (Cold Lake); writing review/editing only.
- **Boudala et al. (2022)**, *Remote Sensing*, ~7 — evaluation of CanESM cloud/cloud-radiative-forcing climatologies vs. CALIPSO-GOCCP/CERES; writing review/editing only.
- **Boudala & Milbrandt (2023)**, *Remote Sensing*, ~1 — solid precipitation and visibility measurements (CARE & Bratt's Lake); writing review/editing only.

### 8.6 Operational NWP system development, modernization, and evaluation (5 papers)

Papers documenting or evaluating ECCC's GEM/HRDPS forecast systems, where Milbrandt contributed the microphysics component (MY2 → P3) and related expertise.

- **McTaggart-Cowan et al. (2019)**, *JAMES*, ~74 — modernization of atmospheric physics in Canadian NWP; documents the P3 scheme replacing MY2 in HRDPS. (Key reference for the operational MY2→P3 transition.)
- **Ritchie et al. / "RPN report" (2022)**, *Atmosphere-Ocean*, ~3 — invited review of RPN's contributions to NWP; contributed the microphysics-parameterization sections (MY2, P3, HRDPS).
- **Mo et al. (2019)**, *WAF*, ~31 — hydrometeor drift in orographic precipitation (atmospheric rivers, BC); documents an MY2 bias and the P3 improvement for orographic spillover; provided both schemes.
- **Qu et al. (2018)**, *QJRMS*, ~16 — evaluation of GEM's simulated clouds vs. CloudSat/GOES-13/aircraft; provided the MY scheme and microphysics interpretation.
- **Qu et al. (2020)**, *ACP*, ~15 — simulated convective moistening of the extratropical lower stratosphere; provided GEM/MY2 infrastructure and expertise.

### 8.7 Winter precipitation phase and type (2 papers)

Collaborations on simulating winter precipitation type, an application directly enabled by his schemes' explicit ice-phase / liquid-fraction capabilities.

- **Thériault et al. (2006)**, *JGR*, ~65 — simulation of winter precipitation types; provided the MY (2005) double-moment scheme as the model foundation (McGill, supporting Thériault's thesis).
- **Cholette et al. (2020)**, *MWR*, ~11 — impacts of predicting liquid fraction on the 1998 North American Ice Storm; provided the P3 scheme code base and microphysics expertise (study led by Cholette/Thériault). *(Companion to the Tier 2 Cholette liquid-fraction series in Section 4.8.)*

---

## 9. Inventory and Coverage Tracker

**Total processed: 68 papers** — 30 Tier 1/2 (counting combined-series summaries) + 38 unique Tier 3. All papers in scope are processed; see `STATUS.md` for the authoritative inventory, duplicate-PDF resolutions, and the one omitted paper (`Vionnet_etal_2022`).

**Tier 1 & 2 (covered in Sections 1–6):** `Milbrandt_Yau_2001` · `Milbrandt_Yau_2005a` · `Milbrandt_Yau_2005b` · `Milbrandt_Yau_2006a` · `Milbrandt_Yau_2006b` · `Milbrandt_etal_2008` · `Milbrandt_McTaggart-Cowan_2010` · `Milbrandt_etal_2010` · `Morrison_Milbrandt_2011` · `Milbrandt_etal_2012_snowmelting` (=PAAG) · `Milbrandt_etal_2012_snowdensity` · `Milbrandt_Morrison_2013` · `Chosson_etal_2014` · `Theriault_etal_2015` · `Morrison_Milbrandt_2015a` (P3 I) · `Morrison_etal_2015b` (P3 II) · `Milbrandt_Morrison_2016` (P3 III) · `Milbrandt_etal_2016` · `Barszcz_etal_2018` · `Cholette_etal_2019` · `Jouan_Milbrandt_2019` · `Jouan_etal_2020` · `Milbrandt_etal_2021` · `Cholette_etal_2023` · `Park_etal_2024` · `Cholette_etal_2024` · `Cholette_etal_2025` · `Milbrandt_etal_2025`

**Tier 3 (covered in Section 8):** all 38 papers listed in Section 8.1–8.7.

**Notes:**
- `Milbrandt_etal2012_PAAG.pdf` and `Milbrandt_etal_2012-1Dsnowmelting.pdf` are the same paper (DOI 10.1007/s00024-012-0552-y); `Milbrandt_etal_2012_snowmelting-summary.md` is authoritative.
- `Gultepe_BAMS_14` and `Gultepe_etal_2014_BAMS` are the same paper (counted once).
- `Milbrandt et al. (2014)` (the 1D snow-melting/precip-phase model) is referenced by Thériault et al. (2015) and P3 Part III but is not a separate summary file in this corpus.

---

## 10. Open Items and Placeholders for Future Additions

This is a living document. When new material is added, append it in the appropriate section, update the Section 5 table and the Section 9 inventory, and revise the Section 6 synthesis if the arc changes.

- **Conference presentations / invited talks** — *(placeholder; none catalogued yet)*.
- **New papers (post-2025)** — add to Section 5 (Tier 1/2) or Section 8 (Tier 3) and to `STATUS.md`.
- **Outstanding `⚠ verify` items to resolve against a source:**
  - Exact deployment date of the `3MOM_LF` operational P3 configuration in HRDPS (Cholette et al. 2023).
  - Whether P3 is implemented in E3SM (and the current operational P3 version number / "v5" label).
  - Milbrandt's specific role (aircraft / Convair-580) in the Korolev et al. (2020) SIP campaign.
  - Milbrandt's specific contribution to Joe et al. (2025).
  - `Milbrandt_Yau_2001` citation count (not retrieved; Semantic Scholar lookup needed).
  - Confirm whether Qu et al. (2022) warrants Tier 2 (co-conceptualization noted in author-contributions statement).

*Last full revision: 2026-06-06 — extended from 14-paper draft to complete 68-paper coverage (all Tier 1/2 through 2025 + thematic Tier 3 section).*
