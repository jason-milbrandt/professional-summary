# Summary: McTaggart-Cowan et al. (2019)

**Full citation:** McTaggart-Cowan, R., Vaillancourt, P. A., Zadra, A., Chamberland, S., Charron, M., Corvec, S., Milbrandt, J. A., Paquin-Ricard, D., Patoine, A., Roch, M., Separovic, L., and Yang, J., 2019: Modernization of atmospheric physics parameterization in Canadian NWP. *J. Adv. Model. Earth Syst.*, **11**, 3593–3635. DOI: 10.1029/2019MS001781
**Journal:** Journal of Advances in Modeling Earth Systems (JAMES)
**Year:** 2019
**Authors:** R. McTaggart-Cowan, P. A. Vaillancourt, A. Zadra, S. Chamberland, M. Charron, S. Corvec, J. A. Milbrandt, D. Paquin-Ricard, A. Patoine, M. Roch, L. Separovic, J. Yang
**DOI:** 10.1029/2019MS001781
**Author's role:** Tier 3 — Contributed to the microphysics component of the physics modernization; the P3 scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) replaced MY2 in the HRDPS as part of this upgrade (7th of 12 authors)

---

## Overview

This paper documents a multiyear physics modernization project for the Canadian Meteorological Centre's suite of operational NWP systems, based on the GEM model. The project achieved two primary goals — reducing unphysical sensitivity to vertical resolution and improving the global energy and hydrological cycle representation — and delivered significant improvements in forecast guidance skill across global and regional systems. The updated physics package was adopted operationally by the GDPS, RDPS, and REPS in mid-2019, while the HRDPS had already adopted the P3 microphysics scheme (replacing MY2) in late 2018.

## Context and Motivation

Prior to this project, the CMC operational suite suffered from an overactive hydrological cycle linked to excessive latent heat fluxes over tropical and subtropical oceans, and sensitivity to vertical resolution changes that degraded guidance skill when the model grid was refined. Without addressing these systematic biases, increasing vertical resolution and introducing better physics would have been counterproductive due to compensating errors. The project required not only introducing new parameterizations but ensuring energy/water conservation across the full suite, which had not been rigorously verified previously.

## Key Scientific Contributions

- Documented replacement of the Milbrandt–Yau (2005) MY2 scheme with the single ice category P3 (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) in the HRDPS, showing improved spatial distribution of precipitation in mountainous areas due to P3's continuous representation of riming-induced fall speed changes
- Implemented a conservative framework (liquid water static energy and total water mixing ratio budgets) to identify and correct leading-order nonconservation in shallow convection and other schemes, reducing a ~5% overprecipitation bias and enabling reliable hydrological cycle diagnostics
- Introduced a new thermodynamic mixed layer scheme (Zeng & Beljaars, 2005) and salt water correction to reduce excessive tropical/subtropical oceanic latent heat fluxes — a primary driver of the overactive hydrological cycle
- Developed a unified, regime-dependent boundary layer mixing length formulation applicable across all GEM configurations, eliminating a winter cold bias that previously prevented use of the Blackadar (1962) mixing length in global systems
- Introduced a new midlevel convection scheme that reduced grid-point storm artifacts and significantly improved summer precipitation frequency bias (~30% reduction at high thresholds)

## Methods Summary

The physics modernization was evaluated using a hierarchy of modeling systems: 1-year climate integrations (4 × 13-month lagged ensemble), data assimilation cycles (winter 2017 and summer 2016), forecast sequences (44 cases), and case studies. Objective metrics included upper-air temperature, geopotential and wind RMSE, surface station scores, precipitation equitable threat scores and frequency bias, and global energy budget comparisons against ERA-Interim, ERA5, and Stephens et al. (2012) observational estimates. The updated systems were validated across GDPS (15 km global), RDPS (10 km regional), and REPS (10 km ensemble). Vertical resolution was increased from L80 to L84 (bottom thermodynamic level lowered from ~20 m to 10 m) as part of the same package.

## Key Results

- **Global energy budget:** Solar constant correction, water conservation fixes, and reduced oceanic latent heat fluxes together brought the model energy budget into substantially better agreement with observational estimates
- **Upper-air scores:** Significant improvements in temperature and geopotential for both winter and summer GDPS and RDPS forecast sequences; one notable degradation — stratospheric warm bias from updated ozone temperature dependence in the radiation scheme
- **Surface scores:** Improved temperature, dew-point, and wind speed RMSE at most forecast lead times
- **Precipitation:** Summer frequency bias reduced ~30% for large precipitation thresholds; equitable threat scores improved; linked primarily to the new midlevel convection scheme
- **High-resolution (HRDPS):** P3 microphysics improved spatial distribution of orographic precipitation relative to MY2
- **Other:** Tropical cyclone guidance and Madden-Julian Oscillation prediction improved; quasi-biennial oscillation unaffected
- **Computational cost:** 25–35% increase in total integration time (depending on system)

## Limitations and Caveats

- The updated stratospheric ozone temperature dependence introduced a stratospheric warm bias, an acknowledged degradation at high altitudes (similar to other NWP centers)
- Not all CMC systems were migrated simultaneously; GEPS and HRDPS followed a separate schedule
- Conservative corrections to some parameterizations are applied post hoc (tendency corrections) rather than through scheme reformulation, which may obscure some error sources
- Further work identified as needed: scale-aware parameterizations spanning 50–1 km, continued unification of physics across all GEM configurations, and more prognostic cloud fraction treatment at high resolution

## Relation to Author's Research Program

Milbrandt's contribution to this paper is as the developer of both the MY2 scheme (which was replaced) and the P3 scheme (which replaced it). The paper documents the operational transition of the HRDPS from MY2 to P3 — a milestone in the adoption of Milbrandt's microphysics research into operational NWP. The description of the P3 scheme and its performance in mountainous precipitation forecasts (Section 3.7.2) is directly tied to Milbrandt's core research program. This paper represents the formal documentation of that operational milestone, placing Milbrandt as a contributing author to the broader physics suite effort rather than the intellectual driver of the modernization project as a whole.

## Impact and Citations

**Citation count:** ~74 (Semantic Scholar, retrieved 2026-06-06)

This paper has attracted substantial citations as a comprehensive reference for the 2019 Canadian NWP physics upgrade. It is a standard citation for work involving GEM model configurations (GDPS, RDPS, HRDPS, REPS) and serves as the primary documentation for the physics suite adopted by CMC in mid-2019. The 74-citation count reflects its value to the broad NWP community as both a technical reference and a template for documenting multi-scheme physics modernization efforts. ⚠ verify specific downstream studies citing this for the P3 microphysics component.

## Related topics
- [[nwp-system-development]]
- [[p3-scheme]]
