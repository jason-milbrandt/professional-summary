# Summary: Stanford et al. (2019)

**Full citation:** Stanford, M. W., Morrison, H., Varble, A., Berner, J., Wu, W., McFarquhar, G., and Milbrandt, J., 2019: Sensitivity of simulated deep convection to a stochastic ice microphysics framework. *J. Adv. Model. Earth Syst.*, **11**, 3362–3389. DOI: 10.1029/2019MS001730
**Journal:** Journal of Advances in Modeling Earth Systems
**Year:** 2019
**Authors:** McKenna W. Stanford, Hugh Morrison, Adam Varble, Judith Berner, Wei Wu, Greg McFarquhar, Jason Milbrandt
**DOI:** 10.1029/2019MS001730
**Author's role:** Tier 3 — Contributing co-author; the P3 microphysics scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) forms the basis of the stochastic framework implemented in this study; Milbrandt contributed as the scheme developer and domain expert

---

## Overview

This paper implements a stochastic framework into the P3 microphysics scheme within WRF to explore the impacts of "natural variability" in ice particle mass-size (m-D) relationships on simulated deep convective clouds. Rather than using fixed empirical coefficients as in standard bulk schemes, the approach stochastically varies the m-D coefficients spatially and temporally during a simulation, guided by aircraft in situ observations from the MC3E field campaign. The key finding is that stochastic m-D variability produces significant variability in anvil cirrus optical depth and cloud radiative forcing that is independent of ice water path — an effect that cannot be reproduced by deterministic simulations.

## Context and Motivation

Ice particle properties (mass, fall speed, projected area) in bulk microphysics schemes are typically represented by fixed empirical power laws whose coefficients are constant in time and space. However, observations show these properties vary significantly even in similar cloud types and thermodynamic environments. This "natural variability" means that the true range of cloud radiative impacts cannot be captured by any single deterministic simulation. The stochastic approach provides a physically motivated way to represent this uncertainty, guided by real observations rather than arbitrary perturbations.

## Key Scientific Contributions

- First application of stochastic microphysical parameter perturbations guided by aircraft in situ observations of ice particle m-D variability in deep convection simulations
- Demonstrated that stochastic m-D variability produces significant cloud optical depth (τ) variability for a given ice water path — a τ-IWP relationship variability that deterministic simulations cannot produce
- Showed that cloud and precipitation structure is more sensitive to systematic model error (fixed parameter bias) than to random natural variability (stochastic perturbations)
- Established that stochastic m-D perturbations produce CRF variability from both IWP and ice particle effective radius variability, while stochastic V-D perturbations produce CRF variability almost entirely through IWP (sedimentation)
- The observed case-to-case variability in the τ-IWP relationship can be captured by the stochastic m-D scheme but not by nonstochastic simulations

## Methods Summary

The stochastic framework was implemented into the P3 microphysics scheme in WRF. The scheme samples the prefactor ($a$) and exponent ($b$) of the ice m-D relationship from observationally derived distributions (MC3E aircraft data), with perturbations varying spatially and temporally according to a prescribed autocorrelation scale. Simulations were performed for two MC3E deep convective cases (20 May 2011 squall line; 24 May 2011 bow echo). Five ensemble configurations were compared: stochastic m-D, stochastic V-D, fixed-parameter, ICBC perturbation, and grid-scale noise ensembles. Results were evaluated against satellite and precipitation observations.

## Key Results

- Domain-accumulated precipitation: only slightly affected by stochastic m-D scheme; variability was smaller than from ICBC or fixed-parameter ensembles
- Anvil cirrus optical depth: stochastic m-D ensemble showed spread in median τ of up to 15 units; fixed-parameter ensemble showed up to 70 units; both less than ICBC ensemble's total τ spread
- The τ-IWP relationship variability (from case to case in observations) was captured by the stochastic m-D scheme but not by other ensemble approaches
- Stochastic V-D perturbations produced larger rain rate variability than stochastic m-D; median rain rates varied by up to 1.5–2 mm/hr in stochastic ensembles
- Cloud radiative forcing variability from stochastic m-D arises from both IWP and effective radius variability; V-D variability arises almost entirely from IWP differences

## Limitations and Caveats

- Only two MC3E deep convection cases were studied; generalizability to other storm types or regions is uncertain
- The stochastic framework was applied only to unrimed and partially rimed ice, not to graupel or small spherical ice
- The amplitude of systematic vs. random errors was implicitly assumed equal; in reality their relative magnitudes may differ
- Modifying the P3 lookup tables to incorporate stochastic m-D parameters required code changes beyond the standard WRF implementation, limiting immediate operational applicability

## Relation to Author's Research Program

Milbrandt contributed to this paper as the co-developer of the P3 microphysics scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016), which forms the foundation of the stochastic framework. P3's design — with continuously evolving ice particle properties derived from prognostic bulk variables — is uniquely suited for stochastic m-D parameterization because the m-D relationship already varies within each simulation based on the riming state of ice. The paper demonstrates a new research direction enabled by P3's flexible design: using it as a platform for stochastic physics experiments. The finding that cloud radiative forcing variability can be produced independently of IWP through m-D variability is scientifically significant for understanding uncertainty in climate projections driven by convective anvil properties. This work illustrates how the P3 scheme continues to attract research use beyond its original application to NWP.

## Impact and Citations

**Citation count:** ~19 (Semantic Scholar, retrieved 2026-06-06)

The paper occupies a niche at the intersection of stochastic physics parameterization and ice microphysics — an active area in climate and weather modelling. With 19 citations it has had moderate uptake. Its core finding — that ice particle m-D variability creates cloud radiative uncertainty independent of IWP — is directly relevant to GCM cloud-climate feedback studies and to the growing use of stochastic physics in NWP systems.
