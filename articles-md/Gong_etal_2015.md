# Gong et al. (2015) — Modelling aerosol–cloud–meteorology interaction: A case study with a fully coupled air quality model (GEM-MACH)

**Full citation:** Gong, W., P.A. Makar, J. Zhang, J. Milbrandt, S. Gravel, K.L. Hayden, A.M. Macdonald, and W.R. Leaitch, 2015: Modelling aerosol–cloud–meteorology interaction: A case study with a fully coupled air quality model (GEM-MACH). *Atmos. Environ.*, **115**, 695–715. DOI: 10.1016/j.atmosenv.2015.05.062

**Journal:** Atmospheric Environment  
**Year:** 2015  
**Authors:** W. Gong, P.A. Makar, J. Zhang, J. Milbrandt, S. Gravel, K.L. Hayden, A.M. Macdonald, W.R. Leaitch

---

## Abstract

A fully coupled on-line air quality forecast model, GEM-MACH, was used to study aerosol–cloud interactions for a case of an urban-industrial plume impacting stratocumulus. The aerosol effect on cloud microphysics was achieved by parameterization of cloud droplet nucleation predicted from on-line size- and composition-resolved aerosols coupled with a double-moment cloud microphysics parameterization (Milbrandt–Yau, MYDM). Model simulations with and without the on-line aerosol effect on cloud microphysics were compared against in-situ aerosol and cloud observations from ICARTT 2004. Inclusion of the on-line aerosol interaction with cloud resulted in increased modelled cloud amount and LWC due to increased cloud droplet number concentration ($N_d$), decreased droplet size, and reduced warm precipitation. The modelled LWC and $N_d$ agreed more closely with observations when the on-line aerosol feedback was active. The increased cloud amount reduced downward shortwave radiative flux and surface air temperature, contributing to decreased ozone and increased particle sulphate from enhanced aqueous-phase production.

---

## 1. Introduction

Aerosol–cloud interactions (aerosol indirect effects) affect cloud optical properties, precipitation, and cloud amount. Regional air quality models have historically used off-line meteorology, preventing aerosol feedback to cloud microphysics. The GEM-MACH model (Global Environmental Multiscale model — Modelling Air quality and CHemistry) is an on-line chemical transport model embedded in the Canadian weather forecast model (GEM). This study introduces an aerosol–cloud feedback mechanism in GEM-MACH and evaluates it against in-situ observations from ICARTT 2004 (International Consortium for Atmospheric Research on Transport and Transformation).

---

## 2. The GEM-MACH Model and Feedback Mechanism

### GEM-MACH

GEM-MACH is Environment Canada's operational air quality prediction model. Aerosol chemistry is represented with 9 components; this study uses a 12-bin sectional size representation (0.01–40.96 μm geometric diameter), versus the 2-bin operational version.

### MYDM microphysics

The cloud microphysics scheme used is the Milbrandt–Yau double-moment scheme (MYDM; Milbrandt and Yau, 2005a,b), which predicts mass mixing ratios and number concentrations for six hydrometeor categories: cloud droplets, rain, pristine ice, snow, graupel, and hail. The warm-phase coalescence component is based on bin-model solutions. The original MYDM used a single, invariant CCN type and concentration.

### Aerosol–cloud feedback mechanism

For the AQMEII-2 project, an aerosol–cloud feedback was introduced by:
1. Replacing the Cohard nucleation scheme in MYDM with the Abdul-Razzak and Ghan (AR-G) aerosol activation scheme using on-line, size- and composition-resolved aerosols from the chemistry module.
2. Passing the prognostic $N_d$ from the microphysics back to the chemistry module for cloud processing of tracers.

The updraft speed needed for AR-G activation is parameterized following Hoose et al. (2010):

$$\sigma_w = w_t + 2 \left[ \frac{\text{m}}{\text{kg}_\text{air}} \cdot s^{-1} \cdot g_\text{water}^{-1} \right] \cdot \text{LWC}$$

where $w_t = 0.1$ m s⁻¹ is the turbulent velocity scale.

### Simulation configurations

| Run | Feedback | Nucleation in microphysics |
|-----|----------|--------------------------|
| 2.5-km base case | No | Cohard with invariant CCN |
| ARG0 (default feedback) | Yes | AR-G with on-line aerosols; updraft from Hoose eq. |
| ARG1 | Yes | AR-G; updraft = 0.6 m s⁻¹ (observed $\sigma_w$ Flight 16) |
| ARG2 | Yes | AR-G; updraft = grid-scale vertical velocity |
| BC1 | No | Cohard with invariant CCN; $N_d$ from MYDM used in aerosol module |

---

## 3. Study Case and Simulation Setup

