# Mailhot et al. (2014): An Experimental High-Resolution Forecast System During the Vancouver 2010 Winter Olympic and Paralympic Games

**Full citation:** Mailhot, J., Milbrandt, J.A., Giguère, A., McTaggart-Cowan, R., Erfani, A., Denis, B., Glazer, A., and Vallée, M. (2014): An experimental high-resolution forecast system during the Vancouver 2010 Winter Olympic and Paralympic Games. *Pure and Applied Geophysics*, **171**, 209–229. DOI: 10.1007/s00024-012-0520-6

**Journal:** Pure and Applied Geophysics (PAGEOPH)
**Year:** 2014 (received 2011, accepted 2012, published online August 2012)
**Authors:** J. Mailhot, J.A. Milbrandt, A. Giguère, R. McTaggart-Cowan, A. Erfani, B. Denis, A. Glazer, M. Vallée
**Affiliation:** Environment Canada (Atmospheric Numerical Weather Prediction Research; Canadian Meteorological Centre)

---

## Abstract

Environment Canada ran an experimental numerical weather prediction (NWP) system during the Vancouver 2010 Winter Olympic and Paralympic Games, consisting of nested high-resolution (down to 1-km horizontal grid-spacing) configurations of the GEM–LAM model, with improved geophysical fields, cloud microphysics and radiative transfer schemes, and several new diagnostic products such as density of falling snow, visibility, and peak wind gust strength. The performance of this experimental NWP system has been evaluated in these winter conditions over complex terrain using the enhanced mesoscale observing network in place during the Olympics. As compared to the forecasts from the operational regional 15-km GEM model, objective verification generally indicated significant added value of the higher-resolution models for near-surface meteorological variables (wind speed, air temperature, and dewpoint temperature) with the 1-km model providing the best forecast accuracy. Appreciable errors were noted in all models for the forecasts of wind direction and humidity near the surface. Subjective assessment of several cases also indicated that the experimental Olympic system was skillful at forecasting meteorological phenomena at high-resolution, both spatially and temporally, and provided enhanced guidance to the Olympic forecasters in terms of better timing of precipitation phase change, squall line passage, wind flow channeling, and visibility reduction due to fog and snow.

---

## 1. Introduction

The Vancouver 2010 Winter Olympic and Paralympic Games (12–28 February and 12–21 March 2010) were held in the Vancouver and Whistler areas of British Columbia. Environment Canada developed several experimental NWP systems to augment operational products for the Olympic Forecast Team (OFT): a regional ensemble prediction system, a high-resolution deterministic prediction system, and an external land surface microscale modeling system.

This paper focuses on the high-resolution deterministic NWP system: three one-way nested GEM–LAM grids at 15-, 2.5-, and 1-km horizontal grid spacing (REG15, LAM2.5, LAM1). The venues experienced rapidly changing winter weather conditions due to their location near the Pacific Ocean and surrounding mountains, representing major challenges for forecasters.

---

## 2. The 1-km Resolution Experimental Prediction System

### 2.1 Dynamical Core

The dynamical core is GEM model version 4.0.6 with a hybrid terrain-following, log-pressure based vertical coordinate and Charney-Phillips staggering. Three one-way nested grids:

- **REG15:** 15-km, 261×260 grid points
- **LAM2.5:** 2.5-km, 344×349 grid points
- **LAM1:** 1-km, 456×379 grid points

All grids had 58 vertical levels with a model top at 10 hPa (~30 km). A time-dependent adjustable topography ("growing orography") procedure was applied to reduce interpolation errors at the start of integration. The full run typically required ~2 h of wall clock time on the IBM pSeries 690 supercomputer (52 min for LAM2.5 on 256 CPUs; 68 min for LAM1 on 320 CPUs).

### 2.2 Physics Package

Improvements over the operational physics package:

**Radiation:** The Li and Barker (2005) radiative transfer scheme was used, reducing the cold bias noted during winter conditions and improving cloud-radiation interaction representation.

**Cloud microphysics:** The **two-moment Milbrandt–Yau (MY2) bulk microphysics scheme** (Milbrandt and Yau 2005) was used — described as the first time a full two-moment microphysics scheme was used for this type of operational forecast system. The scheme predicts mass mixing ratio and total number concentration for six hydrometeor categories: cloud droplets, rain, ice, snow, graupel, and hail.

**Snow-to-liquid ratio (SLR):** A new method to predict the instantaneous SLR (SLR_inst) of precipitation directly from the MY2 microphysics scheme was developed (Milbrandt et al. 2011). The method exploits the fact that the "snow" category in MY2 has a realistic bulk density inversely proportional to its size (well simulated by the two-moment scheme), removing the need for assumed SLR values such as the "10-to-1" rule.

