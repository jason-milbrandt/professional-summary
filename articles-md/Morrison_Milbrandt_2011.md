# Comparison of Two-Moment Bulk Microphysics Schemes in Idealized Supercell Thunderstorm Simulations

**Authors:** Hugh Morrison (National Center for Atmospheric Research, Boulder, Colorado); Jason Milbrandt (Numerical Weather Prediction Research Section, Meteorological Research Division, Environment Canada, Dorval, Quebec, Canada)

**Journal:** *Monthly Weather Review*, **139**, 1103–1130 (April 2011)

**Manuscript:** received 26 March 2010, in final form 10 November 2010

**DOI:** 10.1175/2010MWR3433.1

---

## Abstract

Idealized three-dimensional supercell simulations were performed using the two-moment bulk microphysics schemes of Morrison (MOR) and Milbrandt–Yau (MY) in the Weather Research and Forecasting (WRF) model. Despite general similarities in these schemes, the simulations were found to produce distinct differences in storm structure, precipitation, and cold pool strength. In particular, the Morrison scheme produced much higher surface precipitation rates and a stronger cold pool, especially in the early stages of storm development. A series of sensitivity experiments was conducted to identify the primary differences between the two schemes that resulted in the large discrepancies in the simulations.

Different approaches in treating graupel and hail were found to be responsible for many of the key differences between the baseline simulations. The inclusion of hail in the baseline simulation using the Milbrandt–Yau scheme with two rimed-ice categories (graupel and hail) had little impact, and therefore resulted in a much different storm than the baseline run with the single-category (hail) Morrison scheme. With graupel as the choice of the single rimed-ice category, the simulated storms had considerably more frozen condensate in the anvil region, a weaker cold pool, and reduced surface precipitation compared to the runs with only hail, whose higher terminal fall velocity inhibited lofting. The cold pool strength was also found to be sensitive to the parameterization of raindrop breakup, particularly for the Morrison scheme, because of the effects on the drop size distributions and the corresponding evaporative cooling rates. The use of a more aggressive implicit treatment of drop breakup in the baseline Morrison scheme, by limiting the mean-mass raindrop diameter to a maximum of 0.9 mm, opposed the tendency of this scheme to otherwise produce large mean drop sizes and a weaker cold pool compared to the hail-only run using the Milbrandt–Yau scheme.

---

## 1. Introduction

The parameterization of cloud and precipitation microphysics is a major challenge in the numerical simulation of moist deep convection. Microphysical processes directly impact buoyancy and hence convective fluxes through condensate loading and latent heating/cooling. Regional-scale NWP models are now commonly run at deep-convective scale (~1-km horizontal grid spacing). Two-moment bulk microphysics schemes (BMSs) have become increasingly common for organized deep convection simulation (e.g., MY06; MTT09; Luo et al. 2010; Dawson et al. 2010).

Despite improvements relative to one-moment schemes, considerable sensitivity to specific aspects of two-moment schemes remains. The appropriate number and type of ice-phase categories is unclear. The evaporation of rain strongly controls cold pool strength and storm dynamics, and is sensitive to both the PSD of rain (controlled partly by drop breakup parameterization) and the mean size of hail/graupel (which affects how melting produces rain drops). While two-moment schemes add flexibility to represent PSD evolution, parameter settings remain uncertain.

This study seeks to: (1) compare the behavior of the baseline MOR and MY scheme configurations for an idealized supercell; and (2) examine, through sensitivity tests, the primary reasons for the discrepancies, focusing on graupel/hail treatment and raindrop breakup.

## 2. Model description

All simulations used ARW-WRF version 3.1 (Skamarock et al. 2007), a compressible, nonhydrostatic, 3D mesoscale model using a time-split integration with third-order Runge–Kutta. Horizontal/vertical turbulent diffusion used a 1.5-order TKE scheme. Advection used fifth- and third-order discretization (horizontal/vertical) with a positive-definite limiter. Surface fluxes were zero; no radiative transfer.

**List of main simulations (Table 1):**

| Simulation | Description |
|---|---|
| MOR-BASE | Baseline run (MOR) |
| MOR-GRPL | MOR with single rimed-ice category set to medium-density graupel parameters |
| MOR-BASE-V | Same as MOR-BASE except with MY V–D parameters for rain and hail |
| MOR-GRPL-V | Same as MOR-GRPL except with MY V–D parameters for rain |
| MOR-HV | MOR-BASE with bulk density of hail set to that of graupel |
| MOR-GV | MOR-GRPL with bulk density of graupel set to that of hail |
| MOR-BRK_Z | Same as MOR-BASE-V except Z85 breakup parameterization |
| MOR-BRK_VC | Same as MOR-BASE-V except VC93 breakup |
| MOR-BRK_S | Same as MOR-BASE-V except S08 breakup |
| MOR-DMR5 | Same as MOR-BASE-V except $D_{mr\_max} = 5$ mm |
| MY-BASE | Baseline run (MY) |
| MY-GRPL | Graupel only (hail category shut off) |
| MY-HAIL | Hail only (graupel category shut off) |
| MY-DMR5 | Same as MY-HAIL except Ziegler (1985) rain drop breakup turned off |
| MY-DMR0.9 | Same as MY-DMR5 except $D_{mr\_max} = 0.9$ mm |
| MY-BRK_VC | Same as MY-HAIL except VC93 breakup |
| MY-BRK_S | Same as MY-HAIL except S08 breakup |

