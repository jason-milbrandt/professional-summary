# A Mesoscale Modeling Study of the 1996 Saguenay Flood

**Authors:** J. A. Milbrandt and M. K. Yau  
**Affiliation:** Department of Atmospheric and Oceanic Sciences, McGill University, Montreal, Quebec, Canada  
**Journal:** Monthly Weather Review  
**Volume:** 129  
**Pages:** 1419–1440  
**Published:** June 2001  
**Manuscript received:** 14 January 2000; in final form 2 November 2000  
**DOI:** (not extracted from PDF; journal: Mon. Wea. Rev., 129, 1419–1440)

---

## Abstract

A mesoscale simulation of the 19–21 July 1996 Saguenay flood cyclone was performed using the Canadian Mesoscale Compressible Community (MC2) model to study the processes leading to the explosive development and the large amount of precipitation. The performance of the simulation is verified by careful comparison with available observations with particular emphasis on the quantitative forecast of precipitation. It was shown that the model accurately simulates the wind, temperature, and humidity fields. Using the Kong and Yau microphysics scheme, the model performs quite well in the threat scores over a broad range of precipitation thresholds. Comparison of model precipitation against an objective analysis from rain gauge measurements and against the time evolution of accumulated precipitation at specific sites indicates generally good agreement except that the magnitude of the maxima is about 10% lower in the simulation.

Potential vorticity (PV) inversion and sensitivity experiments show that the rapid deepening of the cyclone results from a combination of upper-level forcing from two shortwave troughs that partially merge, an upper-level jet streak, latent heat release, and low-level thermal advection. Condensational heating was integral for the establishment of a phase lock between the surface cyclone and a strong, upper-level trough that steers the cyclone. The flow field associated with a weaker trough, located downstream of the stronger trough, acted to retard the progression of the stronger trough, ultimately causing the cyclone to be located in a favorable position to interact with orography. It was shown that in the middle of the explosive deepening period, the contributions to the 900-hPa geopotential height anomaly from the upper-level dry PV anomaly, the low-level moist PV anomaly, and the surface potential temperature anomaly were 47%, 41%, and 12%, respectively.

The contribution to the precipitation from orographic variation is quantified through sensitivity experiments in which aspects of the orography field are altered in the model conditions. It was found that orographic variation contributed to approximately 15% of the 48-h accumulated precipitation in the region of the flooding and up to over 25% in other local areas.

---

## 1. Introduction

A severe flood occurred in the Saguenay region of Quebec, Canada, on 19–21 July 1996. The maximum accumulated precipitation is found in the Saguenay valley, which is surrounded by mountains on its north, southwest, and southeast sides. There are two man-made reservoirs, Lake Kenogami and Lake Ha!Ha!, with ten dikes and three dams. Two weeks before the flood, the eastern half of North America was dominated by a longwave trough and the inclement weather resulted in saturation of the soil in the Saguenay region. Rain started to fall around 1200 UTC 19 July. Although the average rainfall rate over the area is only 8 mm h$^{-1}$, the persistent precipitation led to a large accumulation. One automatic rain gauge near Lake Kenogami recorded 279 mm of accumulated rain, most of which fell in a 36-h period from 1200 UTC 19 July to 0000 UTC 21 July.

On the morning of 20 July, 28 h after rain started to fall at Lake Ha!Ha!, water ruptured an earthen dike and dug a trench through the forest before joining the Ha!Ha! River to swamp the communities downstream. Similarly, water began accumulating in the nearly full Lake Kenogami on the morning of 19 July. By the next morning, water poured out of the drainage basin and flooded properties downstream. The event represents the most catastrophic flood in Canadian history, with 10 deaths and 800 million dollars (Canadian) in property damage (Grescoe 1997). Heavy rainfall warnings were issued by the Quebec Weather Centre. However, the Canadian operational models initialized at 0000 UTC 19 July predicted the bulk of the precipitation too far east. The forecasted location of rainfall was more accurate when the models were initialized 12 h later but the forecast still underpredicted the 48-h accumulated precipitation beginning at 1200 UTC by 50% (Verret et al. 1996).

