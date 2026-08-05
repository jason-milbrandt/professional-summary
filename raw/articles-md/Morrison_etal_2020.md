# Confronting the Challenge of Modeling Cloud and Precipitation Microphysics

**Full citation:** Morrison, H., M. van Lier-Walqui, A. M. Fridlind, W. W. Grabowski, J. Y. Harrington, C. Hoose, A. Korolev, M. R. Kumjian, J. A. Milbrandt, H. Pawlowska, D. J. Posselt, O. P. Prat, K. J. Reimel, S.-I. Shima, B. van Diedenhoven, and L. Xue, 2020: Confronting the challenge of modeling cloud and precipitation microphysics. *J. Adv. Model. Earth Syst.*, **12**, e2019MS001689. DOI: 10.1029/2019MS001689

**Authors:** Hugh Morrison and 15 co-authors (J. A. Milbrandt is 9th of 16)  
**Journal:** Journal of Advances in Modeling Earth Systems  
**Year:** 2020  
**Note:** Commissioned manuscript (invited review/perspective). 68 pages.

---

## Abstract

In the atmosphere, microphysics refers to the microscale processes that affect cloud and precipitation particles and is a key linkage among the various components of Earth's atmospheric water and energy cycles. The representation of microphysical processes in models continues to pose a major challenge leading to uncertainty in numerical weather forecasts and climate simulations. In this paper, the problem of treating microphysics in models is divided into two parts: (i) how to represent the population of cloud and precipitation particles, given the impossibility of simulating all particles individually within a cloud, and (ii) uncertainties in the microphysical process rates owing to fundamental gaps in knowledge of cloud physics. The recently developed Lagrangian particle-based method is advocated as a way to address several conceptual and practical challenges of representing particle populations using traditional bulk and bin microphysics parameterization schemes. For addressing critical gaps in cloud physics knowledge, sustained investment for observational advances from laboratory experiments, new probe development, and next-generation instruments in space is needed. Greater emphasis on laboratory work, which has apparently declined over the past several decades relative to other areas of cloud physics research, is argued to be an essential ingredient for improving process-level understanding. More systematic use of natural cloud and precipitation observations to constrain microphysics schemes is also advocated. Because it is generally difficult to quantify individual microphysical process rates from these observations directly, this presents an inverse problem that can be viewed from the standpoint of Bayesian statistics. Following this idea, a probabilistic framework is proposed that combines elements from statistical and physical modeling. Besides providing rigorous constraint of schemes, there is an added benefit of quantifying uncertainty systematically. Finally, a broader hierarchical approach is proposed to accelerate improvements in microphysics schemes.

---

## 1. The Problem of Representing Cloud and Precipitation Microphysics in Models

Microphysics refers to the physical and chemical processes occurring at the scale of individual cloud and precipitation particles (sub-micron to several centimeters). These include nucleation, diffusional growth, collision-coalescence, freezing, melting, and evaporation.

Microphysics schemes face two major challenges:
1. **Representation problem**: How to parameterize the population of hydrometeors in a model grid volume, given that it is computationally impossible to represent all hydrometeors individually even for small cloud volumes (~$10^{17}$ particles in a 1 km³ cloud)
2. **Process uncertainty**: Uncertainties in microphysical process rates owing to critical gaps in cloud physics knowledge — especially for ice-phase processes

Unlike turbulence (Navier-Stokes) and radiation (line-by-line), microphysics has no complete set of governing equations or benchmark model, and molecular-scale processes may be important for nucleation and ice growth.

---

## 2. A Brief History of Microphysics Scheme Developments

**Bulk schemes**: Predict one or a few variables describing bulk properties of cloud within a grid volume (mass, number). Computationally efficient. Two-moment schemes predict mass and number mixing ratios, allowing PSD shape to evolve. Multi-moment schemes (e.g., Milbrandt and Yau 2005; Morrison and Milbrandt 2015) predict additional moments or particle properties. Recent approaches (P3) use prognostic particle properties rather than fixed ice categories.

**Bin schemes**: Represent particle distributions explicitly over size bins. Many more degrees of freedom but computationally costly. Provide valuable benchmarks for bulk schemes.

**Lagrangian particle-based schemes**: Emerged in the early 21st century. The particle population is represented by discrete "super-particles," each representing a multitude of real particles following trajectories. Key conceptual advantage: as the number of super-particles approaches the number of actual particles and model resolution approaches DNS scales (~1 mm), the scheme converges to particle-by-particle DNS — providing a rigorous path toward numerical convergence not possible with bulk or bin approaches. Main limitation: computational cost.

Historical benchmark papers include: Marshall-Palmer (1948), Gunn-Marshall (1958), early bin schemes (Berry 1967; Hall 1980), first bulk schemes with multiple moments (Koenig-Murray 1976; Ziegler 1985; Ferrier 1994; Milbrandt-Yau 2005), and the P3 scheme (Morrison-Milbrandt 2015; Milbrandt-Morrison 2016).

---

## 3. Challenges in Parameterizing Cloud Microphysics

### 3.1 Representing particle populations (the "parameterization problem")

**Challenges with bulk schemes:**
- Assumption of analytic particle size distribution (PSD) functions (e.g., gamma) introduces uncertainty; the correct form is poorly known, especially for ice
- Higher-moment schemes improve PSD representation but add complexity, parameters, and computational cost
- Traditional ice category approaches (cloud ice, snow, graupel, hail) are physically arbitrary — PSDs overlap and particles transition between categories in ways that are difficult to represent
- The number and nature of ice categories is a source of substantial uncertainty

