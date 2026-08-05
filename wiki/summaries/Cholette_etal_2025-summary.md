# Summary: Cholette et al. (2025)

**Full citation:** Cholette, M., J. A. Milbrandt, H. Morrison, J. M. Thériault, K.-S. Lim, W.-Y. Chang, K. Kim, and G. Lee, 2025: Simulation of wet snow during winter orographic precipitation using the Predicted Particle Properties (P3) microphysics scheme. *Mon. Wea. Rev.*, **153**, 2491–2512. DOI: 10.1175/MWR-D-25-0017.1
**Journal:** Monthly Weather Review
**Year:** 2025
**Authors:** M. Cholette, J. A. Milbrandt, H. Morrison, J. M. Thériault, K.-S. Lim, W.-Y. Chang, K. Kim, G. Lee
**DOI:** 10.1175/MWR-D-25-0017.1
**Author's role:** Tier 2 — Co-developer of the P3 scheme and the liquid fraction (LF) parameterization central to the study; senior co-author supervising application of P3 to wet snow in a 3D NWP context

---

## Overview

This paper evaluates kilometer-scale numerical weather model simulations of wet snow — a precipitation type consisting of mixed-phase ice-liquid particles — using the P3 microphysics scheme and observational data from the ICE-POP 2018 field campaign in South Korea. Ten winter storm cases are simulated with and without the P3 liquid fraction prediction enabled. The study demonstrates that explicitly predicting the liquid mass fraction on ice hydrometeors improves both the identification of wet snow as a surface precipitation type and the representation of wet snow bulk properties (density and liquid fraction), particularly at coastal observation sites.

## Context and Motivation

Wet snow is a societally important but poorly represented precipitation type in NWP models. Its rapid accumulation on structures causes power line damage, vegetation loss, and transportation disruptions. Standard bulk microphysics schemes do not predict wet snow explicitly — melted water is transferred to rain instantaneously, preventing the model from representing partially melted, mixed-phase particles. The P3 scheme (Morrison and Milbrandt 2015) includes an optional prognostic bulk liquid fraction ($F_{i,liq}$) introduced in Cholette et al. (2019), but this capability had only been tested for hail, ice pellets, and freezing rain, and for wet snow only in idealized 1D simulations. This paper is the first 3D NWP evaluation of P3's LF capability for wet snow against observationally-based retrievals of liquid fraction and snow density.

## Key Scientific Contributions

- Demonstrated that P3 with predicted liquid fraction shifts precipitation phase from rain to wet snow in all 6 of 6 warm cases where wet snow was observed, while without LF the model produces rain instead.
- Showed that simulated liquid fraction and snow density trends (higher near the coast vs. inland/elevated supersites, factor of 2–3 density gradient) are well reproduced with LF.
- Established that LF captures case-to-case variability in melting behavior tied to riming degree, while noLF gives uniform melting behavior regardless of particle type.
- Identified a limitation: the model fails to simulate "cold wet snow" (liquid fraction > 0 at $T < 0°C$ from supercooled liquid accretion), flagged for future work.
- Provided the first comparison of simulated mixed-phase particle properties (variable bulk density, liquid fraction) against instrument-derived retrievals in a 3D model context.

## Methods Summary

Ten cases from ICE-POP 2018 were simulated using GEM (Global Environmental Multiscale model) with three nested domains: 10 km → 2.5 km → 1 km. At 1-km resolution, paired simulations with (LF) and without (noLF) predicted liquid fraction were run. Both use the 3-moment ice PSD and two free ice categories. LBCs for the 1-km runs came from the 2.5-km LF simulation, eliminating LBC differences as a confounding factor.

Simulated precipitation types were determined diagnostically at each model level using a decision tree based on $F_{i,liq}$, $F_{i,rim}$, bulk density, mean diameter, and surface temperature. Wet snow is diagnosed when $F_{i,liq} > 0.15$. Model outputs were compared against AWS station accumulations, atmospheric soundings, and 10-min retrieved bulk liquid fraction and snow density from collocated MRR + Parsivel instruments at five supersites spanning coast to mountains.

## Key Results

- **Wet snow diagnosis:** LF produces wet snow in all warm cases with observed wet snow; noLF gives rain.
- **Liquid fraction:** Simulated $F_{i,liq}$ averages ~0.21 (LF) vs. retrieved ~0.12 at coastal supersites during warm cases; model overestimates slightly. Cold cases: near-zero, consistent with observations.
- **Snow density:** Lower in simulations than retrievals for all cases (both LF and noLF), but substantially improved with LF at coastal supersites. Factor of 2–3 density gradient (coast vs. mountains) well captured.
- **Melting behavior:** For unrimed ice ($F_{i,rim} < 0.1$) melting aloft, LF gives much higher solid precipitation fraction at near-surface $T$ between 0°–1.5°C. LF shows case-dependent melting variability; noLF does not.
- **Temperature and total accumulation:** Negligible differences between LF and noLF; systematic cold biases of ~−2°C at supersites in all cases.
- **Cold wet snow failure:** Cases 5, 6, and 10 show retrieved $F_{i,liq} > 0$ at $T < 0°C$ (supercooled accretion); LF simulations fail to reproduce this.

## Limitations and Caveats

- Simulated bulk snow density is lower than retrievals at all supersites for both LF and noLF — the parameterized relationship between bulk ice density and liquid fraction may need improvement.
- "Cold wet snow" ($F_{i,liq} > 0$ at $T < 0°C$) is not reproduced; the physics of supercooled liquid accumulation on cold ice at temperatures below 0°C needs further investigation.
- Systematic ~−2°C near-surface cold biases in GEM contribute to underestimation of wet snow at inland high-elevation supersites (YPO, MHS, CPO) during cold cases.
- Comparison uses nearest-grid-point to observation, which can miss spatial variability; single-point time series can be misleading.
- Sample size for wet snow events is small (332 data points across all cases/supersites) — quantitative comparisons have high standard deviations.

## Relation to Author's Research Program

This paper represents a direct application and evaluation of the liquid fraction capability that Milbrandt co-developed with Cholette and Morrison (Cholette et al. 2019) and that was introduced in the broader P3 framework he built with Morrison (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016). The study is part of a systematic series expanding P3 LF evaluation across precipitation types: freezing rain (Cholette et al. 2020), squall lines with triple-moment ice (Cholette et al. 2023), secondary ice production and freezing rain (Cholette et al. 2024), hail (Milbrandt et al. 2025), and now wet snow in orographic terrain. While Cholette led the research and analysis, Milbrandt's role as co-developer of both P3 and the LF scheme, and as senior ECCC scientist guiding the work, is substantive. The GEM+P3 1-km configuration used here (analogous to ECCC's operational HRDPS, which Milbrandt helped develop and document in Milbrandt et al. 2016) situates this directly within Milbrandt's operational NWP portfolio.

## Impact and Citations

**Citation count:** 0 (Semantic Scholar, retrieved 2026-06-06)

The paper was published in November 2025 and is too recent to have accumulated citations. It extends a productive line of P3 LF evaluation work that has collectively garnered over 100 citations across the Cholette et al. (2019, 2020, 2023, 2024) series. The use of ICE-POP 2018 field campaign data and the novelty of comparing 3D NWP simulations with explicit mixed-phase particles against retrieved density and liquid fraction observations positions this paper as a key reference for wet snow parameterization evaluation.

## Related topics
- [[p3-modern-extensions]]
