# A Multimoment Bulk Microphysics Parameterization. Part III: Control Simulation of a Hailstorm

**Authors:** J. A. Milbrandt (Dept. of Atmospheric and Oceanic Sciences, McGill University, Montreal, and Recherche en Prévision Numérique, Meteorological Service of Canada, Dorval, Quebec, Canada); M. K. Yau (Dept. of Atmospheric and Oceanic Sciences, McGill University, Montreal, Quebec, Canada)

**Journal:** *Journal of the Atmospheric Sciences*, **63**, 3114–3136 (December 2006)

**Manuscript:** JAS3816 (received 1 April 2005, in final form 10 March 2006)

**DOI:** 10.1175/JAS3816.1

---

## Abstract

With continuous increase in the resolution of operational numerical weather prediction models, grid-scale saturation schemes that model cloud microphysics are becoming increasingly important. In Parts I and II of this study, the importance of the relative dispersion of the hydrometeor size distribution in bulk microphysics parameterizations was demonstrated and a closure approach for a three-moment scheme was proposed. In this paper, the full three-moment version of the new multimoment scheme is tested in a 3D simulation of a severe hailstorm. The modeled microphysical fields are examined, with particular attention paid to the simulated hail fields including the maximum hail sizes at the ground.

A mesoscale model was initialized using synoptic analyses and successively nested to a resolution of 1 km. When compared to observations of the real storm from a nearby radar, the simulated storm reproduced several of the observed characteristics including the direction and speed of propagation, a bounded weak echo region, hook echo, mesocyclone, and a suspended overhang region. The magnitudes of radar reflectivity and surface precipitation are also well simulated.

The mass contents, total number concentrations, equivalent reflectivities, and mean mass diameters of each hydrometeor category in the model were examined. The spatial distributions of the various hydrometeors throughout the storm appeared realistic and their values were consistent with published observations from other storms. Using the three predicted parameters of the gamma size distribution for hail, a method was introduced to determine the maximum hail size simulated from a bulk scheme that is physically observable. The observed storm produced golf ball–sized hail while the simulation produced walnut-sized hail at approximately the same time and location. The results suggest that because of the additional information provided about the size distribution, there is added value in prognosing the relative dispersion parameter of a given hydrometeor category in a bulk scheme.

---

## 1. Introduction

Since the initial success of barotropic models in the 1960s, operational numerical weather prediction (NWP) models have improved considerably due to increases in computer power and advanced treatment of physical processes (Bacon et al. 2000). As model resolution approaches the convective scale, it becomes possible to resolve the strong updrafts of severe convective storms (e.g., Weisman and Klemp 1984). At horizontal grid spacing on the order of 1–2 km or less, grid-scale condensation schemes, rather than subgrid-scale convective parameterizations, are employed. In cloud-resolving models, such condensation schemes continue to play an important role in atmospheric research.

Milbrandt and Yau (2005a, hereafter Part I) demonstrated the importance of the spectral dispersion of the hydrometeor size distributions in bulk microphysics schemes. It was shown that $\alpha$, the spectral shape parameter that is a measure of the relative dispersion in a gamma size distribution of diameter of the form

$$N(D) = N_0 D^\alpha e^{-\lambda D}, \tag{1}$$

significantly affects the computation of sedimentation and microphysical growth rates. A three-moment closure method was proposed with three independent prognostic parameters. With this approach, Milbrandt and Yau (2005b, hereafter Part II) introduced a multimoment bulk microphysics parameterization consisting of six distinct hydrometeor types, two liquid and four ice phase categories, each represented by a complete gamma size distribution function of the form of (1). The full version of the scheme predicts three moments of the distributions — the mass content, total number concentration, and radar reflectivity — for the five sedimenting categories and two (mass content and number concentration) for cloud droplets.

With the introduction of predictive equations for the reflectivity, the relative dispersion in the Part II scheme varies independently. The new scheme has since been interfaced with a fully compressible, nonhydrostatic mesoscale model. The simulation described in this paper is, to the authors' knowledge, the first cloud-resolving model simulation with a three-moment bulk scheme.

