# Simulation of an Orographic Precipitation Event during IMPROVE-2. Part I: Evaluation of the Control Run Using a Triple-Moment Bulk Microphysics Scheme

**Authors:** J. A. Milbrandt (Meteorological Research Division, Recherche en Prévision Numérique, Dorval, Quebec, Canada); M. K. Yau (McGill University, Montreal, Quebec, Canada); J. Mailhot and S. Bélair (Meteorological Research Division, Recherche en Prévision Numérique, Dorval, Quebec, Canada)

**Journal:** *Monthly Weather Review*, **136**, 3873–3893 (October 2008)

**Manuscript:** received 12 March 2007, in final form 24 January 2008

**DOI:** 10.1175/2008MWR2197.1

---

## Abstract

This paper reports the first evaluation of the Milbrandt–Yau multimoment bulk microphysics scheme against in situ microphysical measurements. The full triple-moment version of the scheme was used to simulate a case of orographically enhanced precipitation with a 3D mesoscale model at high resolution (4- and 1-km grid spacings). The simulations described in this paper also serve as the control runs for the sensitivity experiments that will be examined in Part II of this series. The 13–14 December 2001 case of heavy orographically enhanced precipitation, which occurred over the Oregon Cascades, was selected since it was well observed during the second Improvement of Microphysical Parameterization through Observational Verification Experiment (IMPROVE-2) observational campaign. The simulated fields were compared with observed radar reflectivity, vertical velocity, precipitation quantities from rain gauges, and microphysical quantities measured in situ by two instrumented aircraft. The simulated reflectivity structure and values compared favorably to radar observations during the various precipitation stages of the event. The vertical motion field in the simulations corresponded reasonably well to the mountain-wave pattern obtained from in situ and dual-Doppler radar inferred measurements, indicating that biases in the simulations can be attributed in part to the microphysics scheme. The patterns of 18-h accumulated precipitation showed that the model correctly simulated the bulk of the precipitation to accumulate along the coastal mountains and along the windward slope of the Cascades, with reduced precipitation on the lee side of the crest. However, both the 4- and 1-km simulations exhibited a general overprediction of precipitation quantities. The model also exhibited a distinct bias toward overprediction of the snow mass concentration aloft and underprediction of the mass and vertical extent of the pockets of cloud liquid water on the windward side of the Cascades. Nevertheless, the overall spatial distribution of the hydrometeor fields was simulated realistically, including the mean-mass particle diameters for each category and the observed trend of larger snow sizes to be located at lower altitudes.

---

## 1. Introduction

Increased computer power allows more sophisticated cloud microphysics schemes in high-resolution atmospheric models. Such schemes are useful for forecasting the type and quantity of surface precipitation and for providing correct latent heat release and radiative forcing. An important function is prediction of the hydrometeor size spectra. Two basic approaches exist: (1) the fully explicit **bin-resolving method** (e.g., Kogan 1991; Reisin et al. 1996; Geresdi 1998), generally prohibitively expensive for 3D NWP; and (2) the **bulk method (BMS)**, in which the hydrometeor spectrum is partitioned into categories represented by an analytic function (e.g., Lin et al. 1983; Cotton et al. 1986; Ferrier 1994; Reisner et al. 1998). Bulk schemes require far fewer prognostic variables and are generally preferred in NWP.

Several deficiencies in BMSs have been identified (autoconversion, cloud condensation nuclei, ice initiation, ice-particle terminal velocities, the assumed size distributions, snow aggregation, etc.; Stoelinga et al. 2003, hereinafter S03). Schemes vary considerably in complexity — in number of categories (one to seven or more), number of prognostic moments per category (one, two, or three: Milbrandt and Yau 2005a,b; Szyrmer et al. 2005), and number/detail of processes. It is not obvious a priori which aspects are of primary importance.

