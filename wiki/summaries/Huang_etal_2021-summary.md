# Summary: Huang et al. (2021)

**Full citation:** Huang, Y., Wu, W., McFarquhar, G. M., Wang, X., Morrison, H., Ryzhkov, A., Hu, Y., Wolde, M., Nguyen, C., Schwarzenboeck, A., Milbrandt, J., Korolev, A. V., and Heckman, I. (2021): Microphysical processes producing high ice water contents (HIWCs) in tropical convective clouds during the HAIC-HIWC field campaign: evaluation of simulations using bulk microphysical schemes. *Atmospheric Chemistry and Physics*, **21**, 6919–6944. DOI: 10.5194/acp-21-6919-2021
**Journal:** Atmospheric Chemistry and Physics
**Year:** 2021
**Authors:** Yongjie Huang, Wei Wu, Greg M. McFarquhar, Xuguang Wang, Hugh Morrison, Alexander Ryzhkov, Yachao Hu, Mengistu Wolde, Cuong Nguyen, Alfons Schwarzenboeck, Jason Milbrandt, Alexei V. Korolev, Ivan Heckman
**DOI:** 10.5194/acp-21-6919-2021
**Author's role:** Tier 3 — Contributing co-author at ECCC; the P3 scheme (Morrison and Milbrandt, 2015) is one of the four schemes evaluated; Milbrandt likely contributed expertise in the P3 scheme and its properties in the HIWC context, and is a co-author on the companion Korolev et al. (2020) secondary ice production study that motivates this work

---

## Overview

This paper evaluates four bulk microphysics schemes — WSM6 (one-moment), Morrison (two-moment), and P3 with one and two ice categories — in high-resolution WRF simulations of a tropical oceanic convective system observed during the HAIC-HIWC field campaign near Cayenne, French Guiana (26 May 2015). The study focuses on whether current bulk schemes can reproduce the high ice water content (HIWC) regions characteristic of tropical convection — regions with predominantly small ice crystals (median mass diameter < 300 µm) and low radar reflectivities (< 20 dBZ). The key finding is that no scheme outperforms others across all metrics, and all fail to capture the observed small ice crystal peak, pointing to missing secondary ice production parameterizations.

## Context and Motivation

HIWC regions pose a critical aviation hazard: high concentrations of small ice crystals ingested by jet engines can cause power loss and damage, and are difficult to detect with onboard pilot radars due to their low reflectivity. Numerical models need to accurately represent these regions for operational hazard forecasting and certification purposes. Earlier studies showed that existing microphysics schemes consistently overestimate radar reflectivity above the melting level in tropical convection. This paper extends such evaluation to include the P3 scheme — the most physically-based ice representation available in WRF at the time — to test whether its fundamentally different approach to ice yields better performance.

## Key Scientific Contributions

- Demonstrates that all four bulk schemes overestimate radar reflectivity above the melting layer by >30% (in areal extent and intensity), including P3 despite its novel ice representation
- Identifies that all schemes miss the observed peak in ice number distribution for particle sizes 0.1–1 mm (the small crystal signature of HIWC regions)
- Shows that overpredicted liquid water content above the melting layer (in MORR, P3-1ICE, P3-2ICE) drives collection-based riming that increases ice particle size/mass without increasing number, generating large particles inconsistent with HIWC observations
- Demonstrates that P3-2ICE (two ice categories) produces the closest storm coverage to observations (only −2.3% bias vs. −34.3% for WSM6)
- Provides quantitative evidence that missing secondary ice production (SIP) parameterizations — particularly "freezing-drop-shattering" — may be responsible for low bias in ice number at −10°C

## Methods Summary

WRF model with three nested domains (innermost 1-km). Simulations evaluated against radiosondes, GOES-13 satellite brightness temperature, airborne X-band radar (French Falcon 20 and NRC Convair 580), and in situ cloud microphysics probes. X-band radar reflectivity forward simulators were developed for each scheme to enable direct comparison. Four schemes: WSM6, Morrison, P3-1ICE, P3-2ICE. Analysis focused on the tropical oceanic MCS over French Guiana on 26 May 2015.

## Key Results

- All simulations broadly reproduce temperature profiles (bias < 1.6%), but storm coverage is underestimated (WSM6: −34%, MORR: −30%, P3-1ICE: −13%, P3-2ICE: −2%)
- Simulated 95th percentile reflectivity above 6 km: WSM6/MORR/P3-1ICE/P3-2ICE all greatly exceed observed (< 30 dBZ), reaching 41–47 dBZ
- All schemes miss the peak of the observed ice number distribution for 0.1 < D < 1 mm by up to 1 order of magnitude
- MORR and WSM6 simulate fewer small particles and more large particles than observed; P3-1ICE overestimates number at most levels; P3-2ICE produces large spread
- Mixed-phase processes at −10°C associated with LWC overprediction drive collection-based ice mass growth without number increase → overly large particles → excess reflectivity

## Limitations and Caveats

- Single case study; representativeness to other HIWC events not established
- 1-km resolution is not cloud-resolving (O(100 m)), so horizontal entrainment is not resolved; this affects liquid available for riming growth in updrafts
- Missing SIP parameterizations (secondary ice production) are hypothesized but not tested in this paper; sensitivity experiments are identified as future work
- P3 scheme tested is an early version; later implementations may perform differently

## Relation to Author's Research Program

Milbrandt is a co-author on this paper, which uses the P3 scheme he co-developed (with Morrison) as one of the four microphysics parameterizations under evaluation. The study provides an independent evaluation of P3's performance in the tropical HIWC context — a regime distinct from the mid-latitude winter/mixed-phase precipitation for which P3 was originally designed. The finding that P3 does not clearly outperform two-moment bulk schemes in this environment is an honest assessment that points to the need for additional process parameterizations (SIP) beyond what any current bulk scheme includes. Milbrandt is also listed as a co-author on Korolev et al. (2020), which proposes the "freezing-drop-shattering" SIP mechanism that this paper identifies as potentially critical for producing the observed small ice crystal populations.

## Impact and Citations

**Citation count:** ~21 (Semantic Scholar, retrieved 2026-06-06)

This paper contributes to the growing literature evaluating bulk microphysics schemes against HAIC-HIWC field campaign observations, a critical application area for aviation safety. It is one of a small number of papers to evaluate P3 in a tropical oceanic convection context, providing useful cross-regime performance information. The study's focus on secondary ice production as a key missing process has broader implications for tropical cloud modeling.

## Related topics
- [[sip-hiwc-mixed-phase]]
