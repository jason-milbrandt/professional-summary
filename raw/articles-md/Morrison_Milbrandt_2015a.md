# Parameterization of Cloud Microphysics Based on the Prediction of Bulk Ice Particle Properties. Part I: Scheme Description and Idealized Tests

**Full citation:** Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311, doi:10.1175/JAS-D-14-0065.1.

**Manuscript received:** 20 March 2014 | **Final form:** 3 August 2014 | **Published:** January 2015

**Note:** This is Part I of a two-part series. Part II (Morrison et al. 2015) presents 3D WRF case study comparisons with observations and other schemes.

---

## Abstract

A method for the parameterization of ice-phase microphysics is proposed and used to develop a new bulk microphysics scheme. All ice-phase particles are represented by several physical properties that evolve freely in time and space. The scheme prognoses four ice mixing ratio variables—total mass, rime mass, rime volume, and number—allowing 4 degrees of freedom for representing the particle properties using a single category. This approach represents a significant departure from traditional microphysics schemes in which ice-phase hydrometeors are partitioned into various predefined categories (e.g., cloud ice, snow, and graupel) with prescribed characteristics. The liquid-phase component uses a standard two-moment, two-category approach.

The proposed method and a complete description of the new predicted particle properties (P3) scheme are provided. Results from idealized 2D squall-line simulations in WRF illustrate the overall behavior of the scheme. Despite its use of a single ice-phase category, the scheme simulates a realistically wide range of particle characteristics in different regions of the squall line, consistent with observations. Sensitivity tests show that both the prediction of the rime mass fraction and the rime density are important for the simulation of squall-line structure and precipitation.

---

## 1. Introduction

Proper representation of cloud microphysical and precipitation processes is critical for simulating weather and climate. Despite decades of advancement, microphysics parameterization schemes contain many uncertainties. Current schemes use various hydrometeor categories defined by prescribed physical characteristics that broadly describe a given "typical" particle type.

The parameterization of ice-phase microphysics is particularly challenging. Unlike liquid drops, ice particles have a wide range of densities and complex shapes. Partitioning ice-phase particles into a limited number of categories with specified shape, density, and other physical characteristics is a highly simplified representation of nature and necessitates conversion of particles between categories, which is inherently artificial and often done without a strong theoretical or empirical basis.

There has been a general trend to try to address these deficiencies by adding complexity to the representation of the ice phase, either by increasing the number of categories or adding more prognostic variables. However, greater complexity means an increase in the number of uncertain conversion processes and parameters.

An alternative approach that evolves particle properties in time and space instead of separating ice into different predefined categories was first proposed in the bin microphysics scheme of Hashino and Tripoli (2007). Morrison and Grabowski (2008, MG08) developed a bulk scheme that separately prognoses ice mass mixing ratios grown by riming and vapor deposition. Milbrandt and Morrison (2013) advanced this by using predicted graupel density to include physically consistent fall speed calculations.

In this study, the approach is generalized and a method is proposed to predict several bulk physical properties of ice particles using a single ice-phase category, completely eliminating the need for artificial conversion between ice categories. This forms the basis for a conceptually new bulk microphysics scheme—the **predicted particle properties (P3) scheme**.

---

## 2. Scheme Description

### 2a. Overview

The P3 scheme includes a single ice-phase category with four prognostic mixing ratio variables:
- $q_i$: total ice mass mixing ratio
- $N_i$: ice number mixing ratio
- $q_{rim}$: ice mass from rime growth
- $B_{rim}$: bulk rime volume mixing ratio

These are chosen because together they track particle evolution through all the important mechanisms of ice growth: vapor deposition, aggregation, and riming (dry and wet growth). From these prognostic variables, several important **predicted** properties are derived:
- $F_r = q_{rim}/q_i$: bulk rime mass fraction
- $\rho_r = q_{rim}/B_{rim}$: predicted rime density
- Mean particle size, bulk density

The conservation equation for any prognostic microphysical variable $x$ is:

$$\frac{\partial x}{\partial t} = -\mathbf{u} \cdot \nabla x + \frac{1}{\rho} \frac{\partial (\rho V_x x)}{\partial z} + S_x + D^*(x)$$

where $V_x$ is the appropriately weighted fall speed for quantity $x$, $S_x$ is the source/sink term, and $D^*(x)$ is the subgrid-scale mixing operator.

The size distribution is represented by a three-parameter gamma distribution:

$$N'(D) = N_0 D^\mu e^{-\lambda D}$$

