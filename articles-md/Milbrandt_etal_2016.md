# Milbrandt et al. (2016)

**Full citation:** Milbrandt, J. A., S. Bélair, M. Faucher, M. Vallée, M. L. Carrera, and A. Glazer, 2016: The pan-Canadian high resolution (2.5 km) deterministic prediction system. *Wea. Forecasting*, **31**, 1791–1816, https://doi.org/10.1175/WAF-D-16-0035.1

**DOI:** 10.1175/WAF-D-16-0035.1

---

## Abstract

Since November 2014, the Meteorological Services of Canada (MSC) has been running a real-time numerical weather prediction system that provides deterministic forecasts on a regional domain with a 2.5-km horizontal grid spacing covering a large portion of Canada using the Global Environmental Multiscale (GEM) forecast model. This system, referred to as the High Resolution Deterministic Prediction System (HRDPS), is currently downscaled from MSC's operational 10-km GEM-based regional system but uses initial surface fields from a high-resolution (2.5-km) land data assimilation system coupled to the HRDPS and initial hydrometeor fields from the forecast of a 2.5-km cycle, which reduces the spin-up time for clouds and precipitation. Forecast runs of 48 h are provided four times daily. The HRDPS was tested and compared to the operational 10-km system. Model runs from the two systems were evaluated against surface observations for common weather elements (temperature, humidity, winds, and precipitation), fractional cloud cover, and also against upper-air soundings, all using standard metrics. Although the predictions of some fields were degraded in some specific regions, the HRDPS generally outperformed the operational system for a majority of the scores. The evaluation illustrates the added value of the 2.5-km model and the potential for improved numerical guidance for the prediction of high-impact weather.

---

## 1. Introduction

Over the past decades computational resources have increased significantly in operational weather centers around the world, enabling increasingly complex numerical weather prediction (NWP) systems. Operational centers are quickly moving toward the convective scale, with horizontal grid spacings on the order of 1–3 km. Examples include NOAA's operational 3-km HRRR (Pinto et al. 2015), Météo-France's AROME model at 2.5 km (Seity et al. 2010), the DWD COSMO-DE at 2.8 km (Baldauf et al. 2011), and the Met Office Unified Model at 1.5 km (Lean et al. 2008).

The distinct benefits of kilometer-scale configurations over coarser-resolution systems include:
- Higher effective model resolution
- Better representation of orography and topographic forcing
- Reduced need to parameterize deep convection
- Validity and benefit of more detailed cloud and precipitation parameterizations

### Historical Development of Kilometer-Scale NWP at MSC/ECCC

Over the past two decades, MSC and the Meteorological Research Division (MRD) have been experimenting with and moving toward kilometer-scale NWP using the GEM model. Key milestones:

- **1997**: MSC ran the Regional Deterministic Prediction System (RDPS) at 24 km and the 15-km HiMAP (High-Resolution Meteorological Application) domains
- **1999**: Performance of GEM at approximately 4 km explored; showed skill for forecasting convection over the Canadian prairies
- **2001**: Experimental 2.5-km system over the Great Lakes for the ELBOW project
- **2004**: Two experimental real-time 2.5-km domains implemented (western Canada and Great Lakes)
- **2008**: GEM contributed to the MAP-DPHASE forecast demonstration project at 2.5 km over the European Alps; UNSTABLE experiment with 1-km domain over southern Alberta
- **2009**: Additional 2.5-km Arctic domain
- **2010**: Special 2.5-km/1-km/250-m forecast system for Vancouver 2010 Winter Olympic Games (FROST configuration)
- **2011**: Experimental HRDPS system implemented
- **January 2013**: West 2.5-km domain granted formal operational status
- **November 2014**: Pan-Canadian 2.5-km HRDPS implemented with 48-h integrations four times daily

The purpose of this article is to provide a detailed overview of the pan-Canadian HRDPS and to illustrate its added forecast value over the existing operational 10-km system.

---

## 2. Description of the Pan-Canadian 2.5-km System

### a. The GEM Model

All operational weather prediction systems at ECCC use the GEM forecast model. GEM is a nonhydrostatic atmospheric model that solves the fully compressible Euler equations. The model uses a combination of semi-implicit time differencing and semi-Lagrangian advection, which allows for stable model integrations with Courant numbers larger than 1. Several horizontal grid options are available including global uniform, variable-resolution global, and LAM grids.

### b. Main Components of the HRDPS

#### 1) Overview

The pan-Canadian HRDPS provides a deterministic forecast on a regional domain with $\Delta x$ = 0.0225° latitude (approximately 2.5 km) with 48-h integrations four times daily, initialized at 0000, 0600, 1200, and 1800 UTC. The domain covers a large portion of Canada from the Pacific to the Atlantic Oceans and extending southward into the northern United States.

