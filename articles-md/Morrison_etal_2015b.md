# Parameterization of Cloud Microphysics Based on the Prediction of Bulk Ice Particle Properties. Part II: Case Study Comparisons with Observations and Other Schemes

**Full citation:** Morrison, H., J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II: Case study comparisons with observations and other schemes. *J. Atmos. Sci.*, **72**, 312–339, doi:10.1175/JAS-D-14-0066.1.

**Manuscript received:** 20 March 2014 | **Final form:** 3 August 2014 | **Published:** January 2015

**Note:** This is Part II of a two-part series. Part I (Morrison and Milbrandt 2015) describes the P3 scheme and presents idealized 2D squall-line tests.

---

## Abstract

A new microphysics scheme has been developed based on the prediction of bulk particle properties for a single ice-phase category, in contrast to the traditional approach of separating ice into various predefined species (e.g., cloud ice, snow, and graupel). In this paper, the new predicted particle properties (P3) scheme, described in Part I, is tested in 3D simulations using the WRF Model for two contrasting well-observed cases: a midlatitude squall line and winter orographic precipitation. Results are also compared with simulations using other schemes in WRF.

Simulations with P3 can produce a wide variety of particle characteristics despite having only one free ice-phase category. For the squall line, it produces dense, fast-falling, hail-like ice near convective updraft cores and lower-density, slower-falling ice elsewhere. Sensitivity tests show that this is critical for simulating high precipitation rates observed along the leading edge of the storm. In contrast, schemes that represent rimed ice as graupel, with lower fall speeds than hail, produce lower peak precipitation rates and wider, less distinct, and less realistic regions of high convective reflectivity. For the orographic precipitation case, P3 produces areas of relatively fast-falling ice with characteristics of rimed snow and low- to medium-density graupel on the windward slope. This leads to less precipitation on leeward slopes and more on windward slopes compared to the other schemes. Overall, the new scheme produces reasonable results for a reduced computational cost.

---

## 1. Introduction

With recent increases in computer power, NWP at convection-permitting scales ($\Delta x \approx$ a few km) is now routine at many research and operational centers. Parameterizing microphysics remains challenging because of fundamental uncertainty in the underlying microphysical processes, especially for ice. Several studies have shown considerable sensitivity of high-resolution NWP forecasts to the use of different microphysics schemes.

The new P3 bulk scheme (Morrison and Milbrandt 2014, Part I) employs a conceptually different approach: ice evolves through the prediction of various bulk particle properties of a single ice-phase category rather than separating ice into different predefined categories. The scheme includes four prognostic ice mixing ratio variables: total ice mass, rime ice mass, rime volume, and total number—allowing 4 degrees of freedom. This predicts several important physical properties ($\rho_p$, mean size, rime mass fraction $F_r$) as they evolve from microphysical processes.

In this paper, the scheme's practical performance is evaluated by comparing 3D simulations with observations and results using other microphysics schemes in WRF, version 3.4.1. Two contrasting case studies are examined: 1) a midlatitude squall line and 2) an extratropical cyclone with orographic precipitation. Other schemes tested: Morrison (MOR-G, MOR-H), Milbrandt–Yau (MY2), NOAA/NSSL, Stony Brook University–Lin (SBU-LIN), Thompson (THO), WSM6, WDM6.

---

## 2. Case Descriptions and Observations

### 2a. Midlatitude Squall Line

A large mesoscale convective system (MCS) formed in the central Great Plains on 19 June 2007, observed by the dual-polarization WSR-88D radar at Norman, Oklahoma (KOUN) and two 2D video disdrometers (2DVDs). The system developed a classical squall line with strong leading-edge convection and trailing stratiform precipitation.

### 2b. Extratropical Cyclone–Orographic Precipitation (IMPROVE-2)

A large extratropical cyclone and frontal system moved through the Pacific Northwest on 13–14 December 2001 (Garvert et al. 2005a), generating significant vertical motion and orographic precipitation enhancement on the windward slopes of the Cascade Range. This was the focus of the IMPROVE-2 field experiment (Stoelinga et al. 2003). Observations used: microphysical aircraft measurements (P-3 and Convair), soundings, WSR-88D at Portland (KRTX), NCAR S-Pol radar, and surface precipitation gauge network.

---

## 3. Model Description and Setup

WRF model, version 3.4.1. Physical parameterizations for the orographic case: RRTMG radiation, Yonsei University PBL scheme, Noah land surface model.