For ice, $\mu$ follows from Heymsfield (2003) based on observations:

$$\mu = 0.00191 \lambda^{0.8} - 2$$

where $\lambda$ has units of m$^{-1}$. This is limited to $0 < \mu < 6$.

The size distribution parameters $N_0$ and $\lambda$ are related to the prognostic number $N$ and mass $q$ by:

$$N = \int_0^\infty N'(D) \, dD = N_0 \int_0^\infty D^\mu e^{-\lambda D} \, dD$$

$$q = \int_0^\infty m(D) N'(D) \, dD$$

The current version uses a single free ice-phase category, which cannot simultaneously simulate populations of particles with different bulk properties at the same point in time and space. Plans exist to implement a multiple-free-category approach in future development.

### 2b. Particle Mass, Projected Area, and Fall Speed

**Small ice particles** ($D < D_{th}$, the threshold size): approximated as ice spheres:

$$m = \frac{\pi}{6} \rho_i D^3$$

where $\rho_i = 917$ kg m$^{-3}$.

**Large unrimed crystals** (vapor diffusion and/or aggregation, $q_{rim} = 0$): power-law $m$–$D$:

$$m_{va} = a_{va} D^{b_{va}}$$

Parameters from Brown and Francis (1995): $a_{va}$ and $b_{va}$ derived from measurements in midlatitude cirrus. $D_{th}$ is found by equating $m_{va}$ with the mass of an ice sphere, yielding:

$$D_{th} = \left(\frac{6 a_{va}}{\pi \rho_i}\right)^{1/(3-b_{va})}$$

**Partially rimed crystals** ($q_{rim} > 0$, not yet filled in): Based on the conceptual model of rime in-filling from Heymsfield (1982), rime accumulates in crystal interstices without changing $D$. The mass–diameter relation is:

$$m_r = a_r D^{b_r} = \frac{1}{1-F_r} a_{va} D^{b_{va}}$$

This implies constant $F_r$ with $D$ and $b_r = b_{va}$.

**Graupel** (completely filled with rime): assumed spherical with predicted density $\rho_g$:

$$m_g = \frac{\pi}{6} \rho_g D^3$$

The critical size for complete in-filling, $D_{cr}$, is found by equating $m_r = m_g$:

$$D_{cr} = \left[\frac{1}{1-F_r} \frac{6 a_{va}}{\pi \rho_g}\right]^{1/(3-b_{va})}$$

A third critical size $D_{gr}$ separates graupel from unrimed ice (where the masses are equal):

$$D_{gr} = \left(\frac{6 a_{va}}{\pi \rho_g}\right)^{1/(3-b_{va})}$$

The bulk density $\rho_g$ is found from an $F_r$-weighted average of the predicted rime density $\rho_r$ and the density of the unrimed part $\rho_d$:

$$\rho_g = \rho_r F_r + (1-F_r) \rho_d$$

where $\rho_d$ is a mass-weighted average of the unrimed particle density. The set of equations for $\rho_d$, $\rho_g$, $D_{cr}$, and $D_{gr}$ is solved by iteration.

[Figure 1: Examples of the ice particle m–D relationship across the range of particle sizes — image not reproducible in markdown]

**Projected area $A(D)$:** For spheres (cloud droplets, rain, dense spherical ice, graupel), $A = \pi D^2/4$. For dense nonspherical and unrimed nonspherical ice, empirical $A$–$D$ relationships from Mitchell (1996) are used (parameters for aggregates of side planes, bullets, columns, and assemblages of planar polycrystals). For partially rimed crystals, a linear weighting between sphere (graupel) and unrimed ice values based on $F_r$ follows MG08.

**Terminal fall speed:** $V = a_1 D^{b_1}$ where $a_1$ and $b_1$ are derived following Mitchell and Heymsfield (2005) based on the Re–X relationship, which includes an explicit dependence on particle density through $m$–$D$ and $A$–$D$ relationships. The air density modification follows Heymsfield et al. (2007): a multiplicative factor of $(\rho_0/\rho)^{0.54}$.

The same mass-weighted terminal fall speed is applied to $q_i$, $q_{rim}$, and $B_{rim}$; the number-weighted fall speed is applied to $N_i$.

Because of the complicated dependence of the fall speed on $D$ (through the varying $m$–$D$ and $A$–$D$ relationships), analytic integration over the PSD is not possible. A lookup table approach is employed, with values of $N_0$, $\lambda$, and relevant PSD moments pre-calculated as a function of $q_i$, $N_i$, $F_r$, and $\rho_r$.

