# Parameterization of Cloud Microphysics Based on the Prediction of Bulk Ice Particle Properties. Part III: Introduction of Multiple Free Categories

**Authors:** J. A. Milbrandt and H. Morrison
**Journal:** Journal of the Atmospheric Sciences
**Volume:** 73, pp. 975–995
**Year:** 2016 (March)
**DOI:** 10.1175/JAS-D-15-0204.1
**Received:** 17 July 2015; in final form 16 November 2015

---

## Abstract

The predicted particle properties (P3) scheme introduced in Part I of this series represents all ice hydrometeors using a single "free" category, in which the bulk properties evolve smoothly through changes in the prognostic variables, allowing for the representation of any type of ice particle. In this study, P3 has been expanded to include multiple free ice-phase categories allowing particle populations with different sets of bulk properties to coexist, thereby reducing the detrimental effects of property dilution. The modified version of P3 is the first scheme to parameterize ice-phase microphysics using multiple free categories.

The multicategory P3 scheme is described and its overall behavior is illustrated. It is shown using an idealized 1D kinematic model that the overall simulation of total ice mass, reflectivity, and surface precipitation converges with additional categories. The correct treatment of the rime splintering process, which promotes multiple ice modes, is shown to require at least two categories in order to be included without introducing problems associated with property dilution. Squall-line simulations using a 3D dynamical model with one, two, and three ice categories produce reasonable reflectivity structures and precipitation rates compared to radar observations. In the multicategory simulations, ice hydrometeors from different categories and with different bulk properties are shown to coexist at the same points, with effects on reflectivity structure and precipitation. The new scheme thus appears to work reasonably in a full 3D model and is ready to be tested more widely for research and operational applications.

---

## 1. Introduction

The representation of ice-phase processes in bulk microphysics schemes (BMSs) has advanced considerably over the past 10–20 yr. While in early schemes ice was represented by one or two predefined categories with prescribed bulk physical properties and a single prognostic variable for each (e.g., Rutledge and Hobbs 1983; Lin et al. 1983), many current BMSs now include several ice-phase categories and up to three prognostic moments each (e.g., Straka and Mansell 2005; Milbrandt and Yau 2005a,b; Seifert and Beheng 2006; Thompson et al. 2008; Morrison et al. 2009; Mansell et al. 2010; Loftus et al. 2014).

In the past decade there has been a paradigm shift away from the continued addition of predefined categories and toward providing more predictive information of the particle properties (Hashino and Tripoli 2007; Grabowski and Morrison 2008; Mansell et al. 2010; Milbrandt and Morrison 2013; Harrington et al. 2013).

In Morrison and Milbrandt (2015, Part I) the predicted particle properties (P3) scheme was proposed, employing a fundamentally different approach whereby all types of ice-phase hydrometeors are represented by a single "free" ice category where bulk properties evolve smoothly. It was demonstrated in Part I and Part II (Morrison et al. 2015) that the single-category P3 scheme is competitive in simulation quality and computational efficiency against state-of-the-art BMSs. P3 was included in a real-time 4-km WRF ensemble forecast system during the spring 2014 HWT Spring Forecasting Experiment; forecasts with P3 were on par with other schemes despite being the first time P3 was tested in real-time mode.

However, the single-category P3 has the inherent limitation that it cannot represent more than one population of ice particles with different bulk properties at the same point in time and space. In nature, two or more modes of ice particles can coexist due to gravitational size sorting, particle recycling, or in situ ice initiation (e.g., rime splintering, drop freezing) in the presence of existing ice. Mixing two populations into a single category with a single set of bulk properties results in a smoothing—"dilution"—of individual population properties. This dilution can be detrimental: for example, nucleation of tiny new crystals into a category containing large graupel causes the mean size and fall speed to decrease significantly, altering subsequent evolution of the rimed ice.

To address this, P3 has been expanded to allow multiple free ice-phase categories. This is the first time this approach to model ice-phase microphysics has been attempted.

---

## 2. Description of the Multicategory Scheme

### a. Summary of One-Category Version

In the original scheme, all ice-phase hydrometeors are represented by a single free category with four prognostic variables: $Q_{i\_tot}$, $Q_{i\_rim}$, $N_{i\_tot}$, and $B_{i\_rim}$. The two mass mixing ratios allow independent prediction of deposition mass and rime mass. $B_{i\_rim}$ as a prognostic variable allows prediction of rime density ($\rho_{rim} = Q_{i\_rim}/B_{i\_rim}$). At each time step, size distribution parameters and mass-size, area-size, and fall speed–size parameters are computed for various size intervals.

**Table 1. List of symbols.**

