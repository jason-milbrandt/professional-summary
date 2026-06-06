# Milbrandt et al. (2021): A Triple-Moment Representation of Ice in the Predicted Particle Properties (P3) Microphysics Scheme

**Full citation:** Milbrandt, J. A., H. Morrison, D. T. Dawson II, and M. Paukert, 2021: A triple-moment representation of ice in the Predicted Particle Properties (P3) microphysics scheme. *J. Atmos. Sci.*, **78**, 439–458. DOI: 10.1175/JAS-D-20-0084.1

**Authors:** Jason A. Milbrandt (ECCC), Hugh Morrison (NCAR), Daniel T. Dawson II (Purdue University), Marco Paukert (PNNL)

**Journal:** Journal of the Atmospheric Sciences

**Volume/Pages:** 78, 439–458

**Published:** February 2021

**DOI:** 10.1175/JAS-D-20-0084.1

---

## Abstract

In the original Predicted Particle Properties (P3) bulk microphysics scheme, all ice-phase hydrometeors are represented by one or more "free" ice categories, where the physical properties evolve smoothly through changes to the four prognostic variables (per category), and with a two-moment representation of the particle size distribution. As such, the spectral dispersion cannot evolve independently, which thus results in limitations in representation of ice—in particular, hail—due to necessary constraints in the scheme to prevent excessive gravitational size sorting. To overcome this, P3 has been modified to include a three-moment representation of the size distribution of each ice category through the addition of a fifth prognostic variable, the sixth moment of the size distribution. The details of the three-moment ice parameterization in P3 are provided. The behavior of the modified scheme, with the single-ice-category configuration, is illustrated through simulations in a simple 1D kinematic model framework as well as with nearly large-eddy-resolving (250-m grid spacing) 3D simulations of a hail-producing supercell. It is shown that the three-moment ice configuration controls size sorting in a physically based way and leads to an improved capacity to simulate large, heavily rimed ice (hail), including mean and maximum sizes and reflectivity, and thus an overall improvement in the representation of ice-phase particles in the P3 scheme.

---

## 1. Introduction

Traditional bulk microphysics schemes (BMSs) have evolved from single-moment prescribed-category approaches toward multi-moment, fewer-category formulations that include more predictive information. The Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015, hereafter MM15; Milbrandt and Morrison 2016) represents all ice-phase hydrometeors using user-specified "free" frozen categories whose physical properties evolve smoothly.

Recent P3 developments prior to this work include: a three-moment rain category (Paukert et al. 2019), a prognostic liquid fraction for mixed-phase particles (Cholette et al. 2019), and a diagnostic subgrid-scale cloud scheme (Chosson et al. 2014).

**Limitation of two-moment ice in P3:** The shape parameter $\mu$ of the gamma PSD varies monotonically with the slope parameter $\lambda$ through the diagnostic relation:

$$\mu = 0.0019 \lambda^{0.822}$$

(following Heymsfield 2003, where $\lambda$ is in m$^{-1}$, constrained to $0 < \mu < 6$). This means $\mu$ cannot vary independently from mean size, which:

1. Prevents independent evolution of spectral dispersion
2. Requires imposing a stringent upper limit on the mass-weighted mean ice diameter ($D_{i,\text{limit}} = 2$ mm) to control size sorting
3. Leads to poor representation of hail (too-small sizes, incorrect dual-polarization signatures; Johnson et al. 2019)

The three-moment approach (originally developed in Milbrandt and Yau 2005a,b) allows $\mu$ to vary freely by predicting a third independent moment. This was shown to improve sedimentation treatment and overcome excessive size sorting.

---

## 2. Scheme Description

### 2a. Overview of the Original P3

Each ice category $n$ is described by four prognostic mixing ratio variables:
- $Q_{i\_tot}^{(n)}$: total ice mass mixing ratio
- $Q_{i\_rim}^{(n)}$: rime ice mass mixing ratio
- $N_{i\_tot}^{(n)}$: total ice number mixing ratio
- $B_{i\_rim}^{(n)}$: rime ice volume mixing ratio

The gamma PSD is:
$$N(D) = N_0 D^\mu e^{-\lambda D}$$

