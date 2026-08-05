# FROST-2014: The Sochi Winter Olympics International Project

**Full citation:** Kiktev, D., P. Joe, G. A. Isaac, A. Montani, I.-L. Frogner, P. Nurmi, B. Bica, J. Milbrandt, M. Tsyrulnikov, E. Astakhova, A. Bundel, S. Bélair, M. Pyle, A. Muravyev, G. Rivin, I. Rozinkina, T. Paccagnella, Y. Wang, J. Reid, T. Nipen, and K.-D. Ahn, 2017: FROST-2014: The Sochi Winter Olympics International Project. *Bull. Amer. Meteor. Soc.*, **98**, 1908–1929. DOI: 10.1175/BAMS-D-15-00307.1

*Note: The source PDF is named "Kirkev_BAMS_2017.pdf" — this is a typo of the first author's name (Kiktev). The normalized stem for this paper is `Kiktev_etal_2017`.*

---

## Overview

The Forecast and Research in the Olympic Sochi Testbed (FROST-2014) was a combined Research and Development Project (RDP) / Forecast Demonstration Project (FDP) organized under the WMO World Weather Research Programme (WWRP), associated with the 2014 XXII Winter Olympic Games and XI Paralympic Games in Sochi, Russia (7–23 February and 7–16 March 2014, respectively). Six nowcasting systems, nine deterministic mesoscale NWP models, and six ensemble prediction systems participated. The Sochi mountain cluster, located in the Krasnaya Polyana area of the Greater Caucasus range, presented extreme challenges for high-resolution NWP due to complex terrain and rapidly varying weather.

---

## 1. Introduction

Since Sydney 2000, WMO-endorsed meteorological projects have been organized for each Olympics. FROST-2014 addressed nowcasting and short-range NWP in complex terrain during winter, following SNOW-V10 (Vancouver 2010). The project goals were:
1. Improved nowcasting and short-range NWP in complex terrain
2. Better use of enhanced observation coverage
3. Improved assimilation of specialized observations
4. Improved understanding of high-impact weather (HIW) physics
5. Evaluation of developed forecasting systems

---

## 2. Observation Network

- 38 automatic weather stations with 10-min (some 1-min) sampling intervals, measuring standard meteorological variables plus solid precipitation, visibility, cloud base, radiation, and snow cover
- Vaisala WRM200 C-band dual-polarization Doppler radar on Mount Akhun (680 m ASL)
- Upstream radars from Turkey (C-band) and Ukraine (X-band) providing nearly complete Black Sea coverage
- RPG humidity/temperature profiler, Scintec sodar, METEK micro rain radars, temperature profiler
- High-resolution radiosondes at 0000, 0600, 1200, 1800 UTC
- Webcam images and snow surveys

---

## 3. Participating Systems

### Nowcasting Systems (6 total)

| System | Organization | Country |
|--------|-------------|---------|
| ABOM | ECCC | Canada |
| CARDS | ECCC | Canada |
| INCA | ZAMG | Austria |
| INTW | ECCC | Canada |
| JOINT | Roshydromet | Russia |
| MeteoExpert | IRAM | Russia |

**ECCC (EC) nowcasting systems:**
- **ABOM** (Adaptive Blending of Observations and Model): Combines observations, observation trends, and NWP model trends; used GEM at 1 and 0.25 km; predicted T2m, RH2m, wind, and visibility at 10-min intervals up to 8 h
- **INTW** (Integrated Weighted): Integrated nowcasts from multiple NWP models (GEM 1 km, GEM 0.25 km, COSMO 7 and 2.2 km, WRF-ARW-NIMS); used Boudala et al. (2012) visibility parameterization
- **CARDS** (Canadian Radar Decision Support): Lagrangian radar extrapolation nowcasting using mosaicked radar data; cross-correlation technique for precipitation forecasts

### Deterministic NWP Models (9 total)

ECCC contributed **three GEM model configurations** (described in Milbrandt et al. 2016):
| Model | Grid spacing | Frequency |
|-------|-------------|-----------|
| GEM-2.5 | 2.5 km | 1 run/day, 27 h |
| GEM-1 | 1 km | 1 run/day, 25 h |
| GEM-0.25 | 0.25 km | 1 run/day, 24 h |

Other models: COSMO-Ru (7, 2.2, 1.1 km), NCEP NMMB/NEMS, HARMONIE-AROME (1 km)

### Ensemble Prediction Systems (6 total)

Includes COSMO-S14-EPS, GLAMEPS, ALADIN-LAEF, NMMB-EPS, COSMO-Ru2-EPS, HarmonEPS. Two convection-permitting EPSs (COSMO-Ru2-EPS, HarmonEPS) tested in research mode.

---

## 4. Forecast Verification and Key Results

### Near-Surface Forecast Performance

- HARMONIE-AROME (1 km) performed very well when averaged over all runs
- GEM showed clear improvement with increasing resolution for T2m; transition from 2.5 to 1 km was unambiguously beneficial
- Transition from 7 to 2.2 km COSMO improved T2m, RH2m, and 10-m wind direction; further refinement to 1.1 km helped mainly for wind speed

### Key Weather Events

Key weather events during the Games included foehn events (most models underestimated temperatures by 1.4°–4.4°C at upper elevations), a precipitation dissipation event (most models predicted precipitation that was not observed), wind gusts (underestimated by 3.5–7 m s⁻¹ by most models), and a critical low-visibility event.

**Low-visibility event (16–17 February 2014):** This was the most serious weather impact on the Games; the men's biathlon mass start was postponed from 16 to 18 February and the snowboard qualification from 17 to 18 February. The GEM-0.25 km model most successfully reproduced the timing of the sharp visibility reduction on 16 February (though the duration was underestimated). Both COSMO-Ru1 and COSMO-Ru2 also captured the event well in RH2m. The predicted window of good visibility on the afternoon of 17 February was leveraged to reschedule the women's biathlon mass start.

---

## 5. Ensemble Prediction Results

Ensemble prediction systems provided probabilistic products including ensemble mean, ensemble spread, probability of threshold exceedance, and ensemble meteograms. Convection-permitting EPSs (COSMO-Ru2-EPS, HarmonEPS) were tested in research mode. Calibrated and hourly-updated GLAMEPS forecasts were produced.

---

## 6. Nowcasting Verification

Six nowcasting systems were verified against station data. ABOM and INTW provided 10-min interval forecasts for T2m, RH2m, wind, and visibility at venue locations. Nowcasting systems that had been developed primarily for summer convective weather and flat terrain faced challenges in complex mountain terrain.

---

## 7. Lessons Learned and Legacy

- High-resolution NWP (hectometric scale) showed clear benefit for complex terrain forecasting
- The integration of multiple NWP models via blending/weighting (INTW, ABOM) generally outperformed individual models
- Ensemble approaches provided valuable uncertainty information, particularly for high-impact events
- Winter mountain nowcasting remains more challenging than summer convective nowcasting
- FROST-2014 established a foundation for the subsequent ICE-POP project for the 2018 PyeongChang Games, which focused more specifically on winter microphysics

[Figures 1–10: Maps of the Sochi Olympic area and observation network; radar coverage composite; MAE and EDI score plots for deterministic models; visibility forecasts for the 16 Feb event; ensemble verification plots. Tables 1–5: Weather case summaries, participating institutions, nowcasting system characteristics, deterministic model configurations, ensemble system configurations.]
