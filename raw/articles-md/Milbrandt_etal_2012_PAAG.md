# Modeling the Phase Transition Associated with Melting Snow in a 1D Kinematic Framework: Sensitivity to the Microphysics

**Authors:** J. A. Milbrandt¹, J. Thériault², and R. Mo³
¹ Atmospheric Numerical Prediction Research, Environment Canada, Montreal, Canada
² Université du Québec à Montréal, Montreal, Canada
³ National Laboratory for Coastal and Mountain Meteorology, Environment Canada, Vancouver, Canada

**Journal:** *Pure and Applied Geophysics*, **171**, 303–322 (2014 in print; published online 10 August 2012)

**DOI:** 10.1007/s00024-012-0552-y

**Note on PDF files:** This paper exists as two PDFs in the project library: `Milbrandt_etal2012_PAAG.pdf` (the online-first 2012 version) and `Milbrandt_etal_2012-1Dsnowmelting.pdf` (the final print 2014 version). They are the same paper; this markdown is based on the final print version.

---

## Abstract

A simple 1D kinematic cloud model coupled to a two-moment bulk microphysics scheme is used to perform quasi-idealized simulations of snow, with a prescribed upper boundary snow field based on observed radar reflectivity and temperature, falling into a low-level melting layer. The model realistically simulates the formation of a nearly isothermal layer below the melting level, the surface precipitation rate, and the phase transition from liquid to solid, consistent with observations for this case. A series of test runs is performed to examine the sensitivity of modeling the timing and duration of the phase transition period to details of specific parameterization aspects related to snow in the microphysics scheme. The sensitivity tests include varying the number of prognostic moments, the mass–diameter relation, the fall velocity–diameter relation, the treatment of aggregation, and the lower limit for the slope of the size distribution. It is shown that the simulated transition period, for such a case with the initial melting level being close to the surface, can be quite sensitive to model parameters specified within realistic ranges and/or ranges within our physical understanding.

---

## 1. Introduction

Wintertime precipitation forecasting is inherently challenging due to the complex series of physical processes that ultimately determine surface precipitation. When the melting level is close to the surface, prediction of precipitation phase and timing of phase transitions is particularly challenging. The treatment of snow melting affects the low-level temperature structure, feeds back to the melting rate calculation, and in mountainous regions can induce downward air motion with significant effects on surface flow.

During the **Vancouver 2010 Winter Olympic and Paralympic Games**, accurate prediction of precipitation phase and intensity was critical. Environment Canada ran a special high-resolution (1-km) GEM configuration in real time for the Vancouver–Whistler region (Mailhot et al. 2012). Numerous studies have shown sensitivity to the BMS (e.g., Liu and Colle 2011; Morrison and Milbrandt 2011; Wu and Petty 2010) and to the number of prognostic moments (e.g., Milbrandt and Yau 2006; Morrison et al. 2009; Milbrandt et al. 2010). Recent work has highlighted sensitivity to specific assumptions in specific processes.

This study examines, through simple 1D kinematic model simulations using a two-moment BMS, the sensitivity of basic assumptions in the parameterization of snow to the diabatic cooling and surface precipitation phase change for snow falling into a near-surface melting layer.

## 2. Case overview

During the first weekend of the 2010 Vancouver Games (13–14 February 2010), a heavy precipitation event occurred as an intense frontal system swept across the BC coast. Widespread snow was reported on Whistler Mountain with periods of rain at the base. The 0000 UTC sounding at VOC showed the freezing level at ~500 m AGL. A nearly isothermal layer formed by 0600 UTC. A shift from upslope to downslope valley-mountain flow was observed by 0300 UTC, hypothesized to be diabatically induced from melting snow (Thériault et al. 2012). The surface temperature dropped ~5°C to ~1°C as melting precipitation cooled the air.

[Figure 1: Orography in the Whistler Mountain region with station locations — image not reproducible in markdown]
[Figure 2: Observed radar reflectivity and Doppler wind velocity at 0000 and 0300 UTC 14 February 2010 — image not reproducible in markdown]
[Figure 3: Observed soundings at 0000 and 0600 UTC 14 February 2010 at VOC — image not reproducible in markdown]
[Figure 4: Precipitation rate from FD12P optical sensor and observed surface temperature at VOT station — image not reproducible in markdown]

## 3. Description of modeling system

