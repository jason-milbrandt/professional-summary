# Prediction of Graupel Density in a Bulk Microphysics Scheme

**Full citation:** Milbrandt, J. A., and H. Morrison, 2013: Prediction of graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429, doi:10.1175/JAS-D-12-0204.1.

**Manuscript received:** 17 July 2012 | **Final form:** 4 September 2012 | **Published:** February 2013

---

## Abstract

A method to predict the bulk density of graupel $\rho_g$ has been added to the two-moment Milbrandt–Yau bulk microphysics scheme. The simulation of graupel using the modified scheme is illustrated through idealized simulations of a mesoscale convective system using a 2D kinematic model with a prescribed flow field and different peak updraft speeds. To examine the relative impact of the various approaches to represent rimed ice, simulations were run for various graupel-only and graupel-plus-hail configurations.

Because of the direct feedback of $\rho_g$ to terminal fall speeds, the modified scheme produces a much different spatial distribution of graupel, with more mass concentrated in the convective region resulting in changes to the surface precipitation at all locations. With a strong updraft, the model can now produce solid precipitation at the surface in the convective region without a separate hail category. It is shown that a single rimed-ice category is capable of representing a realistically wide range of graupel characteristics in various atmospheric conditions without the need for a priori parameter settings.

Sensitivity tests were conducted to examine various aspects of the scheme that affect the simulated $\rho_g$. Specific parameterizations pertaining to other hydrometeor categories now have a direct impact on the simulation of graupel, including the assumed aerosol distribution for droplet nucleation (which affects drop sizes of both cloud and rain) and the mass–size relation for snow (which affects its density and hence the embryo density of graupel converted from snow due to riming).

---

## 1. Introduction

With increasing computer power and model resolution, the representation of cloud and precipitation microphysics has moved to the forefront of physical parameterization development. Many uncertainties remain, including the parameterization of ice-phase microphysics, given the wide variety of ice particle shapes and types and lack of observational constraints.

Graupel—heavily rimed crystals that have not undergone wet growth—is commonly parameterized as "medium-density graupel" with a bulk density $\rho_g$ of 400 kg m$^{-3}$ and corresponding fixed fall speed parameters. In nature, graupel has a large range of densities and fall speeds (Locatelli and Hobbs 1974; Pruppacher and Klett 1997).

There is considerable sensitivity of simulations to the values of the fixed density and fall speed parameters. Gilmore et al. (2004) and van Weverberg et al. (2010) showed large sensitivity of simulated supercell storms to changes in $\rho_g$. Recent work has shown considerable sensitivity of storm structure and dynamics to graupel–hail fall speed parameters in two-moment BMSs (Morrison and Milbrandt 2011; Bryan and Morrison 2012). Fall speeds should depend explicitly on $\rho_g$, with higher values resulting in greater fall speeds (Locatelli and Hobbs 1974; Mitchell and Heymsfield 2005).

The first work on modeling changes to $\rho_g$ in a microphysical model is that of Farley (1987). Connolly et al. (2006) added a third prognostic variable—the bulk volume mixing ratio—to their two-moment scheme. Mansell et al. (2010, M2010) addressed limitations by parameterizing rime density as a function of temperature, impact speed, and droplet size following Heymsfield and Pflaum (1985).

In this study, a prognostic approach to model $\rho_g$ has been added to the two-moment version of the Milbrandt and Yau (2005a,b, MY2005ab) multimoment scheme. The approach is similar to M2010 but uses a different rime density parameterization based on the laboratory experiments of Cober and List (1993, CL1993) and includes a physically based treatment of graupel fall speeds following the Reynolds number–best number approach of Khvorostyanov and Curry (2002) and Mitchell and Heymsfield (2005).

---

## 2. Description of Method

The prognostic-$\rho_g$ method is incorporated into MY2. In principle, this method can be used in any BMS, but is most effective when applied to two-moment (or higher) schemes.

### 2a. The New Prognostic Variable

