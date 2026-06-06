# Makar et al. (2021)

**Full citation:** Makar, P. A., Akingunola, A., Chen, J., Pabla, B., Gong, W., Stroud, C., Sioris, C., Anderson, K., Cheung, P., Zhang, J., and Milbrandt, J., 2021: Forest-fire aerosol–weather feedbacks over western North America using a high-resolution, online coupled air-quality model. *Atmos. Chem. Phys.*, **21**, 1–31. DOI: 10.5194/acp-21-1-2021

---

## Abstract

The influence of both anthropogenic and forest-fire emissions, and their subsequent chemical and physical processing, on the accuracy of weather and air-quality forecasts, was studied using a high-resolution, online coupled air-quality model. Simulations were carried out for the period 4 July through 5 August 2019, at 2.5 km horizontal grid cell size, over a 2250 × 3425 km² domain covering western Canada and USA, prior to the use of the forecast system as part of the FIREX-AQ ensemble forecast. Several large forest fires took place in the Canadian portion of the domain during the study period. A feature of the implementation was the incorporation of a new online version of the Canadian Forest Fire Emissions Prediction System (CFFEPSv4.0). This inclusion of thermodynamic forest-fire plume-rise calculations directly into the online air-quality model allowed simulation of the interactions between forest-fire plume development and weather.

Incorporating feedbacks resulted in weather forecast performance that exceeded or matched the no-feedback forecast, at greater than 90% confidence, at most times and heights in the atmosphere. The feedback forecast outperformed the no-feedback forecast at 35 out of 48 statistical evaluation scores, for PM₂.₅, NO₂, and O₃. Relative to the climatological CCN and aerosol optical properties used in the no-feedback simulations, the online coupled model's aerosol indirect and direct effects were shown to result in feedback loops characterized by decreased surface temperatures in regions affected by forest-fire plumes, decreases in stability within the smoke plume, increases in stability further aloft, and increased lower troposphere cloud droplet and raindrop number densities. The aerosol direct and indirect effect reduced oceanic cloud droplet number densities and increased oceanic raindrop number densities, relative to the no-feedback climatological simulation.

---

## 1. Introduction

Atmospheric aerosols modify weather through the aerosol direct effect (ADE — absorption/scattering of solar radiation) and aerosol indirect effect (AIE — modification of cloud properties through changes in CCN). Forest fires are of particular interest due to the large amounts of aerosols released and the expectation that fire-conducive meteorological conditions may increase under climate change.

Prior operational air-quality forecast systems predicted forest-fire plume rise using a priori weather forecasts that lack meteorological feedback from fire aerosols. This paper addresses whether online coupling of ADE and AIE within a regional-scale forecast model can improve both weather and air-quality forecasts, and whether the changes in forest-fire plume rise associated with online coupling are sufficient to significantly perturb weather and chemistry predictions.

A key consideration in parameterizing the AIE is the cloud condensation scheme. At ~2.5 km grid spacing, detailed bulk microphysics schemes (BMS) are appropriate. A double-moment BMS is required to benefit from predicted CCN and ice nuclei number concentrations. The P3 microphysics scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016) was used for the AIE component in this study.

---

## 2. Model Description

### 2.1 GEM-MACH

The Global Environmental Multiscale – Modelling Air-quality and CHemistry (GEM-MACH) model combines Environment and Climate Change Canada's GEM weather NWP model with gas and particle process representation in an online paradigm. Simulations used a 2.5 km horizontal grid cell spacing over a 900 × 1370 grid cell domain covering most of western Canada and the USA.

**Model configuration highlights:**
- Base weather model: GEM v4.9.8 (Côté et al., 1998; Girard et al., 2014)
- Base air-quality model: GEM-MACH v2 (Moran et al., 2018)
- **Aerosol indirect effect (feedback runs):** Modified P3 cloud microphysics scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016) driven by an aerosol-size- and speciation-specific nucleation scheme (Abdul-Razzak and Ghan, 2002)
- **Aerosol indirect effect (no-feedback runs):** P3 scheme driven by an invariant aerosol population (single log-normal, 100 nm geometric mean diameter, 300 cm⁻³ pure ammonium sulfate)
- **Aerosol direct effect (feedback runs):** GEM-MACH predicted aerosol loading with Mie scattering using binary water-dry aerosol homogeneous mixture assumption
- **Aerosol direct effect (no-feedback runs):** Invariant climatological values for aerosol optical properties
- Forest-fire plume rise: CFFEPSv4.0 (online, energy-balance driven)
- Gas-phase chemistry: ADOMII mechanism (42 gas species)
- Particle microphysics: Sectional size distribution, eight chemical species
- Secondary organic aerosol: Modified yield approach