**Squall-line case:** 3D quasi-idealized, 1-km $\Delta x$, 612 × 122 km$^2$ domain with 100 vertical levels to 25 km. Model top: 25 km; time step: 2.5 s. Initialized from the 0000 UTC Lamont and Norman, Oklahoma, soundings. Convection initiated by prescribed horizontal convergence during the first hour. A horizontal domain translation speed of 17 m s$^{-1}$ was included to keep the storm within the domain.

**Orographic case:** 3D real case, 3-km $\Delta x$, 1200 × 830 km$^2$ domain, initial conditions and lateral forcing from U.S. GFS Final analysis. 72 sigma levels to 100 hPa; time step: 5 s. Model integrations from 0000 UTC 13 December to 1200 UTC 14 December.

---

## 4. Simulation Results: Squall-Line Case

### 4a. Baseline Results with P3

Deep convection is initiated within the first 15 min. Cold pool develops at low levels through melting and evaporation. After ~4 h, the simulated storm reaches a quasi-steady mature phase with dynamical characteristics typical of midlatitude squall lines.

At 6 h:
- Distinct region of high reflectivity (>45 dBZ) approximately 20–30 km wide associated with leading-edge deep convection
- Wide (~160 km) trailing stratiform region with Z mostly 30–40 dBZ
- Broad region of ascending front-to-rear flow at midlevels; descending rear-to-front flow at low levels

P3 features: Dense, fast-falling, hail-like ice in convective updraft cores; lower-density, slower-falling ice in stratiform and anvil regions. Good agreement with observed squall-line structure.

[Figures 3–4: Vertical cross sections and horizontal reflectivity for P3 and other schemes at 6 h — images not reproducible in markdown]

### 4b. Comparison of Microphysics Schemes

Key result: schemes that represent rimed ice as **hail** (MOR-H) or have dense/fast-falling rimed ice (NSSL, P3) reproduce the narrow, intense convective leading edge seen in the observations. Schemes representing rimed ice as **graupel** (MOR-G, WSM6, WDM6) produce broader, weaker, less realistic convective cores.

- P3: narrow region of high convective reflectivity, good agreement with KOUN
- MOR-H: narrow high-reflectivity region (due to hail category), but too narrow trailing stratiform reflectivity
- MOR-G: broader, lower peak convective reflectivity; wider, weaker transition zone
- WSM6, WDM6: similar issues, but WDM6 improves stratiform

All schemes underpredict precipitation rates in the rearward part of the trailing stratiform region. Schemes also struggled to simulate observed raindrop median volume diameter (DSD comparison from 2DVDs).

[Figure 4: Horizontal cross sections of radar reflectivity for all schemes — image not reproducible in markdown]

---

## 5. Simulation Results: Orographic Precipitation Case

### 5a. P3 Results

P3 produces a reasonable reflectivity structure for the broader system. On the windward slope of the Cascades below ~600 hPa: extensive cloud liquid water ($q_c$ up to ~0.5 g kg$^{-1}$), considerable riming with $F_r$ locally exceeding 0.4 between 750 and 850 hPa, consistent with aircraft observations of rimed snow and graupel. Notable increase in $V_m$ in regions with significant rimed ice ($V_m \approx$ 1.6–2.3 m s$^{-1}$ versus <1.6 m s$^{-1}$ elsewhere).

Accumulated precipitation (1400 UTC 13 Dec to 0800 UTC 14 Dec): P3 gives peak values in the central Oregon Cascades and significantly less in the lee of the Coast Range and east of the Cascades. Overall bias: +9.4 mm, RMSE = 16.3 mm (all stations).

[Figures 14–17: Radar reflectivity, P3 microphysical cross sections, accumulated precipitation — images not reproducible in markdown]

### 5b. Comparison of Microphysics Schemes

Key finding: The **spatial distribution** of surface precipitation differs significantly among schemes, primarily due to differences in ice particle fall speeds in rimed conditions:

- **P3**: Greater windward, less leeward precipitation — due to faster fall speeds from predicted rime mass fraction $F_r$
- **SBU-LIN**: Similar tendency to P3 for windward/leeward distribution (uses a diagnostic riming intensity factor), but overall fall speeds about half that of P3
- **MOR-G, MOR-H, NSSL, MY2**: More leeward, less windward precipitation — all predict large amounts of snow with low overall fall speeds relative to graupel
- **WSM6, WDM6**: Produce large graupel mass relative to snow, hence large combined snow–graupel fall speeds; distribution more similar to P3