To investigate these problems, researchers at the University of Washington initiated the Improvement of Microphysical Parameterization through Observational Verification Experiment (IMPROVE). The second campaign — **IMPROVE-2**, the Oregon Cascades Orographic Field Study — was carried out in November–December 2001 on large-scale weather systems with terrain-enhanced precipitation, producing 17 intensive observation periods (IOPs) with remotely-sensed and in situ, ground- and aircraft-based measurements. The **13–14 December 2001 case** had particularly intense, well-observed precipitation and was studied during the 2004 Sixth WMO International Cloud Modeling Workshop (Grabowski 2006) and in a special section of *J. Atmos. Sci.* (2005, Vol. 62, No. 10). Garvert et al. (2005a,b, hereinafter G05a,b) simulated the case with MM5 + Reisner-2 BMS and showed certain forecast errors (e.g., excessive leeside precipitation spillover) traced directly to BMS biases; Colle et al. (2005, C05) examined microphysical budgets; Woods et al. (2005, WSLH) documented the microphysical measurements; Garvert et al. (2007, GSM) examined kinematic flow structures.

The multimoment Milbrandt and Yau (2005a,b, hereinafter MY05a,b) scheme — with options for one, two, or three prognostic moments per category — is an ideal tool to investigate BMS issues such as the importance of the number of moments. The first major test (Milbrandt and Yau 2006) simulated a supercell hailstorm; the modeled fields appeared realistic, but no in situ microphysical measurements were available, and subtleties of BMS behavior may be masked under the strong forcing of deep convection. It is therefore desirable to test the scheme on other weather systems with detailed in-cloud observations.

This paper is the first of a two-part study. Its main objectives are to further evaluate the new BMS by comparing simulated precipitation and microphysical fields with observations, and to identify potential deficiencies. It is shown that the MY05 scheme produces a reasonably accurate spatial distribution of precipitation (with systematic overprediction of quantities) and that there are distinct biases in the simulated hydrometeor fields. The paper also describes the control simulation used for the sensitivity studies in Part II (Milbrandt et al.), where the effects of the number of predicted moments are examined.

## 2. Model description and experimental setup

Simulations used the limited-area version of the **Global Environmental Multiscale (GEM) model** (fully compressible Euler equations; Mercator projection; one-way self-nesting; Côté et al. 1998), with a comprehensive physics package (Mailhot et al. 1998): a TKE-based PBL scheme (Benoit et al. 1989), implicit/explicit vertical/horizontal diffusion, a detailed land surface scheme (Bélair et al. 2003a,b), and interactive solar (Fouquart and Bonnel 1980) and infrared (Garand and Mailhot 1990) radiation.

The setup follows the Grabowski (2006) WMO workshop guidelines used by G05a,b (MM5 + Reisner-2), enabling direct scheme comparison. The 36-km simulation was initialized at 0000 UTC 13 December 2001 from the modified NCEP-AVN analysis (G05a), with 6-hourly lateral boundary conditions over the 36-h run, successively nested to **12-, 4-, and 1-km grids**, all with 49 vertical levels.

[Figure 1: Nested GEM model grids, with nesting times for each grid — image not reproducible in markdown]

[Figure 2: Model orography (shading) for (a) 4-km grid subdomain and (b) full 1-km grid; cross hairs depict model locations of rain gauges — image not reproducible in markdown]

In all runs, shallow convection used the Kuo-transient scheme (Bélair et al. 2005). Subgrid convection in the 36- and 12-km runs used Kain and Fritsch (1993); grid-scale clouds there used the Sundqvist et al. (1989) condensation scheme. The **4- and 1-km simulations used the triple-moment version of the MY05 scheme**.

The MY05 BMS has six hydrometeor categories: **liquid** — *cloud* (small, nonsedimenting droplets) and *rain* (sedimenting drops including drizzle); **frozen** — *ice* (pristine crystals), *snow* (large crystals and aggregates), *graupel* (medium-density rimed crystals), and *hail* (high-density graupel and frozen drops). Each size distribution is a three-parameter complete gamma function. The full triple-moment version predicts mass content, total number concentration, and radar reflectivity for each category (except cloud, for which reflectivity is not predicted). ~50 distinct microphysical processes are parameterized (MY05a,b). Only triple-moment control-run results are presented here; single- and double-moment results are in Part II.