| Symbol | Description | Units |
|--------|-------------|-------|
| $\rho_{rim}$ | Rime density | kg m$^{-3}$ |
| $B_{i\_rim}(n)$ | Rime volume mixing ratio for ice category $n$ | m$^3$ kg$^{-1}$ |
| $D_i(n)$ | Mean-mass diameter for ice category $n$ | m |
| $D_{new}$ | Diameter of new ice | m |
| $E_{j,k}$ | Collection efficiency among ice categories | — |
| $F_{rim}(n)$ | Rime mass fraction for ice category $n$ | — |
| $n$ | Ice category index | — |
| $n_{Dest}$ | Ice category index for new ice | — |
| $n_{Cat}$ | Number of ice categories | — |
| $N_{i\_tot}(n)$ | Total number mixing ratio for ice category $n$ | kg$^{-1}$ |
| $N_{i\_total}$ | Total number mixing ratio for all categories | kg$^{-1}$ |
| $\Delta D_{init}$ | Diameter difference threshold for ice initiation | m |
| $Q_{i\_rim}(n)$ | Rime mass mixing ratio for ice category $n$ | kg kg$^{-1}$ |
| $Q_{i\_tot}(n)$ | Total mass mixing ratio for ice category $n$ | kg kg$^{-1}$ |
| $Q_{i\_total}$ | Total mass mixing ratio for all categories | kg kg$^{-1}$ |
| $V_i(n)$ | Mass-weighted fall speed for ice category $n$ | m s$^{-1}$ |
| $w_{max}$ | Peak updraft speed | m s$^{-1}$ |
| $Z_e$ | Equivalent reflectivity | dBZ |

### b. New Elements for the Multicategory Version

In the generalized scheme, ice is distributed among $n_{Cat}$ free categories (user-specified integer ≥ 1). Each category evolves freely and can represent any type of ice particle. The prognostic variable arrays $Q_{i\_tot}$, $Q_{i\_rim}$, $N_{i\_tot}$, and $B_{i\_rim}$ have an additional dimension of $n_{Cat}$. Process rate and sedimentation computations loop over $n_{Cat}$.

Three new algorithmic elements are required:

#### 1) Determination of the Destination Category of New Ice

To minimize dilution, the mean-mass ice particle size $D_i$ of newly initiated ice is compared to that of existing ice in each category. If no ice is present, ice is initiated into the first category. If categories are populated, the destination category is determined as follows:
- If at least one empty category exists and the minimum size difference with existing categories exceeds $\Delta D_{init}$, the first available empty category is used.
- Otherwise, ice is placed into the category with the smallest $|D_i - D_{new}|$.

The size $D_{new}$ of new ice depends on the initiation mode: ~10 μm for heterogeneous nucleation and rime splintering; ~10–30 μm for frozen cloud droplets; ~1 mm for frozen raindrops.

Example outcomes for $n_{Cat}=3$ are summarized in Table 2. The value of $\Delta D_{init}$ should decrease with increasing $n_{Cat}$; a trial-and-error calibration using the 1D model gives optimal $\Delta D_{init} = f(n_{Cat})$ (Fig. 7 of the paper).

#### 2) Collection Among Ice-Phase Categories

Collection between categories $j$ and $k$ uses a gravitational collection kernel integrated over the size distributions:

$$\frac{\partial X_{j,k}}{\partial t} = \int_0^\infty \int_0^\infty \rho E_{j,k}(A_j + A_k) G(V_j - V_k) Y_k N_j(D_j) N_k(D_k)\, dD_j\, dD_k$$

$$\frac{\partial X_{k,j}}{\partial t} = \int_0^\infty \int_0^\infty \rho E_{j,k}(A_j + A_k) G(V_k - V_j) Y_j N_j(D_j) N_k(D_k)\, dD_j\, dD_k$$

where $G$ is zero for negative arguments (prevents unphysical transfer), $Y$ depends on the quantity being transferred ($1$, $m$, $mF_{rim}$, $mF_{rim}\rho_{rim}$ for $N_{i\_tot}$, $Q_{i\_tot}$, $Q_{i\_rim}$, $B_{i\_rim}$ respectively), and the double integral is precomputed in a lookup table.

Collection efficiency $E_{j,k}=0.1$ for ice crystals, with a linear taper to 0 for collector fall speeds $V_i$ between 1 and 2 m s$^{-1}$ when $F_{rim}>0.5$ (to suppress collection involving graupel/hail). The double integral is stored in lookup tables for efficiency.

#### 3) Merging of Categories with Similar Ice Properties