Since $\rho_g$ is not conserved during advection, a new variable is introduced: the **bulk graupel volume mixing ratio** $B_g$ (m$^3$ kg$^{-1}$), following Connolly et al. (2006) and M2010. The quantity $\rho B_g$ is advected and diffused (where $\rho$ is air density). At any point in time and space:

$$\rho_g = \frac{q_g}{B_g}$$

This is analogous to accurate evolution of mean-mass particle diameter $D_x$ based on separate advection of $q_x$ and $N_x$ in two-moment schemes. The conservation equation for $B_g$ is:

$$\frac{\partial B_g}{\partial t} = \left.\frac{\partial B_g}{\partial t}\right|_{advection} + \left.\frac{\partial B_g}{\partial t}\right|_{diffusion} + \frac{\partial \rho_g q_g}{\partial t} \frac{1}{\rho_g^2}\bigg|_{micro} + \left.\frac{\partial B_g}{\partial t}\right|_{sedimentation}$$

The variables and parameters pertaining to graupel in the prognostic-$\rho_g$ scheme are summarized in Table 1. The prognostic variables are $q_g$ (mass mixing ratio, kg kg$^{-1}$), $B_g$ (bulk volume mixing ratio, m$^3$ kg$^{-1}$), and $N_g$ (total number mixing ratio, kg$^{-1}$). $\rho_g$, $c_g$, $N_{0g}$, $\lambda_g$, and $\mu_g$ are diagnostic parameters.

### 2b. Fall Speed Parameters

The terminal fall speed for a graupel particle of diameter $D$ is:

$$v_g = \left(\frac{\rho_0}{\rho}\right)^{0.5} a_g D^{b_g}$$

where $\rho_0$ is the reference air density at mean sea level. Using the Re–X approach of Khvorostyanov and Curry (2002) and Mitchell and Heymsfield (2005), where the best number is:

$$X = \frac{4 \rho_g g \rho D^3}{3\eta^2}$$

the coefficients are:

$$a_g = a_1 \nu^{(1-2b_1)} \left(\frac{4\rho_g g}{3\rho a}\right)^{b_1}$$

$$b_g = 2b_1$$

with $a_1$ and $b_1$ depending on the Re–X relationship through nondimensional surface roughness parameters $C_1 = 4/(d_0^2 C_0^{1/2})$, $C_2 = d_0^2/4$, $d_0 = 5.83$, $C_0 = 0.292$.

Because of the complicated dependence of $a_g$ and $b_g$ on $D$, these parameters are diagnosed from numerical solutions and stored in a lookup table as a function of $\rho_g$ (Table 2), with linear interpolation for intermediate values.

**Table 2: Fitted fall speed parameters**

| $\rho_g$ (kg m$^{-3}$) | $a_g$ (m$^{1-b_g}$ s$^{-1}$) | $b_g$ |
|------------------------|-------------------------------|--------|
| 50 | 62.923 | 0.678 19 |
| 150 | 94.122 | 0.637 89 |
| 250 | 114.74 | 0.621 97 |
| 350 | 131.21 | 0.612 40 |
| 450 | 145.26 | 0.605 72 |
| 550 | 157.71 | 0.600 66 |
| 650 | 168.98 | 0.596 63 |
| 750 | 179.36 | 0.593 30 |
| 850 | 189.02 | 0.590 48 |

[Figure 1: Terminal graupel fall speed as a function of diameter for various densities — image not reproducible in markdown]

### 2c. Microphysical Processes

The updated $\rho_g^*$ is computed as the mass-weighted sum of $\rho_g^0$ and the density of new or depleted graupel mass from individual processes:

$$\rho_g^* = \frac{q_g^0 \rho_g^0 + \Delta q|_{CN_{sg}} \rho_s + \delta_{irg}(\Delta q|_{CL_{ir}} + \Delta q|_{CL_{ri}}) \rho_h + \delta_{srg}(\Delta q|_{CL_{sr}} + \Delta q|_{CL_{rs}}) \rho_{srg} + \delta_{rgg}(\Delta q|_{CL_{rg}}) \rho_{rgg} + (\Delta q|_{CL_{cg}} + \Delta q|_{CL_{rg}}) \rho_{rime}}{q_g^0 + \Delta q|_{CN} + \delta_{irg}(\Delta q|_{CL_{ir}} + \Delta q|_{CL_{ri}}) + \delta_{srg}(\Delta q|_{CL_{sr}} + \Delta q|_{CL_{rs}}) + \delta_{rgg}(\Delta q|_{CL_{rg}}) + (\Delta q|_{CL_{cg}} + \Delta q|_{CL_{rg}})}$$

