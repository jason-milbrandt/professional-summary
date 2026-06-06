# Mo et al. (2019)

**Full citation:** Mo, R., Brugman, M. M., Milbrandt, J. A., Goosen, J., Geng, Q., Emond, C., Bau, J., and Erfani, A., 2019: Impacts of hydrometeor drift on orographic precipitation: Two case studies of landfalling atmospheric rivers in British Columbia, Canada. *Wea. Forecasting*, **34**, 1211–1237. DOI: 10.1175/WAF-D-18-0176.1

---

## Abstract

Two severe winter storms in 2016 and 2017 caused by landfalling atmospheric rivers (ARs) over British Columbia (BC) are investigated. The main concern is the impact of hydrometeor drift on orographic precipitation. It is shown that the dominant contribution to windward orographic precipitation was from horizontal moisture convergence. Precipitation distributions were also influenced by the convergence/divergence of condensed water due to the wind-driven effect on hydrometeors.

Observed hourly and daily precipitation amounts are used to verify the performances of three Canadian NWP systems (GDPS-25km, RDPS-10km, HRDPS-2.5km). These operational systems were capable of predicting the general features of orographic precipitation. However, the two coarse-resolution systems used a diagnostic precipitation scheme that does not fully simulate hydrometeor drift. The HRDPS-2.5km with a prognostic precipitation scheme was substantially more accurate and skillful in predicting upwind precipitation and leeward spillover. Evidence shows the spillover effect was overpredicted by the HRDPS due to a systematic bias originating in the MY2 microphysics scheme. This problem has been improved in the current HRDPS with the P3 microphysics scheme. Two postprocessing schemes (AWB and HDC) are proposed to improve QPFs from diagnostic precipitation schemes.

---

## 1. Introduction

Heavy orographic precipitation triggered by landfalling ARs can cause severe floods, landslides, and avalanches over complex terrain. Predicting the spatial distribution of orographic precipitation is difficult partly due to the hydrometeor drift process — the wind-driven advection of condensed water that can cause precipitation to fall on leeward slopes (spillover). Diagnostic precipitation schemes, which assume hydrometeors fall instantaneously, do not simulate this process.

The January 2016 AR event was a forecast challenge: the Vancouver International Airport (VVR) received only 28 mm in 24 h, but the diagnostic-scheme GDPS-25km and RDPS-10km predicted 85 mm and 74 mm respectively (public warning threshold for Metro Vancouver: 50 mm). This overprediction highlights how diagnostic schemes can mislead forecasters about the spatial distribution of precipitation.

---

## 2. Atmospheric Water Balance Framework

### Water Balance Decomposition

The vertically integrated atmospheric water balance:

$P = E - \frac{\partial(W + W_c)}{\partial t} - \nabla \cdot (Q + Q_c)$

where:
- $P$ = surface precipitation rate
- $E$ = surface evaporation rate
- $W$ = vertically integrated water vapor (IWV)
- $W_c$ = integrated condensed water (ICW)
- $Q$ = integrated water vapor flux (IWVF)
- $Q_c$ = integrated condensed water flux (ICWF)
- $C_{wv} \equiv -\nabla \cdot Q$ = convergence of IWVF
- $C_{cw} \equiv -\nabla \cdot Q_c$ = convergence of ICWF (hydrometeor drift term)

For a synoptic-scale heavy precipitation event, $P$ and $C_{wv}$ dominate; $C_{cw}$ can be 3–20× smaller than $C_{wv}$ in most areas but is locally important over and downwind of mountain crests.

Two postprocessing QPF schemes based on this framework:
- **AWB (Atmospheric Water Balance):** $P_{AWB} = (ECR - \nabla \cdot Q_c) \geq 0$, where $ECR = [E - \partial(W+W_c)/\partial t - \nabla \cdot Q] \geq 0$
- **HDC (Hydrometeor Drift Calibration):** $P_{HDC} = (FPR - \nabla \cdot Q_c) \geq 0$, where FPR is the model forecast precipitation rate

---

## 3. Geography, Data, and NWP Systems

### Physical Geography

Southern BC has four major mountain ranges: Vancouver Island Ranges, Coast–Cascade Mountains, Columbia Mountains, and Rocky Mountains. The coastal mountains receive the greatest precipitation from onshore Pacific airstreams; the rain-shadow effect leaves the interior much drier.

### Observed Data

176 weather stations across southern BC; hourly and daily precipitation data validated against freezing-level information to exclude unreliable gauge data from solid precipitation.

### NWP Systems

