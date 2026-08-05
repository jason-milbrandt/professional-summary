# Summary: Boudala et al. (2022)

**Full citation:** Boudala, F.S., J.A. Milbrandt, and G.A. Isaac, 2022: Evaluation of CanESM Cloudiness, Cloud Type and Cloud Radiative Forcing Climatologies Using the CALIPSO-GOCCP and CERES Datasets. *Remote Sensing*, **14**, 3668. DOI: 10.3390/rs14153668
**Journal:** Remote Sensing
**Year:** 2022
**Authors:** Faisal S. Boudala, Jason A. Milbrandt, George A. Isaac
**DOI:** 10.3390/rs14153668
**Author's role:** Tier 3 — Writing review and editing only; no intellectual leadership in study design or analysis (explicitly stated in author contributions)

---

## Overview

This paper evaluates the cloud fraction (CF), cloud type, and cloud radiative forcing (CRF) simulated by the Canadian Earth System Model (CanESM5 and CanESM2) against CALIPSO-GOCCP lidar satellite data and CERES radiation products. All model configurations underestimate global mean cloud fraction, with CanESM5 performing better than CanESM2. Regional biases in CF and CRF exceed ±40% in some locations, particularly in tropical convective regions and marine stratocumulus zones. Milbrandt's contribution was limited to writing review and editing.

## Context and Motivation

Clouds are the largest source of uncertainty in GCM-based climate projections. CanESM5, Canada's contribution to CMIP6, shows elevated climate sensitivity partly attributed to cloud representation. Evaluating cloud simulation against modern satellite datasets (CALIPSO-GOCCP and CERES EBAF4.1) is a necessary step for identifying model deficiencies. This study extends earlier CanESM2 evaluations and provides a comparison between coupled and atmospheric (AMIP) model configurations, as well as with COSP satellite-simulator-based diagnostics.

## Key Scientific Contributions

- Provided the first comprehensive evaluation of CanESM5 cloud fraction and type against CALIPSO-GOCCP, showing improvement over CanESM2 (global total CF bias −2% vs. −6.4% for coupled versions).
- Demonstrated that AMIP and fully coupled configurations produce similar CF biases, suggesting cloud parameterizations (dynamics, microphysics) rather than ocean-atmosphere coupling are the primary source of error.
- Showed that COSP satellite simulator-based CF products tend to show larger negative biases than direct model CF, complicating like-for-like comparisons.
- Identified key regional CF problem areas: overestimation in ITCZ/tropical HLC and polar regions; underestimation in marine stratocumulus regions and mid-level clouds globally.
- Evaluated cloud radiative forcing at TOA, surface, and atmosphere, finding geographically significant biases (up to ±40 W m⁻²) correlated with low-level and high-level cloud fraction errors.

## Methods Summary

CALIPSO-GOCCP data (2007–2019, 2°×2° grid, 40 vertical levels) used as cloud fraction reference. CERES EBAF4.1 used for radiation validation. Six model configurations compared: coupled and AMIP modes of both CanESM5 and CanESM2, plus COSP-simulator variants. Statistical metrics: global mean bias (MD), RMSE, and geographic bias distributions. Seasonal analysis for DJF and JJA.

## Key Results

- Global total CF bias ranges from −2.0% (coupled-CanESM5) to −7.1% (COSP-AMIP-CanESM2); all models underestimate.
- RMSE for total CF: 10–12% across all configurations; CanESM5 consistently better than CanESM2.
- MLC most poorly simulated: globally averaged bias of −7.6% for CanESM5 (COSP).
- Regionally, biases exceed ±40% CF in tropical oceanic and marine stratocumulus regions.
- NetCRF globally: slight negative biases; geographic distribution biases up to ±40 W m⁻², strongly correlated with LL and HL cloud fraction errors.
- CanESM5 liquid low-level clouds are vertically shallower than GOCCP observations.

## Limitations and Caveats

- CALIPSO-GOCCP is itself subject to retrieval uncertainties, particularly for mixed-phase and optically thin clouds.
- COSP simulator introduces additional complexity in interpretation — some biases may reflect simulator limitations rather than model deficiencies.
- Attribution of CF biases to specific physical processes (microphysics, dynamics, convective parameterization) is not performed in this study.
- Analysis focused on monthly/seasonal climatologies; sub-seasonal variability not assessed.

## Relation to Author's Research Program

Milbrandt's role was writing review and editing only. The subject matter — climate model evaluation of cloud fraction climatology — is relatively distant from his core research on cloud microphysics parameterization for NWP. The connection is that cloud microphysics schemes (including Milbrandt–Yau-type parameterizations) ultimately feed into GCMs and contribute to cloud fraction biases like those documented here, but this paper does not address NWP-scale microphysics. Milbrandt is credited because of his ECCC affiliation and expertise, not because of a substantive intellectual contribution to this work.

## Impact and Citations

**Citation count:** ~7 (Semantic Scholar, retrieved 2026-06-06)

With 7 citations since 2022, the paper has seen modest uptake. GCM cloud evaluation papers have a fairly specialized audience; this contribution is relevant primarily to the CanESM development community and climate modelers working on Canadian ESM configurations.