## 3. Experimental design

An idealized supercell is simulated with open lateral boundary conditions. The domain is 200×200 km² horizontally, with a 1-km horizontal and ~500-m vertical grid spacing, model lid at 20 km, 6-s primary time step. The Weisman and Klemp (1982, 1984) analytic sounding is used; melting level at ~4 km. The Weisman and Rotunno (2000) quarter-circle supercell hodograph is used (shear extended to 7 km; length 40 m s⁻¹). Convection triggered by a 3-K thermal perturbation (10-km horizontal radius, 1.5-km vertical radius, centered at 1.5 km). All simulations integrated for 2 h.

## 4. Baseline simulations

### a. Storm structure and radar reflectivity

Both simulations produced supercell storm splitting around $t = 30$ min. First ~30 min dominated by sounding and forcing. After this, MOR and MY begin diverging. By $t = 60$ min:
- MOR-BASE: stronger low-level convergence and upward motion under midlevel updrafts, between splitting cells; stronger low-level downward motion.
- MY-BASE: stronger forward-flank downdraft; low-level convergence along its edge produces secondary convective cells; more extensive forward-flank $Z$ at distances >30–40 km from primary cells.

By $t = 120$ min, cells are ~70 km apart in MOR-BASE vs ~55 km in MY-BASE; MOR-BASE has a secondary convection line between primary cells; MY-BASE has stronger forward-flank downdraft and associated secondary cells.

$Z$ magnitudes through most of the storm depth are larger in MOR-BASE (more hail and rain), though peak values are larger in MY-BASE. MY-BASE has a long, narrow forward-flank reflectivity band. More distinct BWER and more extensive cold pool downshear in MOR-BASE.

### b. Cold pool and dynamics

After $t = 35$ min, MOR-BASE has a much colder and more extensive cold pool than MY-BASE (Table 2). Minimum $\theta'$ difference exceeds 3 K at $t = 60$ min. MY-BASE colder in the forward-flank region later in the simulation. $u_e$ differences suggest cold pool air descends from higher altitude in MOR-BASE.

**Diabatic cooling** (Table 3): Evaporative cooling rates dominate over melting in both simulations. Column-integrated melting rates are larger in MOR-BASE at $t = 60$ min. MOR-BASE has much larger evaporation rates at $t = 60$ min; by $t = 120$ min MY-BASE has 39% larger column-integrated evaporative cooling. Consistent with the greater depth of melting layer in MOR-BASE (fast-falling hail delivers frozen mass to the melting layer faster).

MY-BASE has larger domain-averaged updraft and downdraft mass fluxes above ~2.5 km. MOR-BASE has slightly larger vertical mass fluxes below 2.5 km and stronger peak downdrafts.

**Selected summary statistics (Table 2):**

| Simulation | Precip at 60 min (mm) | Min $\theta'$ at 60 min (K) | Precip at 120 min (mm) | Min $\theta'$ at 120 min (K) |
|---|---|---|---|---|
| MOR-BASE | 0.14 | −7.60 | 1.28 | −11.32 |
| MOR-GRPL | 0.04 | −3.78 | 0.46 | −6.70 |
| MY-BASE | 0.04 | −4.35 | 0.41 | −9.03 |
| MY-GRPL | 0.04 | −4.57 | 0.48 | −9.84 |
| MY-HAIL | 0.10 | −7.38 | 1.01 | −10.26 |
| MY-DMR0.9 | 0.07 | −9.11 | 0.89 | −11.40 |

### c. Surface precipitation and microphysics

Domain-averaged precipitation is ~3× larger in MOR-BASE at both $t = 60$ and $t = 120$ min. Larger rain mixing ratios near surface in MOR-BASE (larger frozen condensate flux into melting layer). Mean-mass rain diameter $D_{mr}$ is generally smaller in MOR-BASE, contributing to greater evaporation rates. Differences in $D_{mr}$ primarily due to different raindrop breakup and drop size limiter settings (section 5). MY-BASE has much larger graupel/hail mixing ratios above the freezing level (slower fallout of slower-falling graupel).

## 5. Sensitivity tests

### a. Sensitivity to graupel/hail partitioning

**Graupel vs hail choice is a major control.** MOR-GRPL and MY-GRPL are similar to each other; MY-HAIL and MOR-BASE are similar to each other. The inclusion of hail in the baseline MY scheme had little impact (graupel dominated, hail mixing ratios were <0.1% of graupel above the freezing level). This is due to uncertainties in hail particle initiation.

- Graupel-only runs: much more frozen condensate in the anvil (slower fallout), weaker melting-layer flux, weaker cold pool, reduced surface precipitation.
- Hail-only runs: faster fallout, more condensate delivered to melting layer, stronger cold pool, greater surface precipitation.

