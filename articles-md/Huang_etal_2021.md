# Huang et al. (2021): Microphysical Processes Producing High Ice Water Contents (HIWCs) in Tropical Convective Clouds during the HAIC-HIWC Field Campaign

**Full citation:** Huang, Y., Wu, W., McFarquhar, G. M., Wang, X., Morrison, H., Ryzhkov, A., Hu, Y., Wolde, M., Nguyen, C., Schwarzenboeck, A., Milbrandt, J., Korolev, A. V., and Heckman, I. (2021): Microphysical processes producing high ice water contents (HIWCs) in tropical convective clouds during the HAIC-HIWC field campaign: evaluation of simulations using bulk microphysical schemes. *Atmospheric Chemistry and Physics*, **21**, 6919–6944. DOI: 10.5194/acp-21-6919-2021

---

## 1. Introduction

High concentrations of small ice particles (high ice water content, HIWC) ingested into jet engines can cause power loss and damaging events and probe failures. HIWC regions with median mass diameters (MMDs) < 300 µm and low radar reflectivities (< 20 dBZ) frequently occur over oceanic tropical convective systems. The HAIC-HIWC international field campaigns (2014 near Darwin; 2015 near Cayenne, French Guiana) were conducted to explore the formation mechanisms for these HIWC regions.

This study conducts high-resolution WRF simulations of a tropical convective system observed on 26 May 2015 during the HAIC-HIWC campaign out of Cayenne, using four different bulk microphysics schemes including P3, to evaluate their ability to simulate HIWC regions.

---

## 2. Observations

- Radiosondes for thermodynamic profiles
- GOES-13 geostationary satellite for storm coverage and cloud top brightness temperature
- Airborne X-band radar on French Falcon 20 and NRC Convair 580 for radar reflectivity
- Cloud microphysics probes aboard both aircraft for ice particle size distributions (PSDs), ice water content (IWC), and liquid water content (LWC) at different heights
- Aircraft flight altitudes sampled clouds at different temperature levels (−10°C, −30°C, −45°C)

---

## 3. Simulations

WRF model with three nested domains; innermost 1-km domain for the 26 May 2015 tropical convective system. Four microphysics schemes:

| Scheme | Approach | Ice representation |
|--------|----------|-------------------|
| WSM6 | One-moment bulk | Fixed-density snow, graupel |
| MORR (Morrison) | Two-moment bulk | Snow, graupel, separate categories |
| P3-1ICE | Two-moment bulk | Single free ice category (variable rime fraction) |
| P3-2ICE | Two-moment bulk | Two free ice categories |

P3 reference: Morrison and Milbrandt (2015). The P3 scheme uses variable mass–dimensional relations across the size spectrum, unlike WSM6 and MORR which use constant power-law relations.

Radar forward simulators were developed to compute X-band reflectivity from model fields for evaluation against observations.

---

## 4. Results

### 4.1. Thermodynamic Environment

All simulations using different microphysics schemes reproduce the observed sounding profiles:
- Temperature: average bias within 1.6%
- Dew-point temperature: average bias within 6%
- Wind speed: average bias within 14%
- Wind direction: average bias within 36°
- MORR scheme gives closest agreement with soundings

### 4.2. Storm Coverage

WRF reproduces coverage and evolution of the tropical MCS compared to GOES-13 brightness temperature. All simulations underestimate storm coverage (brightness temperature < 232 K) by:
- WSM6: −34.3%
- MORR: −30.0%
- P3-1ICE: −12.9%
- P3-2ICE: −2.3%

P3-2ICE produces closest storm coverage to observations.

### 4.3. Radar Reflectivity

All simulations overestimate intensity and spatial extent of radar reflectivity above the melting layer compared to airborne X-band radar:
- 95th percentile above 6 km: WSM6 < 44 dBZ; MORR < 41 dBZ; P3-1ICE < 45 dBZ; P3-2ICE < 47 dBZ
- 95th percentile observed < 30 dBZ above 6 km
- All simulations extend reflectivity > 0 dBZ above 14 km; observed > 0 dBZ mostly below 14 km

### 4.4. Ice Particle Size Distributions

All simulations miss the peak of the observed ice number distribution function for 0.1 < D_max < 1 mm (small crystal peak associated with HIWC):
- WSM6 and MORR: underestimate number concentration at −45, −30, especially −10°C by up to 1 order of magnitude; simulate fewer small particles and more large particles
- P3-1ICE: overestimates number concentration by up to 1 order of magnitude at some levels; underestimates by ~1 order of magnitude at −10°C
- P3-2ICE: generates large spread (2 orders of magnitude) at −45 and −30°C; underestimates number concentration by ~1 order of magnitude at −10°C, producing more large particles at this level

### 4.5. Mixed-Phase Processes at −10°C

Mixed-phase microphysical processes play an important role at −10°C due to overprediction of LWC in MORR, P3-1ICE, and P3-2ICE above the melting layer:
- MORR: large graupel particles (greater graupel water content, fewer graupel particles) due to rapid collection of cloud water with limited increase in graupel number → large mean graupel size → strong radar reflectivity bias
- P3-1ICE/P3-2ICE: IWC at −10°C increases mainly due to collection of cloud/rain water by ice, which increases mass/size but not ice number → large mean ice particle sizes → strong radar reflectivity
- Underlying cause: collection of liquid water by ice does not increase ice particle number; low ice numbers may also be associated with excessive aggregation and/or missing secondary ice production (SIP) processes (e.g., "freezing-drop-shattering"; Korolev et al., 2020)

---

## 5. Conclusions

1. No single microphysics scheme outperforms others across all evaluated metrics for this tropical oceanic MCS
2. All schemes overestimate radar reflectivity above the melting layer by >30% in area and intensity
3. All schemes miss the observed peak of ice number distribution for 0.1 < D_max < 1 mm
4. P3-2ICE produces closest storm coverage to observations
5. Mixed-phase processes at −10°C associated with LWC overprediction (MORR, P3-1ICE, P3-2ICE) contribute to large simulated radar reflectivity bias
6. Despite P3's fundamentally different ice representation approach, it does not produce greatly different total condensed water content or clearly better comparison to observations
7. Missing secondary ice production parameterizations (SIP; e.g., collision-induced breakup, freezing-drop-shattering) may be responsible for the low bias in ice number concentrations
8. Results are broadly consistent between 1-km and 3-km resolution simulations

---

## References (selected)

- Korolev, A., Heckman, I., Wolde, M., Ackerman, A. S., Fridlind, A. M., Ladino, L. A., Lawson, R. P., Milbrandt, J., and Williams, E. (2020): A new look at the environmental conditions favorable to secondary ice production. *Atmos. Chem. Phys.*, **20**, 1391–1429.
- Morrison, H. and Milbrandt, J. A. (2015): Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311.
- Milbrandt, J. A. and Yau, M. K. (2005a, 2005b): A multimoment bulk microphysics parameterization. Parts I & II. *J. Atmos. Sci.*, **62**, 3051–3081.
