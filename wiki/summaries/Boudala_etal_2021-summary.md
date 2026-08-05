# Summary: Boudala et al. (2021)

**Full citation:** Boudala, F.S., I. Gultepe, and J.A. Milbrandt, 2021: The Performance of Commonly Used Surface-Based Instruments for Measuring Visibility, Cloud Ceiling, and Humidity at Cold Lake, Alberta. *Remote Sensing*, **13**, 5058. DOI: 10.3390/rs13245058
**Journal:** Remote Sensing
**Year:** 2021
**Authors:** Faisal S. Boudala, Ismail Gultepe, Jason A. Milbrandt
**DOI:** 10.3390/rs13245058
**Author's role:** Tier 3 — Writing review and editing only; no intellectual leadership in study design or analysis

---

## Overview

This paper evaluates the performance of commonly used ground-based automated instruments for measuring visibility (VIS), cloud base height (CBH), and relative humidity (RH) at Cold Lake Airport, Alberta, using two years (2015–2016) of observations. Instruments including Vaisala present weather sensors, a Jenoptik ceilometer, a microwave radiometer, and various humidity sensors were compared against standard reference instruments and human observations. The study finds systematic biases and quantization issues in automated instruments, with important implications for their use in aviation safety and NWP model validation.

## Context and Motivation

Automated meteorological sensors are increasingly deployed at airports and remote locations, replacing or supplementing human observers. However, their accuracy relative to standard references and human observation had not been rigorously tested in cold-climate Canadian conditions. Low visibility and ceiling are responsible for a large fraction of weather-related aviation accidents, making instrument accuracy critical.

## Key Scientific Contributions

- Quantified biases between two Vaisala present weather sensors (FS11P vs. PWD22): the FS11P consistently measured higher VIS, with mean differences up to 2.18 km under fog/clear conditions.
- Showed that both instruments report higher VIS than human observers (R ≈ 0.6), with PWD22 being slightly closer to human observation (MD ≈ 0.98 km vs. 1.37 km for VIS < 5 km).
- Established that the Jenoptik ceilometer provides a reasonable CBH estimate (MD ≈ 390 m vs. human, R = 0.80), while the microwave radiometer CBH is unreliable (MD ≈ 1 km, R = 0.65).
- Demonstrated systematic RH underestimation (2–6%) by all tested sensors relative to the AES-Dewcell standard, with errors increasing near saturation (up to ~10% for WXT520 at 100% RH).
- Developed two new extinction-vs-snowfall-rate parameterizations from Cold Lake data, showing differences from prior Ontario-based parameterizations.

## Methods Summary

Two years (2015–2016) of surface observations from the 4Wing Cold Lake Research project at Cold Lake Airport, Alberta (54°N, 110°W). Instruments at an ECCC research site were compared against the standard AES-Dewcell humidity instrument (at a DND site ~948 m away) and trained human observers following MANOBS protocols. Statistical metrics include correlation coefficient (R), mean difference (MD), and best-fit regression lines for binned data.

## Key Results

- VIS (instrument vs. instrument): R = 0.84 (precipitation), R = 0.96 (non-precipitation); FS11P biased high by 410 m–2180 m relative to PWD22 depending on conditions.
- VIS (instrument vs. human): R ≈ 0.6; PWD22 MD = 0.98 km, FS11P MD = 1.37 km for VIS < 5 km.
- CBH (ceilometer vs. human): MD = 390 m (all), 100 m (CBH < 4 km), R = 0.80.
- CBH (MWR): overestimates for CBH < 2 km, underestimates for higher CBH; MD ≈ 1 km, R = 0.65.
- RH: all sensors underestimate vs. AES-Dewcell; WXT520 worst at saturation (~10% error at 100% RH).
- Temperature: excellent agreement across all sensors (R > 0.99, MD < 0.1°C).

## Limitations and Caveats

- Human observations have coarse quantization (1/8 SM increments), making direct comparisons ambiguous at higher VIS values.
- DND Dewcell reference site is ~948 m from the ECCC instrument site, introducing spatial sampling mismatch for RH comparisons.
- Ceilometer underperforms for spatially limited clouds (e.g., convective cells) not directly overhead.
- Extinction parameterizations derived at one site; representativeness for other cold-climate locations is not established.

## Relation to Author's Research Program

Milbrandt's contribution was limited to writing review and editing. This paper is relevant to his work insofar as visibility, cloud base, and humidity measurements are used to validate NWP model output — a context directly relevant to his microphysics parameterization research. However, this paper is observational and instrument-focused rather than model-focused, and Milbrandt did not drive the scientific direction.

## Impact and Citations

**Citation count:** ~9 (Semantic Scholar, retrieved 2026-06-06)

The paper addresses a practical and underserved need in cold-climate aviation meteorology. With 9 citations since 2021, uptake has been modest, consistent with its role as a specialized instrument-evaluation study rather than a methods or parameterization paper. It is part of a series of Cold Lake field campaign publications led by Boudala ⚠ verify.
