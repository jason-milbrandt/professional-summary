# Summary: Qu et al. (2018)

**Full citation:** Qu, Z., H. W. Barker, A. V. Korolev, J. A. Milbrandt, I. Heckman, S. Bélair, S. Leroyer, P. A. Vaillancourt, M. Wolde, A. Schwarzenböck, D. Leroy, J. W. Strapp, J. N. S. Cole, L. Nguyen, and A. Heidinger, 2018: Evaluation of a high-resolution numerical weather prediction model's simulated clouds using observations from CloudSat, GOES-13 and in situ aircraft. *Quart. J. Roy. Meteor. Soc.*, **144**, 1–14. DOI: 10.1002/qj.3318
**Journal:** Quarterly Journal of the Royal Meteorological Society
**Year:** 2018
**Authors:** Zhipeng Qu + 14 co-authors (Milbrandt is 4th of 15)
**DOI:** 10.1002/qj.3318
**Author's role:** Tier 3 — Contributing co-author; provided the Milbrandt–Yau (MY) microphysics scheme used in the GEM model simulations and contributed microphysics interpretation; the paper evaluates GEM performance using the MY scheme

---

## Overview

This paper evaluates the performance of Environment and Climate Change Canada's GEM model at cloud-resolving resolution (0.25 km) in predicting tropical mesoscale convective system (MCS) clouds, using a rich multi-source observational dataset from the HIWC/HAIC aircraft campaigns over French Guiana. By combining CloudSat radar, GOES-13 imagery, and dual-aircraft in situ observations, with corresponding instrument simulators, the study identifies specific biases in GEM's cloud hydrometeor partitioning and attributes them to missing physical processes (secondary ice production) in the MY microphysics scheme.

## Context and Motivation

High Ice Water Content (HIWC) events in tropical convective systems pose a serious aviation hazard: encounters with dense concentrations of small ice crystals can cause jet engine power loss. Forecasting and understanding HIWC requires accurate NWP model representation of tropical MCS cloud microphysics. Evaluating high-resolution NWP models for such clouds is challenging because: (a) the relevant scales are at or below typical model resolutions; (b) tropical MCS clouds have complex three-dimensional structure; and (c) multiple hydrometeor types coexist across a wide vertical range. The HIWC/HAIC field campaigns provided a unique opportunity to validate models simultaneously against satellite and in situ observations for a single MCS event at cloud-resolving resolution.

## Key Scientific Contributions

- Demonstrated a multi-source, multi-instrument model evaluation framework for tropical cloud microphysics at 0.25 km NWP resolution: CloudSat + COSP, GOES-13 + 3D Monte Carlo radiative transfer, and dual-aircraft in situ observations
- Found that GEM/MY correctly captures large-scale cloud structure and temporal evolution of the MCS
- Identified specific biases: too much graupel/snow at ~7 km altitude, too much low-level liquid cloud
- Attributed the midlevel graupel/snow excess to missing secondary ice production in the MY scheme configuration used
- Showed that CloudSat-retrieved IWC values agree well with in situ samples at both 7 km and 11 km, providing cross-validation of the observational dataset
- Provided a reproducible benchmark test case (16 May 2015 MCS over French Guiana) for ongoing model development

## Methods Summary

**Model:** GEM with one-way nesting from coarser outer domains to a 0.25 km (~300 km)² inner domain. Microphysics: Milbrandt–Yau (MY) double-moment scheme (six hydrometeor categories: cloud droplets, rain, ice, snow, graupel, hail; predicts mass and number mixing ratios for each). No secondary ice production.

**Observation operators:**
- COSP (CFMIP Observation Simulator Package): produces CloudSat W-band (94 GHz) synthetic reflectivity and attenuation from GEM cloud fields
- 3D Monte Carlo solar radiative transfer model: produces synthetic GOES-13 visible reflectances

**Observations:**
- CloudSat CPR: cloud-profiling radar, vertical profiles of reflectivity and IWC retrieval
- GOES-13 imager: visible reflectance (cloud spatial/temporal distribution)
- NRC Convair-580: in situ microphysics at ~7 km (~0°C level); high-latitude HIWC regime
- SAFIRE Falcon-20: in situ microphysics at ~11 km; tropical upper-tropospheric ice crystal regime

**Case:** 16 May 2015 MCS over French Guiana.

## Key Results

- GEM correctly captures the large-scale structure and temporal evolution of the MCS (cloud position, anvil extent) as seen in GOES-13
- At 11 km (Falcon-20 level): GEM predicts IWC well; the MY scheme correctly represents upper-level small ice crystals in the anvil
- At 7 km (Convair-580 level): GEM overestimates graupel and snow, generating too-large COSP reflectivities and attenuations compared to CloudSat
- GEM's visible reflectances exceed GOES-13 due to overestimation of low-level liquid cloud
- CloudSat-retrieved IWC values agree well with in situ at both levels, consistent with other HIWC/HAIC studies
- The attributed cause is missing secondary ice production: mechanisms such as Hallett-Mossop rime splintering would reduce supercooled liquid water and graupel concentrations and increase small ice crystal concentrations near 7 km, improving consistency with observations

## Limitations and Caveats

- Single case study; generalizability to other MCS events and regions is uncertain
- The secondary ice production attribution is qualitative — no sensitivity runs with secondary ice production were performed
- COSP and Monte Carlo radiative transfer involve their own assumptions and uncertainties
- The GEM model used a specific MY scheme configuration without secondary ice production; later versions of GEM with P3 microphysics may behave differently ⚠ verify

## Relation to Author's Research Program

Milbrandt is the fourth of fifteen authors. His primary contribution was providing the MY double-moment microphysics scheme used in the GEM simulations, and contributing expertise in the interpretation of microphysical biases. The paper directly evaluates the performance of the MY scheme — Milbrandt's primary early research contribution — in a challenging tropical convective environment at cloud-resolving resolution. The identified biases (missing secondary ice production) point toward specific limitations of the MY scheme configuration and are relevant to ongoing microphysics development work at ECCC. This paper is part of a broader body of GEM/MY model evaluation work at ECCC, related to the HIWC/HAIC aviation safety research program.

## Impact and Citations

**Citation count:** ~16 (Semantic Scholar, retrieved 2026-06-06)

The paper has a modest citation count consistent with its specialized scope (a single case study using Canadian operational models in an aviation-safety context). It is cited in subsequent HIWC/HAIC-related model evaluation studies and in papers evaluating NWP model cloud microphysics using CloudSat and in situ data. The multi-instrument evaluation framework described is a methodological contribution that has been adapted in similar regional model evaluation studies ⚠ verify.

## Related topics
- [[nwp-system-development]]
