# Summary: Jouan et al. (2020)

**Full citation:** Jouan, C., J. A. Milbrandt, P. A. Vaillancourt, F. Chosson, and H. Morrison, 2020: Adaptation of the Predicted Particle Properties (P3) microphysics scheme for large-scale numerical weather prediction. *Wea. Forecasting*, **35**, 2541–2565. DOI: 10.1175/WAF-D-20-0111.1
**Journal:** Weather and Forecasting
**Year:** 2020
**Authors:** C. Jouan, J. A. Milbrandt, P. A. Vaillancourt, F. Chosson, H. Morrison
**DOI:** 10.1175/WAF-D-20-0111.1
**Author's role:** Tier 2 — Co-developer and principal architect of the P3 scheme; provided the scheme, its structure, and domain expertise central to the study; second author at ECCC, closely supervising the adaptation work led by Jouan

---

## Overview

This paper documents the first adaptation of the P3 microphysics scheme for use in large-scale (coarse-resolution) NWP models, specifically ECCC's 25-km global GEM model. The key modification is the addition of a subgrid cloud and precipitation fraction (SCPF) parameterization — adapted from Chosson et al. (2014), which was originally developed for the MY2 scheme — along with microphysical sub-time-stepping. The modified scheme was tested in a series of 5-day global forecast experiments against the operational Sundqvist condensation scheme. Results show that P3+SCPF holds significant promise, with improvements in temperature and geopotential height biases even without recalibrating the full physics suite.

## Context and Motivation

In 2018, P3 was implemented operationally in ECCC's 2.5-km HRDPS system (Milbrandt et al. 2016). However, all other ECCC NWP systems — from the 10-km RDPS to the 25-km GDPS and ensemble/seasonal systems — continued to use the decades-old Sundqvist condensation scheme. Known deficiencies of Sundqvist at these scales include: systematic upwind precipitation displacement, underprediction of IWC aloft, and a fixed effective ice crystal radius of 15 µm for radiation. A path to unified microphysics across all ECCC model resolutions required adapting P3 for use at scales where the cloud is a subgrid phenomenon. This paper represents that first step.

## Key Scientific Contributions

- Applied the Chosson et al. (2014) SCPF approach to P3, enabling subgrid cloud fractions and suppressing binary on/off cloud behavior at 25-km resolution.
- Demonstrated that P3+SCPF substantially reduces the excessively high planetary albedo produced by uncalibrated P3 (0.387 → 0.306, toward observed 30–33%), via reduced cloud fraction in the mid-upper troposphere.
- Identified convective detrainment ice properties as a key sensitivity: prescribing a volume-mean ice radius of 60 µm for detraining anvil ice (P3_SCPF_Rmi60) dramatically improved upper-air T and Z_g biases at 24 h vs. Sundqvist control.
- Showed that the IWC excess in P3 at mid-upper levels (a real improvement over Sundqvist's underestimate) is exacerbated by detrainment assumptions, and this exacerbation can be controlled through the $r_{m,i}$ parameter.
- Established that P3+SCPF_Rmi60 outperforms Sundqvist in temperature bias at 24 h without any recalibration of other physics parameterizations.

## Methods Summary

Five GEM configurations were compared in a series of 5-day hindcast simulations using a 25-km global grid (based on GDPS): SUND (Sundqvist control), P3 (P3 only, no SCPF), P3_SCPF, and P3_SCPF_Rmi{20,40,60}. The SCPF component uses the same top-hat PDF and RH threshold as in Chosson et al. (2014). Microphysical sub-stepping at max 60 s per step was applied. 80 reference cases (40 winter, 40 summer) were run for standard skill score evaluation against radiosondes, plus precipitation FBI over North America, tendency diagnostics, and CERES TOA OLR comparisons.

## Key Results

- **P3 only (no SCPF):** Significant degradation in all scores; excessive IWC and cloud cover in tropics; planetary albedo 0.387 (too high); cold bias below 500 hPa, warm bias above.
- **P3+SCPF:** PA reduced to 0.306 (close to reality); improved T bias below 500 hPa vs. P3; but enhanced warm bias at mid-upper levels; much higher surface precipitation (known issue).
- **P3_SCPF_Rmi60:** Dramatic improvement in T and Z_g bias at 24 h vs. both P3_SCPF and SUND; total temperature tendency profile closer to zero; cirrus anvil cover in tropics closer to observations; by day 5, mixed improvements/degradations; precipitation still excessive.
- Temperature improvement at lower levels: ~2°C cold bias in SUND reduced significantly.
- Key driver of improvement: reducing detrained anvil ice number (larger prescribed $r_{m,i}$) reduces IWC at mid-upper levels, correcting the main temperature/radiation error in P3.

## Limitations and Caveats

- Surface precipitation remains excessively positive with P3+SCPF; this requires recalibration of the precipitation fraction and/or autoconversion parameters.
- Standard deviations of Z_g errors at upper levels degrade by day 5, indicating some instability or error growth.
- No recalibration of the full physics suite (radiation, convection, land surface) was performed; results represent an "uncalibrated" baseline.
- The Yin-yang 25-km grid is now outdated (GDPS operates at 15 km); additional tests at 15 km showed similar overall findings.
- Detrainment assumptions (the $r_{m,i}$ sensitivity) are uncertain and observationally constrained only loosely.

## Relation to Author's Research Program

This paper is a key step in Milbrandt's ongoing project of making P3 the unified microphysics scheme for all ECCC NWP systems across scales. Having led the implementation of P3 in HRDPS (2.5 km) and co-developed the P3 scheme itself (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016), this paper — where Milbrandt is second author and senior ECCC scientist — directly extends that work toward global-scale NWP. The SCPF component draws directly on the MY2 work from Chosson et al. (2014) where Milbrandt was also a co-author. The pathway established here toward replacing Sundqvist with P3 across all ECCC scales represents a central mission-level goal in Milbrandt's research program. A follow-on paper (McTaggart-Cowan et al. 2019 ⚠ verify specific paper) documents broader NWP physics modernization at ECCC in which P3 is a key component.

## Impact and Citations

**Citation count:** ~14 (Semantic Scholar, retrieved 2026-06-06)

The citation count is modest but the paper's operational significance is high: it established the feasibility of using P3 in coarse-resolution NWP and laid the groundwork for eventual replacement of Sundqvist across ECCC's suite of operational prediction systems. Citations are primarily from groups working on scale-adaptive microphysics and ECCC NWP development.

## Related topics
- [[operational-nwp-scale-adaptation]]
