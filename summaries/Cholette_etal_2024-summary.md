# Summary: Cholette et al. (2024)

**Full citation:** Cholette, M., J. A. Milbrandt, H. Morrison, S. Kirk, and L.-É. Lalonde, 2024: Secondary ice production improves simulations of freezing rain. *Geophys. Res. Lett.*, **51**, e2024GL108490. DOI: 10.1029/2024GL108490
**Journal:** Geophysical Research Letters
**Year:** 2024
**Authors:** Mélissa Cholette, Jason A. Milbrandt, Hugh Morrison, Sabrina Kirk, Louis-Émile Lalonde
**DOI:** 10.1029/2024GL108490
**Author's role:** Tier 2 — Co-supervisor and P3/HRDPS domain expert; the P3 scheme and HRDPS system are Milbrandt's, providing both the test platform and the context for the identified bias

---

## Overview

ECCC's HRDPS system systematically overestimates freezing rain (FR) in winter situations where snow is observed. This paper identifies the root cause — supercooled rain forms from liquid-phase autoconversion and accretion in regions with insufficient ice — and shows that parameterizing the Hallett-Mossop (HM) rime splintering secondary ice production (SIP) mechanism in P3 substantially fixes it. With HM active and two ice-phase categories, FR accumulation is reduced by up to 98%, and explicit precipitation-type skill scores over 40 winter hindcasts match or slightly exceed the long-established empirical Bourgouin diagnostic algorithm.

## Context and Motivation

P3's liquid-fraction capability (Cholette et al. 2019, 2023) improved ice pellet and wet snow prediction, but a separate bias persisted: HRDPS regularly forecast FR where snow was observed, particularly where the atmospheric temperature profile was entirely below 0°C with no warm melting layer aloft. In this regime, FR arises not from classical warm-layer melting but from a purely liquid-phase pathway — cloud water autoconverts to rain, which then accretes more cloud water, producing supercooled rain that falls as FR. Without enough ice to intercept and glaciate this rain, the bias is self-perpetuating. SIP offers a natural fix: it generates large numbers of small ice particles that deplete cloud liquid through deposition and riming, suppressing the liquid pathway at its source.

## Key Scientific Contributions

- Identified a systematic HRDPS/P3 bias: excessive explicit FR in snow situations driven by liquid-phase autoconversion in regions with limited primary ice nucleation
- Showed that Hallett-Mossop rime splintering (SIP) substantially and systematically corrects this bias, reducing FR accumulation by 65–98% in a case study
- Quantified the mechanism: HM → ice number/mass increase → enhanced deposition (+465–1,340%) depletes water vapor → reduced cloud condensation (−22–58%), autoconversion (−46–82%), rain accretion (−55–76%) → less supercooled rain → less FR
- Demonstrated that two ice-phase categories (nCat2_HM) outperforms one category (nCat1_HM) by avoiding dilution of particle properties when SIP-generated small ice coexists with large pre-existing ice
- Validated over 40 winter hindcasts: FBI for FR substantially improved; ETS comparable or slightly better than the empirical Bourgouin diagnostic; rain and snow scores unaffected
- First study to demonstrate SIP impacts on FR specifically; prior SIP work focused on convective or orographic clouds

## Methods Summary

GEM model in HRDPS configuration (~2.5 km, 62 levels, 48-hr forecasts) with four P3 configurations in a 2×2 factorial design over {1 vs. 2 ice categories} × {HM off vs. HM on}. P3 version includes the liquid fraction extension (Cholette et al. 2019, 2023). Case study: 27 February 2020 Maritime provinces winter storm (verified against METAR hourly precipitation type at 6 stations, CaPA total precipitation). Hindcast set: 40 cases, January–February 2020, scored with FBI, ETS, POD, FAR for FR at 0.1-mm and 0.5-mm thresholds.

## Key Results

- FR accumulation reduction vs. noHM: 65% for nCat1_HM, 98% for nCat2_HM
- IP accumulation increase vs. noHM: 95% for nCat1_HM, 120% for nCat2_HM
- Dominant liquid-phase process reductions in the HM-active region: autoconversion −46 to −82%, cloud accretion by rain −55 to −76%, rain evaporation −44 to −95%
- Ice deposition enhancement in HM-active region: +465 to +1,340%
- 40-case FBI for FR: nCat2_HM closest to 1 (least biased), slightly better than Bourgouin
- ETS differences among configurations: up to 11–17%; nCat2_HM generally best or tied with Bourgouin
- Rain and snow skill scores: similar among all configurations (no degradation)

## Limitations and Caveats

- HM laboratory reproducibility recently questioned (Seidel et al. 2023); physical basis of the parameterization is uncertain
- Only the Hallett-Mossop mechanism was tested; other SIP mechanisms (collisional fragmentation, sublimation fragmentation, frozen-drop breakup) not examined
- Reduction in POD with nCat2_HM suggests possible overreduction of light FR events; to be investigated
- Single geographic focus (eastern Canada/Maritime provinces) and single two-month period

## Relation to Author's Research Program

This paper closes a loop opened by Barszcz et al. (2018): that paper identified excessive rain–graupel collisional freezing as a cause of FR underprediction; this paper identifies insufficient ice as a cause of FR overprediction. Together they bracket the sensitivity of explicit FR prediction to ice-phase processes in P3/HRDPS. Milbrandt's role is co-supervisor and P3/HRDPS context provider; Cholette drives the investigation. The result — that nCat2_HM achieves comparable skill to the highly tuned Bourgouin diagnostic using only physical prognostic variables — is a milestone for the explicit precipitation-type approach that P3 was designed to enable, and that Milbrandt has championed since the HRDPS design.

## Impact and Citations

**Citation count:** ~8 (Semantic Scholar, retrieved 2026-06-06)

Very recent GRL paper (2024); 8 citations in under two years is solid for a specialized NWP microphysics letter. The operational relevance is high: the paper directly addresses a known HRDPS forecast bias affecting winter precipitation across Canada, and the nCat2_HM result offers a physically principled path toward explicit precipitation-type prediction that matches or beats the incumbent diagnostic algorithm. Likely to be cited in future SIP and winter precipitation microphysics literature.
