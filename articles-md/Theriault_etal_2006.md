# On the Simulation of Winter Precipitation Types

**Authors:** J. M. Thériault, R. E. Stewart, J. A. Milbrandt, and M. K. Yau
**Journal:** Journal of Geophysical Research – Atmospheres
**Year:** 2006
**Volume/Pages:** 111, D18202
**DOI:** 10.1029/2005JD006665

---

## Abstract (paraphrased)

A one-dimensional cloud model coupled with a modified double-moment bulk microphysics scheme was developed to simulate winter precipitation type formation. Systematic variations of temperature and moisture profiles (surface temperature, melting and subfreezing layer depths, inversion temperature) were applied in an environment where snow falls continuously through a temperature inversion. The study demonstrates the complex formation pathways for freezing rain, ice pellets, snow, slush, wet snow, and refrozen wet snow, and shows that semimelted particles critically influence which precipitation types form and their quantities.

---

## 1. Introduction

Winter storms cause major societal impacts, and the type of precipitation (snow, freezing rain, ice pellets, wet snow, etc.) is a key determining factor in their hazard. Previous observational and modeling studies had examined freezing rain and ice pellet formation (e.g., Stewart and King 1987; Zerr 1997; Hanesiak and Stewart 1995), but a comprehensive physically-based study of the full spectrum of winter precipitation types — including semimelted particles — was lacking.

The study used a 1-D cloud model based on the Milbrandt and Yau (2005a,b) double-moment bulk microphysics scheme, modified to include semimelted particle categories (wet snow, slush, refrozen wet snow). All four authors were at the Department of Atmospheric and Oceanic Sciences, McGill University.

---

## 2. Model and Experimental Design

### Framework
- One-dimensional column model from 0 to 3 km above the surface
- Double-moment bulk microphysics based on Milbrandt and Yau (2005a,b), modified to include semimelted categories
- Snow input rate: 5 mm h$^{-1}$ (water-equivalent) from 3 km aloft

### Semimelted Particle Categories Added
- **Wet snow**: partially melted snowflake, mostly ice; size/fall-speed parameters similar to snow
- **Slush**: largely liquid; size/fall-speed parameters similar to rain; can freeze into ice pellets
- **Refrozen wet snow**: product of frozen slush/wet snow

Category thresholds based on Matsuo et al. (1981); wet snow forms at 0–1°C, slush melts to rain at >1.5°C.

### Experimental Setup
Starting from a typical temperature profile (surface: ~−1°C, 1-km melting layer peaking at 2°C, 1.5-km subfreezing layer), systematic variations were applied:
- Surface temperature: −0.5, −1, −2, −4, −6°C
- Depth of melting layer: 1000, 1500, 2000 m
- Depth of subfreezing layer: 500, 1000, 1500 m
- Maximum inversion temperature: 2, 4, 6°C

Five key precipitation-type combinations were analyzed: ZR (freezing rain), IP (ice pellets), ZR-IP, IP-RWS-S (ice pellets, refrozen wet snow, snow), and ZR-IP-SL-RWS-S.

Melting parameter $\beta_M = T_{\max} \cdot H_{\text{melting}}$ and refreezing parameter $\beta_F = T_{\min} \cdot H_{\text{subfreezing}}$ (following Zerr 1997) used to characterize regimes.

---

## 3. Key Results

### Impact of Semimelted Particles
- Without semimelted particles: only cloud, rain, graupel, and freezing rain form
- With semimelted particles: cloud, rain, freezing rain, graupel, wet snow, refrozen wet snow, slush, and ice pellets all form
- Freezing of slush (semimelted snow) is a primary ice pellet formation mechanism — often dominant over refreezing of liquid rain drops
- Semimelted particles reduce freezing rain at the surface by providing additional ice pellet production pathways and increasing collisional freezing

### Temperature and Moisture Feedbacks
- Melting of snow creates an isothermal 0°C layer; evaporation/sublimation creates subsaturated layers
- Refreezing of liquid drops warms the subfreezing layer, creating competing feedback effects on precipitation evolution
- Double-moment scheme more accurately represents sedimentation than single-moment (sedimentation velocity depends on both mixing ratio and number concentration)

### Precipitation Type Regimes
- ZR: high melting parameter, shallow subfreezing layer, warmest surface temperatures
- IP: low melting and refreezing parameters; coldest surface temperatures
- ZR-IP: intermediate conditions, widest range of melting and subfreezing layer depths
- IP-RWS-S and ZR-IP-SL-RWS-S: form only within narrow temperature ranges near 0°C inversion maximum — precise atmospheric conditions required
- Results compare reasonably well with observational analyses of Zerr (1997) for ZR and ZR-IP regimes

---

## 4. Concluding Remarks

- Semimelted particle formation fundamentally alters winter precipitation evolution; excluding them gives an incomplete picture of precipitation type diversity
- Some precipitation-type combinations form only in narrow atmospheric profile windows; others (ZR, IP) form across a wide range of conditions
- Key observational gaps identified: semimelted particles are not operationally reported; fine-scale vertical profiles of temperature, moisture, and precipitation types are needed
- Future work should address particle morphology, phase, and fall velocity changes near 0°C, and more rigorous comparison with observations

---

## Key References

- Milbrandt, J. A., and M. K. Yau (2005a,b): A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 2051–3081.
- Zerr, R. J. (1997): Freezing rain: An observational and theoretical study. *J. Appl. Meteor.*, **36**, 1647–1661.
- Hanesiak, J. M., and R. E. Stewart (1995): The mesoscale and microscale of a severe ice pellet storm. *Mon. Wea. Rev.*, **123**, 3144–3162.
- Stewart, R. E., and P. King (1987): Freezing precipitation in winter storms. *Mon. Wea. Rev.*, **115**, 1270–1279.

[Figures 1–8 not reproduced in markdown — see original paper]