**Case:** 10 August 2004, ICARTT campaign. Two research flights by the NRC Canada Convair 580 sampling in and below stratocumulus ahead of an advancing cold front over Michigan, downwind of the Chicago urban-industrial plume. The plume contained elevated CO, NO$_x$, and SO$_2$ (~100 km horizontal extent). Very little precipitation was observed.

**Simulations:** Nested domains at 15 km (continental), 15 km (regional), and 2.5 km (high-resolution focus domain). The feedback experiments were conducted only at 2.5 km (resolved-cloud resolution). Initialized at 06 Z 10 August 2004 and run for 18 h.

---

## 4. Impact of Aerosol–Cloud Interaction

### 4.1 Cloud Microphysics and Meteorology

- ARG0 feedback run produced significantly more extensive clouds than the base case, especially at 23 Z when the base case predicted very little cloud. LWC increased by 0.2–1 g kg⁻¹ on average ~+0.6 g kg⁻¹ over the study area.
- $N_d$ from the base case: 20–50 cm⁻³; from ARG0: 200–500 cm⁻³.
- Cloud droplet mass-mean diameter: ~30–40 μm (base) versus ~20 μm (ARG0).
- ARG0 significantly reduced warm precipitation.
- Liquid water path (LWP) increased by 0.5–1 kg m⁻² (up to 2 kg m⁻²) over the study area in ARG0.
- Downward shortwave flux at surface reduced by up to 2°C in surface air temperature in ARG0.
- Base case significantly under-predicted $N_d$ (avg < 10 cm⁻³) and cloud extent; ARG0 $N_d$ (avg ~200 cm⁻³, median ~120 cm⁻³) was much closer to observations (avg ~150 cm⁻³).

### 4.2 Chemical Tracers

- Ground-level O₃ decreased in ARG0 over and downwind of Lake Michigan due to increased cloud attenuation of photolysis rates.
- SO₂ differences were subtle; particle sulphate (PM₂.₅) increased in ARG0 due to enhanced in-cloud aqueous-phase sulphate production from increased LWC.

### 4.3 Aerosol Size Distribution

- Modelled aerosol size distributions do not capture the observed three-mode pattern, particularly under-predicting accumulation-mode aerosol (likely due to severe under-prediction of organics).
- In-plume aerosol enhancement is reproduced qualitatively. The feedback run shifts the modelled size distribution to larger sizes.

---

## 5. Model Sensitivity: Aerosol Activation

### 5.1 Updraft Velocity Sensitivity

- ARG1 (constant 0.6 m s⁻¹ updraft from observed below-cloud gust velocity) gave overall lower $N_d$, smaller LWC increases, and larger cloud droplet sizes than ARG0; it showed marked improvement in both LWC and $N_d$ for Flight 16.
- ARG2 (grid-scale vertical velocity) produced the weakest activation and LWC — much less than observed.
- ARG1 cloud fraction (29%) was closest to observations (31%). Parameterization of sub-grid cloud-scale updraft is a major source of uncertainty.

**Offline AR-G sensitivity:** At intermediate updraft speeds (0.3–0.6 m s⁻¹), $N_d$ is relatively insensitive to differences in aerosol size distribution, because the activation diameter (~80 nm) is in a size range where modelled and observed $N_a$ are similar (~10%).

### 5.2 Aerosol Activation and Chemistry

- The Jones empirical scheme in the base case gives $N_d$ near its cap (375 cm⁻³) over the study area; Cohard scheme (BC1) gives $N_d$ mostly < 50 cm⁻³.
- Aerosol activation mainly controls the processed aerosol size distribution; the feedback mechanism (ARG0) also enhances bulk sulphate mass production through increased cloud water.

---

## 6. Conclusions

1. Including on-line aerosol indirect feedback increased modelled cloud amount and LWC by up to 1 g kg⁻¹ (LWP by 0.5–2 kg m⁻²), with higher $N_d$, smaller droplets, and reduced precipitation — consistent with the second aerosol indirect effect.
2. The feedback improved agreement with in-situ observations of LWC, $N_d$, SO₂, and sulphate.
3. Increased cloud from the feedback decreased surface O₃ via reduced photolysis and increased PM₂.₅ sulphate via enhanced aqueous-phase oxidation.
4. Parameterization of cloud-scale updraft velocity is a major uncertainty in the AR-G activation scheme at typical NWP grid spacings.
5. The MYDM scheme (Milbrandt–Yau two-moment) was essential for enabling the aerosol–cloud feedback, as single-moment schemes in GEM cannot accommodate prognostic $N_d$.

---

## Key References

Milbrandt, J.A., and M.K. Yau (2005a, 2005b): A multimoment bulk microphysics parameterization, Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.  
Abdul-Razzak, H., and S.J. Ghan (2002): A parameterization of aerosol activation 3. Sectional representation. *J. Geophys. Res. Atmos.*, **107**. DOI: 10.1029/2001JD000483.
