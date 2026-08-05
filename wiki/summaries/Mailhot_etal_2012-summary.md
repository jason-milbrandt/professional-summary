# Summary: Mailhot et al. (2014)

**Full citation:** Mailhot, J., Milbrandt, J.A., Giguère, A., McTaggart-Cowan, R., Erfani, A., Denis, B., Glazer, A., and Vallée, M. (2014): An experimental high-resolution forecast system during the Vancouver 2010 Winter Olympic and Paralympic Games. *Pure and Applied Geophysics*, **171**, 209–229. DOI: 10.1007/s00024-012-0520-6
**Journal:** Pure and Applied Geophysics
**Year:** 2014 (accepted 2012, published online August 2012)
**Authors:** J. Mailhot, J.A. Milbrandt, A. Giguère, R. McTaggart-Cowan, A. Erfani, B. Denis, A. Glazer, M. Vallée
**DOI:** 10.1007/s00024-012-0520-6
**Author's role:** Tier 3 — Contributed the MY2 microphysics scheme implementation and the snow-to-liquid ratio diagnostic; participated as part of the Environment Canada NWP development team led by Mailhot

---

## Overview

This paper describes the experimental high-resolution NWP system developed by Environment Canada for the Vancouver 2010 Winter Olympic and Paralympic Games. The system used nested GEM–LAM grids at 15-, 2.5-, and 1-km horizontal grid spacings and featured several physics improvements including the two-moment Milbrandt–Yau (MY2) microphysics scheme — described as the first operational use of a full two-moment scheme for this type of forecast system. Objective and subjective evaluations showed the high-resolution configurations significantly outperformed the operational 15-km regional model for near-surface variables in complex mountainous terrain.

## Context and Motivation

High-resolution NWP in complex terrain presents significant challenges due to the need to resolve finescale orographic effects, precipitation phase changes, and local wind systems. The Vancouver and Whistler venues experienced rapidly changing winter weather from Pacific storm systems interacting with coastal mountain topography. Environment Canada used the Olympic Games as an opportunity to develop and test prototype high-resolution systems that would otherwise be difficult to evaluate operationally. A key motivation was demonstrating the value of improved physics — particularly two-moment microphysics — in winter forecast applications.

## Key Scientific Contributions

- Demonstrated significant forecast improvement from 1-km vs. 15-km resolution for near-surface wind speed and temperature in complex winter terrain, with the 1-km model virtually eliminating the wind speed bias present in the operational system
- First documented operational application of a full two-moment bulk microphysics scheme (MY2) in a high-resolution Canadian NWP system
- Introduced and subjectively validated a new snow-to-liquid ratio (SLR) diagnostic derived directly from the MY2 microphysics scheme, enabling explicit prediction of snowfall depth without assumed SLR constants
- Demonstrated operationally feasible visibility forecasting from the Gultepe–Milbrandt parameterizations using prognostic MY2 hydrometeor fields
- Showed that high-resolution models provided enhanced guidance for weather-sensitive Olympic events including precipitation phase change, squall line passage, and wind channeling

## Methods Summary

The Olympic system comprised three one-way nested GEM–LAM grids: REG15 (15-km), LAM2.5 (2.5-km), and LAM1 (1-km), all with 58 vertical levels. The MY2 scheme predicted six hydrometeor categories (cloud, rain, ice, snow, graupel, hail) using two moments each. Visibility was parameterized from prognostic hydrometeor fields. Objective verification used the Olympic Autostation Network (OAN; >40 surface stations) over the 40-day Olympic/Paralympic period (12 February–23 March 2010), with bias and standard error statistics and 84% confidence intervals from block bootstrapping.

## Key Results

- 2-m temperatures: LAMs reduced cold bias by >1°C during daytime vs. REG15; standard errors reduced by ~1.5°C; large warm errors (>3°C) occurred 70 times in REG15 vs. only 4 times in LAM1
- 10-m wind speed: LAM1 essentially unbiased during the day (REG15 too weak by ~0.5 m s$^{-1}$); all models had standard errors ~1.4 m s$^{-1}$
- Wind direction: large standard errors in all models (40–50°); no systematic directional bias
- SLR_inst: correctly captured transition from fluffy-aggregate snow (~SLR 20) to graupel-like pellets (~SLR 5) during a case study on 23 February, consistent with a forecaster's subjective observation
- Visibility and squall line case studies showed the high-resolution system provided enhanced, actionable guidance to venue forecasters

## Limitations and Caveats

- No data assimilation was used in the LAM2.5 or LAM1 grids; errors grew for longer forecast lead times
- Wind direction forecasting remained poor in all configurations (standard errors 40–50°)
- All models were too dry near the surface except in the afternoon
- Objective verification of new products (SLR, visibility) was not completed; only subjective evaluations were presented
- Single-season evaluation limits generalizability

## Relation to Author's Research Program

Milbrandt's primary contribution was providing the MY2 microphysics scheme that served as the centerpiece of the Olympic system's physics improvements, and developing (with Glazer and Jacob) the snow-to-liquid ratio diagnostic based on MY2 hydrometeor outputs. This paper represents an important application milestone for MY2: its first documented use in a quasi-operational high-resolution NWP context. The snow-to-liquid ratio diagnostic developed here was published separately as Milbrandt et al. (2012) ⚠ verify and represents a direct downstream product of MY2's two-moment representation of snow density. The visibility parameterizations used were Gultepe and Milbrandt (2007, 2010), also part of Milbrandt's collaborative work. The Olympic system developments were later incorporated into the operational 2.5-km Canadian NWP system, extending MY2's operational impact.

## Impact and Citations

**Citation count:** ~47 (Semantic Scholar, retrieved 2026-06-06)

This paper has been cited as a reference for high-resolution NWP evaluation in complex winter terrain and as documentation of the MY2 scheme's first quasi-operational implementation at 1-km scale. It is part of a broader SNOW-V10 (Science of Nowcasting Olympic Weather for Vancouver 2010) collection of papers in the same issue of Pure and Applied Geophysics. The Olympic experience contributed directly to the upgrade of Canada's operational 2.5-km LAM system ⚠ verify and to FROST-2014 planning for the Sochi Winter Olympics.

## Related topics
- [[olympics-wwrp-nowcasting]]