The modeling system is a simple **1D kinematic cloud model** coupled to the two-moment version of the Milbrandt and Yau (2005a,b) microphysics scheme (MY2), the same BMS used in the real-time high-resolution NWP runs during the Games. The 1D model uses a single sounding, a prescribed snow field above the melting level, and a zero vertical motion field. Key settings: model top at 1640 m AGL; 47 evenly-spaced levels; vertical grid spacing 35 m; time step 10 s.

For the simulations, the model top was at 1640 m AGL. The observed radar reflectivity of 25 dBZ at 1600 m AGL and air temperature of −5°C at VOC were used to derive the initial and boundary condition snow field: $q_s = 0.45$ g kg⁻¹ and $N_s = 3115$ m⁻³ (see Appendix 3 for details). Each simulation was integrated for 8 h to capture the entire phase transition period.

**List of sensitivity runs (Table 1):**

| Experiment | Description |
|---|---|
| CTR | Control run; baseline two-moment MY2 |
| EXP1 | One-moment for snow |
| EXP2 | m–D parameters: $c_s = (\pi/6)\rho_s$ ($\rho_s = 100$ kg m⁻³), $d_s = 3$ (original spherical) |
| EXP3 | V–D parameters from Ferrier (1994) (slower falling snow) |
| EXP4 | Snow aggregation off |
| EXP5 | Snow aggregation rate doubled |
| EXP6 | $\kappa_{s,min} = 1$ m⁻¹ (no effective lower limit) |
| EXP7 | $\kappa_{s,min} = 1000$ m⁻¹ (more stringent upper size limit) |
| EXP8 | $N_{0s} = f(−2.5°C)$ (colder temperature for upper boundary) |
| EXP9 | $N_{0s} = f(−7.5°C)$ (warmer temperature for upper boundary) |

**Snow parameters in baseline MY2 (Table 2):** $a_s = 11.72$, $b_s = 0.41$, $c_s = 0.1597$, $d_s = 2.078$, $\kappa_{s,min} = 500$ m⁻¹.

## 4. Results

### 4.1. CTR simulation

Snow sediments from 1600 m AGL, begins melting at ~500 m AGL (~15 min into simulation). Temperature below the melting level decreases as diabatic cooling from melting increases. First precipitation reaches the ground after ~20 min as rain. A small amount of snow begins arriving at the surface by ~25 min; a period of ~60–340 min with both rain and snow (each >0.1 mm h⁻¹) at the surface, during which $T_{sfc}$ drops from 4°C to ~0°C. CTR realistically simulates: (a) formation of a nearly isothermal layer below 500 m AGL by ~360 min (matching the VOC sounding at 0600 UTC); (b) surface precipitation rates of 1–2 mm h⁻¹ at VOT. The CTR simulation thus provides a sufficient degree of realism for sensitivity experiments.

[Figure 5: Output from CTR simulation — time–height plots of $q_s$, $q_r$, $T$, melting cooling rate, and surface time series — image not reproducible in markdown]

### 4.2. Sensitivity tests

**EXP1 (one-moment snow):** Similar to 1D sedimentation-only experiments (MY05a; Milbrandt and McTaggart-Cowan 2010): the leading edge falls slower but mass is more evenly distributed in one-moment. Stronger cooling rate in EXP1 (except at the very leading edge). Delayed onset of snow at surface (until ~150 min vs starting ~20 min in CTR). Surface temperature drops to 0°C ~220 min sooner. Results are sensitive to how $N_s$ (or $N_{0s}$) is prescribed in the one-moment configuration.

**EXP2 (original $m$–$D$ parameters):** Little effect on snow melting simulation. Different impacts on snow growth processes (Thompson and Field 2008; Milbrandt et al. 2012).

**EXP3 (slower V–D from Ferrier 1994):** Onset of surface precipitation slightly delayed, but phase transition period greatly increased — slower-falling snow has more time to melt to rain before reaching the surface, so the diabatic cooling occurs more slowly and the surface temperature drops much more slowly. The choice of snow V–D parameters significantly impacts the phase transition rate.

**EXP4 (aggregation off):** Combined effects of reduced fall velocities and increased melting rates cause increased cooling compared to CTR. After ~120 min, the rate of surface temperature decrease becomes considerably faster and the entire phase transition period is much shorter.