The fact that precipitation occurred on relatively large temporal and spatial scales indicated the feasibility of using high resolution mesoscale modeling initiated by operational analysis to investigate the synoptic and mesoscale processes that produced the persistent precipitation. Because of the large accumulated rainfall, latent heat release is likely to have played a role. It is also desirable to investigate the importance of the mountains surrounding the Saguenay Valley. Thus, it is the goal of this work to understand the basic processes in the Saguenay flood using the Canadian Mesoscale Compressible Community model (MC2; see Benoit et al. 1997). Specifically, the paper seeks answers to:

- What physical processes produced the large amount of precipitation?
- Why did the rainfall last for 36 h?
- What is the effect of the latent heat release?

The organization of this paper is as follows. A synoptic overview is presented in section 2. Section 3 describes briefly the model and the experimental setup. The control experiment and its validation form the subject of section 4. Section 5 contains diagnostic studies and sensitivity experiments using the potential vorticity (PV) inversion technique. Concluding remarks are given in section 6.

---

## 2. Synoptic Overview

A low pressure system with a central sea level pressure (SLP) of 1002 hPa originated over southern Manitoba and deepened gradually as it moved eastward. By 1200 UTC 19 July, the Canadian Meteorological Centre (CMC) regional analysis depicts a central SLP of 999 hPa and the system reached just north of Lake Ontario. The cyclone then deepened 20 hPa in 24 h as it moved north-eastward toward the Gaspé Peninsula. The maximum deepening rate of 14 hPa $(12\text{h})^{-1}$ occurred between 19/1800 and 20/0600 and fits the classification of an explosively deepening cyclone according to the criterion of Rogers and Bosart (1986).

Immediately before the rapid deepening period at 19/1200, the cyclone was located just south of a baroclinic zone. Two troughs appeared at 500 hPa. The surface low is located directly under one 500-hPa trough and downstream of another. The cyclone entered the middle of its explosive deepening period at 20/0000. At 20/1200 the cyclone is near Campbellton, New Brunswick, at its deepest stage, with a central SLP of 979 hPa. Strong thermal advection is indicated by strong low-level winds (in the form of a low-level jet) crossing the isotherms at a significant angle. Similar to the finding of Uccellini (1990), cyclogenesis of the Saguenay storm is marked by a low-level thermal field that evolves into an S-shape pattern during the rapid development stage. The system became equivalent barotropic with closed circulations as high as 250 hPa. For the following 24 h, the cyclone gradually filled at about 3 hPa $(6\text{h})^{-1}$ but remained quasi-stationary over the Gaspé Peninsula.

The observed 48-h maximum accumulated precipitation beginning at 19/1200 at Rivière-Aux-Écorces, in the Saguenay region of eastern Quebec, was 274 mm. A secondary precipitation maximum of 189 mm was found near Les Buissons, about 200 km northeast of the Saguenay region. The average 48-h precipitation was about 200 mm over an area of 5000 km$^2$. The period of most intense rainfall coincides with the period of explosive deepening of the cyclone (19/1800–20/0600).

---

## 3. Model Description and Design of Experiment

The simulations were performed using the limited-area mesoscale model MC2 (Robert et al. 1985; Tanguay et al. 1990; Benoit et al. 1997). It is based on the fully compressible Euler equations, solved on a polar stereographic projection (true at 60°N) using the semi-implicit and semi-Lagrangian algorithm. The reference state used is an isothermal hydrostatic atmosphere at rest. The prognostic variables are the three velocity components $u$, $v$, and $w$; logarithm of a dimensionless perturbation pressure $p$ from the reference state $\ln(p/p_o)$ with $p_o = 1000$ hPa; temperature $T$; and the mixing ratios for water substances. Space derivatives are discretized by finite differences on a grid staggered in three dimensions, with an Arakawa C grid for the horizontal and a Tokioka B grid for the vertical. Orography is introduced by the use of the terrain-following Gal-Chen vertical coordinate, modified to allow for compressing or stretching the coordinate in the vertical.

