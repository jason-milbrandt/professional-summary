# Gultepe et al. (2014) — Ice Fog in Arctic during FRAM–Ice Fog Project: Aviation and Nowcasting Applications

**Full citation:** Gultepe, I., T. Kuhn, M. Pavolonis, C. Calvert, J. Gurka, A. J. Heymsfield, P. S. K. Liu, B. Zhou, R. Ware, B. Ferrier, J. Milbrandt, and B. Bernstein, 2014: Ice Fog in Arctic during FRAM–Ice Fog Project: Aviation and Nowcasting Applications. *Bull. Amer. Meteor. Soc.*, **95**, 211–226. DOI: 10.1175/BAMS-D-11-00071.1

**Journal:** Bulletin of the American Meteorological Society  
**Year:** 2014  
**Authors:** I. Gultepe, T. Kuhn, M. Pavolonis, C. Calvert, J. Gurka, A. J. Heymsfield, P. S. K. Liu, B. Zhou, R. Ware, B. Ferrier, J. Milbrandt, B. Bernstein (12 authors; Milbrandt is 11th)

**Note:** This paper exists as two duplicate PDFs: `Gultepe_BAMS_14.pdf` and `Gultepe_etal_2014_BAMS.pdf`. Both are the same article. This is the canonical markdown file for both.

---

## Overview

This BAMS article describes the FRAM–Ice Fog (FRAM-IF) project, a two-month field campaign at the Yellowknife International Airport, NWT, Canada (November 2010 – February 2011), designed to improve understanding of ice fog formation and its impacts on aviation and transportation. The paper reports preliminary results from a comprehensive suite of surface and remote sensing instruments, describes approaches to satellite-based ice fog detection for GOES-R, discusses NWP model challenges (including the GEM model with the Milbrandt–Yau two-moment scheme), and develops preliminary ice fog visibility parameterizations.

---

## Project Context and Motivation

Ice fog occurs at temperatures typically below –15°C and can reduce visibility to near zero, creating major hazards for aviation in Arctic regions. Ice fog occurred about 14% of the time during the project period. Current NWP models were not designed for ice fog prediction and underestimate ice crystal number concentrations (models: ~100 L⁻¹; observed: >1000 L⁻¹). The FRAM-IF project aims to:

1. Improve understanding of ice fog physical processes
2. Improve understanding of relations between ice fog, frost, and light snow
3. Develop an instrument suite for ice fog study
4. Improve understanding of ice fog effects on aviation and transportation
5. Develop ice fog nowcasting skills using remote sensing and forecast models
6. Examine effects of small ice crystals on cloud microphysics and model simulations

---

## Project Site and Observations

