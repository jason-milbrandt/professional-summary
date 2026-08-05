# Operational Precipitation-Type Prediction (Tier 2)

**Summary:** Two papers on the operational reliability of explicit precipitation-type prediction — the design HRDPS pioneered by determining surface precipitation type directly from bulk microphysics rather than a post-processing diagnostic. Barszcz et al. (2018) diagnoses and fixes a freezing-rain *underprediction* bias in MY2; Park et al. (2024) shows Milbrandt's graupel-density-prediction method independently adopted and validated in a different scheme entirely.

**Sources:** [[Barszcz_etal_2018-summary]], [[Park_etal_2024-summary]]

**Last updated:** 2026-08-05

---

## The freezing-rain underprediction bias (Barszcz et al. 2018)

HRDPS was among the first operational NWP systems to determine surface precipitation type explicitly from the microphysics scheme itself, rather than diagnosing it after the fact (see [[operational-nwp-scale-adaptation]]) — an approach with real advantages but real exposure to microphysics formulation errors. Shortly after HRDPS went operational, a systematic freezing-rain underprediction bias emerged. Using a December 2014 Quebec ice-storm case, this paper traced the cause to excessive rain–graupel collisional freezing in [[milbrandt-yau-scheme]] (MY2): more than 90% of precipitation glaciated below the melting layer before reaching the surface, driven by rain–graupel collection rates an order of magnitude larger than rain–snow or rain–ice. Two fixes were tested — a −5°C threshold on collisional freezing, and a reduced rain–graupel collection efficiency — both of which restored realistic freezing-rain amounts. The temperature-threshold fix was implemented operationally in HRDPS, closing the bias for the forecast system serving the whole of Canada.

This paper pairs directly with [[p3-modern-extensions]]'s Cholette et al. (2024), which addresses the *opposite* bias — freezing-rain *overprediction* — via secondary ice production in P3. Together the two papers bracket the sensitivity of explicit precipitation-type prediction to ice-phase process formulation, in two different generations of Milbrandt's schemes.

## Independent adoption of the density-prediction method (Park et al. 2024)

An independent Korean research group ported Milbrandt's prognostic graupel-density method — introduced in Milbrandt & Morrison (2013), see [[ice-phase-modernization]] — into WRF's WDM6 scheme, adding a graupel volume mixing ratio as a sixth prognostic variable so density can evolve dynamically rather than sitting fixed at 500 kg m⁻³. Validated against ICE-POP 2018 (South Korea) 2DVD and MASC instrument data, the modified scheme (WDM6_PD) reproduced the wide observed range of graupel densities and fall velocities that the fixed-density original could not, and alleviated a positive surface-precipitation bias over mountainous terrain. Milbrandt is senior international co-author and originator of the ported method — the paper demonstrates the density-prediction concept's portability well beyond his own scheme family, and connects to the same ICE-POP 2018 dataset used to evaluate P3's liquid-fraction capability in [[p3-modern-extensions]] (Cholette et al. 2025).

## Position in the arc

Both papers sit at the interface between scheme development and operational reliability — the recurring theme that explicit, physically based precipitation-type prediction (as opposed to empirical diagnostics like Bourgouin) is only as good as the ice-phase process formulation underneath it. That theme runs from the original HRDPS design choice through the 2018 and 2024 freezing-rain fixes to the demonstrated portability of the underlying density-prediction concept in 2024.

## Related pages

- [[milbrandt-yau-scheme]] — MY2, the scheme diagnosed and fixed in Barszcz et al. (2018)
- [[ice-phase-modernization]] — origin of the graupel-density-prediction method Park et al. adopt
- [[p3-modern-extensions]] — the SIP-based fix for the opposite (overprediction) freezing-rain bias
- [[operational-nwp-scale-adaptation]] — the HRDPS design choice that makes this class of bias possible
