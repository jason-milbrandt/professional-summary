# Modeling the Phase Transition Associated with Melting Snow in a 1D Kinematic Framework: Sensitivity to the Microphysics

**Full citation:** Milbrandt, J. A., J. Thériault, and R. Mo, 2014: Modeling the phase transition associated with melting snow in a 1D kinematic framework: Sensitivity to the microphysics. *Pure Appl. Geophys.*, **171**, 303–322, doi:10.1007/s00024-012-0552-y.

**Received:** February 22, 2012 | **Accepted:** July 5, 2012 | **Published online:** August 10, 2012 | **Print volume year:** 2014

---

## Abstract

A simple 1D kinematic cloud model coupled to a two-moment bulk microphysics scheme is used to perform quasi-idealized simulations of snow, with a prescribed upper boundary snow field based on observed radar reflectivity and temperature, falling into a low-level melting layer. The model realistically simulates the formation of a nearly isothermal layer below the melting level, the surface precipitation rate, and the phase transition from liquid to solid, consistent with observations for this case. A series of test runs is performed to examine the sensitivity of modeling the timing and duration of the phase transition period to details of specific parameterization aspects related to snow in the microphysics scheme. The sensitivity tests include varying the number of prognostic moments, the mass–diameter relation, the fall velocity–diameter relation, the treatment of aggregation, and the lower limit for the slope of the size distribution. It is shown that the simulated transition period, for such a case with the initial melting level being close to the surface, can be quite sensitive to model parameters specified within realistic ranges and/or ranges within our physical understanding.

---

## 1. Introduction

Wintertime precipitation forecasting using NWP models is inherently challenging due to the complex series of physical processes that ultimately lead to surface precipitation. When the melting level is close to the surface, the prediction of precipitation phase and timing of a phase transition is particularly challenging. The treatment of melting snow in the model affects the low-level temperature structure and feeds back to the calculation of the melting rate. In mountainous regions, diabatic cooling from melting snow can induce downward air motion and result in significant changes to the surface flow field.

During the Vancouver 2010 Winter Olympics, Environment Canada ran a special 1-km GEM NWP model. This study examines, through 1D kinematic model simulations using a two-moment BMS (MY2), the sensitivity of specific assumptions in the parameterization of snow to the diabatic cooling and surface precipitation phase change for a situation with snow falling through a near-surface melting layer.

---

## 2. Case Overview

A heavy precipitation event occurred during 13–14 February 2010 at Whistler Mountain, British Columbia, Canada, during the Vancouver 2010 Winter Olympic Games. The SNOW-V10 field campaign provided detailed observations including Doppler weather radar at VVO station.

The 0000 UTC sounding at VOC indicated the freezing level was approximately 500 m AGL. A nearly isothermal layer formed by 0600 UTC, and a shift from upslope to downslope valley–mountain flow occurred by 0300 UTC. This flow reversal is hypothesized to have been induced by diabatic cooling from melting snow (Thériault et al. 2012).

The precipitation rate at VOT station dropped approximately 5°C between 2100 UTC 13 February and 0300 UTC 14 February as melting precipitation cooled the air below the melting level.

[Figure 1: Orography in the Whistler Mountain region with station locations — image not reproducible in markdown]

[Figure 2: Observed radar reflectivity and Doppler wind velocity at 0000 and 0300 UTC 14 February 2010 — image not reproducible in markdown]

[Figure 3: Observed soundings at 0000 and 0600 UTC 14 February 2010 at VOC — image not reproducible in markdown]

[Figure 4: Precipitation rate and temperature time series at VOT station — image not reproducible in markdown]

---

## 3. Description of Modeling System

The modeling system is a simple 1D kinematic cloud model coupled to the two-moment version of the Milbrandt and Yau (2005a,b) microphysics scheme (MY2). The model was initialized with the 0000 UTC 14 February 2010 sounding at VOC. A snow field was prescribed at 1600 m AGL above the initial melting level (~500 m AGL) and allowed to fall and evolve according to the microphysics. The model top was at 1640 m AGL with 47 evenly-spaced levels (Δz = 35 m) and a time step of 10 s. Each simulation was integrated for 8 h.