The model has a comprehensive physics package (Mailhot et al. 1997). It includes planetary boundary layer processes based on turbulent kinetic energy (Benoit et al. 1989), fully implicit vertical diffusion, and a stratified surface layer based on similarity theory. The surface temperature over land is predicted via the force restore method (Deardorff 1978; Benoit et al. 1989). The diurnal cycle associated with solar and infrared fluxes over ground is modulated by diagnostic clouds. The solar (Fouquart and Bonnel 1980) and infrared (Garand and Mailhot 1990) schemes in the radiation package are fully interactive with the clouds. Total precipitation is the sum of convective and stratiform precipitation. Convective precipitation is generated from a cumulus parameterization (choice between Kuo (1974) scheme and Kain–Fritsch (1993) scheme). Stratiform precipitation is produced either by the Sundqvist et al. (1989) scheme or by the explicit microphysics scheme of Kong and Yau (1997) and Misra et al. (2000), with equations for cloud water, rainwater, ice/snow, and graupel/hail.

The MC2 model allows for a one-way self-nesting capability. The control experiment is a 48-h simulation from 1200 UTC 19 July to 1200 UTC 21 July. A preliminary run is performed with a horizontal resolution of 35 km. Initial and boundary conditions are obtained from the regional data assimilation system at CMC (Chouinard et al. 1994; Mailhot et al. 1997). The 20-km simulations were obtained by one-way nesting from the 35-km runs over the same 48-h period.

**Table 1. Summary of MC2 parameters in control simulation.**

| Parameter | Value |
|-----------|-------|
| Projection | Polar stereographic, true at 60°N |
| Horizontal grid | 180 × 120, 20-km resolution |
| Number of vertical levels | 25 (Gal-Chen levels) |
| Model top | 25 000 m |
| Timestep | 150 s |
| Grid-scale condensation | Explicit (cold) microphysics (Kong and Yau 1997) |
| Convective parameterization | Kuo (Mailhot 1994) |
| PBL scheme | Based on predictive equation for turbulent kinetic energy (Benoit et al. 1989) |
| Solar radiation scheme | Accounts for H$_2$O, CO$_2$, O$_3$, and cloud effects (Fouquart and Bonnel 1980) |
| Infrared radiation scheme | Incorporates cloud interaction and radiation effects of H$_2$O, CO$_2$, and O$_3$ (Garand and Mailhot 1990) |

**Table 2. Simulations performed at a 20-km horizontal resolution with various combinations of resolved-scale and subgrid-scale precipitation parameterization schemes.**

| Run | Subgrid-scale scheme | Resolved-scale scheme | Saguenay peak observed |
|-----|---------------------|-----------------------|------------------------|
| KUOEXP | Kuo | Kong–Yau | Yes (224 mm) |
| KUOSUND | Kuo | Sundqvist | Yes (176 mm) |
| KFEXP | Kain–Fritsch | Kong–Yau | No |
| EXPC | None | Kong–Yau | Yes (215 mm) |

---

## 4. Validation of Control Simulation

### a. Validation of Wind and Mass Fields

The central pressure in CONT is always within 2 hPa of the analysis, but there is a distinct northwestward bias in the storm track. No bias was detected from the height field at 500 hPa. Comparison of modeled and observed soundings at Caribou, Maine, showed reasonable agreement for temperatures and dewpoints, although there is a tendency for the model to overpredict (underpredict) the relative humidity at lower (upper) levels.

[Figure 2: Objective 48-h accumulated precipitation analysis (contour and shading interval 25 mm), central SLP tracks from CONT (solid) and CMC regional analyses (dashed), and inset of central SLP values vs. time — image not reproducible in markdown]

[Figure 3: Observed (dashed) and model (solid) soundings for Caribou, Maine, at (a) 19/1200-00, (b) 20/0000-12, (c) 20/1200-24, and (d) 21/0000-36 — image not reproducible in markdown]

### b. Validation of Quantitative Precipitation

A gridded dataset for precipitation was used to validate the quantitative precipitation forecasting (QPF) from the model. An objective analysis of the 48-h (19/1300–21/1300) accumulated precipitation (PR48) was performed from 293 rain gauge measurements in Quebec using the Barnes (1964) scheme with a radius of influence of 45 km. The CONT experiment is selected from four simulations with different resolved-scale and subgrid-scale precipitation parameterization schemes (Table 2).

The threat score (TS) and bias score (BS) are defined following Anthes (1983):

$$\text{TS} = \frac{C}{F + R - C} \tag{1}$$

$$\text{BS} = \frac{F}{R} \tag{2}$$

where $C$ is the number of grid points correctly forecast to receive a threshold amount of precipitation, $F$ is the number of grid points forecast to receive this amount, and $R$ is the number of grid points where the threshold amount is observed.

