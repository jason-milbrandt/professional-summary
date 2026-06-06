# Jouan and Milbrandt (2019)

**Full citation:** Jouan, C., and J. A. Milbrandt, 2019: The importance of the ice-phase microphysics parameterization for simulating the effects of changes to CCN concentrations in deep convection. *J. Atmos. Sci.*, **76**, 1727–1752, https://doi.org/10.1175/JAS-D-18-0168.1

**DOI:** 10.1175/JAS-D-18-0168.1

---

## Abstract

Simulations of a well-observed squall line that occurred during the Midlatitude Continental Convective Clouds Experiment (MC3E) were conducted using a mesoscale model with a horizontal grid spacing of 1 km to examine the importance of parameterized ice-phase processes to changes in concentrations of activated cloud condensation nuclei (CCN) in a detailed two-moment bulk microphysics scheme. Numerical experiments showed that the simulated squall-line structure was sensitive to changes in activated CCN concentration not only from the direct impacts on cloud droplet sizes and autoconversion rates, but also because of changes in the growth rates and spatial distribution of ice-phase condensate. A microphysical budget analysis highlighted the importance of graupel in rain production and the sensitivity of graupel growth rates on changes to CCN concentrations. Sensitivity tests on the level of detail in the representation of graupel, specifically the treatment of its bulk density and the number of prognostic moments, indicated that changes in the reflectivity and precipitation structure of the simulated storm due to changes in CCN were sensitive to the graupel parameterization. The results suggest that the proper representation of graupel and possibly other ice-phase categories in microphysics schemes may be crucial for correctly simulating the effects of changes to CCN concentrations for continental deep convective systems.

---

## 1. Introduction

Natural and anthropogenic atmospheric aerosols affect Earth's climate by modifying its energy balance and clouds. Recent studies show increasingly the importance of taking into account the aerosol–cloud–precipitation interactions in high-resolution (i.e., 1–3-km horizontal grid spacing) numerical weather prediction (NWP) models for improving short-term forecast accuracy, especially for mixed-phase mesoscale convective systems (MCSs; e.g., Noppel et al. 2010; Seifert et al. 2012; Thompson and Eidhammer 2014).

MCSs are significant rain-producing weather systems common in both midlatitude and tropical environments. They are organized ensembles of convective elements whose appearance and behavior are determined by several factors, including cold pool strength, vertical shear, ambient instability, and storm-relative winds.

A large number of numerical modeling studies have investigated the aerosol–cloud–precipitation interactions on mixed-phase MCSs, leading to the conclusion that discrepancies in precipitation response to aerosol loading depend not only on the MCS type and environmental factors, but also on the particular model configuration and microphysics parameterization used (Lebo and Seinfeld 2011; Tao et al. 2012). Recent work has suggested that including the effects of CCN concentrations in bulk schemes may be sensitive to details in the parameterization of ice-phase categories themselves, such as for the treatment of graupel density (e.g., Milbrandt and Morrison 2013).

The two-moment Milbrandt–Yau (MY2) microphysics scheme is used in the operational 2.5-km High Resolution Deterministic Prediction System (HRDPS; Milbrandt et al. 2016) in Environment and Climate Change Canada (ECCC).

The purpose of this study is to examine the importance of some specific details of the parameterization of ice-phase microphysics, in particular the representation of graupel, in a two-moment BMS to changes in CCN concentrations. The hypothesis tested is that in order to simulate correctly the effects of CCN, which directly affect cloud droplet number concentration only, the simulation of deep convective systems, as well as its sensitivity to aerosol loading, may ultimately depend greatly on details in the representation of ice.

---

## 2. Experimental Design

### a. Case Overview

The 20 May 2011 squall line was the most intense MCS that occurred during the Midlatitude Continental Convective Clouds Experiment (MC3E; Tao et al. 2013; Lang et al. 2014; Fan et al. 2015; Jensen et al. 2016). In the early morning of 20 May, a strong quasi-linear MCS quickly developed into a long leading convective line with a large trailing stratiform precipitation region. Extending to approximately 1000 km, it propagated in an eastward direction across northern Texas, Oklahoma, and southern Kansas to reach its peak in size and intensity near 1100 UTC. The mature phase of the squall line lasted until approximately 1400 UTC and started to dissipate afterward.

CCN number concentrations $N_\mathrm{act}$ measured at the ARM–SGP site varied between 600 and 2000 cm$^{-3}$ at the highest measured supersaturations (0.85% and 1.08%, respectively), with some peaks at 4000 cm$^{-3}$.

### b. Model Configuration

#### 1) GEM Model and Setup