At the end of each time step (following sedimentation), categories containing ice with sufficiently similar properties are merged. The merging condition is: difference in mean-mass diameter $< 150\,\mu$m **and** difference in bulk density $< 100$ kg m$^{-3}$. Merging frees a category for subsequent new ice initiation, thereby reducing future dilution.

These thresholds are subjectively determined; sensitivity to them affects only the efficiency with which categories are used, not fundamental scheme behavior.

### c. Interfacing with Driving Model

The driving model requires four additional advected variables per additional ice category. In a dynamical model, $Q_{i\_tot}(n)$ must be included for mass loading. Note that $Q_{i\_rim}(n)$ is a subset of $Q_{i\_tot}(n)$. The total ice mass $Q_{i\_total} = \sum_n Q_{i\_tot}(n)$.

Cloud optical properties require care since radiative transfer schemes often assume a single ice mode; evaluation of this sensitivity is beyond the scope of this paper.

---

## 3. Idealized 1D Simulations

### a. Effects of Multiple Categories

Simulations use a 1D kinematic driving model (Milbrandt et al. 2014). Temperature and humidity are initialized with a sounding supporting deep convection. A time-varying half-sine-wave vertical motion profile peaks at 30 min and returns to zero by 60 min.

**Control (CTR) configuration:** $\Delta D_{init} = 500\,\mu$m, all processes on.

- **$n_{Cat}=1$:** Ice forms, grows by riming, is transported aloft, falls toward surface. Large, heavily rimed low-density particles ($<150$ kg m$^{-3}$) where ice mass is greatest; tiny high-density crystals at upper levels.
- **$n_{Cat}=2$:** At any given point, the two categories have distinctly different properties. E.g., at 5 km after 60 min: category 1 has high mass ($\sim 20$ g kg$^{-1}$), $F_{rim}\approx1$, $N_{i\_tot}\sim10^4$ kg$^{-1}$, $D_i\approx4$ mm, $V_i\approx3$ m s$^{-1}$; category 2 has low mass, $F_{rim}\approx0$, small $D_i$, $V_i<0.5$ m s$^{-1}$. Majority of ice mass reaches melting layer earlier (~70 min vs. ~90 min for $n_{Cat}=1$) due to reduced dilution and larger ice in category 1.
- **$n_{Cat}=3$:** Similar to $n_{Cat}=2$ in CTR configuration (little ice in category 3). Approximate convergence at $n_{Cat}=3$ for $w_{max}=10$ m s$^{-1}$; $n_{Cat}=2$ for $w_{max}=3$ m s$^{-1}$.

### b. Sensitivity to the Destination Category of New Ice

The optimal $\Delta D_{init}$ depends on $n_{Cat}$ and forcing strength. An ideal configuration has ice in all categories with the last category having a small but nonnegligible amount. Using $\Delta D_{init} = f(n_{Cat})$ (decreasing with $n_{Cat}$), approximate convergence occurs at $n_{Cat}=4$ for $w_{max}=10$ m s$^{-1}$; with CTR ($\Delta D_{init}=500\,\mu$m) convergence was at $n_{Cat}=3$.

If $\Delta D_{init}$ is too large, all ice goes to the first category (equivalent to $n_{Cat}=1$). If $\Delta D_{init}=0$, all categories populate equally, maximizing dilution (also equivalent to $n_{Cat}=1$). In the worst case, P3 simply reverts to one-category behavior; $\Delta D_{init}$ is not a conventional tuning parameter like a conversion threshold but determines how efficiently the available categories are used.

### c. Effects of Ice Multiplication

Rime splintering (Hallett and Mossop 1974) causes a large increase in $N_{i\_total}$ at ~4 km in the $w_{max}=3$ m s$^{-1}$ case, resulting in severe dilution for $n_{Cat}=1$ (reduced fall speeds, delayed precipitation). With rime splintering off and $n_{Cat}=1$, dilution is reduced and results are closer to the multicategory simulations. Therefore: for $n_{Cat}=1$, it is preferable to exclude rime splintering; for $n_{Cat}\geq2$, rime splintering can be included without introducing significant dilution. In the 3D cases of Part II, inclusion of rime splintering with the one-category version was notably detrimental; switching it off reduced dilution and improved reflectivity structure in convective cores.

### d. Effects of Collection Among Ice Categories

Sensitivity tests show that $E_{j,k}$ can have a slight effect on the degree of dilution and the sedimentation of mass. At the extremes (zero collection or excessive merging due to high $E_{j,k}$), P3 reverts to its single-free-category configuration. Improving the specification of $E_{j,k}$ is identified as future work.

---

## 4. Mesoscale Model (3D) Simulations