The forecast cycling used 30 h forecast cycles with meteorological boundary conditions from 10 km GEM forecasts updated hourly. Chemical initial conditions were "daisy-chained" between consecutive 24 h forecasts without chemical data assimilation.

### 2.2 CFFEPSv4.0: Online Forest-Fire Plume-Rise Calculations

The Canadian Forest Fire Emissions Prediction System version 4.0 (CFFEPSv4.0) represents the first online implementation of forest-fire plume injection height calculation within an NWP-coupled operational air-quality forecast model. Key advances over the offline CFFEPSv2.03:

- Original C-language code converted to FORTRAN90 and integrated as an online subroutine within GEM-MACH
- Residual buoyancy calculations carried out over model hybrid levels (rather than 5 preset pressure levels)
- Plume-rise calculations updated during model runtime, allowing fire-induced meteorological changes to feed back into subsequent plume-rise predictions
- When GEM-MACH runs in online coupled mode, ADE and AIE-generated aerosols modify meteorology, which in turn influences fire emissions and plume rise, closing the feedback loop

Note: CFFEPSv4.0 uses fire heat to determine plume rise as a subgrid-scale thermodynamic process parameterization, not a very high-resolution explicit fire growth model. Very local-scale weather modifications due to fire heat are not incorporated into fire spread or GEM microphysics.

### 2.3 Feedback and No-Feedback Simulations

Two parallel simulations for 4 July – 5 August 2019:
- **Feedback:** ADE and AIE enabled (online coupled model)
- **No-feedback:** ADE and AIE use GEM's climatological aerosol radiative and CCN properties (one-way coupled)

Five large forest fires occurred in northern Alberta during the study period. Statistical evaluation at 90% confidence using the Geer (2016) confidence range formulation.

---

## 3. Model Evaluation

### 3.1 Meteorology Evaluation

Surface meteorological evaluation at 3 h intervals using MB, MAE, RMSE, R, and σ at 90% confidence.

Variables with statistically significant differences: 2 m temperature, surface pressure, 2 m dew-point temperature, 10 m wind speed, sea-level pressure, accumulated precipitation.

**Key results:**
- **Surface temperature:** Feedback superior at forecast hours 3, 6, 15, 18, and 24 (>90% confidence); at par at hours 12 and 21; no-feedback superior at hour 9. Feedback improved MAE and RMSE at hours 15 and 18.
- **Surface pressure, dew-point temperature, sea-level pressure:** Initial degradation at hour 3 (model spin-up), then feedback superior for many subsequent hours
- **10 m wind speed:** Feedback improved at hours 3 and 6 for all metrics; slight degradation at hours 21 and 24
- **Precipitation:** HSS improved at hours 12 and 24; improvements were for light precipitation events (<2 mm/6h)
- **Upper-air temperature:** Feedback improved at 250, 300, 400, 500, 850 hPa at forecast hour 12; improvements at 300, 925, 1000 hPa at forecast hour 24

A model spin-up issue was identified: the online coupled model requires ~6 h to equilibrate between aerosol and cloud fields at the start of each forecast cycle.

### 3.2 Chemistry Evaluation

Performance metrics for O₃, NO₂, and PM₂.₅ evaluated using AIRNOW data (AQS network for USA, NAPS for Canada):

| Chemical | Region | Winning simulation | Better scores |
|----------|--------|--------------------|---------------|
| PM₂.₅ | Western Canada | Feedback | Most metrics |
| PM₂.₅ | Western USA | Feedback | Most metrics |
| O₃ | Western Canada | Feedback | Most metrics |
| O₃ | Western USA | Feedback (marginal) | Most metrics |
| NO₂ | Western Canada | Mixed | Similar |
| NO₂ | Western USA | Mixed | Similar |

Overall: 35 out of 48 statistical evaluation scores showed improvement with feedback.

AOD evaluation (MODIS/Aqua): Model generally biased low in AOD (consistent with prior literature showing ~factor-of-2 underprediction with homogeneous mixture assumptions). Using ECMWF+10km GEM-MACH boundary conditions improved AOD performance relative to MOZART2009 climatology, but introduced positive PM₂.₅ biases (partly attributed to ECMWF reanalysis overestimating upwind PM₂.₅).

---

## 4. Effects of Feedbacks on Simulation-Period Averages

### 4.1 Effects on Time-Averaged Meteorology

Comparing feedback minus no-feedback simulation period averages along north-south and east-west cross sections:

**Cloud droplet numbers:**
- Increased throughout lower troposphere (surface to ~500 hPa) over northern domain including Alberta–Saskatchewan fire region, significant at 90% confidence
- Decreased over ocean (feedback aerosol loadings lower than climatological no-feedback)

**Cloud droplet mass:**
- Largely decreased across domain; most significant differences over ocean

**Raindrop numbers:**
- Increased aloft over fire region and ocean at 90% confidence
- Near-surface changes mostly below 90% confidence