**Table 1. Summary of GEM configuration details.**

*Dynamics/Numerics:*
- Nonhydrostatic primitive equations
- Limited-area grid on a latitude–longitude projection
- Uniform horizontal grid spacing of 0.0225° longitude (approx. 2.5 km)
- 62 vertical levels
- Upper-boundary nesting above 10 hPa
- Time step of 60 s
- Terrain-following Gal-Chen vertical coordinate
- Two-time-level semi-implicit time differencing
- 3D semi-Lagrangian advection
- $\nabla^4$ horizontal diffusion ($\nabla^6$ for potential temperature)

*Physics:*
- Planetary boundary layer scheme based on TKE with statistical representation of subgrid-scale cloudiness (MoisTKE)
- Kuo–transient shallow convection scheme
- Milbrandt–Yau two-moment bulk microphysics scheme
- Li–Barker correlated-k distribution radiative transfer scheme (called every 15 min)
- ISBA land surface scheme
- Distinct roughness lengths for momentum and heat/humidity

The HRDPS is driven by the RDPS and consists of three main components: (i) a land data assimilation system, (ii) a coupled 2.5-km GEM 6-h cycle system, and (iii) a full 48-h 2.5-km GEM forecast run.

[Figure 2: Schematic of sequencing for the HRDPS showing RDPS, HRDPS, GSL, ATM, SFC, CLD components, ICs and BCs — image not reproducible in markdown]

#### 2) Surface Initial Conditions

##### (i) CaLDAS

The ICs for mean surface temperature and root-zone soil moisture are provided by a coupled 2.5-km configuration of the Canadian Land Data Analysis System (CaLDAS; Carrera et al. 2015). CaLDAS uses the ensemble Kalman filtering (EnKF) methodology with 24 members to generate surface conditions. For each 6-h period, the 24 ensemble members are forced with 0–6-h atmospheric fields from the 2.5-km HRDPS forecast run.

Data assimilated into CaLDAS include screen-level observations of temperature and dewpoint temperature along with surface observations of snow depth. Every 6-h, snow depth observations are combined with first-guess fields using OI. CaLDAS also provides: superficial soil moisture, surface temperature, frozen soil, water retained in vegetation, water retained in the snowpack, snow albedo, and snow density.

##### (ii) Gulf of St. Lawrence Coupled Ocean–Atmosphere Analysis

For the region of the Gulf of St. Lawrence (GSL), sea surface temperature, ice surface temperature, ice fraction, and ice thickness are provided by an ocean-ice analysis for the GSL (Smith et al. 2012).

#### 3) 2.5-km GEM Cycle

The cycle of consecutive 6-h GEM integrations on the full 2.5-km computational domain is another component. Prognostic cloud and precipitation fields (hydrometeor mass and number mixing ratios from the microphysics scheme) at the initial time come from the 6-h forecast of the previous run in the cycle — this "hot start" procedure means cloud fields are present at the initial time rather than requiring a spin-up period from cloud-free conditions.

The filtered orographic height is initialized with the field from the 10-km driving model (RDPS) and evolves gradually over 1 h to full resolution, reducing instabilities caused by rapid acceleration of air due to abrupt increases in terrain height.

##### Effect of Recycling of Hydrometeor Fields

Without the hot start, clouds form gradually over several hours. The hot-start simulation has initial reflectivity fields already at the same degree of overall coverage as after 3 h of cold-start integration. The average precipitation after only 1 h is approximately 65% of the equilibrium value for the recycling-on runs, compared with 12% for the recycling-off runs. The spin-up time of the hot-start runs appears to be approximately 5 h, 2 h less than for cold-start runs.

[Figure 5: Column-maximum model equivalent reflectivity for HRDPS simulations with hydrometeor recycling off and on — image not reproducible in markdown]
[Figure 6: Domain-averaged 1-h accumulated precipitation over all 80 benchmark cases for run sets with hydrometeor recycling off and on — image not reproducible in markdown]

#### 4) 2.5-km GEM Forecast Run

The full GEM forecast run is identical to the cycle component except integrated for the full 48-h forecast period.

---

## 3. Objective Evaluation and Comparison to the 10-km Operational System

### a. Evaluation Methods

A set of 80 benchmark cases (40 winter, 40 summer, during 2011) were run using each system, with runs starting at 0000 and 1200 UTC but separated by 3 days to provide meteorologically independent cases. Standard skill scores were computed: screen-level temperature $T$, humidity (dewpoint temperature $T_d$), wind speed $V_{spd}$, wind direction $V_{dir}$, and 6-h accumulated precipitation.

Model cloud cover was evaluated against human observations of fractional cloudiness. The 2D model fractional cloud cover was spatially averaged over approximately 70 km × 70 km (27×27 points for the HRDPS and 7×7 for the RDPS), assuming a human observer's range of approximately 35 km.