The importance of ice fall speeds on precipitation distribution is confirmed by a P3 sensitivity test with fall speeds calculated assuming unrimed ice (P3-MOD): the resulting distribution is remarkably similar to MOR-G and MOR-H.

**Table 1 summary (accumulated precipitation statistics):**

| Scheme | Mean (all, mm) | RMSE (all, mm) | Mean (lee, mm) | RMSE (lee, mm) |
|--------|---------------|----------------|----------------|----------------|
| Obs | 35.7 | — | 17.7 | — |
| P3 | 45.1 | 16.3 | 35.1 | 17.9 |
| MY2 | 46.9 | 17.6 | 50.0 | 32.3 |
| MOR-G | 47.3 | 18.6 | 58.5 | 40.9 |
| MOR-H | 47.2 | 19.3 | 58.8 | 41.1 |
| NSSL | 43.3 | 16.5 | 41.7 | 24.0 |
| SBU-LIN | 41.0 | 14.7 | 37.5 | 19.8 |
| THO | 44.6 | 17.0 | 35.4 | 18.0 |
| WSM6 | 45.9 | 16.6 | 39.1 | 21.4 |
| WDM6 | 45.2 | 17.0 | 21.3 | 5.5 |
| P3-MOD | 47.1 | 18.5 | 45.3 | 27.7 |

**Ice water content (IWC) comparison:** P3 produces less ice aloft than most other schemes, consistent with higher fall speeds leading to less ice retention aloft. All simulations overpredict IWC compared to Convair aircraft observations.

[Figures 18–19: Precipitation difference maps and cross-section precipitation — images not reproducible in markdown]

---

## 6. Computational Efficiency Tests

Timing tests show P3 is computationally efficient despite including conceptually more complex ice microphysics:

**Timing (wall clock per time step, relative to WSM6):**

| Scheme | Squall line | Orographic | # Prognostic variables |
|--------|------------|------------|------------------------|
| P3 | 1.113 | 1.061 | 7 |
| MY2 | 1.420 | 1.495 | 12 |
| MOR-H | 1.203 | 1.200 | 9 |
| NSSL | 1.575 | 1.483 | 13 |
| SBU-LIN | 1.014 | 1.052 | 4 |
| THO | 1.212 | 1.174 | 7 |
| WSM6 | 1.000 | 1.000 | 5 |
| WDM6 | 1.184 | 1.148 | 8 |

P3 is 8.2% and 9.7% faster than THO (which has the same number of prognostic variables) for the squall-line and orographic cases, respectively. P3 is only ~11% and ~6% slower than WSM6 (the simplest scheme tested), despite its two additional prognostic variables.

---

## 7. Summary and Conclusions

The P3 scheme was tested in 3D WRF simulations for two contrasting well-observed cases:

**Squall line:**
- Reasonable reflectivity and precipitation structures, producing a narrow leading edge of high reflectivity consistent with hail-like characteristics in the convective region
- Representation of rimed-ice fall speed (hail-like in P3) is critical for squall-line structure
- Schemes representing rimed ice as slower-falling graupel produce less defined convective regions and lower peak precipitation rates
- All schemes struggle with rain DSD; all underpredict trailing stratiform precipitation

**Orographic case:**
- P3 successfully represents increase in fall speed with riming, producing greater windward and less leeward precipitation
- Reduced leeward bias compared to most schemes that overpredict leeward precipitation by a factor of 2.5–3
- Similar distribution to SBU-LIN (which uses a diagnostic riming intensity factor) and WDM6

**Computational performance:** P3 is computationally efficient — faster than all other schemes except WSM6 and SBU-LIN, despite having a conceptually more sophisticated treatment of ice microphysics.

**Limitations and future work:**
- Must be tested on many more cases covering a wide range of conditions
- Cloud cover and radiative fluxes should be investigated
- Multiple free-ice-category version in development

---

## Appendix: Overview of Other Microphysics Schemes

### A. Milbrandt–Yau Two-Moment (MY2)

Six hydrometeor categories with $\mu_x = 0$ for $x = i, r, s, g, h$; prognostic $q_x$ and $N_x$. Snow density varies inversely with size ($c_s = 0.1597$, $d_s = 2.078$). Fixed bulk densities: ice = 100 kg m$^{-3}$, graupel = 400 kg m$^{-3}$, hail = 900 kg m$^{-3}$.

### B. Morrison (MOR-G and MOR-H)

Prognoses mass and number mixing ratios of rain, cloud ice, snow, and graupel/hail. User-set switch for rimed-ice category: graupel (MOR-G) or hail (MOR-H) with different densities and fall speed–size relationships.

