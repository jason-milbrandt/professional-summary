# Thériault et al. (2015)

**Full citation:** Thériault, J. M., J. A. Milbrandt, J. Doyle, J. R. Minder, G. Thompson, N. Sarkadi, and I. Geresdi, 2015: Impact of melting snow on the valley flow field and precipitation phase transition. *Atmos. Res.*, **156**, 111–124. DOI: 10.1016/j.atmosres.2014.12.006

---

## Abstract

The prediction of precipitation phase and intensity in complex terrain is challenging when the surface temperature is near 0°C. In calm weather conditions, melting snow often leads to a 0°C isothermal layer. The temperature feedback from melting snow generates cold dense air moving downslope, altering the dynamics of the storm. A correlation has been commonly observed between the direction of the valley flow and the precipitation phase transition in complex terrain. This study examines the impact of the temperature feedback from melting snow on the direction of the valley flow when the temperature is near 0°C. Semi-idealized 2D simulations using WRF were conducted for a case of moderate precipitation in the Pacific Coast Ranges. Results demonstrate that the temperature feedbacks caused by melting snow affect the direction of the flow in valleys. Several microphysics schemes (1-moment bulk, 2-moment bulk, and bin) all produced a valley flow reversal but at different rates. Experiments examining sensitivity to the initial prescribed snow mixing ratio aloft were conducted to study the threshold precipitation rate at which this change in the direction of the valley flow field can occur.

---

## 1. Introduction

Precipitation phase (rain vs. snow) affects water resources, flood hazard, and storm evolution. Melting snow leads to diabatic cooling that can alter the temperature profile, induce mesoscale circulations, and influence storm evolution. Steiner et al. (2003) observed via radar that a change from up-valley to down-valley flow and precipitation phase transition occur simultaneously. Zängl (2007) concluded that melting only has a small contribution to valley flow changes. Prior work in Milbrandt et al. (2014) in a 1D framework showed that the cooling rate and phase transition timing are sensitive to the representation of snow (fall speed parameters, number of prognostic moments, slope parameter constraints, melting process assumptions).

**This study aims** to better understand the impact of temperature feedbacks from melting snow on (1) the direction of the valley flow field and (2) the precipitation phase, using 2D semi-idealized WRF simulations of the 13–14 February 2010 Whistler, BC case.

---

## 2. Experimental Design

### 2a. Case Overview

The 13–14 February 2010 case in the Callaghan Valley, Whistler, BC, during SNOW-V10 (Vancouver 2010 Winter Olympics). An intense warm frontal system approached slowly. Key observations:
- Rapid decrease of surface air temperature in Callaghan Valley (VOD) from 2230 UTC 13 Feb to 0000 UTC 14 Feb 2010.
- Surface temperature remained at 0°C for several hours (indicating temperature feedback from melting snow as dominant forcing).
- Correlation between the precipitation phase transition and the rapid cooling and change in valley flow direction (observed by Doppler radar, Thériault et al. 2012).
- Wind transitioned from up-valley to down-valley ~60 min after precipitation onset; flow filled the initial melting layer depth ~90 min after reversal onset.

### 2b. Model Setup

WRF version 3.3.1. Semi-idealized 2D configuration:
- Modified orography corresponding to the Callaghan Valley area (north–south cross-section through VVO radar and VOD valley).
- Near-bell-shaped mountain (~1.2 km height); 200-km domain at 250-m grid spacing, top at 22 km.
- 72 vertical levels (spacing 20–750 m in melting layer, 750 m above 9 km).
- Time step: 1 s; duration: 8 h.
- Coriolis force and surface fluxes neglected.
- Open inflow/outflow boundaries; 10-km damping layer at top.
- Initialized with VOC sounding at 0000 UTC 14 February 2010. Snow field initialized at 2.3 km altitude: $q_s = 1.25$ g kg⁻¹, $N_s = 9860$ m⁻³ (based on radar and temperature), to yield ~5 mm h⁻¹ surface precipitation.

**Control run microphysics:** MY2 (Milbrandt and Yau 2005), 6 categories: cloud droplets, rain, pristine ice, snow, graupel, hail.

### 2c. Sensitivity Experiments

1. **Temperature feedback suppression:** Control run with and without diabatic cooling from melting snow, repeated with Thompson (THOMP) scheme and bin scheme (GERBIN, Geresdi 1998).
2. **Prescribed snow mixing ratio aloft:** $q_s = 2.5, 1.875, 1.25, 0.625, 0.3125$ g kg⁻¹ (corresponding to ~10, 7.5, 5, 2.5, 1.25 mm h⁻¹ surface precipitation), using MY2 only.

---

## 3. Impact of Melting Snow on the Valley Flow Field

### 3a. Control Simulation

At 60 min: 0°C isotherm near VVO and VOD. Snow field initiated upstream at 2.3–6 km. Surface precipitation: rain and snow on upstream side, mainly snow with some graupel 5 km north of VVO. Simulated maximum winds > 20 m s⁻¹ above the barrier between 2–4.5 km.

### 3b. Effect of Melting

