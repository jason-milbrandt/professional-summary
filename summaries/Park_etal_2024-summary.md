# Summary: Park et al. (2024)

**Full citation:** Park, S.-Y., K.-S. S. Lim, K. Kim, G. Lee, and J. A. Milbrandt, 2024: Introducing graupel density prediction in Weather Research and Forecasting (WRF) double-moment 6-class (WDM6) microphysics and evaluation of the modified scheme during the ICE-POP field campaign. *Geosci. Model Dev.*, **17**, 7199–7218. DOI: 10.5194/gmd-17-7199-2024
**Journal:** Geoscientific Model Development
**Year:** 2024
**Authors:** S.-Y. Park, K.-S. S. Lim, K. Kim, G. Lee, J. A. Milbrandt
**DOI:** 10.5194/gmd-17-7199-2024
**Author's role:** Tier 2 — Developer of the graupel density prediction methodology (Milbrandt and Morrison 2013) that the entire modified scheme is based on; provided the theoretical framework and domain expertise for the predicted-density approach applied to WDM6; last/senior international co-author from ECCC

---

## Overview

This paper introduces predicted graupel density into the WRF WDM6 double-moment microphysics scheme by adding a prognostic graupel volume mixing ratio, following the approach of Milbrandt and Morrison (2013). The predicted density allows the graupel fall velocity–diameter and mass–diameter relationships to evolve dynamically rather than using a fixed 500 kg m⁻³ constant. The modified WDM6 was evaluated in a 2D idealized squall line and eight winter snowfall events from the ICE-POP 2018 field campaign in South Korea. The key result is that predicted graupel density leads to faster sedimentation, reducing surface snow and the positive precipitation bias present in the original WDM6 over mountainous terrain.

## Context and Motivation

Bulk microphysics schemes traditionally use fixed density parameters for ice categories. For graupel, the choice of density strongly affects the fall velocity–diameter relationship and therefore sedimentation, accretion rates, and ultimately surface precipitation. WDM6 uses a fixed graupel density of 500 kg m⁻³, and several studies showed it produces excess graupel compared to other schemes. The Milbrandt and Morrison (2013) paper established the methodology for predicting bulk ice particle density via a prognostic volume mixing ratio, and this was later used as the foundation for the P3 scheme (Morrison and Milbrandt 2015). This paper applies that specific density-prediction approach to the WDM6 framework within WRF, allowing the community using WRF+WDM6 to benefit from physically evolving graupel density — motivated specifically by comparisons with ICE-POP 2018 observational data from South Korea.

## Key Scientific Contributions

- Successfully implemented predicted graupel density in WDM6 by adding a graupel volume mixing ratio $B_G$ as a sixth prognostic variable (extending an existing WDM6 version with prognostic cloud ice number concentration).
- Demonstrated that WDM6 with predicted density (WDM6_PD) reproduces the wide range of observed graupel densities (100–900 kg m⁻³) and fall velocities captured by 2DVD measurements during ICE-POP 2018, unlike the original WDM6 which uses a single value.
- Showed that the modified WDM6 alleviates the positive surface precipitation bias in the original WDM6 for both cold-low and warm-low snowfall cases during ICE-POP 2018, improving RMSE scores.
- Established the mechanism: lower predicted densities → faster sedimentation → less efficient graupel deposition aloft → surplus water vapor → more efficient snow deposition → redistribution of surface precipitation from mountains to surrounding areas.
- Provided a first comparison of simulated graupel characteristics ($\rho_G$–$V_G$ relationship) with combined 2DVD + MASC observational data during ICE-POP 2018.

## Methods Summary

The predicted density is implemented following Milbrandt and Morrison (2013): $\rho_G = q_G / B_G$, where $B_G$ is the bulk graupel volume mixing ratio. The $V_G$–$D$ and $M_G$–$D$ relationships are updated dynamically at the predicted $\rho_G$, using $V_G$–$D$ coefficients derived by least-squares fitting over $D = 0.3$–20 mm at $\rho_G$ intervals of 100 kg m⁻³. Testing employed: (1) a 2D idealized squall line (following Lim and Hong 2010 design), and (2) WRF v4.1.3 with three nested domains (9/3/1 km) for 8 ICE-POP 2018 winter snowfall cases. Experiments WDM6_FD and WDM6_PD were compared against AWS precipitation (604 stations), and 2DVD + MASC measurements at the MayHills Supersite.

## Key Results

- **Squall line:** WDM6_PD simulates varying graupel densities (low in anvil, high in convective core), reducing graupel mass mixing ratio throughout the column and increasing snow mass. Original WDM6 (fixed 500 kg m⁻³) produces more graupel reaching higher levels.
- **Winter snowfall:** Surface snow reduced by ~92–93% (domain-averaged) in WDM6_PD; surface graupel increased by ~121–124%. RMSE improves for 7 of 8 cases; ETS similar between schemes.
- **$\rho_G$–$V_G$ comparison:** WDM6_PD simulates $\rho_G$ ranging 100–900 kg m⁻³ vs. observed 43–1267 kg m⁻³ (peak 300–400 kg m⁻³). WDM6_PD captures the wide observed range; WDM6_FD's single value significantly underestimates range and fall velocities.
- Computational overhead: 4.3% more CPU time than original WDM6.

## Limitations and Caveats

- Simulated $\rho_G$ in WDM6_PD peaks at lower values (~150 kg m⁻³) than observed (~300–400 kg m⁻³); the density parameterization underestimates the observed maximum normalized frequency.
- Fall velocities in WDM6_PD are slightly larger than observed at the same density.
- The $V_G$–$D$ relationship could be refined with broader observational data for diverse graupel habits (hexagonal, conical, lump graupel, graupel-like snow).
- Equitable threat scores (ETS) are similar between WDM6_FD and WDM6_PD, indicating the improvement is primarily in bias reduction rather than spatial accuracy.
- Only one synoptic category (WL case) was used for the $\rho_G$–$V_G$ validation.

## Relation to Author's Research Program

Milbrandt's contribution here is primarily as the originator of the predicted-density methodology that the entire modification is built upon. The Milbrandt and Morrison (2013) paper introduced prognostic graupel density via a volume mixing ratio into the two-moment multimoment framework, and that exact approach is what Park et al. apply to WDM6. This paper demonstrates that the density-prediction concept Milbrandt developed has been adopted by an independent research group working with a completely different scheme (WDM6/WRF), validating the broader applicability of the approach. It also connects to the ICE-POP 2018 dataset used in Cholette et al. (2025) with P3, showing parallel efforts across the community to evaluate microphysics schemes using the same observational resource. Milbrandt's role is as an external domain expert and originator of the cited methodology, not as a lead of the study itself.

## Impact and Citations

**Citation count:** ~4 (Semantic Scholar, retrieved 2026-06-06)

Published in September 2024 and thus very recent. The paper is novel in combining predicted graupel density with the widely-used WRF+WDM6 combination and in using ICE-POP 2018 observational data for validation. Its uptake will grow as groups evaluating WDM6 and related schemes for winter precipitation encounter its results.