This paper is the third in a series on the new multimoment microphysics parameterization. The goal is to test the new scheme in a high-resolution 3D model and to study the effects of predicting three independent moments of the size distributions. Although a convective storm is examined, the main focus is not on storm dynamics but on the simulated microphysical fields. Considering the importance of hail in severe convective storms, special attention is placed on the simulated hail and its maximum sizes. In Milbrandt and Yau (2006, hereafter Part IV), the three-moment simulation described here is treated as the control run, and a number of sensitivity experiments using different versions of the same scheme are compared.

Two main approaches exist to explicitly model convection using a cloud-resolving model. The first uses horizontally homogeneous initial conditions from a single sounding plus an initial impulse to trigger convection; however, even qualitative results are very sensitive to how the perturbation is specified (e.g., McPherson and Droegemeier 1991). The second approach — used here — initializes the model with synoptic-scale data and successively nests it to higher resolution. If the observational data are sufficiently accurate and the model has enough skill to reproduce the correct mesoscale environment, it should be possible to simulate a storm representative of the observed convection, and the hydrometeor fields can be examined to evaluate the microphysics scheme.

## 2. Case description

The case selection was based mainly on the criterion that the storm track, storm structure, and the occurrence of large hail at the ground are sufficiently well-observed, plus the availability of radar data. South-central Alberta, Canada is one of the most highly prone regions in the world for severe hailstorms (Knight and Knight 2001). Since 1996, Weather Modification Inc. (WMI) has run an operational hail suppression project during the summer months (Krauss 2000). A C-band (5-cm wavelength) radar is located at the Olds–Didsbury Airport (ODA).

The selected case is the **14 July 2000 "Pine Lake" storm**, a long-lasting supercell that formed in the midafternoon over the foothills of southwestern Alberta. It tracked eastward over several hours and produced an F3 tornado (Joe and Dudley 2000). There were several observations of large hail at the ground, and the storm was well observed by the ODA radar for several hours, including a period with golf ball to softball-sized hail at the ground.

[Figure 1: Grid configuration for the nested MC2 simulations of the 14 Jul 2000 Pine Lake case, with 240- and 150-km range rings for the Carvel and ODA radars; inset shows the 1-km domain with CNTR storm locations every 30 min from 3:00 to 8:00 P.M. — image not reproducible in markdown]

[Figure 2: Composite of maximum reflectivity from the Carvel radar at (a) 2200 UTC 14 Jul 2000 and (b) 0030 UTC 15 Jul 2000 — image not reproducible in markdown]

### a. Main storm track and precipitation from the ODA radar

The ODA radar (3.2-m antenna, 1.65° beamwidth, 250 kW peak power) was last calibrated one week before the storm. Precipitation inferred from the radar was computed using reflectivity at 1 km AGL converted to instantaneous rain rates using an assumed Marshall–Palmer drop size distribution with $Z = 200 R^{1.6}$. The Pine Lake storm was tracked from its first echo at ~2030 UTC (2:30 P.M.) to 0300 UTC (9:00 P.M.) 15 July. Accumulated precipitation amounts of 25–30 mm (peak >30 mm, one pixel >40 mm) were indicated over areas of tens of square kilometers.

[Figure 3: Accumulated precipitation from ODA radar for 0600 UTC 14 Jul to 0527 UTC 15 Jul 2000 — image not reproducible in markdown]

### b. Evidence of hail

The composite of maximum vertically integrated liquid water (VIL) from the ODA radar is often used as a surrogate for the presence of large hail (Amburn and Wolf 1997). VIL values greater than 27 kg m⁻² generally represent approximately a 50% chance of golf ball–sized hail at the ground. Large hail was likely arriving at the ground from ~2345 to 0015 UTC (5:45–6:15 P.M.), with continuous and widespread large hail from ~0045 UTC (6:45 P.M.) onward, supported by many reports of golf ball–sized hail between 0100 and 0200 UTC.