The prognostic variables for snow are the mass mixing ratio $q_s$ and total number concentration $N_s$. Initial and upper boundary conditions for the snow field were obtained from the observed radar reflectivity of 25 dBZ at 1600 m AGL and air temperature of −5°C, yielding $q_s = 0.45$ g kg$^{-1}$ and $N_s = 3115$ m$^{-3}$.

The 1D model equations are given in Appendix 1; an overview of MY2 is given in Appendix 2.

---

## 4. Results

### 4.1. CTR Simulation

The control simulation (CTR) and sensitivity experiments (EXP1–EXP9) are summarized in Table 1. Snow sediments from its initial level and begins to melt at ~500 m AGL after approximately 15 min. The first precipitation reaches the ground after ~20 min as rain. A non-negligible amount of snow and rain simultaneously precipitates at the surface during approximately 60–340 min, during which $T_{sfc}$ drops from ~4°C to nearly 0°C.

The CTR run realistically simulates:
- Formation of a nearly isothermal layer near 0°C below the melting level (~500 m AGL) by 360 min
- Simulated precipitation rates corresponding well to observed 1–2 mm h$^{-1}$ at VOT

**Table 1: Sensitivity experiments**

| Experiment | Description |
|-----------|-------------|
| CTR | Control run; baseline two-moment MY2 configuration |
| EXP1 | One-moment for snow |
| EXP2 | $m$–$D$ parameters [$c_s = (\pi/6)\rho_s$ with $\rho_s = 100$ kg m$^{-3}$, $d_s = 3$] |
| EXP3 | $V$–$D$ parameters ($a_s = 8.996$, $b_s = 0.42$; from Ferrier 1994) |
| EXP4 | Snow aggregation off |
| EXP5 | Snow aggregation rate doubled |
| EXP6 | $\lambda_{s,\min} = 1$ m$^{-1}$ |
| EXP7 | $\lambda_{s,\min} = 1000$ m$^{-1}$ |
| EXP8 | $N_{0s} = f(-2.5°C)$ |
| EXP9 | $N_{0s} = f(-7.5°C)$ |

**Table 2: Parameters for snow in baseline MY2 (MKS units)**

| Parameter | Value |
|-----------|-------|
| $a_s$ | 11.72 |
| $b_s$ | 0.41 |
| $c_s$ | 0.1597 |
| $d_s$ | 2.078 |
| $\lambda_{s,\min}$ | 500 |

[Figure 5: Output from CTR simulation — image not reproducible in markdown]

### 4.2. Sensitivity to Assumptions and Parameters in MY2

#### 4.2.1. One-Moment versus Two-Moment: EXP1

Setting snow to one-moment delays the onset of surface precipitation, then results in a slightly higher rate. The cooling rate is stronger in EXP1 because the leading edge of falling snow is slower but mass is more evenly distributed throughout the column. The transition period becomes shorter because the one-moment scheme cannot simulate gravitational size sorting. This comparison illustrates the sensitivity to the number of prognostic moments for snow.

[Figure 6: Output from EXP1 simulation — image not reproducible in markdown]

#### 4.2.2. Mass–Diameter Parameters: EXP2

Reverting to the original spherical snow $m$–$D$ parameters ($c_s = (\pi/6) \times 100$ kg m$^{-3}$, $d_s = 3$) has little effect on the simulation of melting snow.

[Figure 7: Output from EXP2 simulation — image not reproducible in markdown]

#### 4.2.3. Fall Velocity–Diameter Parameters: EXP3

Using slower V–D parameters (Ferrier 1994) greatly increases the duration of the phase transition period. Slower falling snow has more time to melt to rain before arriving at the surface, but the melting rate itself is reduced due to a reduced ventilation effect. Overall, the choice of snow V–D parameters has a significant impact on the phase transition rate.

[Figure 8: Output from EXP3 simulation — image not reproducible in markdown]

#### 4.2.4. Treatment of Aggregation: EXP4 and EXP5

Turning off aggregation (EXP4) causes increased cooling due to melting, leading to a much shorter phase transition period. Doubling the aggregation rate (EXP5) has negligible effect. The apparent lack of sensitivity to large increase in aggregation yet sensitivity to shutting it off completely suggests the baseline aggregation rate may be unrealistically high.