For threshold values over 100 mm, the TSs are significantly higher in KUOEXP. The KUOEXP run outperforms the other runs in terms of quantitative precipitation simulation. The maximum of 224 mm in KUOEXP is closest to the analyzed maximum of 246 mm (corresponding to observed maximum of 274 mm). The underprediction is partly related to the fact that rainfall in a grid box represents a spatially averaged amount over an area of 400 km$^2$.

[Figure 4: 48-h accumulated precipitation for (a) KUOEXP, (b) KUOSUND, (c) KFEXP, and (d) EXPC — image not reproducible in markdown]

[Figure 5: (a) Threat scores (with bias scores equalized to KUOEXP) and (b) bias scores (unequalized) for the 20-km simulations — image not reproducible in markdown]

[Figure 6: 48-h accumulated (a) explicit and (b) convective precipitation for KUOEXP (CONT) — image not reproducible in markdown]

The explicit scheme and convective scheme contributed approximately equally to the main precipitation maximum in the Saguenay area. A majority of the convective precipitation fell between 19/1800-06 and 20/0003-15.

[Figure 7: Brightness temperature from GOES-8 at approximately 20/0000-12, instantaneous convective and stratiform precipitation rates — image not reproducible in markdown]

[Figure 8: Evolution of accumulated precipitation at points in (a) the Saguenay region, (b) the Gaspé region, and (c) the Beauce region from rain gauge observations and CONT — image not reproducible in markdown]

---

## 5. PV Inversion Diagnostics and Sensitivity Tests

Ertel's (1942) PV is defined as:

$$q = \rho^{-1} \boldsymbol{\eta} \cdot \nabla\theta \tag{3}$$

where $\rho$, $\boldsymbol{\eta}$, and $\theta$ are air density, absolute vorticity vector, and potential temperature, respectively. PV is a conserved quantity on an isentropic surface in the absence of diabatic and dissipative processes (Hoskins et al. 1985). The piecewise PV inversion technique of Davis and Emanuel (1991) is applied to quantify contributions of upper-level and lower-level processes on cyclogenesis.

The mean state is calculated as a 6-day time average covering the period from 17/1200 to 23/1200. The total PV anomaly is partitioned following Huo et al. (1999a):

**Table 3. Partitioning of PV anomalies.**

| Symbol | PV anomaly | Definition |
|--------|-----------|------------|
| $Q_d$ | Upper-level dry PV anomaly | Positive PV anomaly from 800 to 200 hPa; RH < 30% |
| $Q_m$ | Low-level moist PV anomaly | Positive PV anomaly from 900 to 500 hPa; RH > 70% |
| $Q_\theta$ | Bottom potential temperature anomaly | 1000-hPa potential temperature anomaly and 900-hPa PV anomaly with RH < 70% |
| $Q_r$ | Residual PV anomaly | All remaining PV anomaly from 900 to 200 hPa (not part of $Q_d$, $Q_m$, or $Q_\theta$) |

### a. Structure and Evolution of PV Anomalies in Control Simulation (CONT)

[Figure 9: PV at 400 and 800 hPa and 70% relative humidity at (a) 19/1800-06 and (c) 20/0000-12 and corresponding vertical cross sections (b) and (d) — image not reproducible in markdown]

The elongated pattern of PV at 400 hPa is associated with two shortwave troughs. The PV tongue is located in the unsaturated region, immediately to the west of the model-predicted cloud field. The vertical section at 19/1800-06 indicates that the PV feature at 400 hPa results from the dry descent or intrusion of stratospheric air. A patch of low-level PV, generated by the release of latent heat, is identified in the cloudy region, increasing with time as the cyclone deepens.

[Figure 10: Layer-averaged $Q_d$ (from 600 to 200 hPa) and 500-hPa geopotential height from CONT at (a) 19/1200-00, (b) 20/0000-12, (c) 20/1200-24, and (d) 21/0000-36 — image not reproducible in markdown]

At 19/1200-00, two distinct troughs can be identified. The northern trough has $Q_d$ values twice as large as the southern trough and extends over a larger area. As time progresses, the troughs partially merge. The northern trough intensifies due to continued dry intrusion of stratospheric PV while the southern trough weakens.

