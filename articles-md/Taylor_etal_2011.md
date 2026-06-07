# The Understanding Severe Thunderstorms and Alberta Boundary Layers Experiment (UNSTABLE) 2008

**Authors:** Neil M. Taylor, David M. L. Sills, John M. Hanesiak, Jason A. Milbrandt, Craig D. Smith, Geoff S. Strong, Susan H. Skone, Patrick J. McCarthy, and Julian C. Brimelow
**Journal:** Bulletin of the American Meteorological Society
**Year:** 2011
**Volume/Pages:** 92, 739–763
**DOI:** 10.1175/2011BAMS2994.1

---

## Abstract (paraphrased)

A field and modeling study aimed at improving understanding of atmospheric boundary layer (ABL) processes in the foothills of the Alberta Rocky Mountains and how they relate to the initiation of severe thunderstorms. The UNSTABLE 2008 pilot campaign collected targeted observations and tested measurement strategies for a planned full-scale experiment.

---

## 1. Introduction

Understanding convective initiation (CI) and predicting severe thunderstorms remains a major challenge. Accurate CI forecasts are critical for maximizing lead time and accuracy of severe weather watches and warnings. The small spatial and temporal scales of CI-relevant processes make them difficult to observe and simulate.

In Canada, the prairies are one of the most active regions for severe thunderstorm activity (221 severe events reported per summer on average; McDonald 2009). The foothills of the Alberta Rocky Mountains are a recognized genesis region, with more lightning days than elsewhere on the prairies. Storms from this region move eastward to affect the Edmonton–Calgary corridor. Since 1981, more than 40 deaths and $2.5 billion (CAD) in damage have been attributed to severe thunderstorms in Alberta.

Prior modeling studies (Erfani et al. 2003; Milbrandt and Yau 2006a,b) reproduced supercell-like storm structures consistent with radar observations, indicating a potential for high-resolution NWP to guide forecasters on CI and storm evolution.

---

## 2. UNSTABLE Goals and Experimental Design

### Goals
- Better understand atmospheric processes leading to thunderstorm development over the Alberta foothills
- Improve accuracy and lead time for severe thunderstorm watches and warnings
- Assess the skill of high-resolution NWP to resolve physical processes and forecast severe convection
- Refine conceptual models for CI and severe thunderstorm development

### Three Overarching Science Questions
- **Q1.** What are the contributions of ABL processes (water vapor availability, mesoscale boundaries, dryline) to CI and severe thunderstorms in the Alberta foothills?
- **Q2.** What are the contributions of surface processes (soil moisture, vegetation) to CI and severe thunderstorms?
- **Q3.** To what extent can high-resolution NWP models contribute to forecasting CI and severe convective storms?

### Experimental Domain
Southern Alberta foothills transition zone (Rocky Mountains to prairies), encompassing the climatological maximum for thunderstorm days and the cities of Calgary and Red Deer.

---

## 3. Instrumentation and Observations

A range of fixed and mobile platforms were deployed during the 2008 pilot (9–23 July IOP):

- Fixed surface station networks (ATMOS, FOPEX, FCA — up to 215 stations)
- Mobile instrumented vehicles (IV1 AMMOS, IV2, IV3) — 2-s thermodynamic and wind sampling
- Mobile and fixed rawinsonde systems (2-hourly simultaneous soundings on IODs)
- GPS precipitable water sensors (9 stations)
- Water vapor radiometers (fixed and mobile)
- Doppler sodar (wind/ABL depth profiling)
- Instrumented aircraft (Weather Modification Inc.; thermodynamic and microphysics measurements)
- Hail pads at 2–5-km spacing
- Existing operational C-band Doppler radars (Carvel, Strathmore), GOES-12, CLDN lightning, AMDAR

Eight IOD missions were conducted during the 15-day IOP, targeting: CI-ABL water vapor, CI-mesoscale boundaries, dryline, water vapor gradient (soil moisture), and water vapor gradient (vegetation).

---

## 4. High-Resolution NWP Model Support

