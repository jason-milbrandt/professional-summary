# Joe et al. (2020): The Canadian Arctic Weather Science Project — Introduction to the Iqaluit Site

**Full citation:** Joe, P., Melo, S., Burrows, W. R., Casati, B., Crawford, R. W., Deghan, A., Gascon, G., Mariani, Z., Milbrandt, J., and Strawbridge, K. (2020): The Canadian Arctic Weather Science Project: Introduction to the Iqaluit Site. *Bulletin of the American Meteorological Society*, **101**, E109–E128. DOI: 10.1175/BAMS-D-18-0291.1

---

## 1. Introduction

Developmental pressures combined with social–cultural, technological, and climate–environmental changes are driving increased human activity in the Canadian Arctic. The Northwest Passage is expected to become a prime transportation corridor, with air traffic over the Arctic region growing from ~400 transpolar flights in 2000 to ~12,759 in 2014 (3.5% annual projected growth). The Canadian Arctic also experiences extremely high search and rescue (SAR) incident rates (~240 per 100,000 population), with weather-related hazards as the primary contributing factor.

The Canadian Arctic Weather Science (CAWS) project was initiated by Environment and Climate Change Canada (ECCC) to conduct research into future operational monitoring and forecasting programs for the Arctic.

---

## 2. CAWS Objectives

1. Identify and test future operational monitoring technologies for the Arctic (remote sensing)
2. Validate weather-related satellite products (precipitation from GPM, winds from Aeolus)
3. Understand Arctic weather phenomena and their impact on observation and prediction requirements
4. Develop, validate, and verify atmospheric prediction products for high-impact local weather
5. Co-design communication strategies with the indigenous (Inuit) community
6. Quantify societal benefits and impacts
7. Collaborate with and support the Polar Prediction Project (YOPP) and SAON

---

## 3. Iqaluit Site and Instruments

ECCC established a meteorological reference site at Iqaluit, Nunavut (63°45′N, 68°33′W), beginning fall 2015. Key instruments:

| Instrument | Manufacturer | Deployment | Measurement |
|-----------|-------------|-----------|-------------|
| Ka-band scanning Doppler polarization radar | METEK | Sept 2015 | Reflectivity, radial velocity, depolarization ratio; 10-min; 10-m resolution up to ~25 km |
| Ceilometer CL31 | Vaisala | Sept 2015 | Cloud intensity, height, aerosol profiles, mixing-layer height; 5-min; 5-m resolution |
| PWD52 present weather detector | Vaisala | Sept 2015 | Visibility, precipitation type; 1-min |
| Doppler lidar (HALO) | HALO | Sept 2015 | Line-of-sight wind, aerosol backscatter; 5-min; 3-m resolution up to ~3 km |
| Rosemount icing detector | Rosemount | Sept 2015 | Ice detection |
| Surface meteorological station | Miscellaneous | Ongoing | T, RH, pressure, winds, precipitation; 1-min |
| Radiosondes | Vaisala | Ongoing | T, RH, pressure, winds up to ~30 km; 12-h |
| Canadian Autonomous Arctic Aerosol Lidar (CAAAL) | ECCC | Oct 2016 | Aerosol and water vapor profiles; 355, 532, 1064 nm; 1-min; 3-m resolution up to ~15 km |
| Doppler lidar (Ridge) | HALO | Oct 2017 | Line-of-sight wind, aerosol backscatter; 5-min |
| Scintillometer | Scintec | Aug 2018 | Turbulence, crosswind, heat flux |
| Fog measuring device | DMT | Aug 2018 | Fog intensity, water vapor at surface |
| Far-infrared radiometer | LR Tech | Aug 2018 | Downwelling infrared radiation, cloud microphysics |
| Surface radiation fluxes | Campbell Scientific | Aug 2018 | Shortwave and longwave radiation |
| Water vapor lidar | Vaisala | Aug 2018 | Aerosol and water vapor profiles; 24-h |
| POSS (Precipitation Occurrence Sensor System) | ECCC | Sept 2018 | Precipitation type, rate, particle distribution |

Weather observations show high frequencies of snow, blowing snow, and fog at Iqaluit. Blizzard events (visibility < 0.8 km) are significant and persistent.

---

## 4. Prediction and Products

ECCC runs several GEM-based NWP systems for the Arctic region:
- **GDPS**: Global Deterministic Prediction System, 15-km horizontal grid spacing (not described in detail)
- **CAPS**: Canadian Arctic Prediction System, 3-km grid spacing; experimental (not always available)
- **RDPS**: Regional Deterministic Prediction System, 10-km resolution, 84-h forecasts
- **HRDPS**: High Resolution Deterministic Prediction System, 2.5-km resolution, 48-h forecasts

The HRDPS model, which uses the P3 and/or MY2 microphysics scheme (⚠ verify exact scheme version used during CAWS), is the primary model of interest for Arctic high-resolution validation. Both RDPS and HRDPS are referenced as operational models used extensively in the CAWS project.

New guidance products for warnings include:
1. **Blizzard Potential (BP)**: expert-rule-based heads-up guidance derived from NWP output
2. **Regression analysis**: blowing snow visibility forecast using 40 years of surface observations
3. **Time-offset MOS**: Random Forest classifier for blizzard conditions probability
4. **Fog/stratus forecast**: fog and low-ceiling prediction using RDPS

---

## 5. Example Observations

### Blizzard Event — 20 March 2016 (1420 UTC)

- Ka-band radar: multi-layer structure with very low reflectivities (−30 to −10 dBZ) indicating ice crystals up to 5 km; up to seven wind direction shifts in the lowest layers
- Doppler lidar: consistent wind pattern with radar; reveals fine-scale wind layering
- Very light precipitation layers occur ~40% of the time in winter at Iqaluit (Mariani et al. 2018)

### Wind and NWP Comparison (March 2016)

Time–height displays from Ka-band radar (VAD analysis), Doppler lidar (DBS at 75°), radiosonde, and HRDPS show:
- Wind speeds generally consistent among all observing systems
- HRDPS wind directions show disagreement compared to observations
- Highlights the resolution differences between the observing systems

---

## 6. Community Engagement

Risk communication to the Inuit is a recognized challenge due to cultural differences between traditional ecological knowledge and scientific meteorological information. CAWS engaged with the local community to co-design a project logo (featuring a raven, a culturally significant symbol), and is working toward co-designed communication of warnings specific to Arctic communities.

---

## 7. Summary

The CAWS project has established a near-Arctic meteorological reference site at Iqaluit to:
- Explore new monitoring technologies and network design
- Develop weather information products specific to the Canadian Arctic
- Support validation of space-based precipitation and wind observations
- Provide data for evaluation, validation, and verification of Canadian NWP models
- Understand Arctic meteorology at high latitudes
- Contribute to national and international projects (YOPP, SAON, etc.)

Preliminary results show unique Arctic meteorological features in the lowest few kilometers of the atmosphere that impact NWP temperature and other variable predictions.

---

## References (selected)

- Milbrandt, J. A., and Morrison, H. (2016): Parameterization of ice microphysics based on the prediction of bulk particle properties. Part 3: The effects of multiple free categories. *J. Atmos. Sci.*, **73**, 975–995.
- Morrison, H., and Milbrandt, J. A. (2015): Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