where $N_0$, $\lambda$, and $\mu$ are the intercept, slope, and shape parameters.

In the original P3, the look-up table has three dimensions (rather than four, following a reformulation):
- Normalized mass: $Q^* = Q_{i\_tot}/N_{i\_tot}$
- Rime mass fraction: $F_{rim} = Q_{i\_rim}/Q_{i\_tot}$
- Rime density: $\rho_{rim} = Q_{i\_rim}/B_{i\_rim}$

### 2b. The Three-Moment Ice Version

#### New Prognostic Variable

The sixth moment $M_6$ is added as the new prognostic variable. Any moment $M_x$ is defined by:
$$M_x = \int_0^\infty D^x N(D) \, dD$$

The choice of $M_6$ (related to the radar reflectivity factor) is motivated by its relationship to observable radar reflectivity and by the constraints of Morrison et al. (2016) on preserving bulk quantities during advection.

The third moment $M_3$ is not directly prognostic in P3 (because ice bulk properties depend on up to four size regimes with different $m$-$D$ parameters). Instead, $M_3$ is estimated from the bulk density:
$$\rho_i = \frac{Q_{i\_tot}}{M_3 \cdot \frac{\pi}{6}} \implies M_3 = \frac{6}{\pi \rho_i} Q_{i\_tot}$$

The zeroth moment is simply:
$$M_0 = N_{i\_tot}$$

The key equation relating $\mu$ to the prognostic moments is:
$$G(\mu) = \frac{(6+\mu)(5+\mu)(4+\mu)}{(3+\mu)(2+\mu)(1+\mu)} = \frac{M_0 M_6}{(M_3)^2}$$

where $M_6 \equiv Z_{i\_tot}$ is the new prognostic variable. Equations for $M_0$, $M_3$, and $M_6$ form a system from which $\mu$ can be solved numerically, replacing the diagnostic equation (2).

#### Advected Variable

Following Morrison et al. (2016), it is mathematically preferable to advect/diffuse the normalized quantity:
$$Z_{advect} = Z_{i\_tot} / Q_{i\_tot}$$

rather than $Z_{i\_tot}$ directly, in order to preserve $\mu$ and other PSD parameters during advection. This is consistent with the treatment of secondary variables in P3 (e.g., $F_{rim}$, $\rho_{rim}$).

#### Size Limiter

With triple-moment ice, the stringent upper limit $D_{i,\text{limit}} = 2$ mm on mean ice size is relaxed (removed), since $\mu$ now varies freely and controls size sorting in a physically based way.

#### Initial Conditions for New Ice

New ice initiated (via nucleation or freezing) is assigned an initial $\mu$ value ($\mu_{i\_init}$) from a prescribed relation, which determines the initial spectral width of newly formed ice.

---

## 3. 1D Kinematic Model Results

The three-moment ice scheme was first tested in a simple 1D kinematic cloud model to isolate sedimentation and size-sorting behavior. Key findings:

- **2-MOM**: Produces small mean ice sizes due to the $D_{i,\text{limit}} = 2$ mm constraint; reasonable but artificially constrained
- **2-MOM_DLIM** (two-moment, limiter relaxed): Without the size limiter but with the same diagnostic-$\mu$ relation, ice sizes grow unrealistically large due to uncontrolled size sorting; produces excessive reflectivity
- **3-MOM**: Controls size sorting through the freely varying $\mu$ — as mean size increases, $\mu$ increases (narrower PSD), reducing the number of large particles. Allows larger realistic mean sizes without unphysical runaway size sorting.

The three-moment scheme produces a physically consistent evolution of the PSD during sedimentation, with larger particles falling faster and the PSD width narrowing appropriately.

---

## 4. Idealized Supercell Simulations

### Setup

- Model: CM1 (Bryan and Fritsch 2002)
- Grid spacing: 250 m isotropic (nearly large-eddy-resolving)
- Case: Non-tornadic, hail-producing supercell (1 June 2008, Oklahoma)
- Single-ice-category P3 configuration ($n_\text{Cat} = 1$)
- Configurations compared:
  - **2-MOM**: Original two-moment ice with size limiter
  - **2-MOM_DLIM**: Two-moment, relaxed size limiter
  - **3-MOM**: Three-moment ice (new)
  - **2-MOM_DIAGMU**: Two-moment with new diagnostic-$\mu$ relation (sensitivity test)
  - **3-MOM_ADVZ**: Three-moment, advecting $Z_{i\_tot}$ instead of $Z_{advect}$ (sensitivity test)

