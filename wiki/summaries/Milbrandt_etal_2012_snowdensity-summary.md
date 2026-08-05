# Summary: Milbrandt, Glazer, and Jacob (2012)

**Full citation:** Milbrandt, J. A., A. Glazer, and D. Jacob, 2012: Predicting the snow-to-liquid ratio of surface precipitation using a bulk microphysics scheme. *Mon. Wea. Rev.*, **140**, 2461–2476.
**Journal:** *Monthly Weather Review*
**Year:** 2012
**Authors:** J. A. Milbrandt, A. Glazer, D. Jacob
**DOI:** 10.1175/MWR-D-11-00286.1
**Author's role:** Tier 1 — Lead author; developed the snow-to-liquid ratio prediction method and updated MY2 snow category for operational deployment

---

## Overview

This paper introduces and evaluates a new method to predict the instantaneous snow-to-liquid ratio (SLR) of precipitating snow directly from a bulk microphysics scheme (BMS), eliminating the need to estimate an average snow density for a given event. The method computes the volume flux of solid precipitation independently from the mass flux by exploiting the variable bulk snow density implied by the scheme's mass–diameter relation ($d_s \approx 2$ implies snow density decreasing with particle size). Implemented in the two-moment Milbrandt–Yau scheme (MY2) and run in real time during the Vancouver 2010 Winter Olympics on 2.5- and 1-km grids, the method produces a realistic distribution of SLR values consistent with 20-year climatological observations. The paper also documents several key improvements to the MY2 snow category implemented at this time — the "modernization" announced in IMPROVE-2 Part II.

## Context and Motivation

Operational snowfall forecasting in NWP models typically converts the liquid-equivalent QPF to snow depth by multiplying by an assumed SLR (often the "10-to-1" rule, or a climatologically tuned value). This is inadequate when SLR varies considerably — from 1.9 to 46.8 in a 22-year U.S. climatology (Roebber et al. 2003). More sophisticated methods use NWP sounding statistics or neural networks, but these cannot be applied at arbitrary grid points and do not use the detailed microphysical information available in modern BMSs. As high-resolution models with detailed bulk schemes become operational, an opportunity exists to predict SLR *directly* from the scheme's prognostic variables at no additional computational cost. This paper seizes that opportunity, motivated in part by the real operational challenge of precipitation-type and snowfall-intensity forecasting for the 2010 Vancouver Winter Olympics venues.

## Key Scientific Contributions

- **Introduced the first method to predict SLR explicitly from a BMS** ⚠ verify (claimed in the paper as "first attempt to our knowledge"), using the volume flux of solid precipitation computed independently from the mass flux — a fundamentally different approach from the traditional estimation/application of an assumed SLR.
- **Generalized the volume flux computation for variable-density snow**: for snow with the MY2 $d_s \approx 2$ $m$–$D$ relation, the volume flux is computed by integrating $(\pi/6)D^3 V_s(D) N_s(D)$ directly, rather than dividing mass flux by a fixed density — correctly capturing the inverse size–density relationship.
- **Introduced a liquid fraction correction** for partially melted snow to prevent unrealistically large SLRinst in the melting layer, approximating the liquid fraction as the fraction of total ice-plus-rain mass that is already rain.
- **Documented the comprehensive snow-category modernization of MY2**, including: (a) new $m$–$D$ parameters ($c_s = 0.1597$, $d_s = 2.078$) based on video disdrometer observations (Brandes et al. 2007); (b) new V–D parameters for faster-falling snow (Locatelli and Hobbs 1974 "aggregate" type); (c) PSD slope/intercept constraints ($\lambda_{s,min} = 600$ m⁻¹, $N_{0s,max} = 10^8$ m⁻⁴); (d) reduced capacitance for diffusional growth ($C = D/4$ vs traditional $D/2$); (e) physically based collection efficiencies for snow–cloud and graupel–cloud/rain collection.
- **Demonstrated operational deployment**: the method was run in real time by CMC during the 2010 Olympics and was subsequently incorporated into the operational 2.5-km deterministic prediction system for Canada ⚠ verify.
- **Validated the method against observations**: model SLR PDF closely matches a 20-year climatology at Whistler Mountain (mean 12.2 vs 12.6) and published U.S. climatologies (Roebber et al. 2003; Baxter et al. 2005) — agreement deemed unlikely to be fortuitous given the sensitivity of the field.