The processes that change $\rho_g$ are: conversion from snow to graupel, three-component freezing to graupel, and riming. All other processes affecting $q_g$ and/or $N_g$ (deposition, sublimation, melting, ice multiplication, conversion to hail) are assumed to have negligible impact on $\rho_g$.

### 2d. Sedimentation

After computing $q_g^*$ and $N_g^*$, $B_g^*$ is determined from Eq. (1). Sedimentation of $q_g^*$ at $V_g^*$ and $N_g^*$ at $V_N^*$ gives the final $q_g^+$ and $N_g^+$. Sedimentation of $B_g^*$ is also computed at $V_g^*$ to obtain $B_g^+$.

**Size sorting control:** Because of the now-large range of possible fall speeds, size sorting in two-moment sedimentation can create problems. To control this, a diagnostic shape parameter $\mu_g$ for graupel is proposed (Section 4d):

$$\mu_g = (1000 D_g)^{0.075}$$

---

## 3. Kinematic Model Description and Setup

The modified MY2 scheme is tested in a 2D kinematic model (Szumowski et al. 1998; Grabowski 1999; Morrison and Grabowski 2007; Slawinska et al. 2009). The specified flow field is representative of a mature squall line with strong, deep ascent in the convective region and weak mesoscale ascent/descent in the stratiform region.

The peak updraft speed $w_{peak}$ is increased sinusoidally from 0 to its peak value over 15 min. Grid spacing: horizontal 750 m, vertical 250 m, over a 240 km × 12 km domain. Time step: 5 s. Transport uses the 2D MPDATA scheme (Smolarkiewicz 1984). Temperature is from the 0000 UTC 1 September 1974 GARP GATE sounding.

$w_{peak}$ is varied between 1 and 40 m s$^{-1}$ across simulations. The simulation naming convention is listed in Table 3.

---

## 4. Results

### 4a. Demonstration of the Prognostic-$\rho_g$ Scheme

The effects of the new method are illustrated with PD-20 (prognostic $\rho_g$, diagnostic $a_g$, $b_g$; graupel only; $w_{peak} = 20$ m s$^{-1}$).

At 12 min, elevated graupel is present near the updraft core, initially at high density (~900 kg m$^{-3}$) from freezing rain embryos, then decreasing rapidly as graupel grows by riming. By 15 min, the majority of the graupel mass is located above the updraft core with low densities ($\rho_g < 250$ kg m$^{-3}$), smaller sizes ($D_g < 1$–2 mm), and smaller fall speeds ($V_g \approx 1$–3 m s$^{-1}$). By 20 min, a small amount of graupel reaches the surface with relatively high density ($\rho_g > 600$ kg m$^{-3}$), largest sizes ($D_g > 15$ mm), and high fall speeds ($V_g > 20$ m s$^{-1}$).

[Figure 3: Model reflectivity at indicated times for PD-20 — image not reproducible in markdown]

[Figures 4–5: Graupel fields at early times and at steady state — images not reproducible in markdown]

### 4b. Comparison to Standard Approaches

**Graupel only ($w_{peak}$ = 40 m s$^{-1}$):**
- PD-40 (prognostic $\rho_g$): high-density graupel concentrated in convective region, some solid precipitation at the surface
- FF-40 (fixed $\rho_g = 400$ kg m$^{-3}$, fixed fall speeds): graupel mass spread widely into stratiform region, no solid precipitation at the surface despite copious graupel amounts
- PF-40 (prognostic $\rho_g$, fixed fall speed parameters): nearly identical to FF-40 — demonstrating that it is crucial that fall speed parameters vary correctly as a function of $\rho_g$

