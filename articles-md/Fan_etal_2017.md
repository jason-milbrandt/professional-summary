# Fan et al. (2017) — Cloud-resolving model intercomparison of an MC3E squall line case: Part I—Convective updrafts

**Full citation:** Fan, J., B. Han, A. Varble, H. Morrison, K. North, P. Kollias, B. Chen, X. Dong, S. E. Giangrande, A. Khain, Y. Lin, E. Mansell, J. A. Milbrandt, R. Stenz, G. Thompson, and Y. Wang, 2017: Cloud-resolving model intercomparison of an MC3E squall line case: Part I—Convective updrafts. *J. Geophys. Res. Atmos.*, **122**, 9351–9378. DOI: 10.1002/2017JD026622

**Journal:** Journal of Geophysical Research: Atmospheres  
**Year:** 2017  
**Authors:** Jiwen Fan, Bin Han, Adam Varble, Hugh Morrison, Kirk North, Pavlos Kollias, Baojun Chen, Xiquan Dong, Scott E. Giangrande, Alexander Khain, Yun Lin, Edward Mansell, Jason A. Milbrandt, Ronald Stenz, Gregory Thompson, Yuan Wang

---

## Abstract

An intercomparison study of a midlatitude mesoscale squall line is performed using the Weather Research and Forecasting (WRF) model at 1 km horizontal grid spacing with eight different cloud microphysics schemes to investigate processes that contribute to the large variability in simulated cloud and precipitation properties. All simulations tend to produce a wider area of high radar reflectivity ($Z_e > 45$ dBZ) than observed but a much narrower stratiform area. The magnitude of the virtual potential temperature drop associated with the gust front passage is similar in simulations and observations, while the pressure rise and peak wind speed are smaller than observed, possibly suggesting that simulated cold pools are shallower than observed. Most of the microphysics schemes overestimate vertical velocity and $Z_e$ in convective updrafts as compared with observational retrievals. Simulated precipitation rates and updraft velocities have significant variability across the eight schemes, even in this strongly dynamically driven system. Differences in simulated updraft velocity correlate well with differences in simulated buoyancy and low-level vertical perturbation pressure gradient, which appears related to cold pool intensity that is controlled by the evaporation rate. Simulations with stronger updrafts have a more optimal convective state, with stronger cold pools, ambient low-level vertical wind shear, and rear-inflow jets. Updraft velocity variability between schemes is mainly controlled by differences in simulated ice-related processes, which impact the overall latent heating rate, whereas surface rainfall variability increases in no-ice simulations mainly because of scheme differences in collision-coalescence parameterizations.

---

## 1. Introduction

Deep convective clouds profoundly impact the hydrologic cycle and atmospheric radiation budget. High-resolution cloud-resolving models (CRMs) with different microphysics schemes produce large spreads in simulated cloud and precipitation properties. Previous tropical MCS intercomparisons all drastically overestimated radar reflectivity and vertical velocity in deep convective updrafts but underestimated stratiform rainfall, with large spread among models.

This study uses a constrained approach: the same dynamical core (WRF-ARW) with eight different microphysics schemes to isolate the role of microphysics parameterization in driving spread. The case is a large midlatitude squall line on 20 May 2011 during the Midlatitude Continental Convective Clouds Experiment (MC3E) over the U.S. Southern Great Plains (SGP), with extensive ground-based and aircraft observations available.

---

## 2. Case Description and Observations

The squall-line MCS on 20 May 2011 was oriented northeast–southwest, extending ~1000 km along the line and ~200 km perpendicular at peak size. Observations include:

- Multi-Doppler 3-D wind field retrievals from three radars: CSAPR (C-band), KVNX, and KICT (S-band NEXRAD WSR-88D)
- NEXRAD 3-D mosaic reflectivity (NSSL)
- Three precipitation products: NMQ Q2, bias-corrected Q2, and ABRFC
- Oklahoma Mesonet for near-surface cold pool properties
- ARM 920-MHz UHF Radar Wind Profiler (RWP) at SGP CF

---

## 3. Model Description and Simulation Design

All simulations use WRF-ARW v3.4.1 with four nested domains at 27, 9, 3, and 1 km horizontal grid spacing. 51 vertical levels. Eight cloud microphysics schemes are compared:

| Scheme | Type | References |
|--------|------|------------|
| MORR (Morrison) | Two-moment | Morrison et al. [2005, 2009] |
| MY2 (Milbrandt-Yau) | Two-moment | Milbrandt and Yau [2005a, 2005b]; Milbrandt and McTaggart-Cowan [2010]; Milbrandt et al. [2012] |
| WSM6 | One-moment | Hong and Lim [2006] |
| FSBM (Fast Spectral-Bin) | Bin-resolved | Khain [2009]; Fan et al. [2012] |
| NSSL | Two-moment | Mansell et al. [2010] |
| P3 | Two-moment | Morrison and Milbrandt [2015] |
| THOM (Thompson) | Hybrid | Thompson et al. [2004, 2008] |
| TAMU | Two-moment | Li et al. [2008]; Wang et al. [2011] |

Prognostic variables in MY2: $Q_c, Q_r, Q_i, Q_s, Q_g, Q_h, N_r, N_i, N_s, N_g, N_h$  
Prognostic variables in P3: $Q_c, Q_r, Q_{i,\text{tot}}, Q_{i,\text{rim}}, B_{i,\text{rim}}, N_r, N_{i,\text{tot}}$ (one free ice category)

Simulations initialized 0000 UTC 20 May 2011; run 18 h. Additional "no-ice" sensitivity runs performed for each scheme.

---

## 4. Results

### 4.1 Rainfall and Cold Pool Properties

- Domain-mean surface precipitation rates vary by factor of ~1.5 among schemes (0600–1000 UTC). MY2 and THOM produce the least; WSM6 and TAMU the most.
- Accumulated precipitation (0600–1200 UTC): ranges from 7.3 mm (THOM) to 11.2 mm (WSM6 and TAMU); observed range 8.93–12.19 mm (ABRFC to bias-corrected Q2).
- MY2 accumulation (8.48 mm) falls below ABRFC, suggesting underestimation.
- Simulated systems develop ~1 h earlier than observed; a 1 h lag is applied for comparison.
- All simulations produce a wider area of $Z_e > 45$ dBZ than observed (observed: 7612 km²; MY2: 18,959 km²; P3: 10,674 km²).
- Cold pool: simulated virtual potential temperature drop matches observations at 0900–1000 UTC; pressure rise and wind speed peak are significantly smaller than observed, suggesting shallower simulated cold pools.

### 4.2 Convective Updraft Velocity and Radar Reflectivity

**Comparison with observations:**
- Simulations generally overestimate updraft velocity ($w$) above 5 km altitude, especially for the 99th percentile.
- All simulations underestimate updraft area at upper levels, producing small, intense cores.
- Schemes group into a Stronger Convection Group (SCG: MORR, MY2, WSM6) and Weaker Convection Group (WCG: FSBM, NSSL), with differences of 6–8 m s⁻¹ in strong updrafts at 8 km altitude.

**Causes of updraft spread:**
- Updraft velocity variability correlates well with variability in buoyancy and low-level vertical perturbation pressure gradient (PPG).
- The SCG has stronger cold pools (up to 50% stronger locally; ~20% stronger on average) and stronger rear-inflow jets than the WCG.
- Cold pool intensity is strongly controlled by raindrop evaporation rate. FSBM and NSSL have much weaker evaporation, hence weaker cold pools.
- Stronger convective state in the SCG is associated with larger C/Δu ratios and stronger rear-inflow jets approaching the "optimal" Weisman [1992] balance.
- Condensate loading offsets thermal buoyancy by up to 50% at upper levels.

**Cold pool intensity (C) at 0800–1000 UTC:**

| Scheme | C [m s⁻¹] | H [km] | Δu [m s⁻¹] | C/Δu |
|--------|-----------|--------|------------|------|
| MORR | 29.04 | 3.90 | 8.54 | 3.40 |
| MY2 | 29.82 | 4.19 | 8.55 | 3.49 |
| WSM6 | 29.74 | 4.19 | 9.51 | 3.13 |
| FSBM | 25.82 | 3.16 | 6.85 | 3.77 |
| NSSL | 26.07 | 3.61 | 6.48 | 4.02 |
| P3 | 27.17 | 3.60 | 7.35 | 3.70 |
| THOM | 26.87 | 3.91 | 7.17 | 3.75 |
| TAMU | 26.94 | 3.46 | 6.87 | 3.92 |

