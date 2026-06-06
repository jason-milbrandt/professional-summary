# Summary: Barszcz et al. (2018)

**Full citation:** Barszcz, A., J. A. Milbrandt, and J. M. Thériault, 2018: Improving the explicit prediction of freezing rain in a kilometer-scale numerical weather prediction model. *Wea. Forecasting*, **33**, 767–782. DOI: 10.1175/WAF-D-17-0136.1
**Journal:** Weather and Forecasting
**Year:** 2018
**Authors:** Agnieszka Barszcz, Jason A. Milbrandt, Julie M. Thériault
**DOI:** 10.1175/WAF-D-17-0136.1
**Author's role:** Tier 2 — Co-supervisor and domain expert; the MY2 scheme (Milbrandt's own scheme) is the subject of diagnosis and improvement; Milbrandt guided the investigation and the microphysics interpretation

---

## Overview

This paper diagnoses a systematic underprediction of freezing rain by Canada's operational 2.5-km High Resolution Deterministic Prediction System (HRDPS) during the winter of 2014/15. Using a 24–25 December 2014 case over Quebec as a testbed, the authors show that the root cause is excessive rain–graupel collisional freezing in the Milbrandt–Yau (MY2) microphysics scheme, which nearly completely glaciates the precipitation below the warm-front inversion layer before it reaches the surface. Two targeted microphysics modifications — a temperature threshold for collisional freezing and a reduced rain–graupel collection efficiency — are shown to substantially improve the forecast, and the temperature-threshold fix was subsequently implemented in operational HRDPS.

## Context and Motivation

HRDPS was one of the first operational NWP systems worldwide to determine surface precipitation type explicitly and directly from a bulk microphysics scheme, rather than via a post-processing diagnostic. This approach has significant advantages in principle but exposes the system to errors in the microphysics formulation. A systematic bias toward freezing rain underprediction emerged shortly after HRDPS went operational in 2014. Understanding why — and distinguishing microphysical from dynamical causes — was essential for operational improvement.

## Key Scientific Contributions

- Identified the specific MY2 process responsible for freezing rain underprediction: collisional freezing between rain and graupel below the melting layer, which glaciates >90% of precipitation in the observed case
- Demonstrated that the problem lies in the precipitation-type *partitioning* by MY2, not in the total precipitation amounts (confirmed by substituting the Bourgouin diagnostic on top of MY2 microphysics)
- Showed that imposing a temperature threshold of −5°C on collisional freezing suppresses excessive glaciation and restores realistic freezing rain amounts
- Showed that the freezing rain forecast is very sensitive to the rain–graupel collection efficiency $E_{rg}$ but insensitive to rain–ice and rain–snow efficiencies ($E_{ri}$, $E_{rs}$)
- Quantified a microphysical chain-reaction mechanism: even ~10% graupel content is sufficient to glaciate >90% of precipitation through collisional freezing
- The −5°C threshold fix was implemented in operational HRDPS, eliminating the systematic freezing rain bust

## Methods Summary

A real-time HRDPS bust case (24–25 December 2014, Quebec) was rerun on a reduced domain to isolate and efficiently test microphysical modifications. Three main experiment sets: (1) replacing MY2 with the Sundqvist scheme + Bourgouin diagnostic to confirm the problem is in the microphysics; (2) using MY2 with Bourgouin post-processing to confirm the problem is in type partitioning not total precipitation; (3) sensitivity tests varying the collisional freezing temperature threshold from 0° to −9°C (8 experiments), the rain–graupel collection efficiency $E_{rg}$ (5 experiments), and the rain–ice/rain–snow efficiencies $E_{ri}$/$E_{rs}$ (5 experiments). Verification against METAR, SYNOP, and special observer reports.

## Key Results

- RDPS (10 km, Bourgouin diagnostic) forecast up to ~15 mm of freezing rain; HRDPS (MY2 explicit) forecast <2.5 mm against observed maxima >20 mm
- Rain–graupel collisional freezing rates in CTR were $5 \times 10^{-2}$ kg kg$^{-1}$ s$^{-1}$ — an order of magnitude larger than rain–snow and two orders larger than rain–ice
- With temperature threshold ≤ −5°C: graupel significant only where warm layer is shallowest (<30 km); freezing rain constitutes ~90% of surface precipitation elsewhere
- With $E_{rg}$ = 0.4 (vs. default 1.0): freezing rain reaches the surface and represents >90% of total precipitation along the diagnostic cross section
- Domain-wide: reducing $E_{rg}$ or adding the −5°C threshold both increase freezing rain accumulations significantly; only $E_{rg}$ matters, not $E_{ri}$ or $E_{rs}$

## Limitations and Caveats

- Single case study; the optimal threshold/efficiency values may not generalize to all warm-front freezing rain events
- The temperature threshold is acknowledged as an *ad hoc* fix that compensates for the bulk scheme's inability to track particle temperature
- MY2 lacks a partially melted ice category, preventing proper simulation of ice pellet formation; graupel serves as a proxy
- Bulk collection efficiencies are constant; size-dependent values (requiring lookup tables) would be more physically appropriate
- The rain–graupel collection equation is solved analytically with a single bulk fall-speed difference — problematic for two categories with overlapping fall-speed ranges

## Relation to Author's Research Program

This paper is a direct operational application of the MY2 scheme (Milbrandt and Yau 2005a,b) and the HRDPS system description (Milbrandt et al. 2016). Barszcz is the lead investigator; Milbrandt's role was as co-supervisor and microphysics domain expert. The paper exemplifies how MY2's explicit precipitation-type capability — a design feature of the scheme and the HRDPS system — creates both opportunity (direct precipitation-type output) and vulnerability (biases in the microphysics directly corrupt precipitation-type forecasts). The identified limitations (bulk collection, lack of liquid fraction on melting ice) foreshadow motivations for subsequent scheme development, including the P3 scheme's rimed-fraction variable and later the liquid-fraction extension ⚠ verify. This paper also contributes to Milbrandt's ongoing engagement with the operational performance of his schemes within the Canadian NWP system.

## Impact and Citations

**Citation count:** ~17 (Semantic Scholar, retrieved 2026-06-06)

A modestly cited operational NWP paper, reflecting a specialized community. The direct impact is larger than the citation count suggests: the −5°C collisional freezing threshold fix described here was implemented in operational HRDPS, improving winter precipitation-type forecasts for millions of Canadians. The paper is cited in the precipitation-type diagnosis and mixed-phase microphysics literature and contributes to ongoing efforts to evaluate and improve explicit precipitation-type prediction in kilometer-scale NWP systems.
