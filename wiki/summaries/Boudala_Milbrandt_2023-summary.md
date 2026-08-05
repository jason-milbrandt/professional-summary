# Summary: Boudala and Milbrandt (2023)

**Full citation:** Boudala, F.S. and J.A. Milbrandt, 2023: Solid Precipitation and Visibility Measurements at the Centre for Atmospheric Research Experiments in Southern Ontario and Bratt's Lake in Southern Saskatchewan. *Remote Sensing*, **15**, 4079. DOI: 10.3390/rs15164079
**Journal:** Remote Sensing
**Year:** 2023
**Authors:** Faisal S. Boudala, Jason A. Milbrandt
**DOI:** 10.3390/rs15164079
**Author's role:** Tier 3 — Writing review and editing only; no intellectual leadership in study design or analysis (explicitly stated in author contributions)

---

## Overview

This paper evaluates solid precipitation gauges and non-traditional sensors at two Canadian field sites (CARE in Ontario and Bratt's Lake in Saskatchewan), develops transfer functions to correct wind-induced undercatch, and derives new visibility-snowfall parameterizations for aviation applications. Despite Milbrandt being listed as second author, his contribution was limited to manuscript review and editing. The scientific work — instrument comparison, transfer function derivation, visibility parameterization — was led entirely by Boudala.

## Context and Motivation

Wind-induced undercatch is the primary accuracy problem for solid precipitation gauges. Transfer functions (TFs) correcting for wind speed have been developed from a variety of datasets, but few incorporate fall velocity as an explicit predictor, and TFs derived at one site often show substantial error when applied elsewhere. Accurate solid precipitation measurements are also needed to develop and validate visibility-snowfall parameterizations used in aviation and NWP.

## Key Scientific Contributions

- Derived new transfer functions for double Alter shielded (DAS) Geonor gauges at CARE site, incorporating both wind speed and fall velocity; the multi-predictor TF achieved near-zero bias vs. DFAR reference.
- Showed that existing "universal" TFs (multi-site SPICE) and Marshall-site TFs have notable site-specific biases when applied to CARE and Bratt's Lake data.
- Demonstrated that the HotPlate precipitation sensor is the best non-traditional instrument (−3.4% bias vs. DFAR), while FD12P underestimates by 32% and PARSIVEL2 overestimates by 28%.
- Found strong correlation (R = 0.9) between DFAR solid precipitation intensity and observed visibility, supporting existing aviation parameterizations.
- Developed new Vis–S parameterizations consistent with Boudala and Isaac (2009); temperature adds no significant improvement.

## Methods Summary

Two field sites: CARE (Egbert, Ontario; 2012–2013 SPICE data) and Bratt's Lake (Saskatchewan; 2021–2022). DFAR-shielded Geonor gauge used as reference standard. 30-min averaged data for catch efficiency; 10-min for precipitation type/wind analyses. Transfer functions fitted via least-squares regression. CARE TFs tested as independent validation at Bratt's Lake. Visibility-precipitation relationships derived from co-located FD12P and DFAR measurements.

## Key Results

- DAS Geonor and SAS Pluvio2 both ~70% catch efficiency at CARE; DAS Pluvio at Bratt's Lake ~66%.
- DAS TF(U, V) achieves no systematic bias vs. DFAR; TF(U) alone leaves ~6% residual error.
- CARE-derived DAS TF applied to Bratt's Lake: R = 0.86 but overestimates accumulation by ~12%.
- Locally fitted Bratt's Lake TF performs much better — underscoring site specificity.
- HotPlate bias: −3.4%; FD12P: −32%; PARSIVEL2: +28%.
- VIS–S correlation R = 0.9; new parameterization matches SAE de-icing intensity thresholds better than prior equations.

## Limitations and Caveats

- Transfer functions are site-specific; CARE-derived TF overestimates by 12% at Bratt's Lake, limiting operational generalizability.
- Fall velocity TF could not be tested at Bratt's Lake due to lack of reliable fall velocity data there.
- Visibility parameterizations derived at a single site (CARE) under relatively low-wind conditions; performance in windier or mixed-phase environments is untested.

## Relation to Author's Research Program

Milbrandt's role was writing review and editing only. This paper is tangentially relevant to his work — visibility-snowfall parameterizations and solid precipitation validation are inputs to NWP model evaluation, which connects to his microphysics scheme development. However, Milbrandt did not contribute to the scientific design, analysis, or parameterization work.

## Impact and Citations

**Citation count:** ~1 (Semantic Scholar, retrieved 2026-06-06)

Very recent paper (2023) with only 1 citation to date. The work addresses a practical problem in cold-climate precipitation measurement and is part of Boudala's ongoing observational research program at ECCC. Uptake is expected to be gradual given the specialized, site-specific nature of the findings.

## Related topics
- [[fog-visibility]]