**Graupel and hail ($w_{peak}$ = 40 m s$^{-1}$):**
PD-HAIL-40 and FF-HAIL-40 both produce distinct hail shafts near the convective core with hail ($D_h > 20$ mm, fall speeds > 30 m s$^{-1}$) at the surface. The prognostic-$\rho_g$ treatment of graupel is of clear benefit for more realistic spatial distributions even in two-category schemes.

[Figures 6–10: Comparison of PD, FF, PF, PD-HAIL, FF-HAIL simulations — images not reproducible in markdown]

### 4c. Weak-Updraft Cases ($w_{peak}$ = 3 m s$^{-1}$)

PD-3 produces unrealistically large $D_g$ and $V_g$ values due to uncontrolled size sorting with the now-large range of fall speeds. FF-3 produces a more realistic graupel field (bulk fall speeds < 2 m s$^{-1}$) that entirely melts before reaching the surface.

### 4d. Controlling Size Sorting: Diagnostic Shape Parameter for Graupel

The diagnostic relation $\mu_g = (1000 D_g)^{0.075}$ effectively reduces the size-sorting problem in weak-updraft cases (PD-MU-3) without adversely affecting strong-updraft cases (PD-MU-40).

[Figures 11–14: Weak and strong updraft simulations and size-sorting control — images not reproducible in markdown]

---

## 5. Sensitivity to the Computation of $\rho_g$

Sensitivity experiments with $w_{peak}$ = 3 and 40 m s$^{-1}$ examined aspects of the scheme that affect $\rho_g$ through the budget equation:

- **oldSnow** (original MY2 $m$–$D$ parameters for snow, $\rho_s = 100$ kg m$^{-3}$): For weak updrafts, results in considerable increase in graupel in the convective region due to higher initial embryo density. For strong updrafts, shifts more graupel mass toward the stratiform region.

- **Maritime** (maritime CCN, $N_c \approx 0.8 \times 10^8$ m$^{-3}$): Fewer and larger drops result in larger graupel density and hence more suspended graupel mass for the weak-updraft case.

- **RH85** (Rasmussen and Heymsfield 1985 rime density formulation): Gives larger rime densities and greater fall speeds; results in more graupel mass in the strong-updraft case.

- **delT2** ($T_{sfc} = T + 2°C$ in $\rho_{rime}$ calculation): Very little sensitivity.

- **3comp** (constant $\rho_g$ for three-component freezing): Virtually no sensitivity.

[Figure 15: Summary of sensitivity tests — image not reproducible in markdown]

---

## 6. Conclusions

A method to predict the bulk graupel density $\rho_g$ has been described and added to the two-moment version of the Milbrandt–Yau bulk microphysics scheme. Key contributions:

1. A new prognostic variable $B_g$ (bulk graupel volume mixing ratio) is introduced so that $\rho_g$ evolves correctly during advection.

2. Graupel fall speeds are now explicitly dependent on the predicted $\rho_g$ through diagnostically varying fall speed parameters $a_g(\rho_g)$ and $b_g(\rho_g)$, using the Re–X approach of Mitchell and Heymsfield (2005).

3. Through direct feedback to fall speeds, the prognostic $\rho_g$ produces a much different spatial distribution of graupel with more mass concentrated in the convective region and solid precipitation at the surface for strong updrafts.

4. A single rimed-ice category with prognostic density is capable of representing the wide range of graupel types — from lightly rimed, low-density, slow-falling ice to high-density, fast-falling graupel — without a priori parameter settings.

5. The size-sorting problem introduced by the large range of fall speeds can be controlled by a diagnostic shape parameter $\mu_g = f(D_g)$.

6. The prognostic-$\rho_g$ method may reduce the need for a separate hail category, depending on operational or research requirements.

This work constitutes a significant improvement in the representation of graupel in microphysics schemes and is part of a paradigm shift toward adding physical degrees of freedom for a given hydrometeor type rather than including more categories with prescribed characteristics.

---

## Appendix A: Overview of the MY2 Bulk Microphysics Scheme