**Raindrop mass:**
- Increased aloft; usually below 90% confidence near surface

**Surface and lower-troposphere meteorological fields:**
- Near-surface temperature: −0.5°C maximum decrease between hybrid levels 0.893–0.848 (below smoke plumes); slight increase south of fires
- Specific humidity: increased in fire-impacted region
- Surface pressure: increased over land east of Rockies, decreased over ocean
- PBL height: increased over land except immediately near fires
- Friction velocity: increased (consistent with decreased stability and increased turbulent energy)

These differences fall below 90% confidence for domain-wide averages but reach 90% confidence when comparing to observations at specific forecast times (Fig. 6a) and at multiple heights aloft (Figs. 12, 13).

### 4.2 Effects on Time-Averaged Chemistry

Near-surface PM₂.₅ decreased near fires (more transported and retained aloft due to increased stability above smoke); PM₂.₅ aloft increased significantly (at 90% confidence near fires). NO₂ increased in some urban centers but decreased near surface downwind of fires. Surface O₃ decreased near fires (lower troposphere), increased aloft — pattern consistent with NOₓ-limited chemistry or reduced photolysis rates under clouds.

Summary of most significant feedback effects:
1. Increases in PM₂.₅ aloft and decreases near surface in fire-impacted areas
2. Increases in NO₂ aloft and near-surface decreases near fires
3. Decreases in lower troposphere O₃ near fires

### 4.3 Summary: Feedback Mechanism

The AIE feedback loop:
1. Forest-fire aerosols increase near-surface atmospheric stability
2. More PM remains aloft, acting as CCN at higher levels
3. Cloud droplet numbers increase aloft (first AIE)
4. Increased cloud albedo cools the atmosphere below cloud tops
5. Reduced near-surface particles → smaller near-surface AIE → maintained unstable near-surface gradient

Over oceans, model-generated aerosols are lower than climatological no-feedback values, reducing cloud droplet numbers and increasing raindrop numbers (shift from cloud water to rain water).

---

## 5. Conclusions

1. **Online coupled model with feedbacks improved both weather and air-quality forecasts.** Weather metrics improved or matched no-feedback at 90% confidence for most times and heights. Chemistry metrics improved for 35/48 scores.
2. **Forest-fire plume-rise calculations within online coupled model significantly altered predicted plume dispersion.** Enhanced upward transport in fire plumes due to reduced near-surface stability.
3. **Model spin-up issue identified:** First ~6 h of online coupled forecasts requires adjustment of cloud fields; forecast cycling should include chemistry variables during spin-up.
4. **Boundary conditions strongly influence model air-quality performance.** ECMWF + 10 km GEM-MACH improved AOD but degraded surface chemistry metrics relative to MOZART2009 reanalysis.
5. **AOD biased low overall** despite PM₂.₅ positive biases — homogeneous mixture aerosol optical properties underpredict AOD; separate treatment of forest-fire aerosol optical properties recommended.

---

## Author Contributions

PAM: experiment design, conceptualization, analysis, manuscript. AA: model code, run scripts, statistical analysis, graphics. JC: forest-fire emissions processing system. BP: forecast system simulations. WG: indirect effect updates, P3 implementation advice, manuscript review. CrS: code contributions, manuscript review. ChS: AOD analysis, manuscript review. KA: forest-fire emissions system, manuscript review. PC: forecast simulations. JZ: emissions processing, manuscript review. **JM (Milbrandt): indirect effect updates and advice on implementing AIE in the P3 scheme, manuscript review and contributions.**

---

## References (selected)

- Morrison, H. and Milbrandt, J. A., 2015: Parameterization of Cloud Microphysics Based on the Prediction of Bulk Ice Particle Properties. Part I. *J. Atmos. Sci.*, 72, 287–311.
- Milbrandt, J. A. and Morrison, H., 2016: Parameterization of Cloud Microphysics Based on the Prediction of Bulk Ice Particle Properties. Part III. *J. Atmos. Sci.*, 73, 975–995.
- Milbrandt, J. A. and Yau, M. K., 2005a,b: A multimoment bulk microphysics parameterization. Parts I & II. *J. Atmos. Sci.*, 62.
- Milbrandt, J. A. et al., 2016: The pan-Canadian High Resolution (2.5 km) Deterministic Prediction System. *Weather Forecast.*, 31, 1791–1816.
- Chosson, F., Vaillancourt, P., Milbrandt, J. A., Yau, M. K., and Zadra, A., 2014: Adapting two-moment microphysics schemes across model resolutions. *J. Atmos. Sci.*, 71, 2635–2653.
- Jouan, C., Milbrandt, J. A. et al., 2020: Adaptation of the P3 microphysics scheme for large-scale NWP. *Weather Forecast.*, 35, 2541–2565.