### 4.3 Microphysical Properties in Convective Updrafts

- Total latent heating spread correlates with updraft speed spread; the SCG has the largest total latent heating.
- Condensation dominates latent heating; differences in condensation heating are somewhat consistent with updraft intensity differences, particularly above 6 km.
- No single ice-related process (deposition, riming, drop freezing) shows clear correlation with updraft speed spread — complex interactions are at play.
- Graupel (or hail) is the major contributor to total condensate mass above 6 km in most schemes.
- MY2 has large total condensate mass but low surface rainfall, possibly due to smaller graupel terminal velocity (bulk density of 400 kg m⁻³ from Ferrier [1994]).
- THOM is dominated by slower-falling snow, producing low rainfall despite large condensate.
- Greater rainfall in single-moment schemes (WSM6) is consistent with larger sedimentation rates from the single-moment rain size distribution [Milbrandt and Yau, 2005a, 2005b; Milbrandt and McTaggart-Cowan, 2010].

### 4.4 Rainfall and Updraft Velocity Without Ice-Related Processes

- In no-ice simulations, updraft velocity spread is greatly reduced: from 6–8 m s⁻¹ to only 2–3 m s⁻¹ at the 90th–99th percentiles (excluding MY2 as an outlier).
- Normalized spread at 8 km altitude: reduced from 0.34/0.28 (90th/99th percentile, full physics) to 0.15/0.11 (no-ice).
- Reduced spread results from reduced differences in cold pool intensity, low-level PPG, and buoyancy.
- No-ice simulations agree better with multi-Doppler retrievals than full physics runs.
- Precipitation variability *increases* in no-ice runs, driven by large differences in collision-coalescence parameterizations between schemes; these differences are buffered by ice-related processes in full physics runs.
- MY2 is an outlier in no-ice runs: strongly convective but producing very little rainfall, with a dramatically weakened cold pool and a near-optimal Cj/Δu ≈ 1.7 (versus 2.7–5.5 for other schemes).

---

## 5. Conclusions

1. Most schemes overestimate convective updraft speed and $Z_e$ aloft; all produce small, intense updraft cores rather than the observed wider, weaker distribution.
2. Updraft velocity variability (6–8 m s⁻¹ between strong and weak convection groups) correlates with variability in buoyancy and low-level PPG, both of which are linked to cold pool intensity and evaporation rate.
3. Ice-related microphysics is the dominant source of the updraft speed spread: removing ice reduces spread by more than half and reduces updraft strength.
4. The SCG (MORR, MY2, WSM6) produces stronger updrafts due to larger evaporation, stronger cold pools, stronger rear-inflow jets, and a more "optimal" RKW balance state.
5. For warm cloud processes, collision-coalescence parameterization is the primary driver of precipitation uncertainty.

---

## Key Notes for MY2 and P3 in This Study

- MY2 is in the SCG for updraft intensity but is an outlier for low surface rainfall — associated with small ice particle sizes and graupel terminal velocity.
- In no-ice runs, MY2 produces much stronger convection than other schemes, associated with a dramatically weakened cold pool and near-optimal balance.
- P3 is in an intermediate group with updraft intensity only slightly weaker than the SCG, with smaller total condensate mass due to lower total ice mass despite similarly strong updrafts.

---

## References (selected)

Milbrandt, J. A., and M. K. Yau (2005a, 2005b): Multimoment bulk microphysics parameterization, Parts I–II. *J. Atmos. Sci.*, **62**, 3051–3081.  
Milbrandt, J. A., and R. McTaggart-Cowan (2010): Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.  
Milbrandt, J. A., and H. Morrison (2016): Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III. *J. Atmos. Sci.*, **73**, 975–995.  
Milbrandt, J. A., A. Glazer, and D. Jacob (2012): Predicting the snow-to-liquid ratio of surface precipitation. *Mon. Weather Rev.*, **140**, 2461–2476.  
Morrison, H., and J. A. Milbrandt (2015): Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
