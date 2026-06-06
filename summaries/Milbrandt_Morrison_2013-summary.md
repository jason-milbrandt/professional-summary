# Summary: Milbrandt and Morrison (2013)

**Full citation:** Milbrandt, J. A., and H. Morrison, 2013: Prediction of graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429.
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2013
**Authors:** J. A. Milbrandt, H. Morrison
**DOI:** 10.1175/JAS-D-12-0204.1
**Author's role:** Tier 1 — Lead author; developed the prognostic graupel density approach and the Re–X density-dependent fall-speed framework

---

## Overview

This paper introduces a method to predict the bulk graupel density $\rho_g$ prognostically in the two-moment Milbrandt–Yau scheme, by adding a new prognostic variable: the bulk graupel volume mixing ratio $B_g = q_g/\rho_g$. Graupel fall speeds are now explicitly and physically dependent on the predicted $\rho_g$ via a Reynolds number–best number formulation. The modified scheme is tested in an idealized 2D kinematic squall-line model across a range of updraft strengths. The paper is a direct response to the Morrison–Milbrandt (2011) finding that graupel/hail treatment is the dominant source of inter-scheme uncertainty, and it explicitly frames itself as part of a "paradigm shift... toward adding physical degrees of freedom for a given hydrometeor type" — the conceptual and technical foundation that leads directly to the P3 scheme.

## Context and Motivation

The Morrison and Milbrandt (2011) intercomparison demonstrated that the treatment of rimed-ice density and fall speed is the primary driver of inter-scheme differences in supercell simulations: whether a scheme uses graupel- or hail-like parameters for its single rimed-ice category controls storm structure, cold pool strength, and surface precipitation far more than other scheme differences. The obvious fix — making graupel density prognostic — had been explored in spectral models (Farley 1987) and recently in the two-moment M2010 (Mansell et al. 2010) scheme, but not in MY. The Morrison and Milbrandt (2011) paper also showed that the MY scheme's hail initiation was too weak, causing the scheme to effectively be "graupel-only" in the baseline even when the hail category was present. This paper addresses both problems: it makes $\rho_g$ prognostic and directly links it to physically based fall speeds, enabling a single graupel category to represent the full range from low-density slowly-falling ice to high-density fast-falling graupel — without needing to pre-specify what type the simulation will produce.

## Key Scientific Contributions

- **Introduced prognostic bulk graupel density in MY2** by adding the bulk volume mixing ratio $B_g = q_g/\rho_g$ as a new conserved prognostic variable (following the approach of Connolly et al. 2006 and Mansell et al. 2010), from which $\rho_g$ is diagnosed as $q_g/B_g$ at each time step.
- **Derived physically based density-dependent fall speed parameters** $a_g(\rho_g)$ and $b_g(\rho_g)$ using the Reynolds number–best number approach (Khvorostyanov and Curry 2002; Mitchell and Heymsfield 2005), stored in a lookup table over $\rho_g = 50$–850 kg m⁻³. These cover the observed fall speeds from graupel-like snow to lump graupel and encompass the original MY2 fixed graupel and hail relations.
- **Demonstrated that density-dependent fall speeds are essential**: a simulation with prognostic $\rho_g$ but fixed fall speed parameters (PF) is nearly identical to the fixed-$\rho_g$ scheme (FF). The improvement only manifests when fall speeds are correctly linked to density.
- **Showed that a single rimed-ice category with prognostic $\rho_g$ can produce solid precipitation at the surface in strong-updraft simulations**, unlike the fixed-parameter single-category scheme where all graupel melts before reaching the ground.
- **Demonstrated that the prognostic-$\rho_g$ scheme also changes the stratiform/convective precipitation distribution**: more graupel mass is concentrated in the convective region (faster-falling high-density ice); less is transported to the stratiform region (slower-falling low-density ice), producing more realistic spatial precipitation patterns.
- **Identified and addressed the size-sorting problem** that arises from the now-large range of fall speeds: proposed a diagnostic shape parameter $m_g = (1000 D_g)^{0.075}$ as an interim solution, with the recommendation to derive $m_g = f(D_g)$ properly from three-moment simulations.
- **Showed that other scheme components now directly affect graupel** through their effect on $\rho_g$: cloud droplet number concentration (affecting drop size and hence rime density), snow $m$–$D$ parameters (affecting embryo density for snow-converted graupel), and rime density parameterization choice all have measurable impacts.
- **Explicitly framed the work as a paradigm shift** toward adding physical degrees of freedom per hydrometeor type rather than adding more fixed-parameter categories — directly anticipating P3 and citing Morrison and Grabowski (2008, 2010) and Harrington et al. (2013) in this context.

## Methods Summary