Two configurations of the Canadian Global Environmental Multiscale (GEM) model were run in real time:

**GEM-LAM-2.5** (2.5-km horizontal grid spacing):
- Initialized from 15-km global GEM boundary conditions
- Explicit condensation: single-moment Milbrandt and Yau (2005) scheme
- Run daily 1200 UTC, 24-h forecasts

**GEM-LAM-1** (1-km horizontal grid spacing):
- Nested within GEM-LAM-2.5
- Explicit condensation: double-moment Milbrandt and Yau (2005) scheme
- Increased frequency for radiation scheme (every 15 min)
- Charney–Phillips staggered vertical coordinate (updated for 2009 runs to reduce spurious convection)
- Special orographic gradual evolution technique (McTaggart-Cowan et al. 2010) to reduce numerical instability at model initialization
- Run daily 1500–0300 UTC, June–August 2008 and 2009

Model output (standard diagnostics plus experimental convective diagnostics — CAPE, CIN, LCL/LFC heights, ABL depth/moisture fields) was provided via internal website for operational planning.

---

## 5. Preliminary Results

### Mesoscale Boundaries
- On 13 July 2008, a dryline was detected within the UNSTABLE domain via multiple observation platforms
- UNSTABLE observations resolved the dryline with far greater detail than the existing operational network: moisture gradients of 18 g kg$^{-1}$ km$^{-1}$ over distances of <700 m, with embedded gradients as strong as 42°C km$^{-1}$
- Simultaneous dual-sounding pairs captured the ABL structure on either side of the dryline: deep, warm, dry ABL on the dry side vs. shallow, cool, moist ABL ~35 km from the boundary on the moist side
- Aircraft-derived vertical cross sections resolved the dryline and potential gravity waves/horizontal roll circulations at the top of the moist ABL

### Surface Processes and ABL Evolution (20 July 2008)
- Contrasting ABL evolution observed over forested vs. cropped areas
- Cropped area: cooler, more moist, shallower ABL compared to forested area
- Aircraft-observed moisture cross section showed clear $q_v$ gradient of ~2.0–2.5 g kg$^{-1}$ at low levels (forest vs. crops); dry pocket below 400 m AGL over the forested area
- Mesonet data confirmed higher $q_v$ in the cropped region throughout the IOD
- Results suggest evapotranspiration from crops is an important local ABL moisture source

### High-Resolution NWP Evaluation
- GEM-LAM-2.5 and GEM-LAM-1 both suffered from spurious convection in 2008; the 2009 update to the Charney–Phillips vertical coordinate largely resolved this
- Downscaling to 1-km without data assimilation provided limited improvement in CI forecasting; higher resolution did not correct errors originating in the 2.5-km initial conditions
- Some cases showed the 1-km model improved convective mode simulation (e.g., linear vs. isolated convection) relative to the 2.5-km model
- Conclusion: improved high-resolution data assimilation (rather than simple downscaling) is needed for meaningful CI forecast improvements

---

## 6. Summary and Future Research

UNSTABLE 2008 collected observations of unprecedented spatial and temporal resolution over the Alberta foothills, including:
- The most complete observations of a Canadian dryline to date
- Novel characterization of ABL evolution over contrasting vegetation types

Plans for a future full-scale UNSTABLE experiment (~2013) included: additional mobile Doppler radar, eddy-correlation flux aircraft, additional fixed mesonet stations, ensemble NWP, and higher-resolution data assimilation.

---

## Key References

- Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3082–3132.
- Milbrandt, J. A., and M. K. Yau, 2006a,b: [Severe storms in Alberta] *J. Atmos. Sci.*, **63**.
- McTaggart-Cowan, R., and Coauthors, 2010: [Orographic gradual evolution technique]
- Côté, J., and Coauthors, 1998: The operational CMC–MRB Global Environmental Multiscale (GEM) model. *Mon. Wea. Rev.*, **126**, 1373–1395.

[Tables 1–7 and Figures 1–17 not reproduced in markdown — see original paper]