**Visibility:** Computed using the Gultepe and Milbrandt (2007, 2010) parameterizations:
- Through fog: from prognostic cloud droplet mixing ratio and number concentration
- Through rain: from precipitation rate of the rain category
- Through snow: from precipitation rate of the snow category

**Wind gusts:** Estimated using the Brasseur (2001) physical model based on boundary layer turbulence, providing upper and lower bounds of confidence intervals.

### 2.3 Customized Output Package

Output products included: 2-m temperature, dewpoint, relative humidity; 10-m winds, gusts, standard deviations; precipitation rates (liquid, solid, mixed, total) and amounts; snow-to-liquid ratios; cloud cover, cloud base, snow level; visibility (fog, rain, snow, total); wind chill; solar radiation; skin temperature.

---

## 3. The OAN Observational Dataset

An Olympic Autostation Network (OAN) of >40 standard and special surface observing sites (manual and automatic, hourly or synoptic reports) was established in late 2007. It provided an unprecedented mesoscale observational dataset over complex terrain in Canadian wintertime.

---

## 4. Verification of Near-Surface Meteorological Variables

Objective verification was conducted over the 40-day period of 12 February–23 March 2010 using OAN data. Scores: bias and standard error, with 84% confidence intervals via block bootstrapping (2000 iterations).

Key results:

- **10-m wind speed:** LAM1 showed virtually no bias (REG15 winds too weak by ~0.5 m s$^{-1}$ during the day); standard errors ~1.4 m s$^{-1}$ in all models; LAM1 slightly improved
- **Wind direction:** All models showed large standard errors (40–50°); no systematic directional bias
- **2-m temperature:** Both LAMs reduced cold bias by >1°C during the day vs. REG15; standard errors reduced by ~1.5°C throughout the period; LAM1 better than LAM2.5 especially during daytime. Large errors (>3°C warm) occurred 70 times in REG15 vs. only 4 times in LAM1
- **2-m dewpoint:** All models too dry (biases reaching -2°C); LAM improvements in bias mainly during morning hours; standard errors improved ~1°C with LAMs

---

## 5. Examples of Olympic Forecasts and Verifications

### 5.1 Instantaneous Snow-to-Liquid Ratio

For 23 February 2010 at Cypress Bowl South, the model SLR_inst predicted ~20 in the afternoon (consistent with large, low-density aggregates) switching to ~5 in the evening (approaching the graupel value of 2.5 for bulk graupel density 400 kg m$^{-3}$). A forecaster observation confirmed the transition from "large, fluffy snowflakes" to "fast-falling snow pellets" at the predicted time. The rapid transition was due to a riming period shifting the dominant solid-phase category from snow to graupel.

### 5.2 Model Visibility Comparisons

Visibility forecasts were mixed: for the freestyle skiing women's aerial final on 24 February 2010, the model showed both over- and under-forecasting of poor visibility. When large-scale timing was correct and the forcing for liquid water production was resolved, the visibility parameterization compared favorably with observations.

### 5.3 Squall Line on 14 February 2010

The LAM1 model correctly identified a squall line passage at the nordic ski venue around 1700–1800 UTC that was not predicted by REG15. Forecasters using the LAM guidance correctly anticipated the event (though timing was ~10 min late in absolute terms).

### 5.4 Temperature Along Alpine Ski Slopes

The LAM1 model better represented the temperature gradient along the alpine ski run at three sites at different elevations, important for precipitation phase change forecasts.

### 5.5 Diurnal Winds at Ski Jump

LAM1 captured the diurnal wind reversal cycle (overnight drainage winds to daytime upvalley winds) at Callaghan Valley on 5 March 2010, confirmed by observations.

---

## 6. Concluding Remarks

Objective and subjective verification showed the high-resolution Olympic NWP system provided significant added value over operational products. The 1-km LAM generally provided the best forecast accuracy. Model improvements made for the Olympic system formed the basis for a major upgrade to the 2.5-km LAM system at CMC operations. The experience also promoted Canadian participation in FROST-2014 (Sochi 2014).

---

## References (key)

- Milbrandt, J.A. and Yau, M.K. (2005): A multimoment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, 62, 3065–3081.
- Milbrandt, J.A. and McTaggart-Cowan, R. (2010): Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, 67, 3931–3948.
- Milbrandt, J.A., Glazer, A., and Jacob, D. (2011): Predicting the snow-to-liquid ratio using a bulk microphysics scheme. *Mon. Wea. Rev.* (in press at time of publication)
- Gultepe, I. and Milbrandt, J.A. (2007): Microphysical observations and mesoscale model simulation of a warm fog case. *Pure Appl. Geophys.*, 164.
- Gultepe, I. and Milbrandt, J.A. (2010): Probabilistic parameterizations of visibility. *J. Appl. Meteor. Clim.*, 39, 36–46.

[All figures: maps of model domains, time series verification plots, meteograms, spatial SLR maps — images not reproducible in markdown]