### Key Results

**Size sorting control:**
- 2-MOM: Small mean ice sizes, artificially constrained, low reflectivity in convective core
- 2-MOM_DLIM: Unrealistically large mean ice sizes, excessive reflectivity (uncontrolled size sorting)
- 3-MOM: Intermediate — larger, more realistic mean ice sizes than 2-MOM, controlled by increasing $\mu$ at large sizes

**Hail simulation (reflectivity and sizes):**
- 3-MOM produces higher peak reflectivity values ($Z_H$, $Z_{DR}$) more consistent with observations of hail
- Diagnosed maximum hail size $D_{h,\text{max}}$ (using flux threshold method from Milbrandt and Yau 2006a) is largest and most physically reasonable in 3-MOM
- The $\mu$ field increases in the main updraft/hail growth region, consistent with riming-related narrowing of the PSD

**Ice physical properties in 3-MOM supercell at 55 min:**
- High bulk density ($\rho_i$) and rime fraction in convective core
- Large $D_m$ (mass-weighted mean diameter) in hail shaft
- $\mu$ increases with increasing $D_m$, confirming the physically based width control
- Lower-altitude sedimentation region shows appropriately narrowed PSD compared to 2-MOM

**1-km grid spacing comparison:**
- Simulations repeated at 1-km grid spacing show qualitatively similar relative differences between P3 configurations, confirming conclusions hold for NWP-relevant resolutions

### Sensitivity: Choice of Advected Variable

The 3-MOM_ADVZ simulation (advecting $Z_{i\_tot}$ directly) produces nonnegligible differences compared to 3-MOM (advecting $Z_{advect}$), including less ice mass at lower elevations under the anvil. Advecting $Z_{advect}$ is mathematically more consistent for preserving $\mu$ during transport and is recommended.

### Sensitivity: Improved Diagnostic-$\mu$ for Two-Moment

A new diagnostic relation was tested for the two-moment configuration:
$$\mu_i = 6\left(1 - \frac{D_m}{D_\text{thrs}}\right) - m, \quad \text{for } D_m < D_\text{thrs}$$
$$\mu_i = \max[1, 1 + 0.0842(\rho_i - 400)(D_m - D_\text{thrs})] \cdot 3 F_{rim}, \quad \text{for } D_m > D_\text{thrs}$$

where $D_\text{thrs} = 0.2$ mm and $\mu_i \leq 20$ is imposed. The 2-MOM_DIAGMU simulation is closer to 3-MOM than either 2-MOM or 2-MOM_DLIM, demonstrating that an improved diagnostic-$\mu$ could partially compensate. However, this was tested for only one storm type and would require broader validation.

---

## 5. Discussion

### Computational Cost

The addition of one prognostic variable per ice category increases computational cost marginally. For models using the scaled flux vector transport (SFVT) method (Morrison et al. 2016), the additional cost is minimal since secondary variables (including $Z_{i\_tot}$) are advected at marginal cost relative to the lead variable ($Q_{i\_tot}$).

### Preference for Three-Moment Over Improved Diagnostic-$\mu$

While an improved diagnostic-$\mu$ relation can partially mimic three-moment behavior, the three-moment approach is preferable because:
1. It is physically self-consistent
2. It does not require case-specific tuning of the $\mu$-$D$ relationship
3. $\mu$ evolves based on all microphysical processes, not just mean size and riming

### Future Work

- Triple-moment ice with multi-category configuration ($n_\text{Cat} > 1$)
- Merging with predicted liquid fraction (Cholette et al. 2019) and three-moment rain (Paukert et al. 2019)
- Examination of simulated polarimetric fields for detailed validation against dual-polarization radar observations
- Effects of particle property dilution in single-ice-category configuration at high resolution

---

## 6. Conclusions