| System | Grid | Precipitation scheme |
|--------|------|---------------------|
| GDPS-25km | Yin-Yang, ~17–25 km | Modified Sundqvist (diagnostic: hydrometeors fall instantaneously) |
| RDPS-10km | 10 km | Modified Sundqvist (diagnostic) |
| HRDPS-2.5km | 2.5 km | MY2 or P3 (prognostic: hydrometeors advected by model dynamics) |

GDPS and RDPS use the Sundqvist scheme, which advects non-sedimenting condensate but not precipitating hydrometeors — no hydrometeor drift. HRDPS-2.5km used the **Milbrandt-Yau double-moment (MY2) scheme** (Milbrandt and Yau, 2005a,b) for the 2016 storm analysis. On 18 September 2018, HRDPS-2.5km was upgraded to the **P3 scheme** (Morrison and Milbrandt, 2015; Morrison et al., 2015; Milbrandt and Morrison, 2016); results from a parallel P3 run are shown for the 2017 storm.

---

## 4. The 26–28 January 2016 Storm

### Synoptic Analysis

A deep extratropical cyclone (deepened from off Japan, minimum MSLP ~950 hPa) approached BC, accompanied by a robust AR in the pre-cold-frontal LLJ. The cold front made landfall on the BC South Coast around 1200 UTC 28 January. A blocking anticyclone over the Rocky Mountains strengthened the AR and slowed frontal passage.

### Atmospheric River Analysis

IVT maximum exceeded 500 kg m⁻¹ s⁻¹ ahead of the cold front at landfall. The AR core (WVF > 150 g m⁻² s⁻¹) was ~450 km wide, collocated with a 850–950 hPa LLJ. Water balance analysis (valid at 0000 UTC 28 January):
- $C_{wv}$ dominated on windward slopes (> 4 mm h⁻¹)
- $C_{cw}$ was 3–20× smaller than $C_{wv}$ in most areas, but showed clear dipole patterns across mountain crests indicating spillover
- Significant positive $C_{cw}$ on East Vancouver Island indicates spillover

### Observed Precipitation

- West Vancouver Island: four stations with 24-h totals > 170 mm; maximum at Effingham (FEH) = 379 mm in 24 h, 583 mm in 48 h
- East Vancouver Island (rain shadow): 121 mm at Bowser (FBO), 103 mm at Cochrane (HRN) — both under-forecast and not warned
- Lower Mainland (Metro Vancouver): warning threshold (50 mm) exceeded at several stations; Vancouver Airport (VVR) = 28 mm, Howe Sound maximum = 218 mm

Warning sequence: initial warning for Metro Vancouver at 1245 UTC 27 Jan (6–12 h lead time), East Vancouver Island added at 2310 UTC (late, triggered by observations), West/Inland Vancouver Island even later at 2352 UTC.

### QPF Comparison

Valid at 0000 UTC 28 January:
- HRDPS-2.5km (MY2): VVR predicted 1.1 mm h⁻¹ (observed 1.0 mm h⁻¹); Tatlayoko Lake (XTL, leeward): predicted 2.5 mm h⁻¹ (observed 3.6 mm h⁻¹)
- GDPS-25km: VVR predicted 5.2 mm h⁻¹; XTL predicted 0.0 mm h⁻¹
- HDC scheme: XTL 0.2 mm h⁻¹ (improvement over GDPS 0.0), VVR 4.6 mm h⁻¹ (still over-forecast)
- Major hydrometeor drift effect: clear downstream shift in HRDPS QPF vs. GDPS, especially in lee of Coast–Cascade Mountains

24-h QPF validation (whole domain, 171 stations):

| System | RMSE (mm) | CORR | Bias (mm) | RSS |
|--------|-----------|------|-----------|-----|
| HRDPS-2.5km (MY2) | 24.1 | 0.85 | 0.7 | 0.63 |
| RDPS-10km | 39.4 | 0.70 | 2.7 | 0.0 |
| GDPS-25km | 35.8 | 0.66 | 2.3 | 0.17 |

On windward sides, HRDPS-2.5km was best; on leeward sides, GDPS-25km paradoxically out-performed HRDPS (resolution-smoothing effect + MY2 systematic bias toward over-spillover).

HDC scheme: slight improvement over GDPS-25km QPFs; RSS(GDPS) = 0.38, RSS(HDC) = 0.42 relative to AWB.

---

## 5. The 16–18 January 2017 Storm

### Synoptic Features