Preliminary simulations produced spurious hail (>0.4 g m⁻³ at the surface) in weakly-forced regions, with mean-mass diameters ≤1 mm (better interpreted as ice pellets). The conditions for hail initiation were therefore made more stringent than in MY05b (see Appendix). A terminology convention is adopted: names referring to bulk-scheme *categories* are written in italics, while references to real particles are in non-italics.

## 3. Case overview and simulated large-scale features

### a. Description of the case

The 13–14 December 2001 storm was a large-scale baroclinic system with precipitation enhanced by orographic forcing from strong cross-barrier flow in the lower troposphere. By 0000 UTC 14 December the surface cyclone had moved inland. Between ~2200 UTC 13 December and 0200 UTC 14 December, heavy precipitation occurred as a broad rainband ahead of the cold front; the cross-barrier (southwesterly) flow at 1–2 km MSL was 30–40 m s⁻¹, producing localized upslope flow and significant cloud liquid water available for riming. A radar bright band was detected at ~1.5 km MSL throughout the heavy precipitation period.

### b. Synoptic-scale features

The simulated large-scale features were similar to satellite observations and the NCEP-AVN analyses. Simulated and observed cloud patterns (GOES IR vs simulated OLR) matched in location and areal extent. Near Oregon (upstream of the Cascades), the simulated 500-hPa geopotential height was within 1.2 dam, 850-hPa temperature ~1°C colder, and 850-hPa winds ~27–30 m s⁻¹. The two models (GEM and MM5) showed similar large-scale fields and difference fields, reassuring since both used the same initial/boundary conditions, so differences in microphysics could be isolated.

[Figure 3: Infrared images from GOES and OLR from the 12-km GEM simulation at three times — image not reproducible in markdown]

[Figure 4: Synoptic fields from the 12-km GEM simulation and modified NCEP-AVN analysis at 0000 UTC 14 Dec 2001 — image not reproducible in markdown]

### c. Soundings

Special University of Washington (UW) radiosonde soundings near Cresswell, Oregon, provided upstream measurements. Before heavy precipitation, upstream temperature and low-level humidity were well simulated (model too dry above 700 hPa). The strong southwesterly cross-barrier flow at 1–2 km was correctly simulated. During the stratiform period (0000 UTC), low-level model winds were too weak (~33 m s⁻¹ at 750 hPa vs observed 40 m s⁻¹), likely from a slight phase difference in front arrival. **Upper-level (above 750 hPa) moisture was overpredicted**, consistent with overpredicted snow mass; low-level moisture (the important orographic source) agreed well with observations.

[Figure 5: Map of the IMPROVE-2 study area with model orography (4-km grid) — image not reproducible in markdown]

[Figure 6: Soundings from 1-km simulation and UW radiosonde at 2100, 0000, and 0400 UTC 14 Dec 2001 — image not reproducible in markdown]

## 4. Comparison of mesoscale features

### a. Radar reflectivity pattern

Total equivalent radar reflectivity $Z_e$ at 700 hPa (sum over categories except cloud) was compared to NCAR S-Pol and Portland radar PPIs. The equivalent reflectivity of each category is

$$Z_{ex} = \frac{|K|_i^2}{|K|_w^2}\left(\frac{\rho_w}{\rho_i}\right)^2\left(\frac{c_x}{c_r}\right)^2 Z_x, \tag{1}$$

where $|K|_i^2/|K|_w^2 = 0.176/0.930 = 0.189$ (dielectric constant ratio, ice/water; Smith 1984); $(\rho_w/\rho_i)^2 = 1.189$; $c_r = (\pi/6)\rho_w$; $c_x$ is the mass–diameter coefficient (MY05b); and $Z_x$ (a prognostic variable in the triple-moment scheme) is the sixth moment of the size distribution.

In general, the high-resolution mesoscale features at the prefrontal (1800 UTC), stratiform (0000 UTC), and postfrontal (0400 UTC) stages were realistically simulated. The simulations captured the broad coastal echo region, the showers along the mountains (more pronounced in the 1-km run), the frontal rainband (reflectivity >30 dBZ, some patches >40 dBZ), and the narrow southwest-to-northeast postfrontal bands (reproduced particularly well at 1 km, including values >45 dBZ — though peak simulated values were too large).