**Location:** Yellowknife International Airport (62°27'46"N, 114°26'25"W), NWT, Canada  
**Dates:** 25 November 2010 – 5 February 2011

Key instruments (see Table 1 in paper):
- Fog Monitoring Device (FMD) — droplet spectra (1–50 μm)
- Ground Cloud Imaging Probe (GCIP) — droplet/ice spectra (15–930 μm)
- Ott Parsivel disdrometer — precipitation spectra
- Ice Crystal Imaging probe (Luleå University) — ice crystal images/shapes (>20 μm, 4.2 μm/pixel resolution)
- Vaisala FD12P — visibility, precipitation type/rate
- Sentry visibility sensor; Biral SWS-200
- Vaisala CL31 ceilometer
- Radiometrics MP-3000 profiling microwave radiometer — LWC, T, humidity, RHw profiles
- 40-m Jack Fish Tower with four WXT520 sensors at 2, 10, 20, 40 m levels (T, RHw, wind, pressure)
- Ultra High Sensitivity Aerosol Spectrometer (UHSAS) — aerosol spectra (0.05–1 μm)
- Shortwave/IR radiometers, net radiometer
- Barska microscope and Canon macro camera — ice crystal photography
- Rosemount icing detector (RID 872E3)
- POSS (Precipitation Occurrence Sensor System)
- Microwave rain radar (Biral MRR)

---

## Key Preliminary Results

**Environmental conditions:**
- Mean hourly temperatures during the project were significantly below the 47-yr and 10-yr averages; RHw was also below average.
- Strong surface inversions with tops at ~1–1.5 km were common.
- Ice fog occurred 14 times (Vis < 10 km); frost occurred 12 times; light snow was nearly daily.

**Ice fog microphysics:**
- Ice crystal concentrations exceeded 1000 L⁻¹ during ice fog events.
- Crystal sizes were typically < 200 μm; many < 50 μm; some as small as 5–10 μm.
- Crystal shapes at –35°C were not spherical (columns, plates, and other varieties), contrary to some prior work.
- Bimodal aerosol size spectra observed during fog-free conditions shifted to larger sizes (>0.5 μm) during ice fog, indicating the fraction growing to ice fog particles.

**Visibility:**
- FD12P visibility was ~2× larger than Sentry sensor visibility during ice fog events (for Vis > 2 km), a major calibration/inter-comparison concern.
- Vis–PR relationships showed large scatter; instrument-type matters significantly for light snow.
- New visibility parameterization for ice fog based on ISDAC measurements (ice crystal sizes 10–200 μm):

$$\text{Vis} = 1.19 (\text{IWC} \times N_i)^{-0.5066}$$

---

## Satellite Applications (GOES-R)

FRAM-IF observations are used to validate GOES-R Advanced Baseline Imager (ABI) algorithms for:
- **Cloud phase determination** (liquid water, supercooled water, mixed phase, ice) using effective absorption optical depth ratios — tested with MODIS during the campaign.
- **Low cloud base identification** using a naïve Bayesian classifier to determine probability of marginal VFR (ceiling < 914 m) and IFR (ceiling < 305 m) conditions.

---

## NWP Model Applications

### GEM (Environment Canada)

GEM is run at 2.5 km horizontal grid spacing using the two-moment Milbrandt–Yau (2005a,b) bulk microphysics scheme. In this scheme:
- Ice is represented by two categories: "ice" (pristine crystals) and "snow" (aggregates, sizes > 250 μm)
- Each size distribution is a complete gamma function with two prognostic variables (mass mixing ratio and number concentration)
- Ice nucleation is based on Meyers et al. (1992), derived from limited aircraft and laboratory measurements not representative of Arctic conditions

**Limitation:** The MY scheme's ice nucleation parameterization is not appropriate for Arctic ice fog; ice crystal number concentrations predicted by GEM (~100 L⁻¹) are an order of magnitude below observed values (>1000 L⁻¹). New FRAM-IF measurements will be used to constrain the scheme.

### North American Mesoscale Model (NAM, NCEP)

NAM (12-km) uses ice water content (IWC) to compute visibility via Stoelinga and Warner (1999), which tends to underestimate ice fog water content. Alternative methods tested:
- Surface parameter-based approach (Zhou and Du 2010) — predicts occurrence, not visibility
- Moisture advection approach (Zhou and Ferrier 2008; Zhou 2011) — improved prediction for 16 January 2010 case

---

## Conclusions and Future Work

- Ice fog crystals can be 5–10 μm in size and have concentrations exceeding 1000 L⁻¹.
- Visibility measurements are highly variable at temperatures < –20°C; sensor inter-comparison differences can exceed a factor of 2.
- Ice fog can be parameterized as a function of IWC and $N_i$; if prognostic in models, ice fog Vis can be estimated.
- NWP models currently underpredict $N_i$ for ice fog by ~1 order of magnitude; Arctic-specific ice nucleation parameterizations are needed.
- Satellite-based ice fog nowcasting is possible with next-generation geostationary satellites (e.g., GOES-R ABI).
- Accurate ice fog prediction has direct implications for deicing fluid use and aircraft safety in northern latitudes.