Upper-air forecasts of temperature $T$, dewpoint depression $T-T_d$, geopotential height $\Phi$, and zonal and meridional wind speeds were evaluated against radiosonde observations.

### b. Results

#### 1) Surface Fields

The HRDPS near-surface temperature is consistently warmer than the 10-km model in winter when considering the entire domain, being an improvement in some regions and causing deterioration in others. The STDE is neutral on average but is generally reduced in most specific regions, indicating improvement.

For humidity, there is a general increase in the moist bias in winter, consistent with upper-air scores; however, STDE is generally reduced. Screen-level temperature and humidity forecasts can be improved by modifying the interface between the radiative transfer scheme and microphysics through improved consistency in the computation of cloud optical properties.

For 6-h precipitation amounts exceeding 0.5 mm, there is a distinct improvement in the HRDPS in reducing the overprediction from the RDPS for both winter and summer. The percent correct is also improved for winter.

**Table 2. Summary of objective scores for screen-level fields, precipitation, and cloud cover for winter cases.** (+ = net improvement; − = net deterioration; / = net-neutral; ++ and −− = pronounced change)

| Field | Metric | BC | Prairies | QC-ON | Maritimes | North | USA |
|---|---|---|---|---|---|---|---|
| T (2 m) | BIAS | / | −− | ++ | + | −− | ++ |
| T (2 m) | STDE | ++ | − | ++ | ++ | ++ | ++ |
| T_d (2 m) | BIAS | / | −− | + | ++ | −− | + |
| T_d (2 m) | STDE | / | / | + | ++ | ++ | ++ |
| V_spd (10 m) | BIAS | ++ | −− | ++ | / | + | − |
| V_spd (10 m) | STDE | + | / | ++ | ++ | + | / |
| 6-h precip | BIAS | ++ | | | | | |
| 6-h precip | % CORRECT | + | | | | | |
| Cloudiness | BIAS | ++ | | | | | |
| Cloudiness | % CORRECT | ++ | | | | | |

**Table 3. As in Table 2, but for summer cases.**

| Field | Metric | BC | Prairies | QC-ON | Maritimes | North | USA |
|---|---|---|---|---|---|---|---|
| T (2 m) | BIAS | / | ++ | −− | − | ++ | / |
| T (2 m) | STDE | / | / | / | − | / | ++ |
| T_d (2 m) | BIAS | + | + | ++ | + | ++ | / |
| T_d (2 m) | STDE | + | ++ | ++ | / | ++ | ++ |
| V_spd (10 m) | BIAS | ++ | −− | + | − | − | − |
| V_spd (10 m) | STDE | + | ++ | ++ | ++ | + | / |
| 6-h precip | BIAS | + | | | | | |
| 6-h precip | % CORRECT | / | | | | | |
| Cloudiness | BIAS | / | | | | | |
| Cloudiness | % CORRECT | + | | | | | |

#### 2) Cloud Cover

For cloudiness, there is a distinct improvement in the HRDPS for partial cloudiness and overcast conditions, particularly in winter. The frequency bias scores for the HRDPS in winter are nearly perfect (frequency bias of 1) and there is approximately a 10% improvement in the percent correct. In summer, the HRDPS has too little fractional cloudiness (underprediction) but there is still improvement for overcast conditions.

The MY2 microphysics scheme has a known tendency to overpredict upper-level ice leading to excessively large anvils for cases of deep convection (Cintineo et al. 2014), which may possibly deteriorate the HRDPS cloudiness in the summer. This bias has been addressed and modifications will be considered for a future version.

#### 3) Summary of Surface Fields and Cloud Cover

Overall, the HRDPS shows generally improved scores over the RDPS. There are some notable weaknesses: temperature and humidity in the Prairies and northern regions are distinctly deteriorated in winter. The evaluation provides a guide for targeting future improvements.

#### 4) Upper-Air Scores

The mass (geopotential height) and wind fields for the two models are nearly identical. For winter cases, there is some increase in error in air temperature for the HRDPS. One notable problem in the HRDPS not present in the RDPS is a distinct moist bias in the mid-to-lower troposphere, particularly in winter, as indicated by the negative bias in $T-T_d$. Recent tests indicate this moist bias may originate from the microphysics scheme and could be corrected by modifying certain process rates (e.g., reducing the sublimation of snow).

[Figure 18: Upper-air scores vs. air pressure at 48 h for winter cases — image not reproducible in markdown]
[Figure 19: As in Figure 18 but for summer cases — image not reproducible in markdown]

---

## 4. Example of a Case of Deep Convection

