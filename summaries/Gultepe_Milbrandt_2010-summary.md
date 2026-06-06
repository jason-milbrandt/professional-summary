# Summary: Gultepe and Milbrandt (2010)

**Full citation:** Gultepe, I., and J. A. Milbrandt, 2010: Probabilistic Parameterizations of Visibility Using Observations of Rain Precipitation Rate, Relative Humidity, and Visibility. *J. Appl. Meteor. Climatol.*, **49**, 36–46.
**Journal:** Journal of Applied Meteorology and Climatology
**Year:** 2010
**Authors:** I. Gultepe, J. A. Milbrandt (2 authors; Milbrandt is 2nd)
**DOI:** 10.1175/2009JAMC1927.1
**Author's role:** Tier 3 — contributed NWP modeling expertise and GEM model context; primary observational analysis and parameterization development was Gultepe's

---

## Overview

This paper develops new probabilistic parameterizations of atmospheric visibility as functions of rain precipitation rate (PR) and relative humidity (RHw), using multi-year surface observations from the FRAM (Fog Remote Sensing and Modeling) field project in Ontario and Nova Scotia. The key finding is that existing NWP visibility parameterizations show large errors relative to observations, and that a probabilistic (percentile-based) approach — rather than a single deterministic curve — is better suited for operational use, particularly for extreme-weather applications such as aviation hazard assessment.

## Context and Motivation

Visibility parameterizations in NWP models (e.g., the RUC model's Vis–RHw relationship) were derived from limited measurements and show systematic biases: overestimating Vis near saturation and underestimating it at lower RHw. Existing Vis–PR relationships also show up to an order of magnitude of scatter for a given PR, making single-curve deterministic parameterizations unreliable. The FRAM project provided a comprehensive multi-season, multi-site dataset to derive improved relationships applicable to operational forecast models.

## Key Scientific Contributions

- Derived new Vis–RHw relationships from FRAM observations (FRAM-C and FRAM-L) for both mean and percentile (5%, 50%, 95%) curves, showing substantial departures from RUC model parameterizations.
- Derived new Vis–PR relationships for rain and drizzle using deterministic and probabilistic approaches, with application-specific guidance (5% curve for hazard-critical situations, 50% for most-likely Vis).
- Identified drizzle (100–500 μm drops, PR < ~2 mm h⁻¹) as an under-recognized contributor to low visibility, reducing Vis by at least a factor of 2 relative to rain for a given PR.
- Demonstrated an integrated visibility approach combining RHw-, fog LWC-, and rain-based extinction coefficients for co-occurring fog and rain events, validated against a GEM model case study.
- Confirmed (via Ott Parsivel data) that raindrop number concentration ($N_d$) should be included as an independent variable in Vis parameterizations alongside PR.

## Methods Summary

Surface observations from three FRAM field sites (CARE/Toronto, winter 2005/06; Lunenburg NS, summers 2006 and 2007) using Vaisala FD12P (Vis and PR), YES TPS hot plate (validation of PRR), Ott Parsivel disdrometer (DSD), and Campbell HMP45 (RHw, T). Data filtered to isolate precipitation-only effects on Vis (RHw > 95%, PR > 0.1 mm h⁻¹). Percentile fits applied to binned data to construct probabilistic curves. GEM NWP model outputs used in a brief integrated Vis case study (11 Feb 2009).

## Key Results

- At PRR = 10 mm h⁻¹, observed Vis ranges from ~1.5 km (5th percentile) to ~5 km (95th percentile) — a factor of ~3 spread.
- RUC Vis near RHw = 100% is significantly higher than FRAM observations; at RHw < 95%, RUC Vis is significantly lower.
- Drizzle events occurred ~30% of the time during FRAM-L, and drizzle Vis values were substantially lower than rain Vis for the same liquid PR.
- The integrated Vis approach (GEM outputs, 11 Feb 2009 case) agreed well with observed Vis during fog–rain co-occurrence between 1400–1830 UTC.

## Limitations and Caveats

- Observations are limited to two geographic sites (southern Ontario and Nova Scotia); applicability to other regions or aerosol regimes requires further validation.
- PRR accuracy degrades significantly at drizzle rates (< 0.5 mm h⁻¹), where uncertainty can exceed 75%.
- Snow PR measurements were excluded; snow visibility parameterizations were not addressed.
- The integrated Vis approach requires model LWC within the lowest atmospheric layer (~50 m) — a quantity not always directly available from NWP output.

## Relation to Author's Research Program

Milbrandt is the 2nd author of this 2-author paper. His contribution was providing NWP context and modeling expertise, including the GEM model application used in the integrated visibility case study at the paper's conclusion. The paper does not use the MY microphysics scheme — unlike the companion 2007 paper (Gultepe and Milbrandt 2007) which explicitly used it for fog simulation. The work is peripheral to Milbrandt's core research program in cloud microphysics parameterization, but reflects his co-investigator role in the FRAM project and his contributions to Environment Canada's operational NWP system.

## Impact and Citations

**Citation count:** ~77 (Semantic Scholar, retrieved 2026-06-06)

This paper has had solid uptake in the fog and visibility forecasting literature, frequently cited in studies developing or evaluating NWP visibility schemes, particularly those addressing the need for probabilistic approaches and improved treatment of drizzle. It is a companion to the 2007 Gultepe–Milbrandt PAGEOPH paper and is often cited alongside it in the fog modelling community. ⚠ verify specific citing papers