The multicategory P3 has been interfaced with Environment Canada's GEM model and WRF. For comparison with Part II, the quasi-idealized 3D squall-line case (19–20 June 2007, Oklahoma; 5900 J kg$^{-1}$ CAPE) is rerun using WRF v3.5.1, 1-km horizontal grid spacing, with $n_{Cat}=1,2,3$. Ice multiplication is off for $n_{Cat}=1$ and on for $n_{Cat}>1$.

**Reflectivity:** All three configurations capture the squall-line structure reasonably. Increasing $n_{Cat}$ results in filling in of reflectivity gaps in the stratiform region and broadening of the high-reflectivity region behind the convective core. All runs have too-low reflectivity in the stratiform region (consistent with all other schemes in Part II; likely a WRF configuration issue). A small dynamical effect on storm propagation speed is noted with increasing $n_{Cat}$.

**Precipitation rates:** Line-averaged near-surface rates at 6 h show: all configurations produce reasonable results; broadening of the convective region for higher $n_{Cat}$; underprediction in stratiform region (~one-third of observed for all runs). Peak convective precipitation rates are approximately 89%, 80%, and 68% of the observed peak for $n_{Cat}=1,2,3$, respectively.

**Category properties ($n_{Cat}=3$):** Most ice mass resides in category 1, with little in category 3. In the anvil, ice in category 1 has $F_{rim}\approx0.2$, $D_i\approx67\,\mu$m, $\rho_i=871$ kg m$^{-3}$, $V_i\approx16$ cm s$^{-1}$; category 2 has $F_{rim}\approx0$, $D_i\approx167\,\mu$m, $\rho_i=667$ kg m$^{-3}$, $V_i\approx46$ cm s$^{-1}$. In the convective core, all categories have similar heavily rimed properties but with spread in fall speeds (6.12, 7.82, 7.05 m s$^{-1}$ for categories 1, 2, 3). For this strongly forced case, differences among categories are relatively small; weaker cases (GEM tests, not shown) showed larger impacts.

The $n_{Cat}=1$ simulation (with rime splintering off) produced results similar to the multicategory runs for this case.

---

## 5. Discussion and Conclusions

The P3 BMS has been generalized to allow a user-specified number of free ice-phase categories. This is the first scheme to model ice-phase microphysics using multiple free categories. Key findings:

- Multiple ice populations can now coexist at the same point, with different bulk properties — most importantly demonstrated in 3D simulations.
- 1D simulations show convergence of total ice mass, number, reflectivity, and precipitation rate with increasing $n_{Cat}$. Convergence occurs at lower $n_{Cat}$ for weakly forced cases.
- Rime splintering requires $n_{Cat}\geq2$ to be included without detrimental dilution.
- For NWP applications, it is recommended to use the maximum $n_{Cat}$ permissible by available computational resources, with initiation and merging conditions calibrated for the strongly forced cases.
- P3 with multiple categories should not be interpreted as converging toward a bin scheme: each category is still a bulk scheme with a complete size distribution represented by a few prognostic variables.
- A triple-moment extension would further narrow the spectral dispersion within each category.
- The additional cost of the multicategory version can be substantially reduced by the advection approach of Morrison et al. (2015, submitted), which computes secondary variable advective tendencies by linear scaling of the lead variable fluxes.
- P3 was run with one- and two-category configurations during the 2015 NOAA/HWT spring experiment and in Environment Canada's 2.5-km deterministic forecast system. A future article will present an operational NWP evaluation.

Future work: alternative methods for destination category determination and category merging; specification of $E_{j,k}$; evaluation in GEM; operational NWP testing.

---

## Acknowledgments

Sarah Tessendorf and Kyoko Ikeda provided observational datasets. Ted Mansell and two anonymous reviewers provided constructive comments. HM was partially supported by U.S. DOE ASR DE-SC0008648, U.S. DOE ASR DE-SC0005336 (subawarded through NASA NNX12AH90G), and NSF Science and Technology Center for Multiscale Modeling of Atmospheric Processes (CMMAP), managed by Colorado State University under Cooperative Agreement ARM-0425247.

---

## References

Cheng, G., and M. English, 1983: A relationship between hailstone concentration and size. *J. Atmos. Sci.*, **40**, 204–213.

Côté, J., S. Gravel, A. Méthot, A. Patoine, M. Roch, and A. Staniforth, 1998: The operational CMC-MRB Global Environmental Multiscale (GEM) model. Part I: Design considerations and formulation. *Mon. Wea. Rev.*, **126**, 1373–1395.

Grabowski, W. W., and H. Morrison, 2008: Toward the mitigation of spurious cloud-edge supersaturation in cloud models. *Mon. Wea. Rev.*, **136**, 1224–1234.