[Figure 11: Layer-averaged $Q_m$ (from 900 to 500 hPa) and 850-hPa geopotential height from CONT at (a) 19/1200-00, (b) 20/0000-12, (c) 20/1200-24, and (d) 21/0000-36 — image not reproducible in markdown]

At 19/1200-00, a positive PV anomaly is already present at the lower levels. As the cyclone deepens, $Q_m$ increases as a result of condensational heating, reaching its highest value (1.64 PVU) at 20/0600-18, 6 h before the cyclone achieves its lowest central pressure.

### b. Trough Removal Experiment

The sensitivity experiment NOTR was performed by excluding the southern trough from the initial conditions of CONT, following a similar methodology to Huo et al. (1999b). The southern trough is removed because it has a smaller areal extent and associated $Q_d$ relative to the northern trough.

[Figure 12: Wind field from the inversion of the portion of $Q_d$ associated with the southern trough, and vertical cross sections of total PV anomaly for CONT and NOTR — image not reproducible in markdown]

[Figure 13: Maximum values of (a) $Q_d$ and (b) $Q_m$ for CONT (circles), NOTR (triangles), and DRY (squares) — image not reproducible in markdown]

[Figure 14: Storm tracks for CONT (circles), NOTR (triangles), and DRY (squares), with inset of central SLP values vs. time — image not reproducible in markdown]

The absence of the southern trough slows down the spinup of the cyclone before 6 h. The NOTR cyclone always moves to the east and north of the storm in CONT and with a faster speed. The southern trough retards the progression of the northern trough (which steers the cyclone), by reducing the wind speed in its vicinity and thus reducing the advection of positive PV. This retardation can also be interpreted through vortex–vortex interaction: the southern vortex produces cyclonic (anticyclonic) vorticity advection and geopotential height falls (rises) to the west (east) of the northern vortex, inducing a westward propagation. The precipitation maximum in the Saguenay region of CONT was shifted approximately 200 km eastward in NOTR and its value reduced by 15% (from 224 to 190 mm).

### c. Dry-Run Experiment

The DRY experiment was performed by suppressing the release of latent heat of condensation in the thermodynamic equation. Without latent heating, there is virtually no deepening of the central SLP and the track moves east rather than north-east as in CONT. The latent heat release favors the development of the northern SLP minimum (coastal redevelopment), whereas without it, the cyclone wanders hundreds of kilometers southwest of the track in CONT. Latent heat release was essential during the initial part of the rapid deepening period to establish a phase lock between the portion of $Q_d$ identified as the midlevel northern trough and the surface cyclone.

### d. Contributions to Cyclogenesis

[Figure 16: Contributions to the 900-hPa geopotential height anomaly at the cyclone center from the inversions of $Q_m$, $Q_d$, and $Q_\theta$ for (a, b) CONT, (c, d) NOTR, and (e, f) DRY — image not reproducible in markdown]

In CONT, the contribution from $Q_d$ is the largest and its significance increases with time until 20/1800-30 due to stratospheric intrusion and the increasing vertical alignment of the upper northern trough and the surface cyclone. The contribution from $Q_m$ also indicates an increasing trend throughout the deepening phase. The effect of $Q_\theta$ is the smallest and it actually contributes to a height rise after 20/1200-24 as the cyclone center moves from a region of positive to a region of negative $Q_\theta$ anomaly. At 20/0600-18, the relative contributions from $Q_d$, $Q_m$, and $Q_\theta$ to the 900-hPa height fall are 47%, 41%, and 12%.

### e. Influence of Jet Streak

[Figure 17: 300-hPa wind vectors, isotachs, and SLP from CONT at 20/0000-12, with inset vertical cross section of upward motion — image not reproducible in markdown]

Two jet streaks are present in the vicinity of the cyclone, one upstream and one downstream. Cross sections of ageostrophic wind indicate considerable enhancement of upward motion ($w$) due to a thermally direct circulation in the entrance region of the downstream jet streak. The maximum $w$ of 76 cm s$^{-1}$ occurs at around 450 hPa in the right entrance region of the jet streak. The jet enhances cyclogenesis between 19/2100-09 and 20/0003-15.

### f. Effects of Orography

**Table 4. List of experiments.**