[Figure 2: Mass-weighted bulk ice fall speed as a function of $F_r$ and $\rho_r$ for small, medium, and large $D_m$ — image not reproducible in markdown]

### 2c. Numerical Implementation

The scheme uses a time-split forward Euler solution. Within a time step:
1. Calculate all microphysics source/sink processes (except homogeneous freezing)
2. Update all prognostic state variables
3. Calculate sedimentation
4. Calculate homogeneous freezing

The lookup table approach makes the scheme computationally efficient. Values of $\lambda$ are limited to $1 < D_N < 40$ mm for cloud water and $2 < D_N < 2000$ μm for ice, where $D_N = (\mu+1)/\lambda$ is the number-weighted mean particle diameter. The predicted rime density $\rho_r$ is limited to 50–900 kg m$^{-3}$.

---

## 3. Idealized 2D Squall-Line Simulations

### 3a. Setup

WRF version 3.4.1 is used in a 2D idealized squall-line configuration. Horizontal grid spacing: 1 km; 80 vertical levels to a 20-km model top; time step: 5 s; domain: 500 km × 20 km. The model is initialized with the analytic sounding of Weisman and Klemp (1982, 1984) with initial vertical wind shear of 0.0048 s$^{-1}$ from the surface to 2.5 km (12 m s$^{-1}$ change). Convection is initiated by a thermal perturbation of 3 K. Integrations are for 6 h. Model sensitivity tests are summarized in Table 2.

| Test | Description |
|------|-------------|
| BASE | Baseline version of P3 |
| r400 | Constant $\rho_r = 400$ kg m$^{-3}$ |
| r900 | Constant $\rho_r = 900$ kg m$^{-3}$ |
| FR0 | Constant $F_r = 0$ |
| FR1r400 | Constant $F_r = 1$, $\rho_r = 400$ kg m$^{-3}$ |

### 3b. Baseline Results

Moist convection is triggered within the first few minutes. After ~4 h the storm reaches a quasi-equilibrium mature phase with a well-defined leading edge of convection and trailing stratiform precipitation.

**At 2 h (early symmetric phase):**
- High-reflectivity core with peak Z = 52.3 dBZ at the lowest model level, 60.3 dBZ aloft
- $F_r$ close to 1 in the convective core (large liquid water available for riming)
- Mean mass-weighted ice particle density $\rho_p \approx 300$–600 kg m$^{-3}$ in convective core
- Fall speeds $V_m \approx$ 5–8 m s$^{-1}$ in high-density core region

**At 6 h (mature phase):**
- Leading edge with Z > 45 dBZ over 20–30-km-wide convective region
- Trailing stratiform precipitation with Z mostly 30–40 dBZ
- Large anvil region with $F_r$ near 0 (vapor deposition dominant)
- Large mean particle sizes ($D_m \approx$ 3–4 mm) above the melting level in stratiform region, consistent with aircraft observations
- Notable transport of rimed ice away from convective updrafts

Key finding: predicted properties $F_r$ and $\rho_r$ show no obvious relationships with traditional diagnostic quantities like temperature, vertical velocity, or hydrometeor mass mixing ratios — because transport carries ice away from its growth conditions.

[Figures 3–7: Prognostic and predicted quantities at 2 h and 6 h — images not reproducible in markdown]

### 3c. Sensitivity Tests

There is considerable sensitivity to both $F_r$ and $\rho_r$, with greater sensitivity to $F_r$:
- **FR0** ($F_r = 0$): Very large $V_m < 1.7$ m s$^{-1}$ everywhere → much larger ice mixing ratios aloft, fundamentally different storm structure and surface precipitation
- **r900** ($\rho_r = 900$ kg m$^{-3}$): Higher density → higher fall speeds → less ice aloft near leading edge
- **FR1r400**: Moderate effects; lacks a distinct peak precipitation rate in the convective region
- **r400**: Broader region of high precipitation, no secondary maximum in trailing stratiform region

These results demonstrate the value gained by adding $q_{rim}$ and $B_{rim}$ as prognostic variables, allowing prediction of $F_r$ and $\rho_r$ instead of specification.

[Figures 8–9: Vertical cross sections and surface precipitation rate for sensitivity tests — images not reproducible in markdown]

---

## 4. Discussion and Conclusions

A new bulk microphysics scheme (P3) has been developed that predicts various ice particle properties for a single ice-phase hydrometeor category through four conserved prognostic ice variables. Key features and conclusions:

**Conceptual advantages:**
1. Avoids poorly constrained thresholds and conversion processes between ice categories
2. Represents a continuum of particle properties rather than discrete categories
3. All parameters are real physical quantities that can be measured
4. Computationally efficient — fewer prognostic variables than many bulk schemes

**Idealized squall-line behavior:**
- Single ice category simulates various types of ice-phase particles in expected storm locations
- Predicted $F_r$ and $\rho_r$ exhibit no clear relationships with temperature, vertical velocity, or hydrometeor mass mixing ratios — owing to transport away from growth conditions
- Both $F_r$ and $\rho_r$ have notable impacts on ice condensate aloft and surface precipitation rates

**Limitations and future work:**
- Single category cannot represent different ice types at same location and time
- Multiple free-category version planned to address this limitation
- Future additions: predict crystal axis ratio (following Harrington et al. 2013a,b), liquid water fraction on ice, spectral width via reflectivity (Milbrandt and Yau 2005b)
- Application to bin microphysics schemes is also possible

---

## Appendix A: Overview of Liquid-Phase Component

Prognostic variables: $q_c$, $q_r$, $N_r$ (and optionally $N_c$ and supersaturation). PSDs follow gamma distributions. For cloud droplets, $\mu$ follows Martin et al. (1994). For rain, $\mu$ follows disdrometer observations of Cao et al. (2008):

$$\mu = -0.0201 \lambda^2 + 0.902 \lambda - 1.718$$

Cloud droplet fall speed follows Stokes' law. Rain fall speed uses power-law relationships from Gunn and Kinzer (1949) and Beard (1976). The scheme includes a treatment of droplet condensation/evaporation and ice deposition/sublimation using a quasi-analytic supersaturation formulation following Morrison and Grabowski (2008b).

---

## Appendix B: Microphysical Process Rates

Source/sink terms for the prognostic variables include:

**Liquid phase:**
$$S_{q_c} = QCNUC + QCCON - QCAUT - QCACC - QCCOL - QCHET - QCHOM - QCEVP$$

$$S_{q_r} = QCAUT + QCACC + QIMLT + QCSHD - QRHET - QRHOM - QRCOL - QREVP$$

**Ice phase:**
$$S_{q_{rim}} = QCCOL + QRCOL + QCHET + QRHET + QCHOM + QRHOM - \frac{q_{rim}}{q_i}(QISUB + QIMLT)$$

$$S_{q_i} = QINUC + QIDEP - \frac{(q_i - q_{rim})}{q_i}(QISUB + QIMLT) + S_{q_{rim}}$$

$$S_{N_i} = NINUC + NCHET + NRHET + NCHOM + NRHOM - NISUB$$

$$S_{B_{rim}} = \frac{QCCOL + QCHET + QCHOM + QRHET + QRHOM + QRCOL}{r^*} + \frac{QCCOL}{r_{0r}} + BIWET - \frac{q_{rim}}{r_r q_i}(QISUB - QIMLT)$$

where $r_{0r}$ is the density of rime collected locally (calculated following Milbrandt and Morrison 2013), and $r^* = 900$ kg m$^{-3}$ is the density of rime during wet growth and freezing.

Process naming: Q = mass, N = number, B = volume; second letter = species being reduced (C = cloud, R = rain, I = ice); remaining letters define process type (NUC = nucleation, DEP = deposition, COL = collision/collection, HET/HOM = heterogeneous/homogeneous freezing, etc.).

---

## Appendix C: Microphysical Process Formulations (Key Sections)

**Droplet activation:** Morrison and Grabowski (2007, 2008b), assuming a lognormal aerosol size distribution (300 cm$^{-3}$ total concentration, mean size 0.05 μm, ammonium sulfate). Ice nucleation follows Cooper (1986) as implemented in Thompson et al. (2004); limited to $T \le -15°C$ and $S_i \ge 5\%$.

**Supersaturation formulation:** The quasi-analytic formulation of Morrison and Grabowski (2008b) is extended to include ice. The absolute supersaturation $\delta = q - q_{sl}$ evolves as a linear ODE:

$$\frac{d\delta}{dt} = A_c - \frac{\delta}{\tau}$$

with solution $\delta(t) = A_c \tau + (\delta_{t=0} - A_c \tau) e^{-t/\tau}$, where $\tau$ is the multiphase supersaturation relaxation time scale.

**Collection of cloud droplets by ice:** Parameterized using the continuous collection assumption. The collection kernel uses ice particle fall speed $V(D)$ and projected area $A(D)$ numerically integrated over the PSD (pre-computed in lookup table). Collection efficiency = 1.

