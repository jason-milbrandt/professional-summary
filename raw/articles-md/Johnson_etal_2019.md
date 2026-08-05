# Effects of the Representation of Rimed Ice in Bulk Microphysics Schemes on Polarimetric Signatures

**Full citation:** Johnson, M., Y. Jung, J. A. Milbrandt, H. Morrison, and M. Xue, 2019: Effects of the Representation of Rimed Ice in Bulk Microphysics Schemes on Polarimetric Signatures. *Mon. Wea. Rev.*, **147**, 3785–3809. DOI: 10.1175/MWR-D-18-0398.1

---

## Abstract

Many flavors of multicategory, multimoment bulk microphysics schemes (BMPs) have various treatments of rimed ice. This study compares three two-moment schemes available in the WRF Model — Milbrandt–Yau (MY2), National Severe Storms Laboratory (NSSL), and the two-category configuration of the Predicted Particle Properties (P3) scheme — focusing on differences in rimed-ice representation and their impacts on surface rain and ice. Idealized supercell simulations are performed. A polarimetric radar data simulator is used to evaluate their ability to reproduce the $Z_{DR}$ arc and hail signature in the forward-flank downdraft, well-known supercell polarimetric signatures that are potentially sensitive to rimed-ice parameterization.

Both MY2 and NSSL simulate enhanced surface $Z_{DR}$ bands, but neither simulates a $Z_{DR}$ arc fully consistent with observations. Surface $Z_{DR}$ in the default P3 scheme is homogeneous in the supercell's forward flank, due to the scheme's restrictive minimum rain PSD slope bound ($\Lambda_{r,min}$) preventing the presence of larger drops creating a $Z_{DR}$ arc. The NSSL scheme simulates the location of the hail signature in the forward-flank downdraft more consistently with observations than the other two schemes. Large hail in MY2 sediments well downstream of the updraft (atypically compared to observations) near the surface. The sedimentation of large ice in the default P3 scheme is limited by a restrictive maximum ice number-weighted mean diameter limit ($D_{ni}$), precluding the scheme's ability to reduce $Z_{DR}$ (and $\rho_{HV}$) near the surface.

---

## 1. Introduction

Cloud microphysics processes — from cloud particle formation to precipitation — are complex and highly nonlinear. While liquid-phase drops are well-represented as constant-density spheres, ice processes lack adequate observations and theoretical understanding of their highly variable shape and density evolution.

Bulk microphysics schemes (BMPs) assume analytic (typically gamma) particle size distributions (PSDs) and predict moments thereof. Two-moment schemes predict both mass mixing ratio ($q_x$) and number mixing ratio ($N_x$). Spectral bin microphysics (SBMs) offer greater PSD flexibility but have significant computational cost.

Key prior work motivating this study:
- Morrison and Milbrandt (2011): Weaker cold pools and less surface precipitation using two-moment graupel-like vs. hail-like rimed ice in supercells
- Milbrandt and Morrison (2013): Predicted rimed-ice particle volume (and density) in MY2 and NSSL
- Morrison and Milbrandt (2015): Proposed the P3 "free category" approach to ice-phase hydrometeors — no fixed predefined ice categories
- Dawson et al. (2014): Size sorting of rimed ice (not just rain) drives the $Z_{DR}$ arc in simulated supercells
- Multiple studies showing polarimetric variables are effective diagnostics for evaluating BMP accuracy

---

## 2. Data and Methods

### 2.1 WRF Simulations

Idealized supercell simulations using WRF v3.9.1. Three BMPs evaluated:
- **MY2**: Milbrandt–Yau two-moment scheme — separate graupel and hail categories with predicted density
- **NSSL**: National Severe Storms Laboratory two-moment scheme — includes graupel-to-hail conversion and $N_t$ modification to prevent spuriously large reflectivity
- **P3–2**: Two-category configuration of the P3 "free ice" scheme — two "free" (not predefined) ice categories

The two ice categories in P3–2 should not be directly equated to graupel/hail in MY2 and NSSL; both P3–2 categories can represent any type of frozen particle.

### 2.2 Polarimetric Radar Simulator

Simulated polarimetric variables (horizontal reflectivity $Z_H$, differential reflectivity $Z_{DR}$, cross-correlation coefficient $\rho_{HV}$) are computed using a forward operator applied to the model output, allowing direct comparison with observed polarimetric signatures.

### 2.3 Evaluation Framework

Evaluation focuses on two well-known supercell polarimetric signatures:
1. **$Z_{DR}$ arc**: Low-level maximum of $Z_{DR}$ on the storm's southern flank, caused by size sorting of rain and rimed ice
2. **Hail signature**: Low $Z_{DR}$ / low $\rho_{HV}$ in the forward-flank downdraft, caused by resonance-sized hailstones