[Figures 7–9: Reflectivity from NCAR S-Pol and Portland radars vs equivalent reflectivity at 700 hPa from the 4- and 1-km simulations at three times — images not reproducible in markdown]

### b. Vertical motion

Vertical velocity ($w$) is one of the most fundamental parameters driving a microphysics scheme. The strong cross-barrier flow set up a quasi-stationary mountain-wave pattern. The simulated $w$ along P-3 flight leg 2 was compared to in situ measurements and dual-Doppler retrievals (GSM) and to the 1.33-km MM5 simulation. Simulated peak values ranged +1.6 to −1.6 m s⁻¹ vs ~+3 to −3 m s⁻¹ from the P-3, but were very similar to G05a,b's 1.33-km MM5 values. The strong lee downdraft was well captured (~−3.5 m s⁻¹ simulated vs ~−3.0 m s⁻¹ observed). **The vertical motion in the 1-km GEM simulation was thus realistic, though somewhat lower than observed, and very close to the MM5 simulation** — meaning hydrometeor-field errors can be attributed in part to the BMS rather than the forcing.

[Figures 10–11: Vertical velocity from the 1-km simulation along cross sections / along leg 2 — images not reproducible in markdown]

### c. Precipitation

The 18-h (1400–0800 UTC) accumulated precipitation was compared with 145 rain gauges (4-km grid; 65 within 1-km grid). The 4-km run's spatial distribution compared favorably (high values >40 mm along the coast, lower in the Willamette valley, >50 mm on the windward Cascades, <20 mm in the east leeside), but with a **systematic overprediction of quantities**. The 1-km QPF was qualitatively and quantitatively similar.

Compared to G05a's MM5 runs, both models showed very similar overprediction biases and data spread. However, one notable difference: **the GEM/MY05 simulations did not suffer from the pronounced leeside overprediction that appeared in the MM5/Reisner-2 runs** (illustrated further in C05's Fig. 1 and GSM's Fig. 16). Since both models used the same initial/boundary conditions and produced similar forcing, the QPF differences are likely attributable primarily to the different microphysics schemes. (Part II shows that using a different BMS in GEM reproduces the MM5-like leeside overprediction.)

[Figures 12–14: Observed vs simulated 18-h accumulated precipitation for 4-km and 1-km runs, and scatterplots vs the 1.33-km MM5 run — images not reproducible in markdown]

### d. Hydrometeor fields

The simulated hydrometeor fields were compared to in situ aircraft measurements during the intense stratiform period (2300–0100 UTC), when the NOAA **P-3** (five north–south legs) and the UW **Convair-580** (southwest-to-northeast path) made continuous in-cloud measurements (imagery, size spectra, number concentrations; WSLH, G05b). Intrinsic comparison difficulties were noted (probe vs grid-box scale mismatch; spatial/temporal hydrometeor variability; small phase/magnitude errors in the forcing).

The mean-mass diameter for each category was computed as

$$D_x = \left(\frac{\rho q_x}{c_x N_{Tx}}\right)^{1/d_x}, \tag{2}$$

where $\rho$ is air density, $c_x$ and $d_x$ are mass–diameter parameters (MY05a), $q_x$ is mixing ratio, and $N_{Tx}$ is total number concentration ($q_x$ and $N_{Tx}$ explicitly predicted by the triple-moment scheme).

**1) Overview of observed and modeled fields.** The Convair-580 observed single ice crystals above 4.5 km MSL (sectors, side planes, hexagonal plates), dendrites between 3–4 km, columns and aggregates between 2–4 km. Pockets of cloud liquid water (CLW) were observed as high as 4 km on the windward slope, with graupel between 3–4 km (supported by NCAR polarimetric radar; Houze and Medina 2005). Below the melting layer (~2 km MSL) rain was observed all along the windward slope. The overall simulated spatial distribution of hydrometeor mass was fairly consistent with observations.