## Methods Summary

The method computes for each hydrometeor category contributing to "snow" (the observable: ice + *snow* + graupel categories in MY2) the unmelted volume flux [Eqs. (1)–(6)] using the particle mass, density, fall speed, and size distribution. For ice and graupel (constant bulk density), the volume flux is simply mass flux divided by density. For *snow* (variable density via $d_s \approx 2$), the volume flux is computed by explicit integration of $(\pi/6)D^3 V_s N_s$ over $D$. A liquid fraction correction accounts for partial melting above 0°C. The method was implemented in MY2 (two-moment, fixed-$m_x$ version) and run on 2.5- and 1-km GEM LAM grids over Vancouver–Whistler from 26 January 2010 to 2 March 2011, producing twice-daily forecasts. Verification used 941 observations at the VOA station (Whistler Mountain) from a 20-year CAA climatology.

## Key Results

- The model produced SLRinst values of ~20 (large fluffy aggregates) and ~5 (rimed/graupel-dominated), consistent with forecaster observations of the precipitation type during the 2010 Games.
- The liquid fraction correction effectively eliminated unrealistically large SLRinst values in the melting layer.
- The model SLR PDF for the 2.5-km grid closely matched the 20-year Whistler Mountain climatology (model mean 12.2 vs observed 12.6), except for underprediction of extreme values (SLR < 6 or > 18).
- No point forecast skill was found for individual cases at individual stations in this complex terrain — the field is too spatially variable for station-to-gridpoint verification.
- Composite PDF over the full 2.5-km domain closely resembled U.S. continental climatologies ⚠ verify.

## Limitations and Caveats

- The assumption of spherical snow particles (volume = $\pi D^3/6$) for the volume flux means SLRinst is an upper estimate (real aggregates are not spherical; some packing occurs).
- Constant graupel density ($\rho_g = 400$ kg m⁻³) does not capture riming-induced density variability; variable graupel density is noted as under development.
- No account of post-precipitation processes (compaction, fragmentation) — the method predicts the volume of snow as it arrives at the surface, not the eventual snowpack depth after settling.
- No forecast skill demonstrated for individual point-to-gridpoint comparisons in complex terrain; neighborhood-scale or probabilistic verification is recommended for future work.

## Relation to Author's Research Program

This paper is the implementation companion to the 1D snow-melting sensitivity study (Milbrandt et al. 2012, *Pure Appl. Geophys.*): that paper identified which snow parameters matter for the phase transition; this paper documents the updated parameters now in MY2. Together they constitute the "forthcoming paper" on snow-category modernization promised in IMPROVE-2 Part II (Milbrandt et al. 2010). The broader significance is twofold. First, it represents Milbrandt's **transition from pure scheme development to operational application**: the SLR method and snow-category updates were deployed in ECCC's real-time operational NWP system ⚠ verify, directly connecting his research to forecast products for end users. Second, the new $d_s \approx 2$ snow $m$–$D$ relation — which gives snow a realistic inverse size–density relationship — is an important step toward more physically consistent representation of ice-phase particles, anticipating the fuller variable-property approach in the P3 scheme (Morrison and Milbrandt 2015). The collaboration with Glazer ⚠ verify and Jacob ⚠ verify reflects the operational applications context of this work.

## Impact and Citations

**Citation count:** ~26 (Semantic Scholar, retrieved 2026-06-06)

As an applied operational-NWP paper focused on a specific forecast product (SLR), this paper has modest citation count compared to the scheme-description papers, consistent with its specialized audience ⚠ verify. Its significance is primarily: (a) as the documentation of important MY2 snow-category updates that affected all subsequent uses of the scheme in GEM ⚠ verify; (b) as the introduction of the explicit SLR prediction technique, which may have influenced subsequent snow-forecasting tool development ⚠ verify; and (c) as evidence of Milbrandt's growing engagement with operational NWP applications beyond basic scheme development.

## Related topics
- [[ice-phase-modernization]]