[Figures 9–10: Output from EXP4 and EXP5 simulations — images not reproducible in markdown]

#### 4.2.5. Minimum Allowable $\lambda_s$: EXP6 and EXP7

Removing the lower limit for $\lambda_s$ (EXP6, set to 1 m$^{-1}$) has very little effect since the lowest values of $\lambda_s$ in CTR are usually above 500 m$^{-1}$ anyway. Increasing the limit to 1000 m$^{-1}$ (EXP7) imposes smaller mean snow sizes in the melting layer, giving slower fall velocities and faster melting rates — very similar to turning off aggregation (EXP4).

[Figures 11–12: Output from EXP6 and EXP7 simulations — images not reproducible in markdown]

#### 4.2.6. N₀s Temperature Sensitivity: EXP8 and EXP9

Prescribing initial $N_{0s}$ from a colder temperature (EXP8, −7.5°C) gives larger initial $N_s$ and $q_s$, resulting in larger precipitation rates and a slightly shorter transition period. The reverse holds for EXP9 (−2.5°C).

[Figures 13–14: Output from EXP8 and EXP9 simulations — images not reproducible in markdown]

---

## 5. Discussion

### 5.1. Implications of Results

The sensitivity tests clearly indicate that the timing and duration of the precipitation phase transition can be sensitive to details in the parameterization of snow. A high-resolution NWP model using a similar BMS may have similar sensitivity and will thus be subject to similar uncertainties in forecasting phase transitions.

An important limitation of the MY2 scheme (and most BMSs) is the treatment of melting. When snow melts, the melted portion immediately becomes rain. In nature, a snowflake retains the liquid portion from melted mass until it collapses into a single drop (Knight 1979). This means the scheme systematically overestimates the mixed-phase transition period. A modification to MY2 has been implemented to estimate the liquid fraction of partially melted snow and adjust fall velocities accordingly; preliminary tests indicate a more realistic transition period.

### 5.2. Potential Application of 1D Model as a Forecasters' Tool

The 1D model is extremely economical — a single simulation takes only a few seconds on a desktop computer. Two potential applications:
1. **Ensemble system** — run large numbers of members with perturbed microphysics parameters or initial conditions
2. **What-if experiments** — forecasters can rapidly test different scenarios for a given forecast situation

Environment Canada forecasters explored the possibility of using this 1D modeling system as an operational tool for cases with expected large high-resolution NWP model errors.

---

## 6. Conclusion

A simple 1D kinematic model coupled to a two-moment microphysics scheme was used to simulate the surface precipitation phase transition, based on a case from the Vancouver 2010 Winter Olympics. Sensitivity tests showed that:

- The timing and duration of the precipitation phase change can be quite sensitive to parameterization details of specific snow processes
- Fastest phase transitions result from: larger snow fall speeds, turning off aggregation, or imposing a high minimum $\lambda_s$ constraint
- The number of prognostic moments affects size sorting and hence the sedimentation profile

Users of high-resolution model output should be conscientious of these inherent uncertainties.

---

## Appendix 1: Description of the 1D Kinematic Model

The 1D model solves the mass divergence form of the continuity equation:

$$\frac{\partial(\rho W_x)}{\partial t} + \nabla \cdot (\rho W_x \vec{U}) = S_1$$

for each prognostic hydrometeor variable $W_x$, where $W$ is either $q$ or $N'$, the hydrometeor mixing ratio or total number mixing ratio, respectively. Using the anelastic approximation $\rho = \rho_0(z)$, the tendency equation becomes:

$$\frac{\partial W_x}{\partial t} + w \frac{\partial W_x}{\partial z} = -W_x \frac{\partial w}{\partial z} - W_x w \frac{\partial \ln \rho_0}{\partial z} + S_x$$

A forward-in-time/backward-in-space Eulerian advection scheme is used. The vertical motion profile follows a half sine wave:

$$w(k) = w_{max} \sin\left[\pi \frac{z(k) - z(n_k)}{H - z(1)}\right]$$