- P3 has been modified to include an optional triple-moment ice representation through addition of a fifth prognostic variable: the sixth moment $Z_{i\_tot}$ of the ice PSD
- This allows $\mu$ to vary independently, overcoming the limitation of the original diagnostic-$\mu$ relation
- The size limiter ($D_{i,\text{limit}} = 2$ mm) can be removed because size sorting is now controlled physically
- In 1D and 3D (250-m supercell) tests, 3-MOM controls size sorting while allowing large, realistic mean sizes and improved hail representation
- Advecting $Z_{advect} = Z_{i\_tot}/Q_{i\_tot}$ rather than $Z_{i\_tot}$ directly is recommended for preserving PSD parameters during transport
- This modification is a significant advancement for hail simulation in P3

---

## Appendix: Diagnosing Maximum Hail Sizes from a Bulk Scheme

The maximum hail size $D_{h,\text{max}}$ is estimated from the flux of hail particles larger than a given threshold size $D^*$:
$$R(D^*) = \int_{D^*}^\infty V(D) N(D) \, dD$$

Following Milbrandt and Yau (2006a), a critical flux of $1.7 \times 10^{-4}$ m$^{-2}$ s$^{-1}$ is used to delineate between observable and non-observable hail. This is applied to ice with bulk density $> 750$ kg m$^{-3}$ and rime fraction $> 0.75$ (defined as hail).

---

## References (selected)

- Bryan, G. H., and H. Morrison, 2012: Sensitivity of a simulated squall line to horizontal resolution and parameterization of microphysics. *Mon. Wea. Rev.*, **140**, 202–225. https://doi.org/10.1175/MWR-D-11-00046.1
- Cholette, M., H. Morrison, J. A. Milbrandt, and J. M. Theriault, 2019: Parameterization of the bulk liquid fraction on mixed-phase particles in the predicted particle properties (P3) scheme. *J. Atmos. Sci.*, **76**, 561–582. https://doi.org/10.1175/JAS-D-18-0278.1
- Dawson, D. T., II, E. R. Mansell, Y. Jung, L. J. Wicker, M. R. Kumjian, and M. Xue, 2014: Low-level $Z_{DR}$ signatures in supercell forward flanks. *J. Atmos. Sci.*, **71**, 276–299. https://doi.org/10.1175/JAS-D-13-0118.1
- Johnson, M., Y. Sun, J. A. Milbrandt, H. Morrison, and M. Xue, 2019: Effects of the representation of rimed ice in bulk microphysics schemes on polarimetric signatures. *Mon. Wea. Rev.*, **147**, 3785–3810. https://doi.org/10.1175/MWR-D-18-0398.1
- Milbrandt, J. A., and M. K. Yau, 2005a: A multimoment bulk microphysics parameterization. Part I. *J. Atmos. Sci.*, **62**, 3051–3064.
- Milbrandt, J. A., and M. K. Yau, 2005b: A multimoment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, **62**, 3065–3081.
- Milbrandt, J. A., and M. K. Yau, 2006a: A multimoment bulk microphysics parameterization. Part III. *J. Atmos. Sci.*, **63**, 3114–3136.
- Milbrandt, J. A., and M. K. Yau, 2006b: A multimoment bulk microphysics parameterization. Part IV. *J. Atmos. Sci.*, **63**, 3137–3159.
- Milbrandt, J. A., and R. McTaggart-Cowan, 2010: Sedimentation error in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.
- Milbrandt, J. A., and H. Morrison, 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III. *J. Atmos. Sci.*, **73**, 975–995.
- Morrison, H., A. J. Jensen, J. Y. Harrington, and J. A. Milbrandt, 2016: Advection of coupled hydrometeor quantities in bulk cloud microphysics schemes. *Mon. Wea. Rev.*, **144**, 2809–2829.
- Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Paukert, M., J. Fan, P. J. Rasch, H. Morrison, J. A. Milbrandt, J. Shpund, and A. Khain, 2019: Three-moment representation of rain in a bulk microphysics model. *J. Adv. Model. Earth Syst.*, **11**, 257–277.

[Figure X: Various figures showing PSD illustrations, 1D kinematic model results, 3D supercell fields including $Q_{i\_tot}$, $\mu_i$, $\rho_i$, $D_m$, $D_{h,\text{max}}$, $Z_e$ — images not reproducible in markdown]