| Experiment | Orographic feature(s) modified | PR48 different from CONT |
|-----------|-------------------------------|--------------------------|
| NOR1 | NOR, SW, SE, and VAL | Yes |
| NOR2 | NOR | No |
| NOR3 | SW | No |
| NOR4 | SE | Slightly |
| NOR5 | VAL | Yes |
| NOR6 | SE and VAL | Yes |

(VAL = Saguenay valley; NOR = mountain to north; SE = mountain to southeast; SW = mountain to southwest)

[Figure 18: Orography, storm track, SLP, and surface wind vectors at 20/1200-24 from CONT, with insets of vertical cross sections for CONT and NOR6 — image not reproducible in markdown]

In all experiments, the track and deepening rate remained relatively unchanged. In NOR1 (all orographic features modified), the main maximum of 224 mm in CONT was reduced to 159 mm. In NOR6 (SE and VAL removed), the value was reduced to 165 mm.

[Figure 15: 48-h accumulated precipitation and orography for (a) CONT, (b) NOTR, and (c) NOR6 — image not reproducible in markdown]

The removal of the Saguenay valley and the southeast mountain in NOR6 results in significant reduction of upward motion. The maximum $w$-value over the Saguenay valley at 700 hPa is reduced from 0.33 m s$^{-1}$ (CONT) to 0.22 m s$^{-1}$ (NOR6), a reduction of 33%. At 400 hPa, the value decreases from 0.41 m s$^{-1}$ in CONT to 0.36 m s$^{-1}$ in NOR6, a reduction of slightly over 10%.

**Table 5. 48-h accumulated total, explicit, and convective precipitation amounts for CONT and NOR6 at the grid points of maximum total precipitation in CONT (point 1) and the maximum difference between CONT and NOR6 (point 2) and the area average.**

| Point | Total CONT (mm) | Total NOR6 (mm) | Explicit CONT (mm) | Explicit NOR6 (mm) | Convective CONT (mm) | Convective NOR6 (mm) |
|-------|----------------|----------------|-------------------|-------------------|---------------------|---------------------|
| 1 | 224 | 165 (26%) | 115 | 82 (15%) | 109 | 83 (12%) |
| 2 | 214 | 146 (32%) | 96 | 64 (15%) | 117 | 82 (16%) |
| Area ave. | 202 | 156 (23%) | 101 | 75 (13%) | 101 | 81 (10%) |

**Table 6. Differences in PR48 between runs CONT and NOR6 in two particular areas.**

| | Area of Saguenay PR48 maximum | Area of main differences in PR48 between CONT and NOR6 |
|--|-------------------------------|--------------------------------------------------------|
| Average PR48 difference | 48.1 mm | 41.0 mm |
| Average PR48 in CONT | 203.8 mm | 188.6 mm |
| Percent difference | 23.6% | 21.7% |

**Table 7. Differences in PR48 between runs CONT and NOR6 at specific grid points.**

| | Location of PR48 maximum in CONT | Location of maximum difference in PR48 between CONT and NOR6 |
|--|----------------------------------|---------------------------------------------------------------|
| Difference in PR48 | 59.5 mm | 67.2 mm |
| PR48 value | 224.1 mm | 213.2 mm |
| Percent difference | 26.6% | 31.5% |

**Table 8. Differences in PR48 between runs CONT and NOR6 due specifically to VAL, SE, and the interaction between VAL and SE (factor separation).**

| | Area of Saguenay PR48 maximum | Area of main differences in PR48 between CONT and NOR6 |
|--|-------------------------------|--------------------------------------------------------|
| VAL | 33.4 mm (69.6%) | 24.5 mm (59.9%) |
| SE | 12.2 mm (25.4%) | 14.6 mm (35.7%) |
| VAL + SE interaction | 2.4 mm (5.0%) | 1.8 mm (4.4%) |

The factor separation technique of Stein and Alpert (1993) shows that the interaction between VAL and SE played only a minor role (about 5%). The total effect on PR48 is essentially the linear combination of the contributions of VAL and SE.

---

## 6. Conclusions

A state-of-the-art mesoscale model at a horizontal grid spacing of 20 km was used to perform a 48-h simulation of the Saguenay cyclone. Comparison with observations and analyses demonstrated good performance in terms of mass and wind fields, humidity distribution, and quantitative precipitation forecasting in both space and time.