A complication is that the Pine Lake storm had been seeded prior to 2345 UTC to reduce hail sizes (Krauss 2000); seeding effects were not included in the model and their effect on observed hail sizes is unknown. The authors argue that neglecting this aspect is unlikely to interfere with conclusions about the overall skill of the microphysics scheme.

[Figure 4: Composite of maximum VIL from ODA radar for 1200 UTC 14 Jul through 0200 UTC 15 Jul 2000 — image not reproducible in markdown]

## 3. Model description and nesting strategy

Simulations were performed using the Canadian Mesoscale Compressible Community Model (MC2), a fully compressible, nonhydrostatic, limited-area model capable of one-way self-nesting (Benoit et al. 1997; Mailhot et al. 1998). A triply nested simulation was performed with outer, middle, and inner domains having horizontal grid spacings of **12, 3, and 1 km**, respectively. Initial and six-hourly boundary conditions for the 12-km run were supplied by the Canadian Meteorological Centre (CMC) analysis system based on the regional GEM model.

The 12-km simulation was initialized at 1200 UTC 14 July 2000 and run 18 h; the 3-km run for 13 h from 1700 UTC; the 1-km run for 6 h from 2000 UTC. The 1-km control simulation (**CNTR**) used the three-moment version of the microphysics scheme from Part II and covered 2000 UTC (2:00 P.M.) 14 July to 0200 UTC (8:00 P.M.) 15 July. (Full model settings are given in Appendix A.)

## 4. Thermodynamic structure

The simulated thermodynamic structure near the model storm on the 1-km grid was consistent with the observed supercell. The 2300 UTC (5:00 P.M.) model sounding showed approximately **1430 J kg⁻¹ of CAPE**, with some low-level convective inhibition (CIN), and the wind shear vector veered with height — favorable for a right-moving supercell (Weisman and Klemp 1984). However, the surface-to-400-hPa shear magnitude was ~20 m s⁻¹, considered barely sufficient to support supercell development. (This becomes relevant in Part IV, where the SM_A sensitivity run had a much stronger cold pool and a more multicellular storm.)

[Figure 5: Prestorm model (1-km grid) sounding and hodograph in the Pine Lake region at 2300 UTC 14 Jul 2000 — image not reproducible in markdown]

## 5. Comparison of control simulation to radar observations

### a. Storm track, intensity, and precipitation

**1) Storm track.** In the 1-km simulation, two major cells formed along the foothills 1 h into the integration (2100 UTC) and tracked northeastward. The southern cell was the most coherent and is hereafter referred to as the **CNTR storm**; it is validated against the observed Pine Lake storm despite a southward displacement. The model storm had a northward propagation bias relative to the observed storm (consistent with the steering-level flow difference), but both moved to the right of the steering-level winds at similar speeds (model: 48–52 km h⁻¹; observed: 46–52 km h⁻¹).

**2) Updraft intensity.** The CNTR storm developed gradually for the first 1.5 h, then rapidly intensified at 2:30 h (4:30 P.M.) as the updraft increased from 13 to 26 m s⁻¹ over 15 min, reaching 31 m s⁻¹ by 3:15 h and peaking at 33 m s⁻¹ at 5:30 h (7:30 P.M.). Using CAPE = 1430 J kg⁻¹ and $w_{max} = \sqrt{2 \times \text{CAPE}}$ gives 53 m s⁻¹, roughly double the modeled 29 m s⁻¹ — consistent with parcel theory overestimating $w_{max}$ by up to a factor of two (Bluestein 1993).

[Figure 7: (a) Maximum instantaneous vertical velocity and (b) maximum instantaneous total, liquid, and solid precipitation rates in the vicinity of the main storm of CNTR — image not reproducible in markdown]

**3) Precipitation.** All rates peaked at 3:45 h when the maximum total, liquid, and solid precipitation rates were **185, 166, and 87 mm h⁻¹**, respectively. The storm had a period of intense hail precipitation from ~3:15–4:15 h (5:15–6:15 P.M.) with solid rate exceeding 50 mm h⁻¹. The pattern and quantity of total accumulated precipitation (peak ~33 mm) were quite close to the radar-inferred pattern (patches of 25–30 mm, peak 40–50 mm). The accumulated hail at the surface corresponded reasonably well to the observed VIL composite, though the model failed to simulate the observed reintensification of large hail after ~6:45 P.M.