High-resolution 3D simulations were performed using the nested limited-area Global Environmental Multiscale (GEM) model (Côté et al. 1998; Girard et al. 2014) with one-way nested domains (D1 and D2) with horizontal grid spacings of 2.5 and 1 km, respectively. The model uses 62 vertical sigma–pressure hybrid coordinate levels, with the lowest thermodynamic level at ~20 m AGL and the top at 10 hPa.

**Table 1. Summary of GEM model configuration.**

| Model aspect | Details |
|---|---|
| Grid | Arakawa C grid; two nested horizontal grids (D1: 1080×984 pts, $\Delta x$=2.5 km, $\Delta t$=60 s; D2: 1125×810 pts, $\Delta x$=1 km, $\Delta t$=20 s); 62 vertical levels |
| Initial and lateral boundary conditions | RDPS (GEM, 10 km) + CaLDAS (Carrera et al. 2015) |
| Microphysics scheme | Milbrandt–Yau two-moment scheme (MY05a,b; Milbrandt and Morrison 2013) |
| Convective scheme | Kuo transient shallow convection scheme (Bélair et al. 2005) |
| Planetary boundary layer scheme | TKE with statistical representation of subgrid-scale cloudiness (MoisTKE; Bélair et al. 2005) |
| Radiation scheme | Li–Barker correlated-k distribution radiative transfer scheme (called every 15 min; Li and Barker 2005) |
| Surface scheme | Soil, Biosphere, and Atmosphere (ISBA) land surface scheme (Noilhan and Planton 1989; Bélair et al. 2003) |

#### 2) Overview of MY2

Cloud microphysical processes are parameterized by the MY2 bulk scheme. MY2 predicts the mass contents and number concentrations for six hydrometeor categories: cloud water, rain, cloud ice, snow, graupel, and hail. The particle size distribution of each category is represented by a complete gamma function with a fixed spectral shape parameter of 1 for cloud water and 0 for rain and all ice categories. The CCN activation parameterization is based on Cohard and Pinty (2000), with maritime ($N_{ccn}$ = 66.6 cm$^{-3}$) or continental ($N_{ccn}$ = 842 cm$^{-3}$) air masses.

### c. Simulations Description

All simulations are initialized at 0000 UTC 20 May 2011 and integrated for 18 h. A control simulation (CTL) with continental CCN was first run. Sensitivity experiments used prescribed activated CCN concentrations of either $N_\mathrm{act}$ = 100 cm$^{-3}$ (CLN, clean) or $N_\mathrm{act}$ = 4000 cm$^{-3}$ (POL, polluted).

**Table 2. List of simulations and modifications in MY2.**

| Run | Details |
|---|---|
| CTL | Original MY2 with background CCN in continental mode and fixed graupel density $\rho_g$ |
| CLN | As CTL, but with $N_\mathrm{act}$ = 100 cm$^{-3}$ |
| POL | As CTL, but with $N_\mathrm{act}$ = 4000 cm$^{-3}$ |
| CLN_2A | As CLN, but with no autoconversion process |
| CLN_2B | As CLN_2A, but with lower graupel collection efficiency $E_{cg}$ [$D_{mc}$ in (4) replaced by $D_0$ using fixed $N_0 = N_{tc} = N_\mathrm{act}$ = 4000 cm$^{-3}$] |
| CLN_3A | As CLN, but with prognostic $\rho_g$ |
| POL_3A | As POL, but with prognostic $\rho_g$ |
| CLN_3B | As CLN, but with one moment for graupel |
| POL_3B | As POL, but with one moment for graupel |

---

## 3. Overview of Control Simulation

A control simulation (CTL) was run to establish that the squall-line system is sufficiently well simulated with GEM. The simulation correctly developed an elongated leading convective line oriented from southwest to northeast with a bowing structure, as observed. The GEM simulation also captures a large trailing stratiform region. However, the weak echo transition zone is not well captured, and the simulation produces a wide area of high reflectivity (>45 dBZ) in the convective region, consistent with a known bias of MY2 (Morrison et al. 2015; Fan et al. 2017).

[Figure 2: NEXRAD reflectivity and CTL simulated reflectivity at 1 km AGL for the 20 May 2011 event at 1100 UTC — image not reproducible in markdown]

[Figure 3: Time series of hourly accumulated precipitation averaged over D2 for CTL and observational data products, and for CLN and POL — image not reproducible in markdown]

---

## 4. Sensitivity of Ice-Phase Processes to CCN Concentrations

### a. Reflectivity Structure and Precipitation