Temperature evolves by advection plus adiabatic ascent/descent. The model uses $n_k = 47$ evenly spaced levels with $\Delta z = 35$ m.

---

## Appendix 2: Overview of the Microphysics Scheme (MY2)

The BMS (Milbrandt and Yau 2005a,b) has prognostic equations for the mass mixing ratio, total number concentration, and radar reflectivity ($q_x$, $N_x$, and $Z_x$) for six categories: cloud, rain, ice, snow, graupel, and hail. The PSD of each category is a complete gamma function:

$$N_x(D) = N_{0x} D^{\lambda_x} e^{-\kappa_x D}$$

where $N_{0x}$, $\kappa_x$, and $\lambda_x$ are the intercept, slope, and shape parameters.

In the two-moment fixed-$\lambda_x$ version (MY2), $\lambda_x = 0$ for $x = i, r, s, g, h$ and $\lambda_x = 3$ for cloud droplets.

**Mass–diameter relation:**
$$m_x(D) = c_x D^{d_x}$$

For snow: $c_s = 0.1597$, $d_s = 2.078$ (MKS), implying a non-constant bulk density inversely proportional to $D$.

**Fall velocity–diameter relation:**
$$V_x(D) = c \cdot a_x D^{b_x}$$

where $c = (\rho_0/\rho)^{0.5}$ is the air density correction factor.

---

## Appendix 3: Calculations of Initial Snow Field

The initial reflectivity factor for snow $Z_s$ relates to the equivalent reflectivity $Z_{es}$ by:

$$Z_{es} = \frac{|K|^2_i}{|K|^2_w} \left(\frac{\rho_w}{\rho_i}\right)^2 \frac{c_s^2}{c_r^2} Z_s$$

where $|K|^2_i/|K|^2_w = 0.189$, $(\rho_w/\rho_i)^2 = 1.189$, and $c_r = (\pi/6)\rho_w$.

Given the observed 25 dBZ at 1600 m AGL and $T = -5°C$, $N_{0s}$ is estimated from the Thompson (2004) temperature relation:

$$N_{0s} = \min\left(2 \times 10^8,\; 2 \times 10^6 \exp[0.12 \cdot \min(0.001,\; T - 273.15)]\right)$$

This yields initial conditions $q_s = 0.45$ g kg$^{-1}$ and $N_s = 3115$ m$^{-3}$ for CTR.

---

## References

Brimelow, J. C., G. W. Reuter, R. Goodson, and T. W. Krauss, 2006: Spatial forecasts of maximum hail size using prognostic model soundings and HAILCAST. *Wea. Forecasting*, **21**, 206–219.

Ferrier, B. S., 1994: A double-moment multiple-phase four-class bulk ice scheme. Part I: Description. *J. Atmos. Sci.*, **51**, 249–280.

Gultepe, I., and Coauthors, 2012: Roundhouse (RND) Mountain Top research site: Measurements and uncertainties for winter alpine weather conditions. *J. Pure Appl. Geophy.*, in press.

Heymsfield, A. J., P. Field, and A. Bansemer, 2008: Exponential size distributions for snow. *J. Atmos. Sci.*, **65**, 4017–4031.

Isaac, G. A., and Coauthors, 2012: Science of Nowcasting Olympic Weather for Vancouver 2010 (SNOW-V10): A World Weather Research Programme project. *J. Pure Appl. Geophy.*, in press.

Knight, C. A., 1979: Observations of the morphology of melting snow. *J. Atmos. Sci.*, **36**, 1123–1130.

Kong, F., and Coauthors, 2011: Storm-scale ensemble forecasting for the NOAA Hazardous Weather Testbed. Sixth European Conf. on Severe Storms.

Lin, Y. L., R. Farley, and H. D. Orville, 1983: Bulk parameterization of the snow field in a cloud model. *J. Climate Appl. Meteor.*, **22**, 1065–1092.

Liu, C., K. Ikeda, G. Thompson, R. Rasmussen, and J. Dudhia, 2011: High-resolution simulations of wintertime precipitation in the Colorado Headwaters region. *Mon. Wea. Rev.*, **139**, 3533–3553.