- With melting: valley flow starts to change direction at ~120 min, completely reversed at ~210 min (timing comparable to observed).
- Without melting: flow direction and strength remain constant throughout the simulation.
- Melting-induced convection occurs temporarily within and below the melting layer (localized cooling destabilizes the profile), but has little overall effect on the cooling rate.

### 3c. Dynamical Mechanism

The temperature feedback from melting increases the moist non-dimensional mountain height $H_m = N_m h/U$:
- Before melting: $H_m = 1.9$.
- After melting: $H_m = 3.3$ (flow stagnation favored above threshold ~$H = 0.85$ for a 2D ridge).
- Without melting (sublimation only): $H_m = 2.2$ (more modest change).

**Mechanism:** Melting cools the low-level air to 0°C, bringing it to saturation, condensing excess vapor, and greatly increasing the dry stratification ($\theta$ and $N_m^2$). This low-level high-pressure anomaly (up to 0.5 Pa over the mountain slopes extending upwind) produces horizontal pressure gradients that decelerate the horizontal flow. As air lifts over the decelerated air near the mountain base, pressure anomalies propagate far upwind, eventually causing flow stagnation and reversal.

---

## 4. Factors Impacting the Timing of the Valley Flow

### 4a. Microphysics Scheme Comparison (MY2, THOMP, GERBIN)

All three schemes produce valley flow stagnation/reversal when melting is active. None produce reversal when the temperature feedback from melting is disabled.

Timing differences:
- Wind speed reaches 0 m s⁻¹ at 180 min (MY2), 210 min (THOMP), 200 min (GERBIN).
- MY2 cools faster because: (1) snow falls faster in MY2; (2) in THOMP, terminal velocity is doubled when T > 0°C in the melting layer (shorter melting-layer residence time → reduced cooling); (3) bin scheme provides discrete melted-water mass bins without shedding.

Precipitation phase transition timing: 50/50 rain/snow at surface between 68–80 min for all schemes; differences due to different snow parameterization and shedding treatment.

### 4b. Sensitivity to Precipitation Rate (MY2)

All 5 prescribed precipitation rates (1.25–10 mm h⁻¹) produce a flow reversal, but at different timings:
- Onset of flow change: varies by ~40 min from 1.25 to 5 mm h⁻¹; much faster for rates > 5 mm h⁻¹.
- At 10 mm h⁻¹: valley flow starts reversing nearly immediately; complete reversal takes ~180 min.
- At 1.25 mm h⁻¹: onset of reversal takes ~4 h; complete reversal takes ~360 min.
- Elapsed time between onset and complete reversal increases with precipitation rate (65 min at 10 mm h⁻¹, 110 min at 1.25 mm h⁻¹).
- Rain–snow boundary descends the mountainside before the valley flow completely reverses for higher precipitation rates (e.g., for 5 mm h⁻¹, reversal onset and 0°C arrival at mountain base occur simultaneously).

Even very light snowfall (~1 mm h⁻¹) will eventually cool and stratify the air enough to reverse the valley flow, but requires ~8 h of sustained calm synoptic conditions.

---

## 5. Summary and Conclusions

Key findings:
1. The temperature feedback from melting snow is necessary and sufficient to produce a valley flow direction change in all microphysics schemes tested.
2. Without this feedback, no reversal occurs in any scheme.
3. All precipitation rates tested produce a flow reversal, but timing varies substantially.
4. Faster precipitation rates cool the valley air faster, accelerating flow reversal onset.
5. The rain–snow boundary at the mountain base generally precedes complete reversal of the valley flow field.
6. MY2 scheme cools and produces flow reversal slightly faster than THOMP, due to different snow fall speed and melting parameterizations.

Demonstrated practical relevance for local weather prediction during the Vancouver 2010 Winter Olympics, where this type of valley flow and phase transition was critical for safe competition conditions.

**Future work:** Full 3D atmospheric model; study the impact of valley geometry; examine relative timing of large-scale warm air advection vs. melting-induced cooling.

---

## References (selected)

- Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, **62**, 3065–3081.
- Milbrandt, J. A., J. M. Thériault, and R. Mo, 2014: Modeling the phase transition associated with melting snow in a 1D kinematic framework: sensitivity to the microphysics. *Pure Appl. Geophys.*, **171**, 303–322.
- Thériault, J. M., and Coauthors, 2012: A case study of processes impacting precipitation phase and intensity during the Vancouver 2010 Winter Olympics. *Wea. Forecasting*, **27**, 1301–1325.
- Steiner, M., and Coauthors, 2003: Airflow within major alpine river valleys under heavy rainfall. *Q. J. R. Meteorol. Soc.*, **129**, 411–431.
- Thompson, G., P. R. Field, R. M. Rasmussen, and W. D. Hall, 2008: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part II. *Mon. Wea. Rev.*, **136**, 5095–5115.
- Geresdi, I., 1998: Idealized simulation of the Colorado hail storm case: comparison of bulk and detailed microphysics. *Atmos. Res.*, **45**, 237–252.

[Figure captions not reproduced — see original paper for Figs. 1–13]