In both CLN and POL simulations, a precipitating convective system appears after 2 h, and the squall line develops subsequently. Clear differences appear at 0800 UTC where model reflectivity is much larger in POL compared to CLN. In CLN, the separation between the trailing stratiform region and the convective line is better reproduced.

In CLN, the squall line developed 1 h earlier than in POL. During the main development phase (0600–1200 UTC), the hourly surface precipitation averaged over D2 varies by a factor of 1.19 from CLN to POL — the same order of magnitude as between CTL and observations.

**Table 3. Accumulated total surface precipitation (mm) from 0600 to 1200 UTC averaged over D2.**

| Run | Amount (mm) |
|---|---|
| Q2_GAUGE | 6.72 |
| Q2_STAGEIV | 4.85 |
| CTL | 7.28 |
| CLN | 8.17 |
| POL | 6.84 |
| CLN_2A | 7.26 |
| CLN_2B | 7.01 |
| CLN_3A | 8.55 |
| POL_3A | 7.70 |
| CLN_3B | 7.62 |
| POL_3B | 7.00 |

### b. Vertical Distribution of Hydrometeors

[Figure 6: Cross section of microphysical fields for CLN and POL at 1100 UTC — image not reproducible in markdown]

An increase in $N_\mathrm{act}$ leads to an increase in the mass of slow-falling hydrometeors such as cloud water ($q_c$), ice crystals ($q_i$), and snow mass content ($q_s$). Although $q_c$, $q_i$, and $q_s$ increase considerably, the mass content of graupel ($q_g$) decreases significantly with increasing activated CCN concentration. The mass content of hail ($q_h$) slightly increases with increasing $N_\mathrm{act}$.

In CLN, graupel is transported horizontally throughout almost the entire extent of the stratiform region, with contents all above or near the 0°C isotherm level (~4-km altitude). In POL, the $q_g$ total and peak quantities tend to decrease and are shifted downward, under the 0°C isotherm level. This suggests that graupel grows to larger mean sizes in polluted conditions with higher fall speeds, limiting horizontal transport to the stratiform region and promoting the formation of larger hail.

### c. Microphysical Budget Study

#### 1) Budget Setup

The budget methodology follows Colle and Zeng (2004) and Colle et al. (2005). Each microphysical process rate $Q^\mathrm{AB}_{xy}$ is output every 10 min, averaged over 0600–1200 UTC, and integrated vertically and horizontally, then normalized by the integrated water vapor loss (WVL):

$$\Pi^\mathrm{AB}_{xy} = \frac{\sum_{i,j} Q^\mathrm{AB}_{xy}(i,j,k)\,\rho(i,j,k)}{\sum_{i,j,k} \mathrm{WVL}(i,j,k)\,\rho(i,j,k)} \times 100\%$$

where WVL = $Q^\mathrm{VD}_{yc}$ [condensation] + $Q^\mathrm{VD}_{y,\mathrm{isgh}}$ [deposition] + $Q^\mathrm{NU}_{yi}$.

#### 2) Relative Contributions

[Figure 8: Microphysical flowchart for MY2 between 0600 and 1200 UTC for CLN and POL — image not reproducible in markdown]

The most important pathway of water vapor depletion is condensation: VD$_{yc}$ (cond = 78.12%) in CLN and VD$_{yc}$ (cond = 85.83%) in POL. Graupel depositional growth VD$_{yg}$ (depo = 16.99%) is another important pathway in CLN; deposition onto snow dominates in POL (VD$_{ys}$ = 8.22%).

An increase in $N_\mathrm{act}$ decreases the mean size of cloud droplets (below 7-km altitude), reducing the accretion rate (CL$_{cr}$ = 16.83%) and completely shutting off autoconversion in MY2 in POL (CN$_{cr}$ = 0%). The suppression of warm-rain processes retains more $q_c$ in the system, which freezes homogeneously to ice crystals at higher levels (FZ$_{ci}$ = 8.78% in POL). This results in increased cloud ice aloft, which is rapidly converted to snow (CN$_{is}$ = 12.09% of WVL in POL).

The lower graupel number concentration in POL is attributed to reduction of collisional freezing between graupel and rain (CL$_{grg}$ is a factor of 2.76 lower in POL), and the reduced riming rate (CL$_{cg}$ = 23.82% for CLN vs. 19.81% for POL), driven by the smaller mean cloud droplet size reducing the bulk collection efficiency $E_{cg}$.

### d. Impact on Updraft Speed

For POL, there is increased vertical motion compared to CLN from approximately 2.5 to 7.5 km AGL, indicating a convective invigoration effect due to aerosol loading. However, the trend reverses in upper levels and updrafts are weaker for POL.

### e. Sensitivity Experiments for Specific Processes