Hallett, J., and S. C. Mossop, 1974: Production of secondary ice particles during the riming process. *Nature*, **249**, 26–28.

Harrington, J. Y., K. Sulia, and H. Morrison, 2013: A method for adaptive habit prediction in bulk microphysical models. Part I: Theoretical development. *J. Atmos. Sci.*, **70**, 349–364.

Hashino, T., and G. J. Tripoli, 2007: The Spectral Ice Habit Prediction System (SHIPS). Part I: Model description and simulation of the vapor deposition process. *J. Atmos. Sci.*, **64**, 2210–2237.

Li, J., and H. W. Barker, 2005: A radiation algorithm with correlated-k distribution. Part I: Local thermal equilibrium. *J. Atmos. Sci.*, **62**, 286–309.

Lin, Y. L., R. Farley, and H. D. Orville, 1983: Bulk parameterization of the snow field in a cloud model. *J. Climate Appl. Meteor.*, **22**, 1065–1092.

Loftus, A. M., W. R. Cotton, and G. G. Carrio, 2014: A triple-moment hail bulk microphysics scheme. Part I: Description and initial evaluation. *Atmos. Res.*, **149**, 35–57.

Mansell, E. R., C. L. Ziegler, and E. C. Bruning, 2010: Simulated electrification of a small thunderstorm with two-moment bulk microphysics. *J. Atmos. Sci.*, **67**, 171–194.

Milbrandt, J. A., and M. K. Yau, 2005a: A multimoment bulk microphysics parameterization. Part I: Analysis of the role of the spectral shape parameter. *J. Atmos. Sci.*, **62**, 3051–3064.

——, and ——, 2005b: A multimoment bulk microphysics parameterization. Part II: A proposed three-moment closure and scheme description. *J. Atmos. Sci.*, **62**, 3065–3081.

——, and H. Morrison, 2013: Prediction of graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429.

——, J. Thériault, and R. Mo, 2014: Modeling the phase transition associated with melting snow in a 1D kinematic framework: Sensitivity to the microphysics. *Pure Appl. Geophys.*, **171**, 303–322.

Morrison, H., and J. A. Milbrandt, 2015: Parameterization of ice microphysics based on the prediction of bulk particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311.

——, G. Thompson, and V. Tatarskii, 2009: Impact of cloud microphysics on the development of trailing stratiform precipitation in a simulated squall line. *Mon. Wea. Rev.*, **137**, 991–1007.

——, S. Tessendorf, K. Ikeda, and G. Thompson, 2012: Sensitivity of a simulated midlatitude squall line to parameterization of raindrop breakup. *Mon. Wea. Rev.*, **140**, 2437–2460.

——, J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II: Case study comparisons with observations and other schemes. *J. Atmos. Sci.*, **72**, 312–339.

Pruppacher, H. R., and J. D. Klett, 1997: *Microphysics of Clouds and Precipitation*. 2nd ed. Kluwer Academic, 954 pp.

Rutledge, S. A., and P. V. Hobbs, 1983: The mesoscale and microscale structure and organization of clouds and precipitation in midlatitude cyclones. VII: A model for the "seeder-feeder" process in warm-frontal rainbands. *J. Atmos. Sci.*, **40**, 1185–1206.

Seifert, A., and K. Beheng, 2006: A two-moment cloud microphysics parameterization for mixed-phase clouds. Part II: Maritime versus continental deep convective storms. *Meteor. Atmos. Phys.*, **92**, 67–88.

Skamarock, W. C., and J. B. Klemp, 2008: A time-split non-hydrostatic atmospheric model for research and forecasting applications. *J. Comput. Phys.*, **227**, 3465–3485.

Sölch, I. K., and B. Karcher, 2010: A large-eddy model for cirrus clouds with explicit aerosol and ice microphysics and Lagrangian ice particle tracking. *Quart. J. Roy. Meteor. Soc.*, **136**, 2074–2093.

Straka, J. M., and E. R. Mansell, 2005: A bulk microphysics parameterization with multiple ice precipitation categories. *J. Appl. Meteor.*, **44**, 445–466.

Thompson, G., P. R. Field, R. M. Rasmussen, and W. D. Hall, 2008: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part II: Implementation of a new snow parameterization. *Mon. Wea. Rev.*, **136**, 5095–5115.

Yuter, S. E., and R. A. Houze, 1995: Three-dimensional kinematic and microphysical evolution of Florida cumulonimbus. Part I: Spatial distribution of updrafts, downdrafts, and precipitation. *Mon. Wea. Rev.*, **123**, 1921–1940.
