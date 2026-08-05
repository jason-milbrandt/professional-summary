# Summary: Cholette et al. (2020)

**Full citation:** Cholette, M., J.M. Thériault, J.A. Milbrandt, and H. Morrison, 2020: Impacts of Predicting the Liquid Fraction of Mixed-Phase Particles on the Simulation of an Extreme Freezing Rain Event: The 1998 North American Ice Storm. *Mon. Wea. Rev.*, **148**, 3799–3821. DOI: 10.1175/MWR-D-20-0026.1
**Journal:** Monthly Weather Review
**Year:** 2020
**Authors:** Mélissa Cholette, Julie M. Thériault, Jason A. Milbrandt, Hugh Morrison
**DOI:** 10.1175/MWR-D-20-0026.1
**Author's role:** Tier 3 — Provided the P3 microphysics scheme code base and microphysical expertise; intellectual leadership in this study was Cholette's (lead) and Thériault's (supervisor)

---

## Overview

This paper tests a modified version of the P3 bulk microphysics scheme — extended to predict the bulk liquid fraction (Fi,liq) of mixed-phase particles — in a real-case WRF simulation of the 1998 North American Ice Storm. The predicted liquid fraction allows explicit representation of partial melting and refreezing, enabling the model to produce ice pellets and wet snow alongside freezing rain. Compared to the original P3, the modified scheme reduces freezing rain accumulation by up to 30% and increases solid precipitation, improving agreement with observations.

## Context and Motivation

Most bulk microphysics schemes treat hydrometeors as purely solid or purely liquid, converting melted mass to rain immediately. This prevents realistic simulation of mixed-phase particles and the microphysical transitions that produce ice pellets and freezing rain. Cholette et al. (2019) added a prognostic liquid mass mixing ratio (qi,liq) to the P3 scheme, enabling prediction of Fi,liq; this paper is the first real-case 3D test of that extension, applied to the 1998 Ice Storm — one of the most severe and costly winter weather events in Canadian history.

## Key Scientific Contributions

- First real-case, full 3D simulation of the 1998 Ice Storm using a bulk microphysics scheme with explicit mixed-phase particle prediction (Fi,liq).
- Demonstrated that predicting partial melting reduces freezing rain accumulation by up to ~30% in regions with mixed ice pellet/freezing rain precipitation, improving agreement with observations.
- Showed that the modified P3 can reproduce ice pellets — a precipitation type that the original P3 cannot produce — through realistic partial melting and refreezing.
- Identified three key physical mechanisms: (1) partial melting increases particle density and fall speed; (2) smaller raindrops from partial melting are more likely to refreeze; (3) refreezing grows larger particles, increasing solid precipitation accumulation.
- Provided quantitative demonstration that the liquid fraction prediction capability adds measurable forecast value for complex winter precipitation events.

## Methods Summary

WRF v3.9.1.1 with 3-km horizontal grid spacing over southern Quebec. Two simulations: P3_ORIG (original P3; Morrison and Milbrandt 2015; Milbrandt and Morrison 2016) and P3_MOD (P3 with predicted Fi,liq; Cholette et al. 2019). Initial/lateral boundary conditions from NARR reanalysis. Simulated period: 4–10 January 1998. Evaluation against surface station observations of precipitation type and accumulation.

## Key Results

- Both simulations reproduced the synoptic-scale storm structure and near-surface temperatures.
- P3_MOD reduces freezing rain accumulation up to ~30% in mixed ice pellet/freezing rain regions; small but consistent improvement in bias and RMSE vs. observations.
- P3_MOD produces ice pellets and wet snow explicitly; P3_ORIG cannot distinguish these types.
- Solid (non-freezing-rain) precipitation rates are generally higher in P3_MOD due to increased particle density and fall speed.
- P3_MOD underpredicts total solid accumulation near Montreal, attributed in part to absence of secondary ice production in single-category P3.

## Limitations and Caveats

- Single ice category in P3 precludes secondary ice production, which may have contributed to ice pellet formation in the actual storm.
- Validation of precipitation type is challenging at near-0°C temperatures; ice pellets are often underreported in observations.
- High-temporal-resolution observations of precipitation type and vertical T/RH profiles needed for rigorous process-level validation.
- Results are from a single case study; generalizability to other winter storm archetypes is not established.

## Relation to Author's Research Program

Milbrandt is third author. The P3 scheme (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016) is Milbrandt's primary scheme, and this paper tests an extension of it developed by Cholette and Thériault. Milbrandt contributed the P3 code base and microphysical expertise. This paper is directly relevant to his work as it demonstrates the value of extending P3 for winter precipitation prediction — a natural direction for the scheme. However, the scientific leadership in designing the liquid fraction extension and conducting this case study belonged to Cholette and Thériault.

## Impact and Citations

**Citation count:** ~11 (Semantic Scholar, retrieved 2026-06-06)

With 11 citations since 2020, the paper has had reasonable uptake in the winter precipitation microphysics community. It is the first real-case demonstration of mixed-phase particle prediction in a full 3D model, making it an important proof-of-concept. Follow-on work by Cholette and collaborators has continued to develop this extension ⚠ verify.

## Related topics
- [[winter-precipitation-type]]