#### 1) Cloud Water Autoconversion

Simulation CLN_2A (no autoconversion) shows similar profiles to POL for cloud water, ice, and snow, confirming that suppression of autoconversion with increasing CCN plays an important role in convective invigoration.

#### 2) Graupel Collection Efficiency

In MY2, the collection efficiency between graupel and cloud water is:

$$E_{cg} = 0.55 \log(2.51 K)$$

where the dimensionless Stokes parameter is:

$$K = \frac{\rho_c V D_{mc}^2}{9\eta D_{mg}}$$

with $\eta$ the dynamic viscosity of air, $\rho_c$ the cloud water density, $D_{mc}$ the cloud water mean-mass diameter, $D_{mg}$ the graupel mean-mass diameter, and $V$ the impact velocity.

Simulation CLN_2B (low $E_{cg}$ using fixed $N_{tc}$ = 4000 cm$^{-3}$) brings CLN_2B even closer to POL, confirming that differences in graupel growth rates are strongly affected by the droplet size effect through the parameterized collection efficiency.

---

## 5. Sensitivity of the Parameterization of Graupel to CCN

### a. Prognostic Graupel Density

In all simulations discussed so far, $\rho_g$ had a fixed value of 400 kg m$^{-3}$. Milbrandt and Morrison (2013) described a development to the scheme in which $\rho_g$ is prognostic, using a rime density parameterization based on laboratory experiments.

With prognostic $\rho_g$ (CLN_3A and POL_3A), the response to CCN loading is quantitatively different in terms of magnitudes compared to the fixed-$\rho_g$ simulations, though qualitatively similar. The high $N_\mathrm{act}$ in POL_3A leads to a suppression of autoconversion and a reduction of the cloud collection rate (CL$_{cr}$ = 17.50%), similar in order of magnitude to POL, but with process rates at about half the values. An increase in $N_\mathrm{act}$ has less impact on ice-phase hydrometeor masses for the prognostic-$\rho_g$ configuration than for fixed $\rho_g$.

### b. One Moment for Graupel

Simulations CLN_3B and POL_3B used one-moment graupel (prognostic $q_g$ only, with fixed intercept $N_0$ = 4×10$^6$ m$^{-4}$). With a two-moment scheme, $q_g$ sediments at a faster bulk fall velocity than $N_{Tg}$, allowing a realistic size-sorting effect. In a one-moment scheme, $N_T$ and $D_m$ are diagnosed directly from $q$ with a single mean fall speed.

The results show that with the one-moment graupel configuration, the response to CCN loading is much less sensitive than with the two-moment graupel configuration. An increase in $N_\mathrm{act}$ has little impact on the mass of ice-phase hydrometeors for the one-moment graupel configuration.

[Figure 15: Differences in mass content between POL and CLN, POL_3A and CLN_3A, and POL_3B and CLN_3B — image not reproducible in markdown]
[Figure 17: Time series of hourly precipitation differences for CLN–POL, CLN_3A–POL_3A, and CLN_3B–POL_3B — image not reproducible in markdown]

---

## 6. Summary and Discussion

A midlatitude continental squall line was simulated with a mesoscale model using a fully two-moment bulk scheme. Sensitivity experiments were conducted in which elements of the graupel parameterization were modified for various pairs of simulations with high and low CCN concentrations.

Key conclusions:

1. The simulated squall-line structure is sensitive to changes in activated CCN concentration both from direct impacts on cloud droplet sizes and autoconversion rates, and because of changes in ice-phase growth rates and spatial distribution.

2. The CCN concentration affects cloud droplet number concentration and hence mean droplet diameter, causing changes in:
   - Graupel growth through the collection efficiency $E_{cg}$ between graupel and droplets
   - In the prognostic graupel density configuration, the instantaneous rime density

3. Whether the graupel category is one moment or two moment has a notable impact on the response to CCN.

4. The conclusions regarding the graupel–cloud droplet collection efficiency, treatment of graupel density, and the need for at least two-moment graupel should be valid for other deep convective systems and for other schemes.

5. These results lend support to the general idea of abandoning predefined ice-phase categories and moving toward particle property-based approaches (Morrison and Milbrandt 2015) for the representation of ice in models.

---

## Appendix: MY2 Bulk Scheme Prognostic Equations

In MY2, mass mixing ratios of water vapor $q_y$, cloud water $q_c$, cloud ice $q_i$, rain $q_r$, snow $q_s$, graupel $q_g$, and hail $q_h$ are related through numerous microphysical processes:

$$\frac{dq_y}{dt} = -Q^\mathrm{VD}_{yc} - Q^\mathrm{VD}_{yr} - Q^\mathrm{NU}_{yi} - Q^\mathrm{VD}_{yi} - Q^\mathrm{VD}_{ys} - Q^\mathrm{VD}_{yg} - Q^\mathrm{VD}_{yh} \tag{A1}$$

$$\frac{dq_c}{dt} = Q^\mathrm{VD}_{yc} - Q^\mathrm{CN}_{cr} - Q^\mathrm{CL}_{cr} - Q^\mathrm{FZ}_{ci} - Q^\mathrm{CL}_{cs} - Q^\mathrm{CL}_{cg} - Q^\mathrm{CL}_{ch} \tag{A2}$$

$$\frac{dq_r}{dt} = Q^\mathrm{CN}_{cr} + Q^\mathrm{CL}_{cr} + Q^\mathrm{VD}_{yr} + Q^\mathrm{ML}_{ir} + Q^\mathrm{ML}_{sr} + Q^\mathrm{ML}_{gr} + Q^\mathrm{ML}_{hr} - Q^\mathrm{CL}_{ri} - Q^\mathrm{CL}_{rs} - Q^\mathrm{CL}_{rg} - Q^\mathrm{CL}_{rh} + Q^\mathrm{SH}_{hr} - Q^\mathrm{FZ}_{rh} \tag{A3}$$

$$\frac{dq_i}{dt} = Q^\mathrm{NU}_{yi} + Q^\mathrm{FZ}_{ci} + Q^\mathrm{VD}_{yi} + Q^\mathrm{IM}_{si} + Q^\mathrm{IM}_{gi} - Q^\mathrm{CL}_{ir} - Q^\mathrm{CL}_{is} - Q^\mathrm{CL}_{ig} - Q^\mathrm{CL}_{ih} - Q^\mathrm{CN}_{is} - Q^\mathrm{ML}_{ir} \tag{A4}$$

$$\frac{dq_s}{dt} = \delta_{srs}(Q^\mathrm{CL}_{rs} + Q^\mathrm{CL}_{sr}) + Q^\mathrm{CN}_{is} + Q^\mathrm{VD}_{ys} + Q^\mathrm{CL}_{cs} + Q^\mathrm{CL}_{is} - Q^\mathrm{CN}_{sg} - Q^\mathrm{CL}_{sr} - Q^\mathrm{CL}_{sh} - Q^\mathrm{IM}_{si} - Q^\mathrm{ML}_{sr} \tag{A5}$$

$$\frac{dq_g}{dt} = \delta_{irg}(Q^\mathrm{CL}_{ir} + Q^\mathrm{CL}_{ri}) + \delta_{srg}(Q^\mathrm{CL}_{sr} + Q^\mathrm{CL}_{rs}) + \delta_{grg}(Q^\mathrm{CL}_{gr} + Q^\mathrm{CL}_{rg}) + Q^\mathrm{CN}_{sg} + Q^\mathrm{CL}_{cg} + Q^\mathrm{CL}_{ig} - Q^\mathrm{CL}_{gr} + Q^\mathrm{VD}_{yg} - Q^\mathrm{CN}_{gh} - Q^\mathrm{ML}_{gr} - Q^\mathrm{IM}_{gi} \tag{A6}$$

$$\frac{dq_h}{dt} = \delta_{irh}(Q^\mathrm{CL}_{ir} + Q^\mathrm{CL}_{ri}) + \delta_{srh}(Q^\mathrm{CL}_{sr} + Q^\mathrm{CL}_{rs}) + \delta_{grh}(Q^\mathrm{CL}_{gr} + Q^\mathrm{CL}_{rg}) + Q^\mathrm{FZ}_{rh} + Q^\mathrm{CN}_{gh} + Q^\mathrm{CL}_{ch} + Q^\mathrm{CL}_{rh} - Q^\mathrm{SH}_{hr} + Q^\mathrm{CL}_{ih} + Q^\mathrm{CL}_{sh} + Q^\mathrm{VD}_{yh} - Q^\mathrm{ML}_{hr} \tag{A7}$$

The microphysical process rate (kg kg$^{-1}$ s$^{-1}$) is denoted by $Q^\mathrm{AB}_{xy}$, where AB is the microphysical process (CL for collection, CN for conversion, FZ for freezing, IM for ice multiplication, ML for melting, NU for nucleation, SH for shedding, VD for diffusional growth), and the subscript $xy$ indicates the transfer of mass from species $x$ to $y$. The $\delta_{xyz}$ correspond to the delta function for three-component freezing between hydrometeors $x$ and $y$ to produce category $z$.

---

## References

[Full reference list in original paper — see pp. 1749–1752]
