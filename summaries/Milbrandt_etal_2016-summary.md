# Summary: Milbrandt et al. (2016)

**Full citation:** Milbrandt, J. A., S. Bélair, M. Faucher, M. Vallée, M. L. Carrera, and A. Glazer, 2016: The pan-Canadian high resolution (2.5 km) deterministic prediction system. *Wea. Forecasting*, **31**, 1791–1816, https://doi.org/10.1175/WAF-D-16-0035.1
**Journal:** Weather and Forecasting
**Year:** 2016
**Authors:** Jason A. Milbrandt, Stéphane Bélair, Manon Faucher, Marcel Vallée, Marco L. Carrera, Anna Glazer
**DOI:** 10.1175/WAF-D-16-0035.1
**Author's role:** Tier 1 — Lead author; led the design, implementation, and verification of the HRDPS 2.5-km operational NWP system

---

## Overview

This paper provides a comprehensive description and evaluation of Canada's first pan-national kilometer-scale operational numerical weather prediction (NWP) system: the High Resolution Deterministic Prediction System (HRDPS) at 2.5-km grid spacing, which became operational in November 2014. The system is built around the GEM forecast model and uses the Milbrandt–Yau two-moment bulk microphysics scheme (MY2). The paper documents the system architecture, demonstrates its added value over the existing operational 10-km RDPS through objective skill scores against surface observations, cloud cover, and upper-air soundings, and presents a convective case study. It also describes subsequent 2015 upgrades including a freezing rain fix to MY2.

## Context and Motivation

Operational weather centers worldwide were moving toward kilometer-scale NWP systems in the early 2010s (e.g., NOAA's 3-km HRRR, Météo-France's AROME at 2.5 km, UK Met Office at 1.5 km). MSC/ECCC had been building toward this capability through a decade of experimental runs over regional domains, accumulating experience from the Vancouver 2010 Olympics, FROST-2014 (Sochi), and the 2015 Pan American Games. The pan-Canadian HRDPS replaced a patchwork of regional 2.5-km windows with a single coherent system. The publication provides the first formal documentation and verification of this operational system for the scientific community.

## Key Scientific Contributions

- First comprehensive description of Canada's pan-Canadian 2.5-km real-time operational NWP system (HRDPS)
- Demonstrated the system's overall improved forecast skill over the 10-km RDPS for surface fields and cloud cover across most regions and seasons
- Demonstrated the value of hydrometeor "recycling" (hot start) for reducing spin-up time: precipitation reaches ~65% of equilibrium after 1 h vs. ~12% for a cold start
- Documented the land data assimilation component (CaLDAS, EnKF-based with 24 members) as an important source of added surface IC value at kilometer scale
- Identified a moist bias in the mid-to-lower troposphere in winter traceable to the MY2 microphysics scheme (excessive snow sublimation), pointing to a specific model development target
- Described a targeted modification to MY2 to correct systematic missed freezing rain forecasts: restricting three-component freezing to temperatures < −5°C to prevent excessive reglaciation of supercooled rain
- Outlined the development pathway toward the P3 microphysics scheme as the planned replacement for MY2 in a future HRDPS version

## Methods Summary

- **Model:** GEM at 2.5 km (0.0225° latitude), 62 vertical levels, 48-h integrations four times daily, with hydrometeor "hot start" from a 6-h cycle
- **Microphysics:** MY2 (Milbrandt and Yau 2005a,b) — two-moment, six-category
- **Surface ICs:** CaLDAS (Canadian Land Data Analysis System; Carrera et al. 2015) providing soil moisture, surface temperature, snow depth via EnKF
- **Ocean ICs (Gulf of St. Lawrence):** Coupled atmosphere–ocean GSL analysis (Smith et al. 2012)
- **Evaluation dataset:** 80 benchmark cases (40 winter, 40 summer, 2011), initialized at 0000 and 1200 UTC, 3 days apart
- **Verification metrics:** BIAS and STDE for 2-m T, 2-m T_d, 10-m V_spd, 6-h precipitation, fractional cloud cover; upper-air scores vs. radiosondes; bootstrapped confidence intervals
- **Geographic subdomains:** BC, Prairies, QC-ON, Maritimes, North, USA

## Key Results

- **Surface temperature:** HRDPS generally warm-biased relative to RDPS in winter; STDE neutral or improved in most regions; mixed results in summer
- **Humidity:** Moist bias increase in winter (also reflected in upper-air scores); STDE generally reduced in summer (improvement)
- **Wind speed:** Considerable regional dependency; improved in BC and QC-ON; degraded in Prairies and Maritimes
- **Precipitation:** Distinct reduction of overprediction bias vs. RDPS for both seasons; % correct improved in winter, neutral in summer
- **Cloud cover:** Significant improvement in winter frequency bias (near-perfect); approximately 10% improvement in percent correct in winter; modest improvement in summer overcast conditions
- **Upper air:** Mass and wind fields nearly identical to RDPS; moist bias in mid–lower troposphere in winter is a notable HRDPS deficiency
- **Deep convection case (8 July 2011):** HRDPS clearly better captures convective structure, precipitation rates (>30 mm h⁻¹), and reflectivity patterns; RDPS produces only diffuse weak precipitation

## Limitations and Caveats

- Evaluation based on 80 cases from a single year (2011); the RDPS configuration had not been modified since 2011, making direct comparison clean but potentially not representative of ongoing RDPS development
- Precipitation verification uses simple point-based comparison, which penalizes high-resolution models with the "double penalty" problem; neighborhood verification not yet applied
- Cloud cover evaluation is an approximation (spatial averaging over ~70 km × 70 km area) rather than strict simulated observations
- The system at the time was experimental/pre-operational; not yet equipped with its own upper-air data assimilation system (downscaled from 10-km RDPS)
- Moist bias traceable to MY2 not yet corrected at time of publication

## Relation to Author's Research Program

This paper documents the operational deployment of the MY2 scheme — Milbrandt's central scientific contribution — at Canada's national kilometer-scale NWP system. It is the definitive reference establishing HRDPS-MY2 as an operational configuration, and as such is widely cited by papers that use or evaluate this system ⚠ verify. The paper also serves as a bridge article: it identifies the limitations of MY2 (moist bias, freezing rain failures) that motivate the transition to P3, and explicitly states the intent to replace MY2 with P3 in a future HRDPS version — directly connecting Milbrandt's microphysics development work (MY series, P3 series) to operational NWP practice at ECCC. The freezing rain fix to MY2 described in Appendix B is an example of Milbrandt's work at the interface of research and operations.

## Impact and Citations

**Citation count:** ~152 (Semantic Scholar, retrieved 2026-06-06)

This is among Milbrandt's most-cited papers, with 152 citations reflecting its role as the primary reference for the HRDPS system. As a system description paper, it is cited by a broad range of studies that use HRDPS output or the GEM/MY2 modeling framework for forecasting and research applications — from convective storm studies to winter precipitation and aerosol–cloud interaction work (e.g., Jouan and Milbrandt 2019). The paper is also cited in international comparisons of kilometer-scale NWP systems, establishing ECCC's contribution to the global movement toward convection-permitting operational NWP ⚠ verify.