[Figure 6: Accumulated 6-h (2:00–8:00 P.M.) (a) total, (b) liquid, and (c) solid precipitation from CNTR on the full 1-km domain — image not reproducible in markdown]

### b. Storm structure

The total equivalent reflectivity $Z_e$ was computed as the sum of the equivalent reflectivities for each hydrometeor category (except cloud):

$$Z_e = Z_{er} + Z_{ei} + Z_{es} + Z_{eg} + Z_{eh}. \tag{2}$$

At 5:47 P.M., the modeled storm showed high reflectivity (>50 dBZ) aloft overlying weaker values below, indicating suspended hail, and a distinct **bounded weak echo region (BWER)** ahead of a high-reflectivity core reaching the ground. A weak echo region (WER) and radar overhang were evident at 6:30 P.M. Core $Z_e$ values from the model were 50–60 dBZ (>55 dBZ between 600–350 hPa at 5:45 P.M.; >60 dBZ at 6:30 P.M.), versus observed core values of 51–54 dBZ. The CNTR storm exhibited a hook echo in the $Z_e$ field due to wrap-around of hail through a rotating updraft, and the 700-hPa winds indicated a mesocyclone — classifying both as high-precipitation (HP) supercells (Rasmussen and Straka 1998).

[Figure 8: Vertical cross sections of radar reflectivity and composites of maximum reflectivity from the ODA radar at 2347 UTC and 0030 UTC — image not reproducible in markdown]

[Figure 9: Vertical cross sections of equivalent reflectivity and 700-hPa equivalent reflectivity from CNTR at 3:45 h and 4:30 h — image not reproducible in markdown]

[Figure 10: Reflectivity CAPPI at 2 km from ODA radar, and 700-hPa equivalent reflectivity with mass contents of hail and rain and horizontal winds from CNTR — image not reproducible in markdown]

## 6. Analysis of microphysical fields

Since the gross features of the simulated storm compare favorably to radar observations up to 7:00 P.M., the growth environment for hydrometeors is judged realistic, allowing analysis of the microphysical fields.

### a. Simulated hydrometeor fields

The predicted equivalent reflectivity ($Z_{ex}$), mass content ($Q_x$), total number concentration ($N_{Tx}$), and mass-weighted mean diameter ($D_{mx}$) for each category were examined at 4:30 h (6:30 P.M.). The major contribution to high $Z_e$ aloft was from hail, while both hail and rain contributed substantially below 700 hPa. The peak total condensed mass content was ~6.8 g m⁻³ at 600 hPa, most of which was hail (peak >4 g m⁻³, concentrated aloft and upshear of the updraft).

Peak raindrop number concentrations ($N_{Tr}$) were ~10³ m⁻³; ice and snow number concentrations were ~10⁸ and ~10⁵ m⁻³. The hail number distribution was biased toward the downshear side of the updraft (small, high-concentration frozen drops carried upward and ejected into the anvil). Mean cloud droplet diameters ranged 5–15 μm in the updraft. Raindrop mean diameters in the hail growth zone (HGZ) ranged ~0.1–1.0 mm, reaching 3 mm at the surface. The maximum mean hail diameter ($D_{mh}$) at this time was 18.4 mm (at 775 hPa), while the maximum size at the ground was 6.1 mm.

[Figure 11: Vertical velocity, storm-relative winds, total equivalent reflectivity, and equivalent reflectivity of rain, ice+snow, graupel, and hail from CNTR at 4:30 h — image not reproducible in markdown]

[Figure 12: Vertical cross sections of mass content $Q_x$ of cloud, rain, ice, snow, graupel, and hail from CNTR at 4:30 h — image not reproducible in markdown]

[Figure 13: As Fig. 12 but for total number concentration $N_{Tx}$ (logarithmic scale) — image not reproducible in markdown]