**Challenges with bin schemes:**
- Numerical diffusion in size space can artificially broaden DSDs
- High computational cost limits applicability
- In multi-dimensional models, the advection problem for many bins is numerically challenging

**Advantages of Lagrangian particle-based schemes:**
- No a priori assumption about PSD form
- Can track individual particle histories (composition, habit, riming history)
- Fundamental conceptual advantage: convergence to DNS as super-particles → real particles
- Challenges: computational cost; representation of collection processes (requires super-particle merging/splitting); treatment of turbulence; statistical sampling uncertainties with finite super-particles

### 3.2 Fundamental process-level knowledge gaps

Major gaps in cloud physics knowledge leading to scheme uncertainty:

**Ice nucleation:**
- Heterogeneous ice nucleation on aerosol particles (ice nucleating particles, INPs) is poorly understood; parameterizations are highly empirical
- Secondary ice production mechanisms (rime splintering, ice-ice collisions, drop fragmentation upon freezing, Wegener-Bergeron-Findeisen process) are even more poorly quantified

**Ice particle properties:**
- The enormous variety of ice particle shapes and their complex habit evolution make parameterizing vapor diffusion growth, fall speeds, and collision efficiencies very challenging
- Existing bulk parameterizations of these properties have large uncertainties

**Collision-coalescence:**
- Collection efficiencies for ice-ice, ice-water, and liquid-liquid collisions are uncertain
- Raindrop breakup parameterizations have significant uncertainties

**Warm microphysics:**
- Turbulent collision enhancement and supersaturation fluctuations in cloud droplet growth remain poorly quantified
- Autoconversion parameterizations are highly uncertain

---

## 4. Possible Paths Forward

### 4.1 Lagrangian particle-based schemes for representing populations

Lagrangian particle-based methods are advocated as the most promising path for representing hydrometeor populations. They have been implemented in LES (e.g., Shima et al. 2009, super-droplet method) and are becoming increasingly feasible. Expected to become a staple of cloud research modeling within the next decade.

Potential uses:
- Direct cloud physics research
- Developing and testing bulk schemes via systematic comparison
- Benchmarking bin schemes

### 4.2 Statistical-physical framework for constraining schemes

A major barrier: microphysical process rates generally cannot be obtained directly from natural cloud observations — only indirectly, by comparing model output with observations. This inverse problem is naturally viewed through Bayesian statistics.

**Proposed statistical-physical framework:**
- Physical constraints from cloud physics knowledge inform the model structure (physically based parameterizations)
- Bayesian inference (e.g., Markov Chain Monte Carlo) is used to constrain scheme parameters and structure using observations
- This provides rigorous observational constraint AND systematic uncertainty quantification
- Contrasts with traditional "physical" approach combined with heuristics and ad hoc tuning
- Related to "theory-guided data science" (Karpatne et al. 2017)

This framework sits between: (a) purely physical models requiring complete governing equations, and (b) "black box" machine learning approaches lacking physical constraints.

### 4.3 Laboratory experiments and field observations

- Laboratory experiments provide a direct way to quantify individual microphysical process rates in a controlled setting
- There has been an apparent decline in laboratory cloud physics work over recent decades — this needs to be reversed
- New probe development (airborne, ground-based) and next-generation space instruments needed for global constraints
- Multi-scale field campaigns that combine in situ, ground-based, and satellite observations are essential

---

## 5. Conclusions and Broader Outlook

The paper identifies two critical challenges and proposes paths forward:

**Challenge 1 (representation):** Lagrangian particle-based schemes are advocated as a promising long-term approach, while improved bulk schemes remain the near-term operational workhorses.

**Challenge 2 (process knowledge):** Sustained investment in laboratory experiments, new instruments, and Bayesian statistical-physical frameworks for scheme development.

**Six specific recommendations:**
1. Sustained support for laboratory facilities to study microphysical processes
2. Sustained support for new airborne and ground-based instrument development and next-generation space instruments
3. Increased emphasis on critical evaluation of model performance using field observations
4. Development of new frameworks for rigorous model evaluation and constraint by observations, leveraging statistical modeling tools
5. Increased focus on systematic quantification of parameter and structural uncertainty in schemes
6. Continued development and use of new methods for microphysical modeling, especially Lagrangian particle-based schemes

**Broader hierarchical approach:** The paper proposes a hierarchical approach connecting laboratory work → Lagrangian/bin detailed models → statistical-physical bulk scheme development → observational constraint via Bayesian inference → scheme evaluation, contrasting with the "traditional" approach of heuristics and ad hoc tuning.

[Figure 1: Schematic of microphysical processes in a cumulonimbus — image not reproducible in markdown]  
[Figure 2: Hierarchy of atmospheric models — image not reproducible in markdown]  
[Figures 3–17: Various schematic and analytical figures from the paper — images not reproducible in markdown]

---

## References

[This paper contains approximately 400 references spanning the full history of cloud microphysics research. Key references include Milbrandt and Yau (2005a,b), Morrison and Milbrandt (2015), Milbrandt and Morrison (2016), Milbrandt et al. (2016 WAF), and extensive literature on Lagrangian schemes, Bayesian methods, and cloud physics observations.]