[Figures 15–17: In situ observed hydrometeor cross section (from G05b); simulated hydrometeor mass contents $Q_x$ and mean-mass diameters $D_x$ from the 1-km triple-moment simulation — images not reproducible in markdown]

**2) Cloud liquid water.** Observed CLW (P-3) vs simulated cloud mass $Q_c$ along five legs:

| Flight leg | Valley (Leg 1) | Windward (Leg 2) | Windward (Leg 3) | Windward (Leg 4) | Lee (Leg 5) |
|------------|------|------|------|------|------|
| Elev (m) [hPa] | 2000 (775) | 2500 (725) | 3450 (650) | 4000 (600) | 3100 (675) |
| Obs avg (peak) g m⁻³ | 0.14 (0.40) | 0.26 (0.50) | 0.20 (0.25) | 0.12 (0.15) | 0.04 (0.10) |
| Model 1-km avg (peak) | 0.22 (0.27) | 0.08 (0.34) | 0.00 (0.09) | 0.00 (0.00) | 0.01 (0.02) |

Low-level values were reasonable, but at higher elevations the model showed a strong **bias toward too-small $Q_c$**, underestimating the vertical extent of the windward cloud pockets — consistent with the simulated low-level vertical motion being too weak.

**3) Ice-particle mass.** Observed ice mass (Convair) vs simulated snow mass $Q_s$:

| Flight leg | Legs a,b | Legs c,d | Legs e,f | Legs g,h |
|------------|------|------|------|------|
| Elev (m) [hPa] | 6000 (450) | 5300 (500) | 4900 (525) | 4300 (625) |
| Obs avg g m⁻³ | 0.12 | 0.17 | 0.25 | 0.27 |
| Model 1-km avg (peak) | 0.85 (1.34) | 0.93 (1.33) | 1.15 (1.67) | 1.67 (1.94) |

There is a **distinct overprediction of snow mass at upper levels — by up to a factor of 7 for leg-average values** during the stratiform period. Overprediction at lower levels was also found (P-3 return-flight legs; Table 3 in original: observed 0.10–0.40 vs model 1.02–1.82 g m⁻³).

**4) Particle sizes.** Aircraft observations showed a clear trend of increasing snow sizes with decreasing altitude (decreasing distribution slopes / increasing mean diameters at lower levels). The simulated mean-mass snow diameter $D_s$ **reproduced this trend well** and gave realistic values (e.g., simulation ~0.8–2.7 mm across 6.0–2.0 km vs observed ~0.1–4 mm). Size sorting in the simulation also produced increasing mean ice diameters with decreasing altitude (observed for cirrus; Heymsfield and Iaquinta 2000). The mean-mass diameters of all categories (cloud $D_c$ 5–25 μm; rain $D_r$ 0.2–1.3 mm; ice $D_i$ 15–40 μm; graupel $D_g$ 0.3–2.7 mm) were realistic compared to literature observations for similar systems.

## 5. Discussion

The MY05 simulations exhibited an underprediction of the vertical extent of cloud-water pockets and an excessive snow mass concentration. While upstream soundings indicated correct low-level moisture and reasonable orographic forcing, the low-level vertical velocity was too weak (partly explaining the underpredicted cloud water), and upper-level moisture was overpredicted (consistent with excessive snow). Beyond these forcing shortcomings, the snow/cloud bias may also reflect deficiencies in the current MY05 configuration.

Previous studies show considerable sensitivity of snow growth and the resulting snow/graupel/cloud water and precipitation to the treatment of the snow category (Reisner et al. 1998; Colle and Zeng 2004; C05 — sensitivity to $N_{0s}$, fall-speed parameters, and the snow-to-graupel conversion threshold). Part II shows that modifying the snow size distribution and fall velocity parameters in MY05 can dramatically alter (improve) the snow-cloud bias via changes in depositional growth and snow residence time. However, the simultaneously occurring processes interact nonlinearly (C05 found no run dramatically improved precipitation, all suffering leeside overprediction). Notably, **the MY05 simulations did not exhibit the leeside overprediction problem**; the reasons are examined in Part II, which also shows that surface precipitation quantities are relatively insensitive to scheme-configuration changes that notably alter the snow/cloud-water fields aloft.