**Wet growth:** Calculated following Musil (1970), numerically integrated over the ice PSD. When dry growth rate < wet growth rate, collected water is shed as 1-mm drops; particles also become soaked and undergo densification with $B_{rim} = q_{rim}/\rho^*$.

**Freezing:** Heterogeneous freezing of cloud droplets and rain follows Bigg (1953) with Barklie and Gokhale (1959) parameters. Homogeneous freezing occurs instantaneously at 233.15 K.

**Melting:** Treated using the simplified diffusion approximation with ventilation and relative humidity effects (similar to Lin et al. 1983). The relevant moment of the ice PSD is numerically integrated offline and stored in a lookup table.

**Sedimentation:** The total mass, rime mass, and rime volume mixing ratios sediment at the mass-weighted fall speed $V_m$; the number mixing ratio sediments at the number-weighted fall speed $V_N$.

---

## References

Brown, P. R. A., and P. N. Francis, 1995: Improved measurements of the ice water content in cirrus. *J. Atmos. Oceanic Technol.*, **12**, 410–414.

Cooper, W. A., 1986: Ice initiation in natural clouds. *Precipitation Enhancement*, Meteor. Monogr., No. 43, Amer. Meteor. Soc., 29–32.

Ferrier, B. S., 1994: A double-moment multiple-phase four-class bulk ice scheme. Part I. *J. Atmos. Sci.*, **51**, 249–280.

Harrington, J. Y., K. Sulia, and H. Morrison, 2013a,b: A method for adaptive habit prediction in bulk microphysical models. Parts I and II. *J. Atmos. Sci.*, **70**, 349–376.

Hashino, T., and G. J. Tripoli, 2007: The Spectral Ice Habit Prediction System (SHIPS). Part I. *J. Atmos. Sci.*, **64**, 2210–2237.

Heymsfield, A. J., 1982: A comparative study of the rates of development of potential graupel and hail embryos in High Plains storms. *J. Atmos. Sci.*, **39**, 2867–2897.

Heymsfield, A. J., 2003: Properties of tropical and midlatitude ice cloud particle ensembles. Part II. *J. Atmos. Sci.*, **60**, 2592–2611.

Heymsfield, A. J., A. Bansemer, and C. H. Twohy, 2007: Refinements to ice particle mass dimensional and terminal velocity relationships. Part I. *J. Atmos. Sci.*, **64**, 1047–1067.

Mansell, E. R., C. L. Ziegler, and E. C. Bruning, 2010: Simulated electrification of a small thunderstorm with two-moment bulk microphysics. *J. Atmos. Sci.*, **67**, 171–194.

Martin, G. M., D. W. Johnson, and A. Spice, 1994: The measurement and parameterization of effective radius of droplets in warm stratocumulus clouds. *J. Atmos. Sci.*, **51**, 1823–1842.

Milbrandt, J. A., and M. K. Yau, 2005a,b: A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.

Milbrandt, J. A., and R. McTaggart-Cowan, 2010: Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.

Milbrandt, J. A., and H. Morrison, 2013: Predicting graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429.

Mitchell, D. L., 1996: Use of mass- and area-dimensional power laws for determining precipitation particle terminal velocities. *J. Atmos. Sci.*, **53**, 1710–1723.

Mitchell, D. L., and A. J. Heymsfield, 2005: The treatment of ice particle terminal velocities, highlighting aggregates. *J. Atmos. Sci.*, **62**, 1637–1644.

Morrison, H., and W. W. Grabowski, 2008: A novel approach for representing ice microphysics in models: Description and tests using a kinematic framework (MG08). *J. Atmos. Sci.*, **65**, 1528–1548.

Morrison, H., and J. A. Milbrandt, 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Wea. Rev.*, **139**, 1103–1130.

Morrison, H., J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of microphysics based on the prediction of bulk ice particle properties. Part II. *J. Atmos. Sci.*, **72**, 312–339.

Musil, D. J., 1970: Computer modeling of hailstone growth in feeder clouds. *J. Atmos. Sci.*, **27**, 474–482.

Thompson, G., R. M. Rasmussen, and K. Manning, 2004: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part I. *Mon. Wea. Rev.*, **132**, 519–542.

Weisman, M. L., and J. B. Klemp, 1982, 1984: The dependence of numerically simulated convective storms on vertical wind shear and buoyancy; The structure and classification of numerically simulated convective storms. *Mon. Wea. Rev.*, **110**, 504–520; **112**, 2479–2498.
