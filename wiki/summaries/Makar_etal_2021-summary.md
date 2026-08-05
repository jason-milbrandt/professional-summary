# Summary: Makar et al. (2021)

**Full citation:** Makar, P. A., Akingunola, A., Chen, J., Pabla, B., Gong, W., Stroud, C., Sioris, C., Anderson, K., Cheung, P., Zhang, J., and Milbrandt, J., 2021: Forest-fire aerosol–weather feedbacks over western North America using a high-resolution, online coupled air-quality model. *Atmos. Chem. Phys.*, **21**, 1–31. DOI: 10.5194/acp-21-1-2021
**Journal:** Atmospheric Chemistry and Physics
**Year:** 2021
**Authors:** Paul A. Makar, Ayodeji Akingunola, Jack Chen, Balbir Pabla, Wanmin Gong, Craig Stroud, Christopher Sioris, Kerry Anderson, Philip Cheung, Junhua Zhang, Jason Milbrandt
**DOI:** 10.5194/acp-21-1-2021
**Author's role:** Tier 3 — Provided indirect effect implementation updates and advice on integrating the AIE within the P3 microphysics scheme; contributed to manuscript review (11th of 11 authors)

---

## Overview

This paper investigates how forest-fire aerosols feed back on weather and air quality when their direct and indirect radiative effects are simulated within a high-resolution online coupled air-quality model (GEM-MACH). Running paired feedback and no-feedback simulations at 2.5 km resolution over western North America during a summer 2019 fire season, the authors show that incorporating aerosol–weather feedbacks improved forecast accuracy for both meteorological and chemical variables at statistically significant levels. The work also introduced the first operational online forest-fire plume-rise scheme (CFFEPSv4.0) embedded within an NWP-coupled system, allowing fire-induced meteorological changes to influence plume injection heights in real time.

## Context and Motivation

Prior operational air-quality models predicted forest-fire plume rise using a priori weather forecasts — they lacked feedback from the fires' own aerosols on atmospheric stability and cloud microphysics. Research had established that large forest fires significantly perturb regional weather (temperature, boundary layer height, cloud cover), yet operational forecast systems were not capturing these feedbacks. With ~2.5 km grid spacing now feasible in operational NWP, detailed double-moment bulk microphysics schemes (like P3) can represent the aerosol indirect effect (AIE), making online coupled fire–weather–chemistry simulations tractable.

## Key Scientific Contributions

- First implementation of online forest-fire plume-rise calculations (CFFEPSv4.0) within an NWP-coupled operational air-quality forecast model, allowing aerosol-modified meteorology to feed back into plume-rise predictions
- Demonstrated that ADE and AIE feedbacks from forest-fire aerosols improve both weather and chemistry forecasts: 35 out of 48 air-quality metrics and most meteorological metrics improved at 90% confidence
- Quantified the AIE feedback loop: fire smoke increases near-surface stability, retaining more PM aloft as CCN, increasing cloud droplet numbers, cooling the atmosphere below clouds, and maintaining the unstable near-surface lapse rate
- Identified a novel model spin-up issue in online coupled systems: ~6 h of adjustment are needed for cloud fields to equilibrate with aerosol concentrations at the start of each forecast cycle
- Showed that lateral boundary condition choice dominates overall chemistry performance, with ECMWF + 10 km GEM-MACH boundaries improving AOD but degrading surface PM₂.₅/O₃/NO₂ relative to MOZART2009 climatology

## Methods Summary

GEM-MACH (Global Environmental Multiscale – Modelling Air-quality and CHemistry) v2 was run at 2.5 km horizontal resolution over a 900 × 1370 grid domain covering western Canada and the USA. The study period was 4 July – 5 August 2019, coinciding with large Alberta–Saskatchewan forest fires and the FIREX-AQ field campaign. Two parallel 24 h forecast cycles were run: (1) a feedback simulation with online ADE and AIE, and (2) a no-feedback simulation using time-invariant climatological aerosol optical properties and CCN.