### C. NOAA/NSSL

Extension of Ziegler (1985). Six categories including separate graupel and hail. Predicts graupel volume for prognostic density. Default inverse-exponential distributions for rain and graupel; $\mu = 1$ for hail.

### D. Stony Brook University–Lin (SBU-LIN)

One-moment scheme with diagnostic approach for precipitating ice properties. Riming intensity parameter $R_i$ (ratio of riming to riming-plus-depositional growth rates) modifies particle properties. Ice fall speed calculated from the Best number approach.

### E. Thompson (THO)

Prognoses mass mixing ratios of 5 species plus $N_r$ and $N_i$. Snow has density varying inversely with diameter and a bimodal PSD. Includes ad hoc boost to snow fall speed in conditions with significant riming. Hybrid graupel–hail category.

### F. WSM6

One-moment, 5 categories (cloud, rain, ice, snow, graupel). Inverse-exponential distributions with prescribed $N_0$. Snow: $N_0$ is temperature-dependent.

### G. WDM6

Two-moment extension of WSM6: adds $N_c$, $N_r$, and cloud condensation nuclei. Ice processes follow WSM6.

---

## References

Bryan, G. H., and H. Morrison, 2012: Sensitivity of a simulated squall line to horizontal resolution and parameterization of microphysics. *Mon. Wea. Rev.*, **140**, 202–225.

Garvert, M. F., B. A. Colle, and C. F. Mass, 2005a: The 13–14 December 2001 IMPROVE-2 event. Part I. *J. Atmos. Sci.*, **62**, 1997–2017.

Garvert, M. F., and Coauthors, 2005b: The 13–14 December 2001 IMPROVE-2 event. Part II. *J. Atmos. Sci.*, **62**, 3520–3534.

Gilmore, M. S., J. M. Straka, and E. N. Rasmussen, 2004: Precipitation uncertainty due to variations in precipitation particle parameters. *Mon. Wea. Rev.*, **132**, 2610–2627.

Kruger, A., and W. F. Krajewski, 2002: Two-dimensional video disdrometer: A description. *J. Atmos. Oceanic Technol.*, **19**, 602–617.

Lin, Y., and B. A. Colle, 2011: A new bulk microphysical scheme that includes riming intensity and temperature-dependent ice characteristics. *Mon. Wea. Rev.*, **139**, 1013–1035.

Mansell, E. R., C. L. Ziegler, and E. C. Bruning, 2010: Simulated electrification of a small thunderstorm with two-moment bulk microphysics. *J. Atmos. Sci.*, **67**, 171–194.

Milbrandt, J. A., and M. K. Yau, 2005a,b: A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.

Milbrandt, J. A., M. K. Yau, J. Mailhot, and S. Bélair, 2008: Simulation of an orographic precipitation event during IMPROVE-2. Part I. *Mon. Wea. Rev.*, **136**, 3873–3893.

Milbrandt, J. A., M. K. Yau, J. Mailhot, S. Bélair, and R. McTaggart-Cowan, 2010: Simulation of an orographic precipitation event during IMPROVE-2. Part II. *Mon. Wea. Rev.*, **138**, 625–642.

Morrison, H., and J. A. Milbrandt, 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Wea. Rev.*, **139**, 1103–1130.

Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.

Morrison, H., G. Thompson, and V. Tatarskii, 2009: Impact of cloud microphysics on the development of trailing stratiform precipitation in a simulated squall line. *Mon. Wea. Rev.*, **137**, 991–1007.

Morrison, H., and Coauthors, 2012: Sensitivity of a simulated midlatitude squall line to parameterization of raindrop breakup. *Mon. Wea. Rev.*, **140**, 2437–2460.

Rasmussen, R., and Coauthors, 2012: How well are we measuring snow? *Bull. Amer. Meteor. Soc.*, **93**, 811–829.

Skamarock, W. C., and Coauthors, 2008: A description of the Advanced Research WRF version 3. NCAR Tech. Note TN-475+STR, 113 pp.

Stoelinga, M. T., and Coauthors, 2003: Improvement of Microphysical Parameterization through Observational Verification Experiment. *Bull. Amer. Meteor. Soc.*, **84**, 1807–1826.

Thompson, G., P. R. Field, R. M. Rasmussen, and W. D. Hall, 2008: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part II. *Mon. Wea. Rev.*, **136**, 5095–5115.

Ziegler, C. L., 1985: Retrieval of thermal and microphysical variables in observed convective storms. Part I. *J. Atmos. Sci.*, **42**, 1487–1509.