Field et al. (2005) showed that midlatitude stratiform snow size distributions can be accurately described using two moments, one estimable from a single temperature-based reference moment — implying a BMS may need only one prognostic snow moment (as applied in the temperature-dependent Thompson scheme). However, such single-moment parameterizations represent an average of many distributions and do not capture the distinct physics of different processes (diffusional growth vs aggregation; non-monotonic correlation of size-distribution parameters, Lo and Passarelli 1982).

Despite the snow overprediction, the realistic mean-mass diameters and the well-captured size-with-altitude trend are **not fortuitous**: they indicate the **mass-to-number ratio was treated realistically** by the BMS [Eq. (2)]. Because a multimoment scheme predicts mass and number independently, the mean-particle diameter evolves realistically for riming/deposition (mass increases, number constant), aggregation (number decreases, mass constant), and gravitational size sorting (requires at least two moments; MY05a). Nevertheless, the snow overprediction cannot be overlooked; the single-moment Field et al. (2005) approach may yet be appropriate for snow. Part II addresses the effect of the number of moments and the snow overprediction.

## 6. Conclusions

The 13–14 December 2001 IMPROVE-2 orographic precipitation case was simulated with a high-resolution mesoscale model using the **triple-moment MY05 BMS**, and compared with radar, rain gauge, and in situ aircraft measurements of microphysical fields and vertical motion. Large-scale features compared favorably to satellite imagery, NCEP-AVN analyses, and upstream soundings. The mountain-wave vertical velocity was correctly simulated (magnitudes slightly low). Although the forcing may have been slightly too weak, the hydrometeor-field errors — **too much snow mass and too little cloud mass** — can be attributed in part to the BMS.

This is the first test of the MY05 scheme against in situ microphysical measurements (it had previously been tested only for strong convection). Positive aspects were demonstrated (reasonable QPF for a complex orographic case), and certain deficiencies revealed. It appears that restrictions on the evolution of the snow size spectrum (allowable range of distribution prognostic parameters) and assumptions about crystal habit (affecting diffusional growth) may be needed to better model the ice-phase and cloud-water fields. The conspicuous difference in precipitation from the G05a,b (MM5/Reisner-2) simulations — particularly the absence of leeside overprediction in MY05 — is very likely linked to the different BMSs, though it is not obvious a priori whether QPF differences are due to the number of predicted moments or to other formulation differences. Part II examines the effects of changing the number of predicted moments and the snow overprediction bias.

---

## Appendix: Modified Hail-Forming Conditions

The following modifications were made to the MY05 scheme to suppress spurious hail initiation under conditions not conducive to real hail, while still allowing hail to form under strong forcing (strong vertical motion and/or large drops in cold conditions):

**a. Conversion from graupel to hail.** The mean-mass graupel diameter $D_g$ must exceed 2.5 mm and vertical air velocity must be > 3 m s⁻¹ upward (in single-moment: $Q_g$ must exceed 1.8 g m⁻³). If met, the minimum hail diameter for wet growth $D_{h0}$ (Shumann–Ludlam limit; MY05b Eq. 48) is computed; conversion occurs if $D_g/D_{h0} > 0.05$.

**b. Three-component freezing.** Collisional freezing of rain with ice, snow, or graupel to form hail can occur only if the mean-mass rain diameter exceeds 1 mm (double-/triple-moment) or rain mixing ratio exceeds 0.3 g kg⁻¹ (single-moment).

**c. Probabilistic freezing of rain.** Spontaneous freezing of rain to hail requires ambient air temperature colder than −10°C. (In single-moment, rain mixing ratio must exceed 0.1 g kg⁻¹.)

---

*Acknowledgments: The authors thank Dr. Mathew Garvert and Dr. Socorro Medina for observational data and two anonymous reviewers. Research funded by the Modelling of Clouds and Climate (MOC2) project through the Canadian Foundation for Climate and Atmospheric Sciences (CFCAS) and NSERC.*