The AIE was represented using the modified P3 cloud microphysics scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016), driven by an aerosol-specific nucleation scheme. The no-feedback runs used P3 with a fixed single log-normal aerosol population (100 nm, 300 cm⁻³ pure ammonium sulfate). Forest-fire emissions were computed by CFFEPSv4.0, running online within GEM-MACH and using model-generated lapse rates for thermodynamic plume-rise calculations. Model performance was evaluated against surface stations (AQS/NAPS networks for chemistry; standard meteorological networks), radiosondes, and MODIS AOD retrievals, using 90% confidence intervals following Geer (2016).

## Key Results

- **Weather:** Feedback improved surface temperature at 5 of 8 evaluated forecast hours (>90% confidence); surface pressure, dew-point, sea-level pressure, and 10 m wind speed also improved. Upper-air temperature profiles improved at multiple levels at forecast hours 12 and 24.
- **Chemistry:** 35/48 air-quality metrics improved with feedback; improvements were most pronounced for PM₂.₅, followed by O₃, with marginal changes in NO₂.
- **Cloud microphysics:** Near-surface and lower-troposphere cloud droplet numbers increased significantly (>90% confidence) in the fire-affected northern domain; raindrop numbers increased aloft over fires and ocean.
- **Atmospheric structure near fires:** Near-surface temperatures decreased by up to −0.5°C within the smoke layer (hybrid levels 0.893–0.848); stability increased within the smoke and above but decreased near the surface below the plume.
- **Pollutant redistribution:** Near-surface PM₂.₅ decreased near fires while PM₂.₅ aloft increased at >90% confidence; O₃ decreased in the lower troposphere near fires.
- **AOD:** Systematically biased low overall (homogeneous mixture assumption); large fire plumes locally biased high (suggesting forest-fire particles are less hygroscopic than assumed).

## Limitations and Caveats

- Forecast cycle duration was limited to 24 h by operational constraints (FIREX-AQ delivery window); longer simulations may be needed to establish higher confidence in some findings
- The identified model spin-up issue (first ~6 h degradation) could be mitigated by including chemistry variables during meteorological spin-up, but was not addressed within this study
- Aerosol optical properties are treated using a homogeneous mixture assumption, leading to AOD underprediction away from fires; external mixture assumptions may be more appropriate
- Forest-fire aerosol hygroscopicity may be overestimated; separate treatment of fire vs. anthropogenic aerosol optical properties is recommended for future work
- Lateral boundary condition quality (from ECMWF reanalysis and 10 km GEM-MACH) significantly influenced inner-domain chemical performance and was identified as a major uncertainty

## Relation to Author's Research Program

Milbrandt's contribution was technical: he provided updates to the aerosol indirect effect implementation and specific advice on how the AIE is realized within the P3 microphysics scheme. The P3 scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016) is the foundation of the online-coupled cloud microphysics used in GEM-MACH to represent the AIE — the scheme's double-moment structure for cloud droplets and ice is what makes it possible to respond to predicted CCN concentrations. This paper is relevant to Milbrandt's research program as an operational demonstration that the P3 scheme, originally designed for NWP contexts, enables physically meaningful aerosol–cloud–weather feedbacks at high resolution in air-quality forecast systems.

## Impact and Citations

**Citation count:** ~26 (Semantic Scholar, retrieved 2026-06-06)

This paper has accumulated a moderate citation count since 2021, reflecting growing interest in online coupled air-quality/weather systems and fire–aerosol–weather interactions. It serves as a methodological reference for implementing fire feedback in operational NWP-coupled air-quality models, and is directly relevant to the FIREX-AQ community. Its documentation of the model spin-up issue in online coupled systems, and the boundary condition sensitivity analysis, are particularly useful for groups developing similar systems. ⚠ verify downstream implementations or specific citations by other groups.
