# Summary: Dawson et al. (2016)

**Full citation:** Dawson, D.T. II, M. Xue, A. Shapiro, J.A. Milbrandt, and A.D. Schenkman, 2016: Sensitivity of Real-Data Simulations of the 3 May 1999 Oklahoma City Tornadic Supercell and Associated Tornadoes to Multimoment Microphysics. Part II: Analysis of Buoyancy and Dynamic Pressure Forces in Simulated Tornado-Like Vortices. *J. Atmos. Sci.*, **73**, 1039–1065. DOI: 10.1175/JAS-D-15-0114.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2016
**Authors:** Daniel T. Dawson II, Ming Xue, Alan Shapiro, Jason A. Milbrandt, Alexander D. Schenkman
**DOI:** 10.1175/JAS-D-15-0114.1
**Author's role:** Tier 3 — Provided the Milbrandt–Yau (MY) multimoment microphysics scheme used in the simulations; the intellectual leadership in the tornado dynamics analysis was from the University of Oklahoma group (Dawson, Xue, Shapiro)

---

## Overview

This is Part II of a two-part study examining how single- versus triple-moment bulk microphysics affects real-data simulations of the 3 May 1999 Oklahoma City tornadic supercell. The paper focuses on the vertical momentum budget of simulated tornado-like vortices (TLVs), showing that triple-moment microphysics produces larger raindrops, less evaporative cooling, weaker cold pools, and substantially stronger/longer-lived tornadoes. A novel finding is that pressure buoyancy within the TLV itself plays a critical positive role in TLV intensification, compensating for slight negative thermal buoyancy in the triple-moment case.

## Context and Motivation

The thermodynamic characteristics of tornado inflow air — particularly the degree of negative buoyancy from cold-pool outflow — are known to influence tornadogenesis and intensity, but quantitative momentum budget analyses had not been performed in realistic data-driven simulations. Part I (Dawson et al. 2015) established that higher-moment microphysics produces weaker cold pools and stronger TLVs. Part II diagnoses the physical mechanisms responsible, using trajectory analysis and buoyancy decomposition.

## Key Scientific Contributions

- Demonstrated that triple-moment microphysics (MY3) produces larger rain drops (O(3 mm) vs. O(1 mm) in MY1A), reducing evaporative cooling and allowing warmer outflow and stronger TLVs in real-data simulations.
- Provided the first quantitative vertical momentum budget analysis for tornado-like vortices in realistic (real-data) simulations, decomposing buoyancy into thermal, pressure, and dynamic components.
- Showed that pressure buoyancy — arising from strong negative pressure perturbations within the TLV core — is a critical positive contributor to upward acceleration inside tornadoes, a term previously under-emphasized in tornado dynamics studies.
- Used trajectory analysis to distinguish inflow air origins: MY3 TLV fed predominantly by environmental inflow with minor cooling; MY1A TLV fed by strongly cooled descending outflow air.
- Corroborated earlier observational studies (Markowski et al. 2002, 2003) finding that weaker cold pools (warmer outflow) are associated with stronger/longer-lived tornadoes.

## Methods Summary

ARPS model with triply nested grids (3-km, 1-km, 250-m). Radar data assimilation on 1-km grid. 250-m free forecasts initialized at 2305 UTC, ~20 min before observed F5 tornado onset. Two microphysics configurations: MY1A (single-moment, default Marshall–Palmer intercept) and MY3 (triple-moment). Backward/forward trajectory analysis; vertical momentum decomposition into thermal buoyancy, pressure buoyancy, and dynamic VPPGA. Case: 3 May 1999 Oklahoma City F5 tornado.

## Key Results

- MY3 TLV: more intense, longer-lived, consistent with observed F5 tornado strength.
- MY1A TLV: weak, short-lived; strong negative thermal buoyancy from cold pool suppresses vortex stretching.
- In MY3: TLV inflow from largely unmodified environment; minor evaporative/melt cooling along trajectories.
- In MY1A: majority of inflow through deep descent with substantial evaporative and melt cooling.
- Pressure buoyancy (from TLV's own negative pressure perturbation) provides substantial positive upward acceleration — key for TLV maintenance in both cases, but decisive in MY3 where it overcomes slight negative thermal buoyancy.
- Dynamic VPPGA dominates vertical acceleration only in the lowest few hundred meters AGL.

## Limitations and Caveats

- Single-case study (3 May 1999); generalizability to other supercell/tornado archetypes requires further testing.
- 250-m grid spacing does not fully resolve internal TLV circulations (corner-flow region); results are for "tornado-like vortices," not fully resolved tornadoes.
- The source of vertical vorticity for the TLVs is deliberately not addressed — focus is solely on the vertical momentum budget.
- Part I and Part II together only compare two of four MY configurations (1M and 3M); the intermediate (2M) is not examined in Part II.

## Relation to Author's Research Program

Milbrandt is the developer of the Milbrandt–Yau multimoment scheme, which is the central tool in this study. His contribution was providing the MY scheme code and expertise; the tornado dynamics investigation, trajectory analysis, and buoyancy decomposition were led by the University of Oklahoma group. This paper is relevant to Milbrandt's work as one of the most prominent demonstrations of the impact of multimoment microphysics on convective storm simulation — specifically, showing that triple-moment (MY3) dramatically outperforms single-moment (MY1A) in simulating a major tornado event. The paper is frequently cited as evidence of the value of higher-moment microphysics for severe convective weather ⚠ verify.

## Impact and Citations

**Citation count:** ~20 (Semantic Scholar, retrieved 2026-06-06)

With 20 citations since 2016, the paper has had solid uptake in the storm dynamics and NWP microphysics communities. It is one of the most thorough analyses of the mechanism by which multimoment microphysics improves tornado simulation, and the pressure buoyancy finding is a notable contribution to tornado dynamics understanding. The companion Part I paper (Dawson et al. 2015) likely has higher citation counts ⚠ verify.

## Related topics
- [[scheme-intercomparisons]]
