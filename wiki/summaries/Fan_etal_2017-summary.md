# Summary: Fan et al. (2017)

**Full citation:** Fan, J., B. Han, A. Varble, H. Morrison, K. North, P. Kollias, B. Chen, X. Dong, S. E. Giangrande, A. Khain, Y. Lin, E. Mansell, J. A. Milbrandt, R. Stenz, G. Thompson, and Y. Wang, 2017: Cloud-resolving model intercomparison of an MC3E squall line case: Part I—Convective updrafts. *J. Geophys. Res. Atmos.*, **122**, 9351–9378.
**Journal:** Journal of Geophysical Research: Atmospheres
**Year:** 2017
**Authors:** Jiwen Fan et al. (16 authors; Milbrandt is 13th)
**DOI:** 10.1002/2017JD026622
**Author's role:** Tier 3 — provided the MY2 (Milbrandt–Yau two-moment) scheme as one of eight microphysics schemes in the intercomparison; contributed scheme-specific expertise

---

## Overview

This paper performs a constrained cloud-resolving model intercomparison of a large midlatitude squall line (20 May 2011, MC3E field campaign) using WRF-ARW at 1 km grid spacing with eight different microphysics schemes. By holding the dynamical core constant and varying only microphysics, the study isolates microphysical processes as the source of large spread in simulated updraft intensity, precipitation, and cold pool properties. The key finding is that ice-related microphysical parameterizations dominate the spread in convective updraft speed, while collision-coalescence parameterizations dominate precipitation variability in warm-only simulations.

## Context and Motivation

Prior model intercomparison studies of tropical and midlatitude convective systems found large spreads in simulated deep convective properties across different models, but those studies used different dynamical cores as well as different microphysics schemes, making it impossible to attribute differences to any single factor. This study directly addresses that gap by using the same dynamical framework with multiple schemes. The MC3E case provided an unusually rich observational dataset (multi-Doppler wind retrievals, radar reflectivity mosaics, Mesonet surface data, and a wind profiler), enabling detailed evaluation of the simulations.

## Key Scientific Contributions

- Demonstrated that ice-related microphysical processes are the dominant cause of spread in simulated convective updraft speed, with removing ice cutting the normalized updraft speed spread by more than half.
- Showed that updraft velocity variability correlates with cold pool intensity and buoyancy, both of which are controlled by evaporation rate — itself driven by differences in rain and ice parameterizations.
- Found that all eight schemes overestimate convective updraft speed and reflectivity aloft, and all produce small, intense updraft cores that do not match observed wider updraft distributions — a bias likely tied to model dynamics (mixing/diffusion) rather than microphysics alone.
- Showed that MY2 and THOM underestimate surface precipitation for this case; WSM6 and TAMU overestimate it.
- Demonstrated that collision-coalescence parameterization is the dominant source of precipitation uncertainty in warm-only simulations, buffered by ice-related processes in full-physics runs.

## Methods Summary

WRF-ARW v3.4.1 with four nested domains (27, 9, 3, 1 km); real-case initialization from NCEP FNL analysis. Eight schemes span one-moment bulk (WSM6), two-moment bulk (MORR, MY2, NSSL, P3, TAMU), hybrid (THOM), and bin-resolved (FSBM) approaches. Additional no-ice sensitivity runs run for each scheme. Evaluation against multi-Doppler wind retrievals, NEXRAD reflectivity mosaics, three precipitation products, Oklahoma Mesonet cold pool data, and an ARM wind profiler.

## Key Results

- Simulated updraft speeds in strong updrafts differ by 6–8 m s⁻¹ between the Stronger Convection Group (SCG: MORR, MY2, WSM6) and the Weaker Convection Group (WCG: FSBM, NSSL).
- Cold pool intensity in the SCG is up to 50% stronger locally (and ~20% stronger on average) than the WCG, driven by larger evaporation rates.
- Turning off ice reduces upper-level updraft speed by ~50% on average and reduces the spread by more than half.
- Precipitation accumulation (0600–1200 UTC) ranges from 7.3 mm (THOM) to 11.2 mm (WSM6 and TAMU); observed range is ~8.9–12.2 mm.
- MY2 underestimates surface precipitation despite having the largest total condensate mass, possibly due to small graupel terminal velocity (bulk density 400 kg m⁻³).
- No single ice-related process (deposition, riming, drop freezing) shows clear one-to-one correlation with updraft speed spread; complex feedbacks among processes are responsible.

## Limitations and Caveats

- Results are from a single case (20 May 2011 MC3E squall line); generalizability to other squall line cases or convective modes is not established.
- The WCG (FSBM and NSSL) both use prognostic cloud droplet number concentration, confounding separation of microphysics-scheme differences from aerosol representation differences.
- Multi-Doppler retrievals have 2–4 m s⁻¹ uncertainty in upper-tropospheric updraft speed, partly reducing the apparent overestimation bias.
- The simulated system is shifted ~1 h early and ~100 km northward relative to observations.
- Ice process contributions cannot be fully disentangled from warm-phase feedbacks within the full-physics framework.

## Relation to Author's Research Program

Milbrandt is the 13th author out of 16, indicating a supporting role. His contribution was providing the MY2 scheme for use in the intercomparison. The study provides important independent evaluation of both MY2 and P3 in a challenging midlatitude MCS context. Results confirm known characteristics of MY2 — including its tendency to underestimate surface precipitation in squall line cases, attributed here to the choice of graupel bulk density — and provide community context for understanding where both schemes sit relative to the broader landscape of bulk and bin microphysics approaches. The paper is relevant to Milbrandt's research program as independent validation evidence from a large multi-scheme comparison that treated his schemes as community benchmarks.

## Impact and Citations

**Citation count:** ~144 (Semantic Scholar, retrieved 2026-06-06)

This paper has accumulated substantial citations for a 2017 JGR-Atmospheres article, reflecting its value as a controlled microphysics intercomparison study. It has become a reference point for understanding the sensitivity of cloud-resolving simulations to microphysics choice in midlatitude convection, complementing earlier tropical intercomparison studies (TWP-ICE). The study is frequently cited in papers developing or evaluating microphysics schemes and in studies of aerosol–convection interactions where the microphysics sensitivity baseline matters. ⚠ verify specific citing papers