The choice of V–D relation is more important than bulk density in driving the graupel/hail difference (MOR-HV and MOR-GV tests), though density has a nonnegligible impact.

**Key V–D and m–D parameter differences (Table 4):**

| Parameter | MOR | MY |
|---|---|---|
| $a_r$ (V–D coeff for rain) | 842.0 | 149.1 |
| $b_r$ (V–D exponent for rain) | 0.8 | 0.5 |
| $a_h$ (V–D coeff for hail) | 114.5 | 206.89 |
| $b_h$ (V–D exponent for hail) | 0.5 | 0.6384 |
| $d_s$ (m–D exponent for snow) | 3 | 2 |
| $D_{mr\_max}$ | 0.0009 m | 0.005 m |

### b. Sensitivity to raindrop breakup

Five sets of experiments examined the drop size limiter ($D_{mr\_max}$) and explicit breakup parameterizations. Key results:

- **MOR-BASE**: no explicit breakup; $D_{mr\_max} = 0.9$ mm. This aggressive limiter is key to MOR-BASE's relatively strong cold pool.
- **MY-HAIL** (baseline for these tests): Ziegler (1985, Z85) breakup with $D_{mr\_max} = 5$ mm.
- MOR-DMR5 (limiter raised to 5 mm): 6.4 K warmer minimum $\theta'$ than MY-DMR5 at $t = 120$ min, showing that other processes in MOR produce larger rain drops (larger mean hail size at the melting level → larger drop size after melting → lower evaporation).
- With S08 (most aggressive breakup) or $D_{mr\_max} = 0.9$ mm, cold pool differences between MOR and MY are minimized.
- Drop breakup has little impact on surface precipitation for either scheme.

**Contributing factors to warmer cold pool in MOR (without aggressive breakup):**
1. Larger mean hail size near the melting level in MOR-DMR5 → larger mean rain drop after melting → reduced evaporation.
2. Less autoconversion in MOR (less widespread cloud water) → fewer small rain drops → larger mean drop.

## 6. Summary and conclusions

Despite overall similar two-moment approaches, MOR-BASE and MY-BASE produced distinctly different supercell simulations, primarily because:

1. **MOR-BASE uses a single hail category; MY-BASE has graupel as the dominant rimed-ice category** (hail in MY-BASE had negligible contribution). Graupel is slower-falling, producing more anvil condensate, weaker cold pool, and less surface precipitation than hail.
2. **Raindrop breakup parameterization** strongly affected the cold pool in MOR (where other processes tend to produce large drops), but had less impact on MY (which inherently produces smaller drops from other processes).
3. **The aggressive $D_{mr\_max} = 0.9$ mm in MOR-BASE** compensates for MOR's tendency to produce larger drops, bringing its cold pool closer to that of MY-HAIL.

**Broader implications:** The large differences between two-moment schemes that are otherwise similar highlight the inherent uncertainties in multimoment parameterizations. As modelers move away from one-moment schemes, they must be cognizant that adding degrees of freedom does not guarantee convergence among schemes. Observational studies of PSDs and ice particle properties are critically needed to constrain parameter settings.

---

## Appendix: Description of the Microphysics Schemes

### a. MOR microphysics scheme

Based on Morrison et al. (2005), subsequently implemented in MM5 and WRF. Predicts $q_x$ and $N_x$ for cloud, ice, snow, rain, and graupel/hail (five categories, with the rimed-ice category using either graupel or hail parameters). All categories have $m_x = 0$ (inverse-exponential PSDs), except cloud where $m_c$ varies from 2–10 based on $N_c$. Sedimentation uses first-order Eulerian scheme. Rimed ice is a single category: baseline uses hail parameters ($\rho_h = 900$ kg m⁻³).

Key process parameterizations: autoconversion via Khairoutdinov and Kogan (2000) with $N_c = 250$ cm⁻³; melting assumes $D_m$ constant, number concentration conserved (number of rain drops = number of melted ice-phase particles); drop size limiter $D_{mr\_max} = 0.9$ mm; shedding produces rain with $D_{mr} = 1$ mm. No explicit breakup parameterization in baseline (implicit via drop size limiter).

### b. MY microphysics scheme

Based on Milbrandt and Yau (2005a,b). Six categories: cloud, ice, snow, rain, graupel, hail (see MY05a,b for details). The two-moment fixed-$m_x$ version (DIAG_B in MY06b) was used with $m_x = 0$ for rain, ice, snow, graupel, hail. Sedimentation uses a diagnostic $\alpha$ relation. The snow m–D exponent is $d_s = 2$ (non-spherical, non-constant density), vs $d_s = 3$ in MOR. The drop size limiter is $D_{mr\_max} = 5$ mm; baseline uses Z85 breakup. Melting conserves total number concentration.

---

*Acknowledgments: This work was supported by the NOAA Grant NA08OAR4310543, U.S. DOE ARM DE-FG02-08ER64574, and the NSF Science and Technology Center for Multiscale Modeling of Atmospheric Processes (CMMAP), managed by Colorado State University.*
