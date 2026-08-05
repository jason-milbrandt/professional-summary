# Summary: Han et al. (2019)

**Full citation:** Han, B., Fan, J., Varble, A., Morrison, H., Williams, C. R., Chen, B., Dong, X., Giangrande, S. E., Khain, A., Mansell, E., Milbrandt, J. A., Shpund, J., and Thompson, G. (2019): Cloud-resolving model intercomparison of an MC3E squall line case: Part II. Stratiform precipitation properties. *Journal of Geophysical Research: Atmospheres*, **124**. DOI: 10.1029/2018JD029596
**Journal:** Journal of Geophysical Research: Atmospheres
**Year:** 2019
**Authors:** Bin Han, Jiwen Fan, Adam Varble, Hugh Morrison, Christopher R. Williams, Baojun Chen, Xiquan Dong, Scott E. Giangrande, Alexander Khain, Edward Mansell, Jason A. Milbrandt, Jacob Shpund, Gregory Thompson
**DOI:** 10.1029/2018JD029596
**Author's role:** Tier 3 — Contributing co-author; the MY2 scheme (Milbrandt–Yau two-moment) and P3 scheme were included as two of the eight microphysics schemes intercompared; Milbrandt's contribution was providing these schemes and their underlying science

---

## Overview

This paper is Part II of a cloud-resolving model intercomparison study using WRF with eight different microphysics schemes (including MY2 and P3) to simulate a well-observed midlatitude squall line from the MC3E field campaign. The focus is on stratiform precipitation properties, following Part I (Fan et al., 2017) which examined convective properties. The study finds that most schemes underestimate total stratiform precipitation primarily due to underestimation of stratiform precipitation area, and identifies convective condensate detrainment as the dominant driver of inter-scheme variability in stratiform precipitation.

## Context and Motivation

Underestimation of stratiform precipitation has been a long-standing problem in cloud-resolving models, but the causes were not well understood. Previous intercomparison studies used different models, making it difficult to attribute differences to specific microphysics factors. This study uses a single dynamical framework (WRF) while varying only the microphysics scheme, enabling cleaner attribution of stratiform biases and spread. The MC3E case provides exceptionally comprehensive multi-platform observations (disdrometers, vertical profiling radars, aircraft in situ, NEXRAD retrievals) for evaluation.

## Key Scientific Contributions

- Demonstrates that most schemes underestimate stratiform precipitation area — not just rain rate — as the primary cause of underestimated total stratiform precipitation
- Identifies low-biased ice number and mass concentrations for 0.2–2 mm diameter particles just above the melting level as the likely cause of underestimated moderate (2–6 mm/hr) rain rates
- Shows that simulated IWC decreases approaching the melting level, opposite to the observed increase — a robust, scheme-independent bias
- Demonstrates that convective condensate detrainment flux is the dominant driver of inter-scheme variability in stratiform precipitation area (correlation coefficient = 0.78)
- Quantifies the sensitivity of stratiform precipitation area to lateral boundary condition update frequency: increasing from 3-hr to 1-hr updates increases stratiform area by ~17–25%
- Shows that two-moment schemes outperform single-moment (WSM6), but bin schemes do not clearly outperform two-moment schemes for this ice-microphysics-dominated case

## Methods Summary

WRF-ARW v3.4.1 with four nested domains; innermost domain at 1-km horizontal resolution. Eight schemes: MORR (two-moment), MY2 (two-moment), WSM6 (one-moment), FSBM (bin), NSSL (two-moment), P3 (two-moment), THOM (hybrid), and FSBM_NEW (modified bin). One-way nesting with lateral boundary conditions every 3 hr from the outer domain. The MC3E squall line event of 20 May 2011 over the ARM SGP site in Oklahoma. Stratiform columns identified by rain rate threshold (1–15 mm/hr) rather than reflectivity-based methods to avoid artifacts from potentially biased simulated reflectivities.

## Key Results

- Most simulations underestimate total stratiform precipitation; stratiform precipitation area is underestimated by all schemes at the 3-hr boundary condition update frequency
- MY2 and P3 produce the largest mean stratiform rain rates (exceeding observed at 6–10 mm/hr); WSM6 and FSBM show low biases in large raindrop concentrations
- IWC is overestimated above 7 km by most schemes but underestimated just above the melting level — simulated IWC decreases toward the melting level while observed IWC increases
- Stratiform precipitation properties vary by a factor of ~1.5 across schemes; variability is primarily driven by variability in ice mass flux above the melting level
- MY2 produces the largest rimed particle amounts with fast fall speeds; P3 shows a realistic transition from unrimed ice aloft to rimed particles near the melting level
- Updating lateral boundary conditions every 1 hr (vs. 3 hr) increases stratiform area by 17–25% for MORR, NSSL, and P3

## Limitations and Caveats

- Single case study; generality of results to other MCS events is not established
- NEXRAD IWC retrievals have uncertain validity at temperatures warmer than −12°C due to aggregation effects on reflectivity–IWC relationships
- Parsivel disdrometers have known biases (low bias for small drops, high bias for large drops)
- The 3-hr boundary condition update frequency may itself introduce artificial underestimation of stratiform area independent of microphysics
- TAMU bulk scheme excluded due to unrealistic graupel size/fall speed in the stratiform region

## Relation to Author's Research Program

Milbrandt's MY2 (Milbrandt–Yau two-moment) and P3 schemes are two of the eight schemes evaluated in this intercomparison. The study provides an external, observationally-constrained evaluation of these schemes in a realistic MCS environment. The results show that MY2 and P3 produce among the largest stratiform rain rates and ice mass fluxes — a consequence of their realistic representation of rimed ice particles and fall speeds. P3's physically-based prediction of rime fraction allows a realistic vertical transition in ice type near the melting level, which the study identifies as a key factor in stratiform precipitation performance. This paper documents how Milbrandt's schemes perform relative to peers in a high-profile intercomparison, contributing to the broader evidence base for the scientific community's adoption of these schemes.

## Impact and Citations

**Citation count:** ~65 (Semantic Scholar, retrieved 2026-06-06)

This paper is the companion to Fan et al. (2017), which garnered ~144 citations. Together the two parts constitute a comprehensive CRM intercomparison study for the MC3E field campaign, providing community benchmark results for microphysics scheme evaluation. The paper's finding that stratiform precipitation area — not just rain rate — is the primary source of underestimation has influenced subsequent MCS modeling studies. The quantification of boundary condition update frequency sensitivity is a notable methodological contribution that has been cited in follow-on evaluation studies.