The modified MY2 scheme was tested in a 2D kinematic model (Szumowski et al. 1998; Grabowski 1999) with a prescribed squall-line flow field (strong convective updraft + mesoscale stratiform updraft/downdraft), initialized from the GATE sounding. Grid: 750 m horizontal, 250 m vertical, 240×12 km, 5-s time step. MPDATA advection. Peak updraft varied from 1–40 m s⁻¹ across simulations. Eleven simulation types compared (Table 3), including: control prognostic-$\rho_g$ with density-dependent fall speeds (PD); fixed-$\rho_g$/fixed fall speed (FF); prognostic-$\rho_g$ with fixed fall speed (PF); and with/without the separate hail category; plus sensitivity experiments varying snow $m$–$D$, CCN, rime density parameterization, and surface temperature.

## Key Results

- **PD-40 vs FF-40**: PD concentrates graupel in the convective region and produces solid precipitation at the surface; FF spreads graupel into the stratiform region and produces none at the surface.
- **PF-40 ≈ FF-40**: Prognostic $\rho_g$ without density-dependent fall speeds has almost no impact — confirms that correctly linking density to fall speed is the essential step.
- **PD-3 (weak updraft)**: Size-sorting problem causes unrealistic graupel at surface despite 3 m s⁻¹ updraft; requires the diagnostic $m_g$ fix.
- **PD-MU-3 (with diagnostic $m_g$)**: Size sorting controlled; graupel no longer reaches surface; PD-MU-40 is nearly identical to PD-40 — the fix works without degrading the strong-updraft case.
- **Snow $m$–$D$ parameters**: Affect the embryo density of graupel converted from snow — notably shifting the graupel distribution toward the stratiform region when the old spherical snow parameters are used.
- **Maritime vs continental CCN**: Larger maritime drops → larger rime density → larger $\rho_g$ → faster-falling graupel → more graupel mass in the convective region (weak-updraft case).

## Limitations and Caveats

- All tests are in an idealized 2D kinematic framework with no dynamics–microphysics feedback; the impacts in a full 3D dynamical model, where latent heat release and hydrometeor loading feed back to the flow, will likely be larger and need separate evaluation ⚠ verify.
- The diagnostic $m_g$ relation [Eq. 14] was chosen through trial and error rather than from physical first principles; a properly calibrated relation from a prognostic-$m_g$ (three-moment) scheme is needed.
- The rime density calculation uses the mean-mass drop diameter as a bulk approximation to the integral over the full drop size spectrum; a lookup-table based full-spectrum computation is planned for future work.
- Results are for warm-season convection; the behavior for winter storms with moderate riming (where the snow-to-graupel embryo density pathway is more important) is not examined.
- The graupel-only PD scheme, while capable of producing solid precipitation at the surface for strong updrafts, cannot simultaneously represent both high-density and lower-density rimed ice at the same grid point — separate categories for graupel and hail are still required for realistic hail simulation.

## Relation to Author's Research Program

This paper occupies a critical position in Milbrandt's research arc — it is the technical bridge between the Morrison–Milbrandt 2011 intercomparison and the P3 scheme. The 2011 paper diagnosed the problem (graupel/hail parameterization is the dominant uncertainty); this paper fixes it within the existing MY framework (make density prognostic, link it to physics-based fall speeds); and the P3 scheme (Morrison and Milbrandt 2015) goes the full logical step, replacing *all* discrete ice-phase categories with a single category whose properties (including rimed fraction and bulk density) evolve continuously from first principles.

Three specific threads from this paper run directly into P3: (1) the paradigm-shift framing — "physical degrees of freedom for a given hydrometeor type rather than more categories" is the defining principle of P3; (2) the suggestion of a four-variable graupel scheme ($q_g$, $B_g$, $N_g$, reflectivity) is essentially a prototype of what P3 implements for ice in general; (3) the need for a properly calibrated $m_g = f(D_g)$ from three-moment simulations directly motivates P3's property-prediction approach. The collaboration with Morrison ⚠ verify (his role vs Milbrandt's) continues the NCAR–ECCC partnership that began with the 2011 intercomparison and leads to the joint first-authored P3 papers.

## Impact and Citations

**Citation count:** ~62 (Semantic Scholar, retrieved 2026-06-06)

Cited comparably to the MY Parts III–IV (2006) papers, this paper's impact is primarily as a **conceptual and technical stepping stone to P3** ⚠ verify rather than as a widely deployed scheme modification in its own right ⚠ verify. It is cited in studies examining graupel/rimed-ice representation in bulk schemes ⚠ verify, and the prognostic bulk volume mixing ratio approach it uses was directly adopted in P3 (where the rime volume mixing ratio $V_r$ serves the same conceptual role for ice as $B_g$ does for graupel here). Its explicit framing of a "paradigm shift" away from fixed-category approaches is frequently cited in scheme-development discussions ⚠ verify.
