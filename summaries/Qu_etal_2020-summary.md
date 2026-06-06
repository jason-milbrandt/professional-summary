# Summary: Qu et al. (2020)

**Full citation:** Qu, Z., Huang, Y., Vaillancourt, P. A., Cole, J. N. S., Milbrandt, J. A., Yau, M. K., Walker, K., and de Grandpré, J., 2020: Simulation of convective moistening of the extratropical lower stratosphere using a numerical weather prediction model. *Atmos. Chem. Phys.*, **20**, 2143–2159. DOI: 10.5194/acp-20-2143-2020
**Journal:** Atmospheric Chemistry and Physics
**Year:** 2020
**Authors:** Zhipeng Qu, Yi Huang, Paul A. Vaillancourt, Jason N. S. Cole, Jason A. Milbrandt, Man-Kong Yau, Kaley Walker, Jean de Grandpré
**DOI:** 10.5194/acp-20-2143-2020
**Author's role:** Tier 3 — Contributing co-author; provided GEM model infrastructure and MY2 microphysics scheme expertise as ECCC (RPN) scientist; one of several co-authors contributing to manuscript

---

## Overview

This paper uses the high-resolution GEM model from ECCC to simulate a lower stratosphere moistening event over North America in August 2013. Simulations at four horizontal resolutions (10, 2.5, 1, and 0.25 km) are compared against MLS satellite data and ER-2 aircraft in situ observations to evaluate how well NWP models reproduce cross-tropopause water vapour transport by deep convection. The study identifies overshooting convection and gravity wave breaking as the dominant physical mechanisms driving stratospheric moistening at high resolution, and diagnoses why coarse-resolution models produce a spurious moist bias in the UTLS.

## Context and Motivation

Stratospheric water vapour (SWV) influences the Earth's radiation budget and stratospheric chemistry, yet the processes controlling SWV in the UTLS are poorly understood. GCMs and reanalyses systematically overestimate water vapour content in the mid-latitude UTLS by factors of 2–5 relative to satellite observations (CMIP5 models vs. A-Train data). One motivation is to identify why this moist bias exists — whether it stems from dynamics, microphysics, or parameterization. The study is specifically motivated by the August 2013 event observed during the SEAC4RS campaign, where aircraft detected anomalously high water vapour concentrations above the tropopause.

## Key Scientific Contributions

- Demonstrated that gravity wave breaking near overshooting convective tops is the dominant mechanism for cross-tropopause water vapour transport at cloud-resolving resolution (dx ≤ 1 km), accounting for 59% of total vertical transport in the 1 km simulation
- Showed that coarse-resolution (10 km) models produce a strong moist UTLS bias through two mechanisms: (1) overabundant ice from the convective parameterization (KFC scheme) that fails to remove ice falling back from overshooting tops, and (2) overly efficient ice sublimation because ice is spread across warm grid cells rather than trapped in cold overshooting tops
- Quantified that in high-resolution simulations only 2–6% of transported ice sublimates in the lower stratosphere, compared to 21–75% in the 10 km simulation
- Validated GEM's capability against aircraft observations: the 2.5 km simulation predicted UTLS water vapour well; the 10 km simulation substantially overestimated it
- Identified the "trapping" of ice in cold overshooting tops as a key microphysical process limiting sublimation in nature — a process unresolvable at 10 km grid spacing

## Methods Summary

The GEM model (ECCC) was run in self-nested configurations at 10, 2.5, 1, and 0.25 km horizontal grid spacing over domains covering the Great Lakes region for a deep convection event on 25–27 August 2013. The Milbrandt-Yau double-moment bulk microphysics scheme (MY2) was used in the three high-resolution simulations; the Kain–Fritsch convective parameterization was used at 10 km. Simulations were evaluated against MLS satellite retrievals and ER-2 aircraft in situ water vapour measurements from the SEAC4RS campaign. Back trajectories from LAGRANTO linked the aircraft-sampled air parcels to specific convective events. A Reynolds decomposition of vertical wind and water vapour fields quantified the contributions of mean updrafts vs. wave-breaking eddies to cross-tropopause transport.

## Key Results

- Gravity wave breaking eddies accounted for 59% of direct vertical transport at the tropopause in the 1 km simulation (39% mean updraft, 59% eddies)
- At 2.5 km, the eddy contribution dropped to 29%, reflecting resolution-dependent representation of wave breaking
- High-resolution simulations (1 and 2.5 km) matched aircraft water vapour measurements well; the 10 km simulation overestimated UTLS water vapour throughout the domain
- Ice water content in the UTLS in the 10 km simulation was significantly higher than in high-resolution simulations, primarily due to the KFC convective scheme failing to represent the fallback of overshooting cloud tops
- High-resolution ice is concentrated in small, cold areas (overshooting tops); 10 km ice is spread over larger, warmer grid cells — resulting in ~10–30× higher sublimation efficiency

## Limitations and Caveats

- Simulations cover only a single case study (August 2013 Great Lakes event), limiting generalizability
- The 0.25 km simulation was restricted to a small domain due to computational cost and could not be used for full Domain A intercomparison
- Spatio-temporal mismatches between GEM-simulated and observed convection locations introduce uncertainty in the satellite/aircraft comparisons
- MLS data have known negative biases (~25%) between 100–300 hPa
- Possible solutions proposed (ice sublimation parameterization, larger ice particle sizes) were not tested in this study

## Relation to Author's Research Program

Milbrandt contributed as one of several ECCC RPN scientists supporting this study. The MY2 scheme (Milbrandt and Yau, 2005a,b) — one of Milbrandt's primary scientific contributions — is the microphysics parameterization used in all high-resolution GEM simulations. The paper is directly relevant to Milbrandt's work on cloud microphysics parameterization and its impact on NWP model performance. The study highlights the critical role of ice-phase microphysics (specifically, the spatial distribution of ice and its sublimation) in determining the UTLS water vapour budget in coarse-resolution models — a finding that has implications for future development of the MY2 and P3 schemes. The GEM model system described in Milbrandt et al. (2016) is the foundation for all simulations in this paper.

## Impact and Citations

**Citation count:** ~15 (Semantic Scholar, retrieved 2026-06-06)

The paper addresses a problem of long-standing concern in the climate and NWP communities — the systematic moist bias in the UTLS in coarse-resolution models — and provides a physically grounded mechanistic explanation. The result that gravity wave breaking dominates cross-tropopause transport at cloud-resolving scales, and that convective parameterizations artificially enhance ice sublimation, is directly relevant to GCM development. With 15 citations it has had moderate uptake in the stratospheric water vapour and tropical convection communities.