The explosive deepening of the storm resulted from the combined effects of:
- Upper-level divergence caused by an upper-level jet streak and two shortwave troughs
- Latent heat release from moist air originating from the Gulf of Mexico
- Warm advection from strong low-level winds in a low-level baroclinic zone

The northern trough was the main source of upper-level forcing. The southern trough was important in retarding the progression of the northern trough, which steered the cyclone, ultimately locating it in a favorable position for surface winds to flow upslope from the Saguenay valley to the mountain immediately to the southeast. Without latent heat release, upper-level forcing would still have been strong but the cyclone would have wandered south, and virtually no deepening occurred. PV diagnostics indicated that in the middle of the explosive deepening period:
- Upper-level dry PV anomaly (northern trough): 47% of 900-hPa geopotential height anomaly
- Low-level moist PV anomaly (latent heat release): 41%
- Surface baroclinicity: 12%

Orographic variation (Saguenay valley + southeast mountain peak) enhanced precipitation, contributing approximately 20% of the 48-h total accumulated precipitation in the Saguenay region, with local effects exceeding 30% in certain areas. Neither the orography to the north of the valley nor the mountain peak immediately to the southwest played significant roles.

Another mechanism contributing to heavy precipitation was ridging to the east of the cyclone, which blocked cyclone movement after 1200 UTC 20 July, keeping it quasi-stationary for approximately 24 h and allowing continued precipitation over the Saguenay region.

---

## Acknowledgments

This research was supported by the Natural Science and Engineering Research Council and the Atmospheric Environment Service of Canada.

---

## References

Anthes, R. A., 1983: Regional models of the atmosphere in middle latitudes. *Mon. Wea. Rev.*, **111**, 1306–1335.

Balasubramanian, G., and M. K. Yau, 1994: The effects of convection on a simulated marine cyclone. *J. Atmos. Sci.*, **51**, 2397–2417.

Barnes, S., 1964: A technique for maximizing details in numerical map analysis. *J. Appl. Meteor.*, **3**, 395–409.

Benoit, R., J. Cote, and J. Mailhot, 1989: Inclusion of a TKE boundary layer parameterization in the Canadian regional finite-element model. *Mon. Wea. Rev.*, **117**, 1726–1750.

Benoit, R., M. Desgagné, P. Pellerin, S. Pellerin, Y. Chartier, and S. Desjardins, 1997: The Canadian MC2: A semi-Lagrangian, semi-implicit wideband atmospheric model suited for finescale process studies and simulation. *Mon. Wea. Rev.*, **125**, 2382–2415.

Chouinard, C., J. Mailhot, H. L. Mitchell, A. Staniforth, and R. Hogue, 1994: The Canadian regional data assimilation system: Operational and research applications. *Mon. Wea. Rev.*, **122**, 1306–1325.

Davis, C. A., 1992a: A potential-vorticity diagnosis of the importance of initial structure and condensational heating in observed extratropical cyclogenesis. *Mon. Wea. Rev.*, **120**, 2409–2428.

Davis, C. A., 1992b: Piecewise potential vorticity inversion. *J. Atmos. Sci.*, **49**, 1397–1411.

Davis, C. A., and K. A. Emanuel, 1991: Potential vorticity diagnostics of cyclogenesis. *Mon. Wea. Rev.*, **119**, 1929–1953.

Davis, C. A., M. T. Stoelinga, and Y.-H. Kuo, 1993: The integrated effect of condensation in numerical simulations of extratropical cyclogenesis. *Mon. Wea. Rev.*, **121**, 2309–2330.

Deardorff, J. W., 1978: Efficient prediction of ground surface temperature and moisture with inclusion of a layer of vegetation. *J. Geophys. Res.*, **83**, 1889–1903.

Environment Canada, 1997: Pluies deluviennes du 18 au 21 juillet 1996, au Quebec: Analyse et interpretation de donnees meteorologiques et climatologiques. Catalog No. En56-122/2-1997F (unpublished internal report), 105 pp.

Ertel, H., 1942: Ein Neuer hydrodynamischer Wirbelsatz. *Meteor. Z.*, **59**, 271–281.

Fouquart, Y., and B. Bonnel, 1980: Computations of solar heating of the earth's atmosphere: A new parameterization. *Contrib. Atmos. Phys.*, **53**, 35–62.

