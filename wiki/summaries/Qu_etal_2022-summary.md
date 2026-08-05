# Summary: Qu et al. (2022)

**Full citation:** Qu, Z., Korolev, A., Milbrandt, J. A., Heckman, I., Huang, Y., McFarquhar, G. M., Morrison, H., Wolde, M., and Nguyen, C., 2022: The impacts of secondary ice production on microphysics and dynamics in tropical convection. *Atmos. Chem. Phys.*, **22**, 12287–12310. DOI: 10.5194/acp-22-12287-2022
**Journal:** Atmospheric Chemistry and Physics
**Year:** 2022
**Authors:** Zhipeng Qu, Alexei Korolev, Jason A. Milbrandt, Ivan Heckman, Yongjie Huang, Greg M. McFarquhar, Hugh Morrison, Mengistu Wolde, Cuong Nguyen
**DOI:** 10.5194/acp-22-12287-2022
**Author's role:** Tier 3 — Contributing co-author; co-conceptualized research goals and co-designed experiments (per author contributions statement); provided P3 microphysics scheme and GEM model expertise from ECCC

> **Note:** The author contributions statement indicates Milbrandt (JAM) co-conceptualized the research and co-designed the experiments with Qu and Korolev, suggesting a more substantive role than typical Tier 3. Designated Tier 3 per Jason's stated tier for this paper. ⚠ verify with Jason if tier should be reconsidered.

---

## Overview

This paper investigates the impacts of secondary ice production (SIP) on the microphysics and dynamics of tropical mesoscale convective systems (MCSs) using quasi-idealized near-cloud-resolving simulations in the GEM model with the P3 microphysics scheme. Simulations at 250 m horizontal grid spacing tested the Hallett–Mossop rime splintering (HM) and fragmentation of freezing droplets (FFD) SIP mechanisms, with results compared to airborne in situ and radar observations from the HAIC-HIWC field campaign (2015). The key finding is that SIP processes are essential for reproducing the observed high ice water content (IWC) and ice number concentrations in tropical convection — without SIP, simulated concentrations are 2–3 orders of magnitude too low.

## Context and Motivation

High IWC regions (>1 g m⁻³) with low radar reflectivity in tropical MCSs pose a hazard for civil aviation (potential engine power loss or damage). Reproducing such conditions in NWP models requires realistic simulation of ice number concentrations, which vastly exceed those producible by primary ice nucleation alone. Previous modelling studies using traditional fixed-category microphysics showed persistent IWC and PSD biases compared to observations. The P3 multi-category scheme, with its "free" ice category framework, is well-suited for incorporating SIP because it can represent co-existing populations of small ice splinters and large pre-existing ice particles — a requirement for physically meaningful SIP simulation.

## Key Scientific Contributions

- Established that a minimum of three P3 ice categories is necessary to meaningfully simulate SIP in deep convection
- Demonstrated that SIP (HM + FFD mechanisms) increases simulated ice number concentrations by up to 3 orders of magnitude at 6–7 km altitude, bringing them into agreement with HAIC-HIWC observations
- Showed that SIP enhances and sustains convective updrafts above the melting layer through increased latent heat release during vapour deposition on secondary ice splinters — a positive dynamical feedback
- Found that the frequency of encountering high-IWC conditions (1–2 g m⁻³) is 1/2 to 1/500 of observed in simulations without SIP; this bias is largely corrected by activating SIP
- Demonstrated that ice aggregation parameterization (specifically collection efficiency) is a major source of uncertainty independent of SIP, affecting IWC and $N_i$ by up to ~1 order of magnitude

## Methods Summary

Quasi-idealized simulations of a tropical MCS were conducted using the GEM model at 250 m horizontal grid spacing (160 km × 160 km domain, 83 levels). Initial conditions were based on a HAIC-HIWC campaign sounding (May 2015, French Guiana, CAPE = 1697 J kg⁻¹). Convection was initiated by updraft nudging. The P3 scheme was extended to include up to four free ice categories with HM and FFD SIP parameterizations. Simulated PSDs, $N_i$, IWC, radar reflectivity, and Doppler velocity were compared against in situ and radar observations from coordinated NRC Convair 580 and SAFIRE Falcon 20 aircraft flights.

## Key Results

- Without SIP: simulated $N_i$ at 6–7 km is ~100× below observations; frequency of high-IWC events is ~1/2 to 1/500 of observed
- With SIP (HM + FFD), $N_i$ increases by up to 1000× at 6–7 km, matching observed concentrations; Doppler velocities above the melting layer also more closely match observations
- SIP initiates new convective updrafts above the melting layer through buoyancy enhancement from latent heat release — a positive dynamical feedback not present in simulations without SIP
- Ice collection efficiency is a major source of uncertainty: using the linear SIP-COL parameterization reduces $F(\text{IWC})$ at high altitudes by up to ~1 order of magnitude compared to SIP-4ICE
- Results at 1 km grid spacing (closer to operational NWP resolution) are very similar to those at 250 m, suggesting SIP impacts are robust across this resolution range

## Limitations and Caveats

- Only HM and FFD SIP mechanisms were tested; other mechanisms (ice–ice fragmentation, thermal shock, etc.) were not included
- The HM and FFD parameterizations used are largely ad hoc and based on limited laboratory experiments; they may not accurately capture the underlying physics of these mechanisms
- The study uses quasi-idealized (horizontally homogeneous) initial conditions, not a real-case simulation, which limits direct validation against specific observed storm events
- Sensitivity to ice collection efficiency parameterization highlights remaining uncertainty in aggregation representation

## Relation to Author's Research Program

Milbrandt co-conceptualized and co-designed this study, which uses his P3 microphysics scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) as the core modelling framework. The multi-category P3 extension that makes SIP simulation possible was developed explicitly by Milbrandt and Morrison (2016). The paper demonstrates the scientific value of the P3 framework's design philosophy — free ice categories whose properties evolve continuously — for advancing the representation of complex ice microphysical processes in NWP models. This study builds directly on the HAIC-HIWC observational campaign work in which Milbrandt also participated (Korolev et al., 2020). The finding that SIP has dynamical feedbacks on convection (not just microphysical effects) is a significant scientific result with implications for the future development of P3.

## Impact and Citations

**Citation count:** ~32 (Semantic Scholar, retrieved 2026-06-06)

With 32 citations in two years, this paper has gained meaningful uptake in the cloud microphysics community, particularly among researchers working on secondary ice production, high-IWC cloud hazards, and tropical convection simulation. The study's direct connection to aviation safety hazards (HAIC-HIWC campaign context) broadens its audience beyond academic researchers to applied NWP and aviation safety communities.

## Related topics
- [[sip-hiwc-mixed-phase]]
