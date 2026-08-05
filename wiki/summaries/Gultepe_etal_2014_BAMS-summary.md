# Summary: Gultepe et al. (2014)

**Full citation:** Gultepe, I., T. Kuhn, M. Pavolonis, C. Calvert, J. Gurka, A. J. Heymsfield, P. S. K. Liu, B. Zhou, R. Ware, B. Ferrier, J. Milbrandt, and B. Bernstein, 2014: Ice Fog in Arctic during FRAM–Ice Fog Project: Aviation and Nowcasting Applications. *Bull. Amer. Meteor. Soc.*, **95**, 211–226.
**Journal:** Bulletin of the American Meteorological Society
**Year:** 2014
**Authors:** I. Gultepe et al. (12 authors; Milbrandt is 11th)
**DOI:** 10.1175/BAMS-D-11-00071.1
**Author's role:** Tier 3 — contributed GEM model context and the Milbrandt–Yau microphysics scheme used operationally in the ice fog prediction section; no direct field campaign role
**Note:** This paper is duplicated as `Gultepe_BAMS_14.pdf` and `Gultepe_etal_2014_BAMS.pdf` — both are identical. The normalized stem is `Gultepe_etal_2014_BAMS`.

---

## Overview

This BAMS article presents the FRAM–Ice Fog (FRAM-IF) project, a two-month field campaign at Yellowknife International Airport (NWT, Canada, November 2010–February 2011), aimed at improving understanding of Arctic ice fog formation and developing improved prediction and nowcasting tools. The paper reports on the observational infrastructure, preliminary microphysical findings, satellite algorithm validation for GOES-R, and NWP model challenges — including explicit discussion of the Milbrandt–Yau two-moment scheme as the microphysics used in GEM and its current limitations for ice fog simulation.

## Context and Motivation

Ice fog — composed of suspended ice crystals at temperatures typically below –15°C — significantly impacts aviation and transportation in northern latitudes, occurring about 14% of the time in the Arctic winter. Existing NWP models dramatically under-predict ice crystal number concentrations (models: ~100 L⁻¹; observed: >1000 L⁻¹), making ice fog prediction unreliable. The FRAM-IF project was designed to fill this observational and parameterization gap, with a focus on aviation safety applications.

## Key Scientific Contributions

- Documented ice fog conditions at Yellowknife: 14 ice fog events, 12 frost events, and near-daily light snow during a 67-day project period.
- Measured ice crystal concentrations exceeding 1000 L⁻¹ and crystal sizes as small as 5–10 μm, with non-spherical shapes at –35°C (columns, plates) — contradicting some prior assumptions of spherical small crystals.
- Identified a factor-of-2 discrepancy between different visibility sensors during ice fog, pointing to calibration issues affecting model validation.
- Proposed a new ice fog visibility parameterization: $\text{Vis} = 1.19 (\text{IWC} \times N_i)^{-0.5066}$, requiring NWP models to predict both IWC and $N_i$.
- Validated GOES-R ABI cloud phase and low cloud detection algorithms using MODIS proxy data, demonstrating feasibility of satellite-based Arctic ice fog nowcasting.
- Explicitly identified the limitation of the Meyers et al. (1992) ice nucleation parameterization within the GEM/MY scheme for Arctic conditions.

## Methods Summary

Comprehensive instrument suite deployed at the Yellowknife Airport site: surface optical probes (FMD, GCIP, Parsivel), ice crystal imaging cameras, visibility sensors (FD12P, Sentry, SWS-200), a 40-m tower with four WXT520 sensors, profiling microwave radiometer, shortwave/IR radiometers, aerosol spectrometers, ceilometer, and a microwave rain radar. Preliminary analysis of particle imagery, size distributions, and visibility statistics. MODIS imagery used as GOES-R proxy for satellite algorithm testing. GEM and NAM model runs described in the context of ice fog prediction.

## Key Results

- Ice crystal concentrations: >1000 L⁻¹ during ice fog; models predict ~100 L⁻¹ — an order-of-magnitude underestimate.
- Ice crystal sizes: typically <200 μm; many <50 μm; smallest observed 5–10 μm.
- Crystal shapes at –35°C were non-spherical (columns, plates), contrary to assumptions of sphericity for small (<100 μm) crystals.
- Visibility sensors disagreed by a factor of ~2 during ice fog (FD12P larger than Sentry), a significant calibration concern for model validation.
- Strong surface inversions with tops at 1–1.5 km were the dominant synoptic feature associated with ice fog events.
- The GEM model with the MY microphysics scheme uses Arctic-inappropriate ice nucleation (Meyers et al. 1992) and will require updates to FRAM-IF observations.

## Limitations and Caveats

- This is a project overview / preliminary results paper; detailed quantitative analysis of the full dataset is deferred to future publications.
- Radiosonde data were only available from Fort Smith (~100 km south), limiting vertical profile information at the project site.
- Ice crystal shape/size classification from the GCIP and microscope imagery was limited by resolution.
- Visibility parameterization in Eq. (1) is derived from ISDAC data (Alaska, April 2008) — applicability to Yellowknife conditions during FRAM-IF remains to be validated.

## Relation to Author's Research Program

Milbrandt is the 11th of 12 authors. His contribution was providing the operational GEM model framework — specifically, the two-moment Milbrandt–Yau (MY) microphysics scheme — which is cited as the current operational tool for ice fog prediction in Canada. The paper explicitly describes both the strengths of the MY approach (prognostic $N_i$ enables IWC×$N_i$ visibility parameterization) and its current Arctic limitation (Meyers et al. ice nucleation inappropriate for very cold, clean Arctic conditions). This is relevant to Milbrandt's research program as evidence that the MY scheme's prognostic-number-concentration design is necessary for ice fog prediction, and as a pointer to where Arctic-specific microphysics improvements are needed.

## Impact and Citations

**Citation count:** ~83 (Semantic Scholar, retrieved 2026-06-06)

This BAMS overview paper has been widely cited in the Arctic fog, ice fog, and polar meteorology communities. As a comprehensive project description with broad scope (instrumentation, satellite, NWP), it serves as the primary reference for the FRAM-IF dataset and has influenced subsequent ice fog parameterization and satellite detection studies. ⚠ verify specific citing papers

## Related topics
- [[fog-visibility]]