Garand, L., and J. Mailhot, 1990: The influences of infrared radiation on numerical weather forecasts. *Preprints, Seventh Conf. on Atmospheric Radiation*, San Francisco, CA, Amer. Meteor. Soc., J146–J151.

Grescoe, T., 1997: After the Deluge. *Can. Geographic*, **117**, 29–40.

Hamill, T. S., 1999: Hypothesis tests for evaluating numerical precipitation forecasts. *Wea. Forecasting*, **14**, 155–167.

Hoskins, B. J., M. E. McIntyre, and A. W. Robertson, 1985: On the use and significance of isentropic potential vorticity maps. *Quart. J. Roy. Meteor. Soc.*, **111**, 877–946.

Huo, Z., D.-L. Zhang, and J. R. Gyakum, 1999a: Interaction of potential vorticity anomalies in extratropical cyclogenesis. Part I: Static piecewise inversion. *Mon. Wea. Rev.*, **127**, 2546–2561.

Huo, Z., D.-L. Zhang, and J. R. Gyakum, 1999b: Interaction of potential vorticity anomalies in extratropical cyclogenesis. Part II: Sensitivity to initial perturbations. *Mon. Wea. Rev.*, **127**, 2563–2575.

Kain, J. S., and J. M. Fritsch, 1993: Convective parameterization for mesoscale models: The Kain–Fritsch scheme. *The Representation of Cumulus Convection in Numerical Models*, Meteor. Monogr., No. 46, Amer. Meteor. Soc., 165–177.

Kong, F.-Y., and M. K. Yau, 1997: An explicit approach to microphysics in MC2. *Atmos.–Ocean*, **33**, 257–291.

Kuo, H. L., 1974: Further studies of the parameterization of the influence of cumulus convection on large-scale flow. *J. Atmos. Sci.*, **31**, 1232–1240.

Mailhot, J., 1994: The Regional Finite-Element (RFE) Model scientific description. Part 2: Physics. Available from RPN, 2121 Trans-Canada, Dorval, QC H9P 1J3, Canada.

Mailhot, J., R. Sarrazin, B. Bilodeau, N. Brunet, and G. Pellerin, 1997: Development of the 35-km version of the Canadian regional forecast system. *Atmos.–Ocean*, **35**, 1–28.

Misra, V., M. K. Yau, and N. Badrinath, 2000: Atmospheric water species budget in mesoscale simulations of lee cyclones over the Mackenzie River Basin. *Tellus*, **52A**, 140–161.

Raymond, D. J., and K. A. Emanuel, 1993: The Kuo cumulus parameterization. *The Representation of Cumulus Convection in Numerical Models*, Meteor. Monogr., No. 46, Amer. Meteor. Soc., 145–148.

Robert, A., T. L. Yee, and H. Ritchie, 1985: A semi-Lagrangian and semi-implicit numerical integration scheme for multilevel atmospheric models. *Mon. Wea. Rev.*, **113**, 388–394.

Rogers, E., and L. F. Bosart, 1986: An investigation of explosive deepening oceanic cyclones. *Mon. Wea. Rev.*, **114**, 702–718.

Stein, U., and P. Alpert, 1993: Factor separation in numerical simulations. *J. Atmos. Sci.*, **50**, 2107–2115.

Sundqvist, H., E. Berge, and J. E. Kristjansson, 1989: Condensation and cloud parameterization studies with a mesoscale numerical weather prediction model. *Mon. Wea. Rev.*, **117**, 1641–1657.

Tanguay, M., A. Robert, and R. Laprise, 1990: A semi-implicit semi-Lagrangian fully compressible regional forecast model. *Mon. Wea. Rev.*, **118**, 1970–1980.

Uccellini, L. W., 1990: Processes contributing to the rapid development of extratropical cyclones. *Extratropical Cyclones, the Erik Palmén Memorial Volume*, C. W. Newton and E. O. Holopainen, Eds., Amer. Meteor. Soc., 81–105.

Verret, R., L. Lefaivre, J.-G. Desmarais, and T. Robinson, 1996: Intense precipitation in Quebec, July 19–20, 1996. *Can. Meteor. Cen. Rev.*, **3**, 1–29.

Yu, W., C. Lin, and R. Benoit, 1997: High resolution simulation of the severe precipitation event over the Saguenay, Quebec region in July 1996. *Geophys. Res. Lett.*, **24**, 1951–1954.
