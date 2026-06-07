# A Case Study of Processes Impacting Precipitation Phase and Intensity during the Vancouver 2010 Winter Olympics

**Authors:** Julie M. Thériault, Roy Rasmussen, Trevor Smith, Ruping Mo, Jason A. Milbrandt, Melinda M. Brugman, Paul Joe, George A. Isaac, Jocelyn Mailhot, and Bertrand Denis
**Journal:** Weather and Forecasting
**Year:** 2012
**Volume/Pages:** 27, 1301–1325
**DOI:** 10.1175/WAF-D-11-00114.1

---

## Abstract (paraphrased)

Accurate forecasting of precipitation phase and intensity was critical for Olympic venue managers during the Vancouver 2010 Winter Games. A winter storm on 13–14 February 2010 during the men's downhill ski event was analyzed using the dense SNOW-V10 observation network, GEM-LAM model runs at 15-km, 2.5-km, and 1-km grid spacing, and 1D sensitivity simulations with a bulk microphysics scheme. The study demonstrates that diabatic cooling due to melting snow was the dominant process keeping near-surface temperatures at 0°C and producing snowfall (rather than rain) on Whistler Mountain during the early part of the storm, before warm-air advection became dominant.

---

## 1. Introduction and Context

Forecasting precipitation phase over complex terrain in near-0°C conditions is a critical challenge. During the Vancouver 2010 Winter Olympics, the elevation of the rain–snow transition zone in the Whistler–Creekside area was near the elevation of the alpine venues, making it very difficult to determine whether rain or snow would occur at competition sites.

The study is part of the SNOW-V10 (Science of Nowcasting Olympic Weather for Vancouver 2010) project, which provided a high-density observing network and high-resolution NWP support for the Games. Related papers include Joe et al. (2010, 2012), Isaac et al. (2012), Mailhot et al. (2010, 2012), and Mo et al. (2012).

---

## 2. The Storm: 13–14 February 2010

An intense frontal system (atmospheric river, 958-hPa low over Gulf of Alaska) brought heavy precipitation to the Whistler area. Strong south-to-southeasterly low-level jets advected warm, moist Pacific air toward the Coast Mountains. Synoptic-scale guidance (15-km models) suggested warm-air advection would keep temperatures above 0°C, but observations showed a rapid cooling to ~0°C at ~0000 UTC 14 February, coinciding with the onset of precipitation (predominantly snow at mountain elevations). 

Eight hours of precipitation was observed (0000–0800 UTC 14 February). The storm produced 8.8–26.9 mm water equivalent at various Olympic sites. A shift from up-valley to down-valley flow was also observed and is analyzed as a consequence of the diabatic cooling.

---

## 3. Observational Analysis

### Key findings from the SNOW-V10 station network:
- Near the top of Whistler Mountain (RND, ~1850 m MSL): below-0°C temperatures, predominantly frozen precipitation (graupel, snow)
- Near the base of Whistler Mountain (VOT, ~805 m MSL): above-0°C temperatures throughout, rain or drizzle
- Callaghan Valley (VOD, ~869 m MSL): temperatures reached 0°C, consistent with stronger diabatic cooling
- The 0°C isothermal layer persisted for ~6 h at lower elevations, consistent with latent heat absorption during snow melting

### Radar observations:
- VVO C-band Doppler radar (0°, 73° cross sections) showed a radar bright band near the melting level
- Freezing level rose from 1.2 to 1.5 km MSL during the storm
- Down-valley flow in the Whistler area was captured by radar radial velocity

---

## 4. NWP Model Comparison (GEM-LAM)

Three nested GEM-LAM configurations were run:
- **LAM-15** (15-km): operational regional analysis initialization; Kain–Fritsch convective parameterization
- **LAM-2.5** (2.5-km): nested within LAM-15
- **LAM-1** (1-km, GEM-LAM 1-km): nested within LAM-2.5; no convective parameterization

All configurations used the **full double-moment Milbrandt and Yau (2005a,b) bulk microphysics scheme** for grid-scale clouds and precipitation. Radar reflectivity was computed from model hydrometeor fields using the formulation of Milbrandt and Yau (2005a,b) and Milbrandt et al. (2008).

### Model performance:
- GEM-LAM 1-km captured the general temperature and precipitation-phase structure reasonably well, especially at higher elevations
- At lower elevations: observed surface temperature was ~2°C warmer than the 15-km model forecast, contributing to forecast errors in phase
- GEM-LAM 1-km showed the down-valley flow and isothermal layer development but slightly underestimated the depth of the down-valley flow
- Both models failed to capture a warming layer at 1.3–1.5 km at 0600 UTC (likely due to wind speed bias in the valley)

---

## 5. Sensitivity Studies: 1D Cloud Model

A 1D kinematic cloud model (Thériault and Stewart 2010) based on the Milbrandt–Yau double-moment scheme was used to isolate the role of diabatic cooling.

Key setup:
- Initialized from 0000 UTC 14 February 2010 sounding (VOC)
- Snow falling from 2.5 km MSL into a melting layer base at 1.2 km MSL
- Precipitation rates tested: 1, 2, 3, 5 mm h$^{-1}$
- Horizontal wind effects neglected (near-calm conditions during 0000–0600 UTC)

### Results:
- Precipitation rate of ≥1 mm h$^{-1}$ produced a deep 0°C isothermal layer within ~6 h
- Higher precipitation rates produced deeper isothermal layers and more rapid surface cooling
- At 2 mm h$^{-1}$: surface temperature ~0.5°C at VOT, ~0°C at VOD — consistent with observations
- Evaporation of rain dominated cooling during the first ~60 min (subsaturated air at low levels); melting snow cooling dominated thereafter
- 1D results strongly support the interpretation that diabatic cooling of melting snow was the primary driver of the temperature drop and precipitation phase transition during 0000–0600 UTC

---

## 6. Concluding Remarks

- Diabatic cooling of melting snow dominated over warm-air advection during the first 6 h of the storm, resulting in snowfall rather than rain at lower elevations of Whistler Mountain and in the Callaghan Valley
- The resulting cold, dense air likely triggered the observed down-valley flow shift
- GEM-LAM 1-km showed considerable promise for capturing such diabatic processes in complex terrain, though biases in wind speed and temperature timing were identified
- Accurate microphysical parameterization of the melting/refreezing layer is critical for winter precipitation forecasting near 0°C in mountainous terrain

---

## Key References

- Milbrandt, J. A., and M. K. Yau (2005a,b): A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 2051–3081.
- Milbrandt, J. A., et al. (2008): *Mon. Wea. Rev.*, **136**, 3873–3893.
- Mailhot, J., and Coauthors (2010): [GEM configuration for Vancouver 2010 Olympics — MPAG]
- Joe, P., and Coauthors (2010): SNOW-V10 observational network — JPAG
- Isaac, G. A., and Coauthors (2012): [IPAG — SNOW-V10]
- Mo, R., and Coauthors (2012): [Orographic processes — SNOW-V10]

[Tables 1 and Figures 1–20, Appendices A–B not reproduced in markdown — see original paper]