The BMS (Milbrandt and Yau 2005a,b, with modifications from Milbrandt et al. 2008, 2012) has prognostic equations for $q_x$ and $N_x$ of six hydrometeor categories. The PSD of each category follows:

$$N_x(D) = N_{0x} D^{\mu_x} e^{-\lambda_x D}$$

The two-moment fixed-$\mu_x$ version (MY2) is used, with $\mu_x = 0$ for $x = i, r, s, g, h$ and $\mu_x = 3$ for cloud droplets.

Snow uses $c_s = 0.1597$ and $d_s = 2.078$ (MKS units). With the prognostic-$\rho_g$ modification, $c_g$ is now a diagnostic function of $\rho_g$.

---

## Appendix B: Parameterization Details

### B.a. Graupel Initiation

For conversion from snow to graupel (CNsg), the density of new graupel mass equals the diagnostic snow density $\rho_s = f(D_s)$ (from Milbrandt et al. 2012). For three-component freezing from rain–ice or rain–snow interactions resulting in graupel, the density is approximated as $\rho_h = 900$ kg m$^{-3}$ (for ice–rain) or a mass-weighted mean density (for snow–rain).

### B.b. Riming

The density of new rime $\rho_{rime}$ due to accretion follows CL1993:

$$\rho_{rime} = 0.078 + 0.184 R_i - 0.015 R_i^2$$

where:

$$R_i = \frac{0.5 D_{drop} V_{impact}}{T_{sfc}}$$

(following Macklin 1962). $D_{drop}$ is the mean-mass diameter of the collected liquid:

$$D_{drop} = \left[\frac{6\rho(q_c + q_r)}{\pi \rho_L (N_c + N_r)}\right]^{1/3}$$

The impact velocity is:

$$V_{impact} = |V(D_g) - V(D_{drop})|$$

Lower and upper bounds on $\rho_{rime}$ (and $\rho_g$) of 50 and 900 kg m$^{-3}$ are imposed.

---

## References

Adams-Selin, R. D., S. C. van den Heever, and R. H. Johnson, 2013: Impact of graupel parameterization schemes on idealized bow echo simulations. *Mon. Wea. Rev.*, in press.

Bryan, G. H., and H. Morrison, 2012: Sensitivity of a simulated squall line to horizontal resolution and parameterization of microphysics. *Mon. Wea. Rev.*, **140**, 202–225.

Cober, S. G., and R. List, 1993: Measurements of the heat and mass transfer parameters characterizing conical graupel growth. *J. Atmos. Sci.*, **50**, 1591–1609.

Cohen, C., and E. W. McCaul, 2006: The sensitivity of simulated convective storms to variations in prescribed single-moment microphysics parameters. *Mon. Wea. Rev.*, **134**, 2547–2565.

Connolly, P. J., and Coauthors, 2006: Cloud-resolving simulations of intense tropical Hector thunderstorms. *Quart. J. Roy. Meteor. Soc.*, **132**, 3079–3106.

Farley, R. D., 1987: Numerical modeling of hailstorms and hailstone growth. Part II. *J. Climate Appl. Meteor.*, **26**, 234–254.

Ferrier, B. S., 1994: A double-moment multiple-phase four-class bulk ice scheme. Part I. *J. Atmos. Sci.*, **51**, 249–280.

Gilmore, M. S., J. M. Straka, and E. N. Rasmussen, 2004: Precipitation uncertainty due to variations in precipitation particle parameters. *Mon. Wea. Rev.*, **132**, 2610–2627.

Grabowski, W. W., 1999: A parameterization of cloud microphysics for long term cloud-resolving modeling. *Atmos. Res.*, **52**, 17–41.

Heymsfield, A. J., and J. C. Pflaum, 1985: A quantitative assessment of the accuracy of techniques for calculating graupel growth. *J. Atmos. Sci.*, **42**, 2264–2274.

Heymsfield, A. J., and M. Kajikawa, 1987: An improved approach to calculating terminal velocities of plate-like crystals and graupel. *J. Atmos. Sci.*, **44**, 1088–1099.

Khvorostyanov, V. I., and J. A. Curry, 2002: Terminal velocities of droplets and crystals. *J. Atmos. Sci.*, **59**, 1872–1884.

