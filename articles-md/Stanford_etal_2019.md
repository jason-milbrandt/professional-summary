# Stanford et al. (2019): Sensitivity of Simulated Deep Convection to a Stochastic Ice Microphysics Framework

**Full citation:** Stanford, M. W., Morrison, H., Varble, A., Berner, J., Wu, W., McFarquhar, G., and Milbrandt, J., 2019: Sensitivity of simulated deep convection to a stochastic ice microphysics framework. *J. Adv. Model. Earth Syst.*, **11**, 3362–3389. DOI: 10.1029/2019MS001730

---

## Abstract

Ice microphysics parameterizations in models must make major simplifications relative to observations, typically employing empirical relationships to represent average functional properties of particles. However, previous studies have established that ice particle properties vary even in similar cloud types and thermodynamic environments, and it remains unclear how this so-called "natural variability" impacts simulated deep convection. This uncertainty is addressed by implementing a stochastic framework into the Predicted Particle Properties (P3) microphysics scheme in the Weather Research and Forecasting model. The approach stochastically varies the coefficients of the mass-size (m-D) relationship ($m = aD^b$) for unrimed and partially rimed ice. Using guidance from aircraft in situ measurements obtained during the Midlatitude Continental Convective Clouds Experiment (MC3E), the scheme samples from distributions of the prefactor (a) and the exponent (b) of the m-D relationship. Simulations of two MC3E deep convective cases indicate that the stochastic m-D scheme produces considerable variability of anvil cirrus cloud optical depth (τ) distributions, even for the same ice water path (IWP). Thus, the stochastic scheme produces variable cloud radiative forcing that is independent of IWP. This τ-IWP relationship variability is nonexistent using the deterministic m-D ensemble. Additional sensitivity tests are performed in which the fall speed-size relationship ($V = cD^d$) is stochastically varied, resulting in variable precipitation amounts and rain rate distributions.

---

## 1. Introduction

Numerous studies have analyzed the sensitivity of simulated MCSs to microphysics representation because these systems have a large impact on weather and climate. Convective ice detrainment into the upper troposphere produces anvil cirrus shields that can significantly impact the atmosphere's radiation budget. Representing ice particle properties is challenging because current bulk microphysical parameterizations typically relate ice particle mass, terminal fall speed, and projected area to the maximum particle dimension through simple power laws with constant coefficients. Previous studies have shown that these parameters vary spatially and temporally even for similar thermodynamic and cloud conditions.

Two related aspects are addressed: (1) the effects of systematic model error, where a parameter is constant but set to a biased value; and (2) random model error, where a parameter exhibits spatiotemporal variations due to spatiotemporal inhomogeneities and uncertain flow dependence.

---

## 2. Scheme Development

### 2.1 P3 Microphysics Scheme

The stochastic framework is implemented within the Predicted Particle Properties (P3) bulk microphysics scheme (Milbrandt & Morrison, 2016; Morrison & Milbrandt, 2015). The P3 scheme includes one or more "free" ice categories. For each category, four prognostic ice variables — total ice mass, rime mass, rime volume, and number mixing ratios — allow evolution of various properties such as bulk density and fall speed.

The mass-size (m-D) relationship varies smoothly for up to four different size ranges of the PSD:
1. Small, spherical ice
2. Nonspherical, unrimed ice (grown by vapour diffusion and/or aggregation)
3. Partially rimed ice
4. Fully rimed ice (graupel or hail)

All m-D relationships follow a power law: $m = aD^b$.

The stochastic framework perturbs the empirical $a$ and $b$ parameters for nonspherical, unrimed ice and partially rimed ice. The deterministic scheme uses $b = 2.1$ and $a = 0.0386$ kg m$^{-b}$, consistent with the mean values in the stochastic scheme.

### 2.2 In Situ Observational Guidance

MC3E aircraft measurements provide the distributions of $a$ and $b$ used to guide the stochastic sampling. Parameters are varied spatially and temporally during simulations according to a prescribed spatiotemporal autocorrelation scale.

---

## 3. Experimental Design

Simulations are performed for two deep convection cases from MC3E (20 May 2011 squall line; 24 May 2011 bow echo) using the WRF model. Multiple ensemble configurations are compared:
- Control (nonstochastic P3)
- Stochastic m-D ensemble (parameter values sampled stochastically in time and space)
- Fixed-parameter ensemble (parameters constant within each simulation but varied among ensemble members)
- Initial/lateral boundary condition (ICBC) ensemble
- Grid-scale noise ensemble (small-amplitude potential temperature perturbations)

---

## 4. Key Results

- Domain-accumulated volumetric precipitation was only slightly affected by the stochastic m-D scheme; spread was small relative to the fixed-parameter and ICBC ensembles
- The stochastic m-D scheme produced considerable variability in anvil cirrus cloud optical depth (τ) for the same ice water path — variability that does not exist in the ICBC ensemble
- Fixed-parameter ensembles at the extremes of the observationally guided range had variability in median τ of up to 70 units; stochastic ensembles had spread in median τ of up to 15 units
- Cloud radiative forcing (CRF) variability in the stochastic m-D ensemble resulted from both IWP and ice particle size variability; in the stochastic V-D ensemble, CRF variability resulted almost entirely from IWP differences
- Cloud and precipitation structure is more sensitive to systematic model error (fixed-parameter ensemble) than random error (stochastic ensemble)
- Stochastic V-D perturbations produced larger variability in rain rate distributions than the stochastic m-D scheme

---

## 5. Discussion and Conclusions

A stochastic framework was implemented into the P3 microphysics scheme to account for natural variability of ice particle properties:
- The stochastic m-D scheme produces variability in cloud radiative forcing that is independent of IWP, which cannot be reproduced by the deterministic scheme
- Precipitation structure variability from stochastic microphysics is smaller than from ICBC perturbations
- The observed τ-IWP relationship variability (which varies from case to case) can be captured by the stochastic m-D scheme but not by nonstochastic simulations
- Results suggest including natural variability in ice microphysical parameters is important for representing variability in cloud radiative properties even when total cloud mass is the same

**Author contributions:** Not formally stated in paper, but Milbrandt is listed as 7th (last) author at ECCC; the P3 scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) serves as the basis for the stochastic implementation.

---

## References

[Selected key references]

- Morrison, H. and Milbrandt, J. A., 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Milbrandt, J. A. and Morrison, H., 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III. *J. Atmos. Sci.*, **73**, 975–995.
- Milbrandt, J. A. and Yau, M. K., 2005: A multi-moment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.
- Morrison, H. and Milbrandt, J., 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Weather Rev.*, **139**, 1103–1130.