Locatelli, J. D., and P. V. Hobbs, 1974: Fall speeds and masses of solid precipitation particles. *J. Geophys. Res.*, **79**, 2185–2197.

Mailhot, J., and Coauthors, 2012: An experimental 1-km resolution forecast model during the Vancouver 2010 Winter Olympic and Paralympic Games. *J. Pure Appl. Geophy.*, in press.

Meyers, M. P., R. L. Walko, J. Y. Harrington, and W. R. Cotton, 1997: New RAMS cloud microphysics. Part II: The two-moment scheme. *Atmos. Res.*, **45**, 3–39.

Milbrandt, J. A., and M. K. Yau, 2005a: A multimoment bulk microphysics parameterization. Part I. *J. Atmos. Sci.*, **62**, 3051–3064.

Milbrandt, J. A., and M. K. Yau, 2005b: A multimoment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, **62**, 3065–3081.

Milbrandt, J. A., and M. K. Yau, 2006: A multimoment bulk microphysics parameterization. Part IV: Sensitivity experiments. *J. Atmos. Sci.*, **63**, 3137–3159.

Milbrandt, J. A., and R. McTaggart-Cowan, 2010: Sedimentation error in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.

Milbrandt, J. A., M. K. Yau, J. Mailhot, S. Bélair, and R. McTaggart-Cowan, 2010: Simulation of an orographic precipitation event during IMPROVE-2. Part II: Sensitivity to the number of moments. *Mon. Wea. Rev.*, **138**, 625–642.

Milbrandt, J. A., A. Glazer, and D. Jacob, 2012: Predicting the snow-to-liquid ratio of surface precipitation using a bulk microphysics scheme. *Mon. Wea. Rev.*, **140**, 2461–2476.

Mitchell, D. L., 1996: Use of mass- and area-dimensional power laws for determining precipitation particle terminal velocities. *J. Atmos. Sci.*, **53**, 1710–1723.

Morrison, H., and J. A. Milbrandt, 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Wea. Rev.*, **139**, 1103–1130.

Morrison, H., G. Thompson, and V. Tatarski, 2009: Impact of cloud microphysics on the development of trailing stratiform precipitation in a simulated squall line. *Mon. Wea. Rev.*, **137**, 991–1007.

Morrison, H., J. A. Curry, and V. I. Khvorostyanov, 2005: A new double-moment microphysics parameterization. Part I. *J. Atmos. Sci.*, **62**, 1665–1677.

Passarelli, R. E., Jr., 1978: An approximate analytical model of the vapour deposition and aggregation growth of snowflakes. *J. Atmos. Sci.*, **35**, 118–124.

Seifert, A., and K. D. Beheng, 2001: A double-moment parameterization for simulating autoconversion, accretion and self-collection. *Atmos. Res.*, **59–60**, 265–292.

Thériault, J., R. Rasmussen, T. Smith, M. Brugman, J. Milbrandt, R. Mo, G. Isaac, P. Joe, J. Mailhot, and B. Denis, 2012: A case study of diabatic cooling of melting snow during the 2010 Vancouver Olympics. *Mon. Wea. Rev.*, in press.

Thompson, G., R. R. Rasmussen, and K. Manning, 2004: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part I. *Mon. Wea. Rev.*, **132**, 519–542.

Thompson, G., P. H. Field, R. M. Rasmussen, and W. D. Hall, 2008: Explicit forecasts of winter precipitation using an improved bulk microphysics scheme. Part II. *Mon. Wea. Rev.*, **136**, 5095–5115.

Walko, R. L., W. R. Cotton, M. P. Meyers, and J. Y. Harrington, 1995: New RAMS cloud microphysics. Part I: The one-moment scheme. *Atmos. Res.*, **38**, 29–62.

Westbrook, C. D., R. J. Hogan, and A. J. Illingworth, 2008: The capacitance of pristine ice crystals and aggregate snowflakes. *J. Atmos. Sci.*, **65**, 206–219.

Wu, L., and G. W. Petty, 2010: Intercomparison of bulk microphysics schemes for model simulations of polar lows. *Mon. Wea. Rev.*, **138**, 2211–2228.
