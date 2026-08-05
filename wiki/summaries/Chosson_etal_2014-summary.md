# Summary: Chosson et al. (2014)

**Full citation:** Chosson, F., P. A. Vaillancourt, J. A. Milbrandt, M. K. Yau, and A. Zadra, 2014: Adapting two-moment microphysics schemes across model resolutions: Subgrid cloud and precipitation fraction and microphysical sub–time step. *J. Atmos. Sci.*, **71**, 2635–2653. DOI: 10.1175/JAS-D-13-0367.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2014
**Authors:** F. Chosson, P. A. Vaillancourt, J. A. Milbrandt, M. K. Yau, A. Zadra
**DOI:** 10.1175/JAS-D-13-0367.1
**Author's role:** Tier 2 — Co-developer of the MY2 scheme (the target scheme for the entire study); contributed domain expertise on MY2 scheme structure and microphysics parameterization; co-author from ECCC Meteorological Research Division alongside Vaillancourt and Zadra

---

## Overview

This paper addresses a fundamental challenge for using detailed two-moment bulk microphysics schemes in NWP models: these schemes are designed for cloud-resolving (~1 km) grid spacings and fail or produce biases when used at coarser resolutions. A twofold solution is proposed and demonstrated in the Milbrandt–Yau two-moment scheme (MY2): a subgrid cloud and precipitation fraction (SCPF) parameterization that allows condensation before grid saturation, and a microphysical sub-time-stepping method to handle large time steps. Validated against satellite-derived cloud properties, the combined approach significantly improves cloud fraction and ice water content at regional NWP scales.

## Context and Motivation

As NWP models span a wide range of resolutions — from 1 km to 30+ km — there was a need to make detailed two-moment microphysics schemes like MY2 usable across all scales without replacing them with simpler schemes at coarser resolutions. At coarse scales, clouds become subgrid phenomena, causing MY2 to underpredict cloud fraction and IWC. Additionally, longer model time steps (300–720 s) lead to catastrophic failure of prognostic sedimentation in MY2 (surface precipitation disappears with time steps > 120 s). The operational GEM Sundqvist scheme handles these issues implicitly but at the cost of simplified microphysics. This paper closes the resolution gap for MY2 specifically.

## Key Scientific Contributions

- Developed and tested the SCPF scheme for use in the MY2 two-moment BMS, using a fixed-width top-hat PDF of total water mixing ratio to diagnose cloud fraction and local in-cloud/clear-sky values.
- Demonstrated that MY2+SCPF allows physically correct ice supersaturation (unlike Sundqvist) while producing realistic cloud fractions at 15-km scale.
- Showed that a microphysical sub-time-step of ~60 s recovers nearly full short-time-step accuracy for surface precipitation at minimal computational overhead (4.39× faster than the equivalent short-time-step run).
- Demonstrated good agreement of MY2+SCPF cloud fraction and in-cloud IWC with CALIPSO/CloudSat DARDAR retrievals vs. baseline MY2 (which loses cloud fraction above ~12 km) and Sundqvist (which underestimates IWC throughout the troposphere).
- Showed that the subgrid precipitation fraction $P_{frac}$ acts as an important tuning parameter for precipitation production and phase.

## Methods Summary

The SCPF scheme uses a top-hat PDF of total water mixing ratio to define a cloud fraction $a$ and separate in-cloud and clear-sky regions. The PDF width is linked to the same height-dependent critical RH threshold $U_{00}$ used in GEM's Sundqvist scheme. Cloud condensates (ice, snow, cloud) are distributed within the cloud fraction; precipitation condensates (rain, graupel, hail) are distributed within a precipitation fraction derived from maximum-random cloud overlap. Testing was done in (1) a 1D kinematic column model initialized from a NARR winter sounding, and (2) the GEM LAM at 15-km grid spacing over the Arctic for a 31-day July 2008 series, validated against DARDAR-Cloud satellite products. Sub-time-stepping was tested at 450-s main time steps with a 60-s microphysics sub-step.

## Key Results

- MY2 without SCPF: cloud fraction drops to zero above ~12 km; no surface precipitation with Dt ≥ 120 s.
- MY2+SCPF: cloud fraction maintained to 14 km; surface precipitation comparable to Sundqvist; IWC in good agreement with DARDAR; realistic in-cloud IWC above 5 km.
- Sundqvist: significantly underestimates IWC (DARDAR comparison); too-low cloud fraction in average; ill-defined liquid-ice partition function produces excess mixed-phase cloud.
- Sub-time-stepping with Dt = 450 s, dt = 60 s achieves almost the same surface precipitation as Dt = 60 s, at 4.39× less computational cost.
- $P_{frac}$ sensitivity: reducing from 100% to 10% doubles surface precipitation while increasing graupel amounts.

## Limitations and Caveats

- Scale dependency of $U_{00}$ and $P_{frac}$ parameters not fully established; further study needed across resolutions from 1 to 50 km.
- Full microphysics physics calibration (interactions with radiation, other parameterizations) not performed.
- Only one case day used for GEM validation; results extended over longer periods needed.
- The 2D nature of the SCPF does not account for vertical velocity, turbulence flux, or other subgrid quantities that are physically interdependent with moisture.

## Relation to Author's Research Program

MY2 is the foundational scheme that Milbrandt developed with Yau (Milbrandt and Yau 2005a,b) and subsequently improved through multiple papers. This work directly applies to the operational use of MY2 at ECCC and represents a key step in making MY2 viable for regional NWP at scales beyond the cloud-resolving limit. Milbrandt and Vaillancourt are co-authors from ECCC's Meteorological Research Division, and the scheme tested here (MY2 with the modifications of Milbrandt et al. 2010) is Milbrandt's primary scientific legacy. The SCPF approach developed here was later directly adapted for the P3 scheme in Jouan et al. (2020), further embedding this work in Milbrandt's research arc.

## Impact and Citations

**Citation count:** ~29 (Semantic Scholar, retrieved 2026-06-06)

The paper had meaningful uptake, primarily cited in the context of adapting bulk microphysics schemes for coarser-resolution models. Its most direct downstream impact is in Jouan et al. (2020), which applied the SCPF approach to the P3 scheme, establishing a pathway for P3 to eventually replace Sundqvist in ECCC's global NWP systems. The paper is also cited in broader discussions of subgrid cloud parameterization for two-moment schemes.

## Related topics
- [[operational-nwp-scale-adaptation]]