**EXP5 (aggregation doubled):** Differences compared to CTR are very small. The apparent lack of sensitivity to large increase in aggregation yet sensitivity to shutting it off completely suggests the baseline aggregation rate may be unrealistically high in situations of phase transition.

**EXP6 ($\kappa_{s,min} = 1$ m⁻¹):** Very little effect for this case since the lowest $\kappa_s$ in CTR stays above 500 m⁻¹ anyway.

**EXP7 ($\kappa_{s,min} = 1000$ m⁻¹):** More stringent limit on mean snow size causes increased diabatic cooling rate, delays onset of snow at surface, and reduces the phase transition period — smaller mean sizes in the melting layer → slower fall velocities → faster melting rates.

**EXP8/EXP9 (colder/warmer upper boundary $N_{0s}$):** Changing the snow field initialization temperature affects the prescribed $N_{0s}$, hence $N_s$ and $q_s$, with corresponding changes in precipitation rates and transition timing. Illustrates the 1D model's utility as a "what-if" forecasting tool.

## 5. Discussion

### 5.1. Implications of results

The sensitivity tests indicate that the timing and duration of the precipitation phase transition from snow to rain when the melting level is near the surface can be quite sensitive to details in the parameterization of snow in the microphysics scheme. An implication is that a high-resolution NWP model using a similar BMS may have similar sensitivity and uncertainties. Approaches to address this include: (a) calibrating the scheme to closely reproduce a detailed model or observations; (b) ensemble approaches with perturbed microphysics parameters.

A key limitation common to all BMS configurations: the model has an unrealistically long mixed-phase period (simultaneous rain and snow), because the BMS does not represent partially melted snow — when snow melts, the resulting liquid immediately becomes rain, rather than remaining as liquid on the snowflake surface and gradually increasing the fall speed and density. The MY2 scheme has been recently modified to estimate the liquid fraction of partially melted snow and adjust fall velocities accordingly; preliminary tests show a more realistic phase transition period. Results with this modification will be reported in a future paper.

### 5.2. Potential application of 1D model as a forecasters' tool

Since a single 1D simulation takes only a few seconds on a single-processor desktop, a forecaster could easily perform a large number of "what if" experiments, varying initial snow field conditions or microphysics parameters. Two potential applications: (1) as an ensemble system with perturbed parameters; (2) as an interactive tool for forecasters to test sensitivity in real-time operational situations where high-resolution NWP models are expected to have large errors and uncertainties (forecasters at Environment Canada are exploring this possibility).

## 6. Conclusion

A simple 1D kinematic model coupled to a two-moment microphysics scheme was used to simulate the surface precipitation phase transition for a case during the Vancouver 2010 Winter Olympics. Sensitivity tests varied: number of prognostic moments (EXP1), $m$–$D$ parameters (EXP2), $V$–$D$ parameters (EXP3), aggregation treatment (EXP4–5), and the minimum allowable slope parameter $\kappa_{s,min}$ (EXP6–7).

When the melting level is relatively close to the ground (as is common in mountainous coastal regions), the predicted timing and duration of the precipitation phase change can be quite sensitive to parameterization details. Users of high-resolution model output should be conscientious of these inherent uncertainties. Despite the 1D framework's limitations (no dynamics, no dynamical feedback), the use of the same microphysics scheme as in the operational model makes the results directly interpretable.

---

## Appendices

**Appendix 1: The 1D model.** A forward-in-time/backward-in-space Eulerian advection scheme solves the mass divergence form of the continuity equation for each prognostic hydrometeor variable. Temperature tendency from adiabatic ascent/descent and microphysics (latent heating/cooling) are computed at each time step.

**Appendix 2: Overview of MY2 scheme.** Six hydrometeor categories, two-moment (fixed $m_x = 0$ for all categories except cloud [$m_c = 3$]), gamma PSD, power-law $m$–$D$ and $V$–$D$ relations. Recent modifications to snow category described in Milbrandt et al. (2012).

**Appendix 3: Initial and boundary condition snow field.** The observed $Z = 25$ dBZ at 1600 m AGL and $T = -5°C$ are used to derive $q_s$ and $N_s$: the reflectivity–SWC–PSD closure equations (using Thompson et al. 2004 $N_{0s}$–$T$ relation) yield $q_s = 0.45$ g kg⁻¹ and $N_s = 3115$ m⁻³.

---

*Acknowledgments: Observational data obtained during the SNOW-V10 field campaign. Open access under Creative Commons Attribution License.*