[Figure 14: As Fig. 12 but for mean-mass diameters $D_{mx}$ — image not reproducible in markdown]

### b. Comparison with observations of hydrometeor properties in other storms

Because in situ microphysical measurements were not made for this storm, simulated values were compared to published measurements in other storms (Huan 1963; Uijlenhoet et al. 2003; Hobbs et al. 1980; Heymsfield and Platt 1984; Locatelli and Hobbs 1974; Cheng and English 1983; etc.). The simulated hydrometeor sizes and number concentrations conformed to the orders of magnitude of observations in similar storms, giving credence to the scheme and the partitioning of the hydrometeor spectrum into categories. (The authors note this is not a rigorous validation.)

### c. Particle size distributions and related aspects

The independent prediction of three moments of each sedimenting category implies a greater range of possible size distributions and allows realistic simulation of maximum particle sizes with a bulk scheme.

**1) Simulation of maximum hail sizes.** Since the hail category can include small frozen droplets as well as large hail, the mean hail diameter is not a good indicator of the presence or absence of large hail. Two parameters are introduced. The first is the total number concentration of particles larger than a particular size $D^*$:

$$N_h^*\{D^*\} \equiv \int_{D^*}^{\infty} N(D)\, dD. \tag{3}$$

A threshold value of $N^*_{CRIT} = 10^{-4}$ m⁻³ is adopted to delineate significant from insignificant concentrations. A second parameter, more appropriate at the surface, is the flux of large hail:

$$R_h^*\{D^*\} \equiv N_h^*\{D^*\} \times V_h(D^*), \tag{4}$$

where $V_h(D^*)$ is the terminal fall velocity at the surface for a hailstone of diameter $D^*$. A threshold $R^*_{CRIT} = 10^{-3}$ m⁻² s⁻¹ (one large hailstone per ten square meters every hundred seconds) is proposed, consistent with $N^*_{CRIT}$ for a fall speed of 10 m s⁻¹.

In CNTR at 5:45 P.M. (3:45 h, peak hail precipitation), the maximum near-surface (900 hPa) values of $N_h^*$ for $D^*$ of 1, 2, and 3 cm (grape-, walnut-, and golf ball–sized, respectively) were $5.70\times10^{-1}$, $2.92\times10^{-3}$, and $1.35\times10^{-5}$ m⁻³. The corresponding $R_h^*$ values were $6.27\times10^{0}$, $5.0\times10^{-2}$, and $2.3\times10^{-4}$ m⁻² s⁻¹. Thus, by the $R^*_{CRIT}$ threshold, a significant quantity of grape- and walnut-sized hail reached the surface, but golf ball–sized hail was insignificant — so the **maximum simulated hail size at the ground was 2–3 cm (walnut-sized)**, versus golf ball–sized hail observed. (Note: the $D_{mh}$ at that location was only 3.4 mm, which by itself says nothing about large hail.)

[Figure 15: Illustration of the application of $N_h^*\{D^*\}$ as an indicator for the presence of hail larger than $D^*$ — image not reproducible in markdown]

[Figure 16: $Q_h$ and $N_h^*\{1\text{ cm}\}$ from CNTR at 5:45 P.M. at 700 hPa and along a vertical cross section — image not reproducible in markdown]

[Figure 17: Vertical profiles of $N_h^*\{1\text{ cm}\}$, $N_h^*\{2\text{ cm}\}$, and $D_{mh}$ from CNTR at 3:45 h — image not reproducible in markdown]

The general point: $N_h^*$ and $R_h^*$ add value to identifying large hail **only if** the size distribution is adequately represented in the scheme, as with the three-moment method. For a one-moment scheme or a two-moment scheme with $\alpha_h$ fixed at 0, these parameters can be unrealistically large because they are greatly affected by the tail of the distribution.

**2) Hail size distributions.** Size distributions at various points show $\alpha_h = 0$ high in the storm (350 hPa) — inverse exponentials with small mean diameters (0.7–1.1 mm) — with greater variability and nonzero $\alpha_h$ lower down. The three-moment scheme yields distributions with more variability and more useful size-spectrum information.