---

## 3. Results

### 3.1 $Z_{DR}$ Arc

- **MY2**: Simulates a weak $Z_{DR}$ gradient in the forward flank; rain (not rimed ice) dominates forward-flank reflectivity. Large hail sediments downstream of the updraft due to lower fall speeds than NSSL hail. The forward-flank $Z_{DR}$ is enhanced but the arc is displaced east of the updraft and not fully consistent with observations.
- **NSSL**: Also simulates enhanced surface $Z_{DR}$ bands. NSSL modifies $N_t$ to prevent spuriously large reflectivity (compared to MY2's excessive rimed-ice size sorting). The $Z_{DR}$ arc location is somewhat better than MY2.
- **P3–2 (default)**: Surface $Z_{DR}$ is nearly homogeneous in the forward flank. The restrictive $\Lambda_{r,min}$ prevents large raindrops on the southern flank, eliminating the drop-size gradient needed for a $Z_{DR}$ arc. Rain size sorting is absent, despite having two-moment rain and two free ice categories.
- **P3–2 with relaxed $\Lambda_{r,min}$ (×0.2)**: A larger rain drop size gradient develops near the southern flank, but the $Z_{DR}$ arc extends too far east of the updraft and does not preferentially decrease in the direction of the deep-layer storm-relative mean wind vector as observed.

### 3.2 Hail Signature

- **MY2**: Produces large hail that reaches the surface, but generally on the southern flank rather than in the forward-flank downdraft (inconsistent with observations). MY2 hail has a smaller horizontally averaged mass-weighted mean fall speed than NSSL hail; MY2 graupel also has atypically small fall speeds, enhancing downstream advection.
- **NSSL**: Best simulates the location of the hail signature in the forward-flank downdraft consistent with observations. Large, wet hail (mixing ratio $\geq 0.5$ g kg$^{-1}$, mass-weighted mean diameter $D_{mh} \geq 14$ mm) dominates the reflectivity core.
- **P3–2 (default)**: Ice generally does not reach the surface due to the restrictive maximum $D_{ni}$ = 2 mm limiter. The small, wet particles that do reach the surface increase $Z_{DR}$. Relaxing this limit (tested with $D_{ni}$ = 7 and 12 mm) allows larger rimed ice to sediment to the surface but produces an unphysically large forward-flank hail zone.

### 3.3 Microphysical Budgets and CFADs

Contoured frequency by altitude diagrams (CFADs) of rain and ice mass-weighted mean diameter confirm:
- MY2 shows excessive rimed-ice size sorting (larger $D_m$ increase with decreasing height than NSSL)
- NSSL's $N_t$ modification limits rimed-ice size sorting
- P3–2 rain melted from ice falls into a very narrow $D_{mr}$ range (3.0–3.25 mm), with near-constant mean size with height — confirming the inability to produce a $Z_{DR}$ arc
- P3–2 ice categories show a broader range of mean sizes than MY2 graupel/hail, but with relatively slow fall speeds

---

## 4. Summary and Discussion

Main findings:
1. All three schemes fail to fully reproduce observed $Z_{DR}$ arc morphology
2. MY2 and NSSL produce enhanced surface $Z_{DR}$ bands consistent with size sorting, though the arc orientation is not fully observed-consistent in either scheme
3. P3–2's restrictive $\Lambda_{r,min}$ prevents the $Z_{DR}$ arc; relaxing it improves the gradient but introduces other inconsistencies
4. Only NSSL correctly simulates the hail signature location in the forward-flank downdraft
5. MY2's large hail sediments downstream of the updraft (inconsistent with observations), due to lower fall speeds
6. P3–2's maximum $D_{ni}$ limiter prevents large ice from reaching the surface

### Suggested Improvements
- MY2: Increase rimed-ice fall speeds; simulate larger graupel particles
- P3: Further investigation of $\Lambda_{r,min}$ and maximum $D_{ni}$ limits; other size-sorting mechanisms may also require examination

[Figure captions: Figures 1–16 show polarimetric signatures near the surface, mixing ratio and mean diameter fields, CFADs, and sensitivity tests for the three BMPs. Figures include $Z_H$, $Z_{DR}$, $\rho_{HV}$, $q_r$, $D_{mr}$, $q_g$, $D_{mg}$, $f_{wg}$, $q_h$, $D_{mh}$, $q_i$, $D_{mi}$ fields, and time series of mean maximum ice category diameters.]

---

*Corresponding author: Youngsun Jung, youngsun.jung@ou.edu*
*Manuscript received 16 November 2018, in final form 24 July 2019*
