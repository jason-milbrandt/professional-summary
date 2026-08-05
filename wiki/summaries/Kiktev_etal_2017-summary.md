# Summary: Kiktev et al. (2017)

**Full citation:** Kiktev, D., P. Joe, G. A. Isaac, A. Montani, I.-L. Frogner, P. Nurmi, B. Bica, J. Milbrandt, M. Tsyrulnikov, E. Astakhova, A. Bundel, S. Bélair, M. Pyle, A. Muravyev, G. Rivin, I. Rozinkina, T. Paccagnella, Y. Wang, J. Reid, T. Nipen, and K.-D. Ahn, 2017: FROST-2014: The Sochi Winter Olympics International Project. *Bull. Amer. Meteor. Soc.*, **98**, 1908–1929.
**Journal:** Bulletin of the American Meteorological Society (BAMS)
**Year:** 2017
**Authors:** Dmitry Kiktev et al. (21 co-authors)
**DOI:** 10.1175/BAMS-D-15-00307.1
**Author's role:** Tier 3 — Contributing co-author (8th of 21 authors); Milbrandt contributed as part of the ECCC team by providing the GEM-LAM forecast model at 2.5 km, 1 km, and 0.25 km horizontal grid spacings used in the FROST-2014 project; the GEM system is described in Milbrandt et al. (2016)

*Note: The source PDF is named "Kirkev_BAMS_2017.pdf" — the first author's name is correctly Kiktev.*

---

## Overview

This paper describes the FROST-2014 international meteorological project organized under the WMO World Weather Research Programme for the 2014 Sochi Winter Olympics. Six nowcasting systems, nine deterministic NWP models, and six ensemble prediction systems from multiple countries provided real-time forecasts for the complex mountain terrain of the Olympic venue cluster in the Greater Caucasus. The paper summarizes the observational network, participating systems, verification results, and lessons learned, with emphasis on the challenges of nowcasting and short-range NWP in complex terrain during winter.

## Context and Motivation

Since Sydney 2000, WMO/WWRP-endorsed meteorological projects have been organized for each Olympics as both Forecast Demonstration Projects (FDPs, demonstrating established technologies) and Research and Development Projects (RDPs, advancing new methods). FROST-2014 addressed the particularly challenging problem of winter mountain forecasting, building on the experience of SNOW-V10 (Vancouver 2010), which was the first winter Olympics nowcasting project in complex terrain. The Sochi mountain cluster in the Krasnaya Polyana area of the Caucasus presented difficult forecasting challenges including foehn events, orographic precipitation, rapid visibility changes, and complex terrain–airflow interactions.

## Key Scientific Contributions

- Documented the first large-scale international intercomparison of nowcasting and NWP systems for complex winter mountain terrain in an operational Olympic context
- Demonstrated clear benefit of hectometric-scale NWP (0.25 km GEM) for visibility prediction in complex terrain: GEM-0.25 was the most successful model for the critical 16 Feb 2014 low-visibility event
- Showed that HARMONIE-AROME (1 km) performed best overall among deterministic NWP models when averaged across all verification metrics
- Established that blended NWP-observation nowcasting systems (INTW, ABOM) — including ECCC's GEM at 1 km and 0.25 km — generally outperformed individual models
- Identified wind forecasting in complex terrain as the weakest point of all participating systems (underestimation of gusts by 3.5–7 m s⁻¹)

## Methods Summary

Verification period: 15 January to 18 March 2014. Forecasts compared against near-surface station data at the 5 Olympic sport venues in the mountain cluster. Systems with gridded output were verified against the closest grid point (no vertical adjustment for terrain differences). Aggregation of verification scores was performed over groups of similar stations to reduce representativeness noise. Metrics included mean absolute error (MAE) for continuous variables and the Extremal Dependence Index (EDI) for precipitation occurrence (a threshold-based skill score suited to rare events). Nine deterministic NWP models at resolutions from 1.1 to 20 km, plus convection-permitting ensemble systems, were evaluated.

## Key Results

- **Resolution scaling**: Increasing GEM resolution from 2.5 to 1 km improved T2m clearly; GEM-0.25 showed additional benefit for visibility; for nighttime wind direction, GEM-0.25 helped but made wind speed slightly worse at some stations
- **COSMO**: The refinement from 7 to 2.2 km improved T2m, RH2m, and wind direction; further refinement to 1.1 km primarily benefited wind speed
- **Critical event (16–17 Feb 2014 low visibility)**: GEM-0.25 (forecast from 0000 UTC 16 Feb) realistically reproduced the timing of the sharp visibility reduction; the predicted afternoon window of good visibility on 17 Feb was used operationally to reschedule the women's biathlon mass start
- **General model difficulty**: Foehn events caused T2m errors of 1.4°–4.4°C in most models; precipitation dissipation events (precipitation predicted but not observed) and strong wind gusts were poorly handled by all systems

## Limitations and Caveats

- The observational network, although substantially enhanced for the Games, remained insufficient to fully characterize precipitation type and visibility in complex terrain (some areas were shaded from radar by mountains)
- Comparing models on different computational grids with different station proximity creates an inherent representativeness bias in the verification
- Nowcasting systems developed primarily for summer convective weather and flat terrain performed below their potential in winter mountain conditions
- The analysis is largely descriptive; quantitative model rankings depend strongly on the aggregation scheme and choice of verification metric

## Relation to Author's Research Program

Milbrandt is the 8th of 21 co-authors, representing ECCC's contribution to FROST-2014. His role was as the developer and provider of the GEM-LAM (Global Environmental Multiscale – Limited Area Model) forecast system at 2.5 km, 1 km, and 0.25 km horizontal grid spacings. The GEM system used in FROST-2014 is the same system described in Milbrandt et al. (2016) — the Pan-Canadian High-Resolution Deterministic Prediction System (HRDPS). ECCC also contributed three nowcasting systems (ABOM, INTW, CARDS) that used GEM output as their NWP component. This paper is relevant to Milbrandt's work as an applied demonstration of ECCC's high-resolution GEM system in a real, high-stakes, operationally demanding forecast environment — particularly the GEM-0.25 km system's performance in the critical 16 Feb visibility event.

## Impact and Citations

**Citation count:** ~19 (Semantic Scholar, retrieved 2026-06-06)

This is a moderately cited project overview paper. The 19 citations reflect its specialized audience within the nowcasting and high-resolution NWP communities interested in winter Olympic meteorology and complex terrain forecasting. As a BAMS article, it serves as the primary project documentation reference and is cited by follow-on work describing the ICE-POP 2018 project (PyeongChang Winter Olympics) and related nowcasting verification studies.