*Selected hail size distribution (HSD) quantities at 700 hPa (Table 1 in original):*

| HSD | $Z_{eh}$ (dBZ) | $Q_h$ (g m⁻³) | $N_{Th}$ (m⁻³) | $\alpha_h$ | $D_{mh}$ (mm) | $N_h^*\{1\text{cm}\}$ (m⁻³) | $N_h^*\{2\text{cm}\}$ (m⁻³) | $N_h^*\{3\text{cm}\}$ (m⁻³) |
|-----|------|------|------|------|------|------|------|------|
| 2 | 60.5 | 4.62 | 119 | 1.21 | 4.35 | $1.09\times10^{0}$ | $1.85\times10^{-?}$ | $2.35\times10^{-6}$ |
| 3 | 53.8 | 3.52 | 9800 | 0.00 | 0.91 | $2.22\times10^{-5}$ | $5.02\times10^{-14}$ | $1.13\times10^{-22}$ |
| 5 | 59.2 | 1.33 | 6.57 | 3.47 | 7.54 | $7.12\times10^{-1}$ | $4.62\times10^{-3}$ | $1.33\times10^{-5}$ |

Distributions 2 and 5 have very similar reflectivities (60.5 and 59.2 dBZ) but very different mass contents (4.62 vs 1.33 g m⁻³) and number concentrations (119 vs 6.57 m⁻³). Distribution 5 has more walnut-sized hailstones despite distribution 2 having more grape-sized hailstones, because the larger $\alpha_h$ for distribution 5 shifts the spectrum toward larger sizes.

[Figure 18: Hail size distributions (HSD) from CNTR at 3:45 h at 350, 500, 700, and 900 hPa — image not reproducible in markdown]

**3) Vertical profiles of selected hail parameters.** While there is some positive correlation between $N_h^*\{1\text{cm}\}$, $N_h^*\{2\text{cm}\}$, and $D_{mh}$, this was not always the case — reinforcing that $N_h^*$, not $D_{mh}$, should indicate the presence of large hail. Size sorting (from Part I) was evident as $D_m$ and $\alpha$ often increased with decreasing elevation, with a distinct but non-monotonic positive correlation between $D_m$ and $\alpha$ — illustrating the appropriateness of the diagnostic $\alpha = f(D_m)$ relations for two-moment schemes (examined further in Part IV).

[Figure 19: Vertical profiles for hail (valid 3:35 h) for $\alpha_h$, $D_{mh}$, $Q_h$, $N_h^*\{1\text{cm}\}$, and $N_h^*\{2\text{cm}\}$ — image not reproducible in markdown]

**What can cause $\alpha$ to decrease in a three-moment scheme?** By design the minimum allowable $\alpha_h$ is 0. The answer is threefold:

1. **Advection.** Rearranging the $Z$–$Q$–$N_T$–$\alpha$ relation as $G = \frac{1}{c^2}\frac{Q^2}{Z N_T}$ (with $G = G(\alpha)$ a monotonically decreasing function of $\alpha$), differentiating, and substituting the 1D advection equations gives $\frac{\partial \ln G}{\partial t} = -w\left(\frac{\partial \ln G}{\partial z}\right)$. Thus upward motion where $\alpha$ increases with height causes a local increase in $G$ and decrease in $\alpha$.

2. **Microphysical source/sink terms.** Adding a small quantity of new hail (e.g., from collisional freezing of ice and rain, with prescribed $\alpha_h = 2$) to an existing broad spectrum can abruptly decrease $\alpha$. A numerical example (Table 2 in original): adding new hail with $\alpha = 2.00$ to an existing spectrum with $\alpha = 12.65$ yields a resulting spectrum with $\alpha = 0.10$, because a single gamma distribution must represent two narrow spectra centered at different diameters.

3. **Sedimentation.** Although it ultimately increases $\alpha$, sedimentation can locally decrease $\alpha$ where a narrow large-mean-size spectrum aloft "catches up" to a smaller-mean-size spectrum below.

