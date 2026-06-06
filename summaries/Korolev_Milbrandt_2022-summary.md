# Summary: Korolev & Milbrandt (2022)

**Full citation:** Korolev, A., & Milbrandt, J. (2022): How are mixed-phase clouds mixed? *Geophysical Research Letters*, **49**, e2022GL099578. DOI: 10.1029/2022GL099578
**Journal:** Geophysical Research Letters
**Year:** 2022
**Authors:** Alexei Korolev, Jason Milbrandt
**DOI:** 10.1029/2022GL099578
**Author's role:** Tier 3 — Co-contributed to conceptualization, methodology, and project administration; contributed to writing review and editing; primary data collection and analysis led by Korolev

---

## Overview

This study examines the spatial structure of mixed-phase clouds using a large airborne dataset collected over 10 years of ECCC flight campaigns. The central finding is that mixed-phase clouds are not homogeneously mixed but instead exhibit high spatial intermittency, with ice and liquid regions forming clusters at scales ranging from ~100 km down to the 100 m instrument resolution limit. This intermittency is currently unconstrained in weather and climate models, which matters because whether liquid and ice coexist in a grid cell (genuinely mixed) or are separated (conditionally mixed) affects glaciation rates, precipitation, and radiation.

## Context and Motivation

Mixed-phase clouds — containing both supercooled liquid droplets and ice particles — are ubiquitous and important for precipitation and radiation. A critical unresolved question is whether ice and liquid are uniformly mixed ("genuinely mixed") or spatially separated ("conditionally mixed"). These two regimes have different physical behaviors: in genuinely mixed clouds, the Wegener–Bergeron–Findeisen (WBF) process actively transfers mass from liquid to ice; in conditionally mixed clouds, spatial separation suppresses WBF, slowing glaciation and altering precipitation. Prior work had suggested high spatial variability, but a systematic statistical characterization across scales was lacking. Weather and climate models do not constrain the degree of overlap between in-cloud ice and liquid within a grid cell, creating a potential source of systematic bias.

## Key Scientific Contributions

- Characterized the probability distributions of continuous ice, liquid, and mixed-phase cloud segment lengths from a multi-campaign, 10-year airborne dataset, finding power-law dependencies across scales from 100 m to ~100 km
- Demonstrated that mixed-phase cloud occurrence **increases at smaller scales** — high spatial intermittency — implying that models biased toward genuinely mixed are likely wrong at most resolved scales
- Distinguished "genuine" from "conditional" mixed-phase at the observational level, providing the first systematic statistics on each type
- Derived a theoretical estimate of the minimum cluster scale ($L_{min} \sim 0.1$–$10$ m for ice; mm scale for droplets), far below current model resolution, showing the problem extends well below what any model can currently represent
- Identified an implication for model evaluation: in situ observations can be used to validate atmospheric models' ability to represent subgrid-scale phase heterogeneity

## Methods Summary

The analysis used the NRC Convair-580 research aircraft equipped with the Nevzorov probe (LWC, IWC), Rosemount Icing Detector, FSSP, and OAP-2DC/2DP probes. Phase was discriminated by the ice water fraction $\mu = IWC/(LWC + IWC)$, with ice defined as $\mu > 0.9$, liquid as $\mu < 0.1$, and mixed-phase as $0.1 \leq \mu \leq 0.9$. The minimum resolved scale was 100 m. Seven ECCC-led campaigns covering midlatitude and Arctic clouds in the range $-35 < T < 0°C$ were analyzed. Continuous cloud segments were identified and their lengths tallied; isolated single-phase clouds were excluded.

## Key Results

- Cloud phase segment lengths span four orders of magnitude: from $\sim 10^1$–$10^2$ km down to the 100 m resolution limit
- Frequency distributions of segment lengths follow power-law dependencies; frequency increases with decreasing scale
- A theoretical framework (turbulent mixing vs. WBF glaciation timescale) predicts spatial phase scales of $L_{ph} \sim 10^1$–$10^4$ m, consistent with observations
- Even models with km-scale grid spacings are likely biased toward genuinely mixed because subgrid heterogeneity is not represented
- The true minimum scale ($L_{min}$) for ice clusters is estimated at 0.1–1 m; for droplets, 2–10 mm — far below any current measurement or model resolution

## Limitations and Caveats

- Minimum resolved scale is 100 m, limited by instrument temporal resolution; the actual minimum cloud cluster scale remains unknown and is identified as an open question
- The theoretical framework for $L_{ph}$ assumes isotropic turbulence in the inertial subrange, applicable only up to ~1 km; larger-scale phase structure is controlled by convection and mesoscale dynamics
- Does not account for cloud processes such as riming, ice sedimentation, or entrainment of out-of-cloud air
- Data collected on the NRC Convair-580 from a limited set of campaigns; generalizability across all cloud types and regions is not fully established

## Relation to Author's Research Program

Milbrandt co-contributed to the conceptualization and methodology of this study. The paper is directly relevant to his work on bulk microphysics parameterization: a central challenge in schemes like MY2 and P3 is representing the coexistence of liquid and ice within a model grid cell. This paper provides observational context for one of the key unresolved problems in cloud microphysics parameterization — the degree of subgrid phase separation — and motivates future parameterization improvements. Milbrandt's contribution was in the design and direction of the study, drawing on his expertise in cloud microphysics modeling, while Korolev led the data collection and analysis.

## Impact and Citations

**Citation count:** ~50 (Semantic Scholar, retrieved 2026-06-06)

This is a well-cited short letter for its age (published late 2022), reflecting the community's recognition that subgrid mixed-phase cloud structure is an outstanding problem in NWP and climate modeling. The paper's framing of "genuine" vs. "conditional" mixed-phase and its power-law scale statistics have been taken up in subsequent discussions of microphysics scheme development and cloud-fraction parameterization. The companion paper Korolev et al. (2020) ⚠ verify laid observational groundwork that this study extends to the statistical characterization of spatial scales.
