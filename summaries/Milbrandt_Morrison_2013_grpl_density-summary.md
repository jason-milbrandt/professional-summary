# Summary: Milbrandt and Morrison (2013)

**Full citation:** Milbrandt, J. A., and H. Morrison, 2013: Prediction of graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429, doi:10.1175/JAS-D-12-0204.1.
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2013
**Authors:** J. A. Milbrandt, H. Morrison
**DOI:** 10.1175/JAS-D-12-0204.1

---

## Overview

This paper introduces a method to prognostically predict the bulk density of graupel ($\rho_g$) within the two-moment Milbrandt–Yau (MY2) microphysics scheme, replacing the traditional fixed bulk density assumption. A new prognostic variable — the bulk graupel volume mixing ratio $B_g$ — is added to the scheme so that $\rho_g$ can be diagnosed and directly fed back into physically consistent, density-dependent terminal fall speeds. Idealized 2D kinematic model simulations show that this modification substantially changes the simulated spatial distribution of graupel and surface precipitation, and enables a single rimed-ice category to represent a realistically wide range of graupel characteristics without a priori parameter settings.

## Context and Motivation

Traditional bulk microphysics schemes (BMSs) parameterize graupel with a fixed bulk density of ~400 kg m$^{-3}$ and corresponding fixed fall speed parameters. In nature, graupel density ranges from ~50 to 900 kg m$^{-3}$ (Macklin 1962; Heymsfield and Pflaum 1985). Several studies (Gilmore et al. 2004; van den Heever and Cotton 2004; Morrison and Milbrandt 2011; Bryan and Morrison 2012) showed large sensitivity of simulated storms to these fixed parameters. Crucially, unless fall speed parameters are simultaneously modified with $\rho_g$, models give an incorrect sensitivity of mass-weighted fall speed to density changes. This work directly follows from the idealized supercell comparison study (Morrison and Milbrandt 2011) and extends the earlier approach of Mansell et al. (2010) by using a different, laboratory-based rime density parameterization and a physically based fall speed formulation from Mitchell and Heymsfield (2005).

## Key Scientific Contributions

- Introduced the **bulk graupel volume mixing ratio $B_g$** as a new conserved prognostic variable, enabling diagnosis of $\rho_g = q_g/B_g$ that evolves consistently during advection
- Implemented physically based, $\rho_g$-dependent graupel fall speed parameters $a_g(\rho_g)$ and $b_g(\rho_g)$ using the Reynolds number–best number (Re–X) approach of Khvorostyanov and Curry (2002) and Mitchell and Heymsfield (2005), stored in a lookup table
- Used the laboratory rime density parameterization of Cober and List (1993) to parameterize rime density as a function of temperature, impact speed, and collected drop size — accounting for the physical dependence of rime density on environmental conditions
- Demonstrated that the prognostic-$\rho_g$ modification (combined with density-dependent fall speeds) enables a single rimed-ice category to produce solid precipitation at the surface in the convective region for strong updrafts — something that a fixed-$\rho_g$ scheme cannot do without a separate hail category
- Identified an uncontrolled size-sorting problem introduced by the large new range of fall speeds, and proposed a diagnostic shape parameter $\mu_g = f(D_g)$ as a solution
- Showed that the snow $m$–$D$ relationship and aerosol distribution (through cloud droplet number) both affect $\rho_g$ indirectly, through their impact on embryo density and rime density respectively

## Methods Summary

The modified MY2 scheme is tested in a 2D kinematic model with a prescribed squall-line flow field representative of a mature mesoscale convective system, following Szumowski et al. (1998). Grid spacing: 750 m horizontal, 250 m vertical; 240 × 12 km domain; time step 5 s. The peak updraft speed $w_{peak}$ is varied between 1 and 40 m s$^{-1}$. Multiple simulation configurations compare: prognostic vs. fixed $\rho_g$; fixed vs. diagnostic fall speed parameters; graupel-only vs. graupel-plus-hail; and various sensitivity tests for the computation of $\rho_g$ (aerosol loading, snow $m$–$D$ parameters, rime density formulation).

## Key Results

- **PD-40 vs. FF-40 (strong updraft, graupel-only):** Prognostic $\rho_g$ produces dense, fast-falling graupel concentrated in the convective region with solid precipitation at the surface; fixed $\rho_g$ spreads graupel widely into the stratiform region with no solid surface precipitation
- **PF-40 (prognostic $\rho_g$, fixed fall speeds):** Nearly identical to FF-40 — **density-dependent fall speed parameters are essential** to realize the benefit of prognostic $\rho_g$; prediction of $\rho_g$ alone without fall speed feedback provides little improvement
- **PD-3 vs. FF-3 (weak updraft):** Prognostic $\rho_g$ introduces an unphysical graupel reaching the surface due to size sorting; FF-3 (fixed parameters) gives a more realistic result for weak convection
- **PD-MU-3 (diagnostic $\mu_g$):** The shape parameter correction effectively controls size sorting for weak updrafts without degrading strong-updraft results
- **Sensitivity tests:** The snow mass–diameter relation and cloud droplet number concentration (aerosol) both have significant effects on $\rho_g$ simulation, highlighting cross-category parameter dependencies

## Limitations and Caveats

- Tested only in a 2D kinematic framework; feedbacks between microphysics and dynamics (latent heat, hydrometeor loading) are absent
- The diagnostic $\mu_g$ relationship is arbitrary and would benefit from calibration against a three-moment scheme
- The impact velocity approximation overestimates somewhat because stagnation pressure is neglected
- Rime density formulation from Cober and List (1993) is based on laboratory measurements; applicability to all natural conditions is uncertain

## Relation to Author's Research Program

This paper sits at the conceptual bridge between the MY2 multimoment scheme family and the P3 scheme. It continues the theme from the MY2 papers of adding physical degrees of freedom to the representation of rimed ice, moving away from fixed prescribed categories. The approach is explicitly cited in Morrison and Milbrandt (2015) as the direct precursor to P3's treatment of rime density and density-dependent fall speeds. The introduction of $B_g$ as a conserved prognostic variable tracking particle volume is the same structural idea that underlies $B_{rim}$ in P3. This paper thus represents an important intermediate step in the paradigm shift from prescribed-category BMSs to property-predicting schemes.

## Impact and Citations

**Citation count:** ~62 (Semantic Scholar, retrieved 2026-06-06)

With 62 citations, this is a moderately well-cited paper with solid impact within the microphysics community. It is primarily cited by: (1) subsequent work on P3 (Morrison and Milbrandt 2015a,b) which explicitly builds on the prognostic $\rho_g$ concept; (2) studies examining the representation of rimed ice in bulk schemes; and (3) microphysics comparisons and sensitivity analyses in the WRF community. The approach of using a predicted bulk volume mixing ratio alongside mass and number mixing ratios to diagnose density has been adopted or extended in subsequent schemes, including P3 where the concept directly generalizes to the rime volume $B_{rim}$. ⚠ verify that specific later schemes beyond P3 adopted the prognostic-$B_g$ approach.