Knight, N. C., and A. J. Heymsfield, 1983: Measurement and interpretation of hailstone density and terminal velocity. *J. Atmos. Sci.*, **40**, 1510–1516.

Locatelli, J. D., and P. V. Hobbs, 1974: Fall speeds and masses of solid precipitation particles. *J. Geophys. Res.*, **79**, 2185–2197.

Macklin, W. C., 1962: The density and structure of ice formed by accretion. *Quart. J. Roy. Meteor. Soc.*, **88**, 30–50.

Mansell, E. R., C. L. Ziegler, and E. C. Bruning, 2010: Simulated electrification of a small thunderstorm with two-moment bulk microphysics. *J. Atmos. Sci.*, **67**, 171–194.

Milbrandt, J. A., and M. K. Yau, 2005a: A multimoment bulk microphysics parameterization. Part I. *J. Atmos. Sci.*, **62**, 3051–3064.

Milbrandt, J. A., and M. K. Yau, 2005b: A multimoment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, **62**, 3065–3081.

Milbrandt, J. A., and R. McTaggart-Cowan, 2010: Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.

Milbrandt, J. A., M. K. Yau, J. Mailhot, and S. Bélair, 2008: Simulation of an orographic precipitation event during IMPROVE-2. Part I. *Mon. Wea. Rev.*, **136**, 3873–3893.

Milbrandt, J. A., A. Glazer, and D. Jacob, 2012: Predicting the snow-to-liquid ratio of surface precipitation using a bulk microphysics scheme. *Mon. Wea. Rev.*, **140**, 2461–2476.

Mitchell, D. L., 1996: Use of mass- and area-dimensional power laws for determining precipitation particle terminal velocities. *J. Atmos. Sci.*, **53**, 1710–1723.

Mitchell, D. L., and A. J. Heymsfield, 2005: The treatment of ice particle terminal velocities, highlighting aggregates. *J. Atmos. Sci.*, **62**, 1637–1644.

Morrison, H., and W. W. Grabowski, 2007: Comparison of bulk and bin warm-rain microphysics models using a kinematic framework. *J. Atmos. Sci.*, **64**, 2839–2861.

Morrison, H., and J. A. Milbrandt, 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Wea. Rev.*, **139**, 1103–1130.

Morrison, H., G. Thompson, and V. Tatarskii, 2009: Impact of cloud microphysics on the development of trailing stratiform precipitation. *Mon. Wea. Rev.*, **137**, 991–1007.

Pruppacher, H. R., and J. D. Klett, 1997: *Microphysics of Clouds and Precipitation*. 2nd ed. Kluwer Academic, 954 pp.

Rasmussen, R. M., and A. J. Heymsfield, 1985: A generalized form for impact velocities used to determine graupel accretional densities. *J. Atmos. Sci.*, **42**, 2275–2279.

Slawinska, J., W. W. Grabowski, and H. Morrison, 2009: The impact of atmospheric aerosols on precipitation from deep organized convection. *Quart. J. Roy. Meteor. Soc.*, **135**, 1906–1913.

Smolarkiewicz, P. K., 1984: A fully multidimensional positive definite advection transport algorithm. *J. Comput. Phys.*, **54**, 325–362.

Straka, J. M., and E. R. Mansell, 2005: A bulk microphysics parameterization with multiple ice precipitation categories. *J. Appl. Meteor.*, **44**, 445–466.

van den Heever, S. C., and W. R. Cotton, 2004: The impact of hail size on simulated supercell storms. *J. Atmos. Sci.*, **61**, 1596–1609.

van Weverberg, K., A. M. Vogelmann, H. Morrison, and J. A. Milbrandt, 2012: Sensitivity of idealized squall line simulations to the level of complexity used in two-moment bulk microphysics schemes. *Mon. Wea. Rev.*, **140**, 1883–1907.

Wisner, C., H. D. Orville, and C. Meyers, 1972: A numerical model of a hail-bearing cloud. *J. Atmos. Sci.*, **29**, 1160–1181.