A summertime case (8 July 2011) of a small-scale convective outbreak over the northern U.S. plains is presented. The HRDPS better captures the strong convective regions with high precipitation rates (>30 mm h$^{-1}$) in terms of location, structure, and magnitude. The HRDPS also discriminates well between convective regions (higher reflectivity values, e.g., >40 dBZ) and stratiform regions (lower reflectivity values, <40 dBZ). In contrast, precipitation rates from the RDPS are diffuse and weak.

Even with downscaling from the 10-km model, the 2.5-km system clearly has potential added forecast value for high-impact weather associated with deep convection. This is partly attributed to better surface initial conditions and to the higher capacity to resolve storm dynamics and the use of a detailed microphysics scheme that can better represent important diabatic processes.

[Figure 20: Model precipitation rates for RDPS and HRDPS, equivalent reflectivity, and observed NEXRAD reflectivity at two forecast lead times — image not reproducible in markdown]

---

## 5. Recent Updates

After the official initial implementation in November 2014, further development led to a set of modifications in December 2015.

### a. Use of a Deep Convective Parameterization Scheme

The most recent upgrade included introduction of the Kain and Fritsch (1990; KF) convective parameterization scheme (CPS) to treat subgrid-scale deep convection. While models with $\Delta x$ of 1–4 km have generally not used a CPS, it has been noted that with any grid spacing greater than 1 km the model is still in the gray zone and there may be a practical benefit. The KF scheme showed a distinct reduction in bias in the diurnal cycle of hourly summertime precipitation and more realistic convective precipitation patterns (more continuous and less "spotty"). The KF scheme was included in the 2015 upgrade.

### b. Modification to the Microphysics to Improve Freezing Rain

A modification to MY2 was made to address missed forecasts of freezing rain. Investigation revealed that excessive reglaciation of supercooled rain occurred primarily because trace amounts of graupel acted sufficiently as an embryo for rain to refreeze via the three-component freezing mechanism. In the original MY2, three-component freezing could occur at all temperatures below 0°C for collection between rain and either ice or graupel, or below −10°C for rain and snow.

A modification was implemented whereby all three-component freezing was restricted to temperatures colder than −5°C. This change has physical justification since drop freezing rates increase with the amount of supercooling (Pruppacher and Klett 1997). The modification successfully reduced the incorrect reglaciation of rain and solved the problem of missed freezing rain forecasts.

### c. Planned Future Development

At the time of writing, future developments included:
- Switching from MY2 to the Predicted Particle Properties (P3) microphysics scheme (Morrison and Milbrandt 2015; Morrison et al. 2015)
- Testing the "aerosol-aware" approach of Thompson and Eidhammer (2014) for cloud droplet nucleation
- Testing the Town Energy Balance model for urban surface fluxes
- Increased vertical resolution in the lower troposphere
- Development of an upper-air data assimilation (DA) system (likely EnKF)

---

## 6. Discussion and Conclusions

A detailed overview of ECCC's real-time experimental 2.5-km deterministic NWP system (HRDPS) has been provided. Standard objective skill scores for the prediction of common meteorological surface fields compared with station observations, fractional cloud cover, and radiosonde observations have been presented with comparison to the 10-km RDPS.

The 2.5-km system was shown to provide an overall improvement for surface fields and cloud cover, with the exception of a moist bias in the troposphere in winter. The effects on upper-air scores were near neutral or improved.

Most of the non-standard applications of kilometer-scale modeling (visibility, freezing rain, aircraft icing, hail, snow-to-liquid ratio) are challenging to observe and quantify systematically. Nevertheless, the increased use of kilometer-scale deterministic NWP systems worldwide, enhancements to observational systems, and developments in verification techniques appropriate for high-resolution models will make it increasingly possible to exploit these capabilities.

Eventually, the 2.5-km deterministic system will likely become MSC's primary source of numerical guidance for short-term NWP in the foreseeable future.

---

## Appendix A: Description of the Verification Package

The objective evaluation was performed using an in-house verification package (USTAT), which computes several standard skill scores. The procedure uses bootstrapping in blocks to capture the dependence structure of neighboring observations. The package can verify: temperature at 2 m, dewpoint temperature at 2 m, wind speed and direction at 10 m, and 6-h accumulated precipitation amounts, as well as total cloud cover. Stations are precisely located to the degrees, minutes, and seconds (resolution of about 30 m).

---

## Appendix B: Modification to the Microphysics

In MY2, frozen hydrometeors can be initiated from the three-component freezing mechanism whereby collection occurs between rain and cloud ice, snow, or graupel to form graupel or hail (Milbrandt and Yau 2005). The modification restricted all three-component freezing to temperatures colder than −5°C. This change is somewhat ad hoc but has physical justification since drop freezing rates are temperature dependent (Pruppacher and Klett 1997), and MY2 assumes the drop temperature to be equal to the air temperature, which may imply an overestimation of the degree of supercooling for drops falling from relatively warm air.

---

## References

[Full reference list in original paper — see pp. 1815–1816]
