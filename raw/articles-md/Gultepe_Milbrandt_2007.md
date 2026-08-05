# Gultepe and Milbrandt (2007) — Microphysical Observations and Mesoscale Model Simulation of a Warm Fog Case during FRAM Project

**Full citation:** Gultepe, I., and J. A. Milbrandt, 2007: Microphysical Observations and Mesoscale Model Simulation of a Warm Fog Case during FRAM Project. *Pure Appl. Geophys.*, **164**, 1–18. DOI: 10.1007/s00024-007-0212-9

**Journal:** Pure and Applied Geophysics  
**Year:** 2007  
**Authors:** I. Gultepe, J. A. Milbrandt

---

## Abstract

The objective of this work is to apply a new microphysical parameterization for fog visibility for potential use in numerical weather forecast simulations, and to compare the results with ground-based observations. Observations from the Fog Remote Sensing And Modeling (FRAM) field project (winter 2005–2006, southern Ontario, Phase I) are used. LWC, droplet number concentration ($N_d$), and temperature were obtained from hot-wire probes, fog measuring device (FMD) spectra, and the Rosemount probe. Visibility (Vis), liquid water path, and inferred fog properties were also used. Results show that Vis is nonlinearly related to both LWC and $N_d$. Comparisons between newly derived parameterizations and those already in use (as a function of LWC alone) suggested that if models can predict the total $N_d$ and LWC at each time step using a detailed microphysics parameterization, Vis can be calculated for warm fog conditions. Using outputs from the Canadian MC2 model with a new multi-moment bulk microphysical scheme, the new Vis parameterization resulted in more accurate Vis values where the correction reached up to 20–50%.

---

## 1. Introduction

Fog occurrence exceeding 10% of time in some regions of Canada motivates improved fog forecasting. The current NWP parameterization for fog visibility (a function of LWC alone, following Kunkel 1986 and Stoelinga and Warner 1999) is inaccurate because it neglects $N_d$. Gultepe et al. (2006) showed that $N_d$ can change from a few droplets per cm³ to 100 cm⁻³ for a fixed LWC, with uncertainties in Vis exceeding 50% if $N_d$ is excluded. This work applies a new Vis parameterization incorporating $N_d$ and evaluates it using an MC2 model simulation with the Milbrandt–Yau multi-moment scheme.

---

## 2. Observations

FRAM field project, 1 December 2005 – 18 April 2006, at the Centre for Atmospheric Research Experiment (CARE) site near Toronto, Ontario. Instruments included:

- DMT fog measuring device (FMD) — droplet size spectra
- Vaisala CT25K ceilometer
- DRI Hot Plate
- Radiometrics MWR (profiling and standard) — LWC, T, RHw profiles
- Vaisala FD12P — visibility
- POSS (Precipitation Occurrence Sensor System)

**Case analyzed:** 4 January 2006 — warm fog event (warm front moving across Ontario).

---

## 3. Parameterization of Visibility

The extinction parameter $\beta_\text{ext}$ is calculated from FSSP measurements:

$$\beta_\text{ext} = \sum Q_\text{ext} \, n(r) \pi r^2 \, dr$$

Converted to visibility via Stoelinga and Warner (1999):

$$\text{Vis} = -\ln(0.02) / \beta_\text{ext}$$

Using RACE in-situ observations, a new "fog index" parameterization is derived:

$$\text{Vis}_\text{fi} = \frac{1}{(\text{LWC} \cdot N_d)^{0.65}}$$  (Eq. 3)

indicating Vis is inversely related to both LWC and $N_d$ (valid for $N_d \leq 400$ cm⁻³, LWC $\leq 0.5$ g m⁻³).

From the 4 January 2006 FRAM data (1-min averages):

$$\text{Vis} = 1.13 (\text{LWC} \cdot N_d)^{-0.51}$$  (Eq. 4)

agreeing with Eq. 3 for low stratiform clouds.

New parameterizations are also derived for the fog settling rate and droplet terminal velocity:

$$V_t \cdot \text{LWC} = 73138 \cdot \text{LWC}^{5/3} \cdot N_d^{-(2/3) \cdot 1.1}$$  (Eq. 5)

$$V_t = 0.006 \left( \frac{\text{LWC}}{N_d} \right)^{0.61}$$  (Eq. 8)

---

## 4. Model Description and Setup

**Model:** Canadian Mesoscale Compressible Community (MC2) model.

**Microphysics:** Triple-moment version of the Milbrandt–Yau (2005a,b) multi-moment bulk scheme at the 2-km domain. The scheme predicts cloud mass mixing ratio and number concentration ($N_d$) independently for separate cloud and rain categories, enabling direct application of the new Vis parameterization (Eq. 3).

**Domain:** Nested; 10-km outer domain (301×301 points) initialized from 15-km CMC regional analyses at 0000 UTC 4 January 2006, nested to 2-km inner domain (251×251 points) run for 18 h starting 0600 UTC. Both domains use 41 modified Gal-Chen levels with 12 in the PBL.

---

## 5. Results

**Observations (4 January 2006):**
- Heavy fog at CARE site between ~20:30–22:30 UTC; T ≈ 5°C, RHw = 100%, Vis ≈ 30–500 m
- Max observed $N_d$ from FMD: ~100 cm⁻³; corresponding LWC: ~0.1 g m⁻³
- Bimodal droplet size distribution, with the second mode from drizzle-sized drops (>15 μm)

**Model (19:00 UTC):**
- Simulated $N_d$: 50–150 cm⁻³ over CARE site
- Simulated LWC: 0.02–0.10 g m⁻³ over CARE site
- Simulated Vis (from Eq. 3): 100–500 m

**Model (21:00 UTC):**
- Peak $N_d$ reached ~200 cm⁻³ in some regions (observed: 100 cm⁻³ at CARE)
- LWC: 0.10–0.30 g m⁻³ near CARE site (observed FMD: up to 0.1 g m⁻³; MWR: up to 0.4 g m⁻³ — elevated by rain contribution)
- Simulated Vis: 50–500 m at CARE site
- Overall the simulated Vis range (50–500 m) broadly agrees with observations (30–500 m)

---

## 6. Conclusions

1. Fog visibility is nonlinearly related to both LWC and $N_d$; parameterizations using LWC alone can have uncertainties exceeding 50%.
2. A new visibility parameterization, $\text{Vis} \sim (\text{LWC} \cdot N_d)^{-0.65}$, is validated against FRAM observations for warm fog.
3. New parameterizations for fog droplet settling rate and terminal velocity are derived.
4. For NWP models, the new Vis parameterization requires a double-moment cloud scheme that prognoses $N_d$ independently of LWC. The MY triple-moment scheme provides this capability.
5. Alternatively, a diagnostic $N_d$ from environmental conditions (T, moisture) could be used in single-moment NWP models to apply the new Vis parameterization.
6. Application potential exists for GEM, WRF, and RUC forecast models.