[Figure 20: Hail size distributions resulting from the addition of hail formed from collisional freezing of ice and rain — image not reproducible in markdown]

**4) Vertical profiles of selected rain parameters.** All of the above comments apply to all categories with three predicted moments (i.e., all except cloud). For rain, $\alpha_r \geq 2$ everywhere (a scheme constraint). Near the surface at the convective core, mean-mass drop diameters were ~3.3 mm with $\alpha_r \sim 4.3$ and rainfall rate 131 mm h⁻¹. The range of the rain shape parameter at the surface in CNTR (~2.5–4.3) was similar to the range of mean shape-parameter values observed by Uijlenhoet et al. (2003) across regions of a squall line (2.11–5.00).

[Figure 21: Vertical profiles for rain (valid 3:35 h) of $\alpha_r$, $D_{mr}$, and $Q_r$ — image not reproducible in markdown]

## 7. Conclusions

The three-moment microphysics scheme of Part II was interfaced with a mesoscale model and used to simulate the 14 July 2000 Pine Lake storm on a high-resolution grid. The simulated supercell exhibited many of the same characteristics as the observed storm — propagation speed and direction, BWER, hook echo, mesocyclone, suspended overhang region, and observed values of radar reflectivity and surface precipitation. The magnitudes and spatial distributions of the various hydrometeor fields were shown to be realistic. An obvious limitation is that the study is limited to a single case with no in situ microphysical observations.

By examining hail distributions at the surface during the period of moderately intense hailfall (~5:45–6:30 P.M.), the model simulated **walnut-sized hail (2–3 cm)** in reasonable agreement with observations of golf ball–sized hail. The examination of hail sizes illustrates two things: (1) predicting three independent moments allows a greater range of spectra, with potential usefulness for radiative transfer calculations; (2) the reasonable maximum hail sizes illustrate the potential for improved hailstorm simulations using high-resolution 3D models where bin-resolving microphysics is computationally prohibitive. The authors advocate further investigation of schemes that allow the relative dispersion to vary — either via the three-moment method or via the two-moment method with a diagnostic dispersion parameter (Part I).

In Part IV, sensitivity experiments using various one- and two-moment versions of the scheme are compared to this control run.

---

## Appendix A: Model Settings

**12-km run:** Version 4.9.3 of MC2; 250×250 km grid centered at ODA radar; 30 Gal-Chen levels with rigid lid at 31 km; initialized with CMC regional ETA Model analyses; boundary conditions every 6 h; time step 90 s; radiation every 1800 s; Kain and Fritsch (1993) convective parameterization scheme; Kong and Yau (1997) explicit microphysics.

**3-km run:** Version 4.9.3 of MC2; 260×225 km² grid; 30 Gal-Chen levels (rigid lid 31 km); initialized with 12-km output; boundary conditions every 1 h; time step 30 s; no CPS; Kong and Yau (1997) explicit microphysics.

**1-km run:** Version 4.9.5 of MC2; 350×160 km² grid; 45 Gal-Chen levels (rigid lid 31 km); initialized with 3-km output; boundary conditions every 1 h; time step 10 s; no CPS; **three-moment version of Milbrandt and Yau (2005b) explicit microphysics**.

## Appendix B: Correction to Part I

Equation (A7) of Part I should read:

$$V_{Zx} = \frac{\int_0^{\infty} D^6 V_x(D_x) N_x(D_x)\, dD_x}{\int_0^{\infty} D^6 N_x(D_x)\, dD_x} = \gamma a_x \frac{\Gamma(7 + \alpha_x + b_x)}{\Gamma(7 + \alpha_x)} \frac{\lambda_x^{(7+\alpha_x)}}{(\lambda_x + f_x)^{(7+\alpha_x+b_x)}}.$$

---

*Acknowledgments: The authors thank Dr. Terry Krauss (Weather Modification Inc.) for the radar data and Dr. Ron McTaggart-Cowan for assistance interfacing the microphysics scheme with the mesoscale model. Research supported by the Canadian Foundation for Climate and Atmospheric Science.*