A similar AR event: 965-hPa occluded cyclone + subtropical high → strong AR developed in tropical western Pacific. Landfall ~1800 UTC 16 January; maintained impact on BC South Coast for 48 h.

### Observed Precipitation

Maximum 24-h amount: 322 mm at Effingham (FEH). East Vancouver Island: 66 mm at FBO (exceeded 50 mm warning criterion). Lower Mainland: 124 mm local maximum in Howe Sound. Warnings did not cover West Vancouver Island (where > 100 mm observed).

### Hydrometeor Drift and MY2 Bias

HRDPS-2.5km significantly outperformed GDPS/RDPS overall. However, HRDPS over-predicted spillover into the lee of the Coast–Cascade Mountains:
- Observed values near ridgeline and Okanagan Valley generally lower than HRDPS predictions
- Root cause: **systematic bias in MY2 microphysics**. In situations of light riming (snow crossing mountains with orographic lift pockets of liquid water), MY2 increases snow mass but not density/fall speed until riming exceeds a threshold for snow-to-graupel conversion. This leads to slower-falling hydrometeors being advected farther downstream.

24-h QPF validation (whole domain, 151 stations):

| System | RMSE (mm) | CORR | RSS |
|--------|-----------|------|-----|
| HRDPS-2.5km (MY2) | — | — | ~0.50* |
| RDPS-10km | — | — | 0.0 (reference) |
| GDPS-25km | — | — | 0.50* |
| HRDPS-2.5km (P3) | — | — | **0.84** |

*Values from text: MY2 RMSE on leeward = worse than RDPS (14.2) and GDPS (17.1)

### P3 Improvement

The P3 scheme (parallel run):
- P3 RMSE on leeward sides: **10.3 mm** (vs. MY2 leeward: not explicitly stated but worse; RDPS leeward: 14.2 mm; GDPS leeward: 17.1 mm)
- P3 RSS (whole domain): **0.84** vs. MY2 ~0.50
- P3 correctly represents gradual increases in fall speed with riming, avoiding the categorical snow→graupel threshold problem

Morrison et al. (2015) noted a similar MY2 vs. P3 difference for an Oregon Cascades orographic case.

---

## 6. Discussion and Conclusions

1. **Moisture convergence dominates** windward orographic precipitation; hydrometeor drift (convergence of condensed water) is 3–20× smaller but locally important on leeward slopes
2. **HRDPS-2.5km with prognostic microphysics substantially outperforms** GDPS/RDPS on overall QPF skill (RMSE, CORR, RSS)
3. **MY2 systematic bias**: overpredicts spillover because predefined snow/graupel categories cannot represent gradual increase in fall speed during light riming; any scheme using predefined ice categories faces this issue
4. **P3 overcomes this bias**: continuous ice particle property evolution eliminates the threshold-dependent conversion problem; RSS improved from ~0.50 to 0.84
5. **Diagnostic scheme postprocessing**: AWB scheme has limitations due to hourly data errors; **HDC scheme** is simpler and achieves slight improvements over raw model QPFs (RSS 0.42 vs. 0.38 for GDPS); further refinement with higher temporal resolution (5–10 min) data recommended
6. **Any model using diagnostic precipitation** will likely suffer from excessive windward QPF and deficient leeward spillover; the HRDPS with P3 avoids both problems

---

## References (selected)

- Milbrandt, J. A. and Yau, M. K., 2005a, b: MY2 microphysics scheme. *J. Atmos. Sci.*, 62, 3051–3081.
- Morrison, H. and Milbrandt, J. A., 2015: P3 Part I. *J. Atmos. Sci.*, 72, 287–311.
- Morrison, H., Milbrandt, J. A., Bryan, G. H., Ikeda, K., Tessendorf, S. A., and Thompson, G., 2015: P3 Part II. *J. Atmos. Sci.*, 72, 312–339.
- Milbrandt, J. A. and Morrison, H., 2016: P3 Part III. *J. Atmos. Sci.*, 73, 975–995.
- Milbrandt, J. A., Bélair, S., Faucher, M., Vallée, M., Carrera, M. L., and Glazer, A., 2016: HRDPS 2.5 km system description. *Wea. Forecasting*, 31, 1791–1816.
- Milbrandt, J. A., Yau, M. K., Mailhot, J., and Bélair, S., 2008: IMPROVE-2 Part I. *Mon. Wea. Rev.*, 136, 3873–3893.
- Milbrandt, J. A. et al., 2010: IMPROVE-2 Part II. *Mon. Wea. Rev.*, 138, 625–642.
