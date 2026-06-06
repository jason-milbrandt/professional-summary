# Summary: Morrison and Milbrandt (2015a) and Morrison et al. (2015b) — P3 Parts I & II

**Note:** This is a combined summary for the two-part P3 series. Parts I and II were submitted together, accepted together, and published in the same journal issue (January 2015). They form a single coherent contribution introducing and evaluating the P3 scheme.

---

## Part I

**Full citation:** Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311, doi:10.1175/JAS-D-14-0065.1.
**Authors:** H. Morrison, J. A. Milbrandt

## Part II

**Full citation:** Morrison, H., J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II: Case study comparisons with observations and other schemes. *J. Atmos. Sci.*, **72**, 312–339, doi:10.1175/JAS-D-14-0066.1.
**Authors:** H. Morrison, J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, G. Thompson

**Journal:** Journal of the Atmospheric Sciences
**Year:** 2015
**DOI Part I:** 10.1175/JAS-D-14-0065.1
**DOI Part II:** 10.1175/JAS-D-14-0066.1

---

## Overview

These two companion papers introduce the **Predicted Particle Properties (P3) microphysics scheme**, a fundamentally new approach to bulk ice-phase microphysics parameterization. Instead of partitioning ice into predefined categories (cloud ice, snow, graupel, hail) with prescribed characteristics, P3 uses a single "free" ice-phase category with four conserved prognostic variables — total ice mass, rime mass, rime volume, and number — allowing the physical properties of ice particles to evolve freely in time and space. Part I describes the scheme and presents idealized 2D squall-line tests; Part II evaluates P3's practical performance in 3D WRF simulations against two well-observed cases (a midlatitude squall line and a winter orographic event) with intercomparison against nine other schemes.

## Context and Motivation

The ice-phase parameterization problem in bulk microphysics schemes is inherently ill-posed when using predefined categories: each category has fixed prescribed characteristics (density, fall speeds, $m$–$D$ relations) that cannot accurately represent the full range of ice types in nature. Conversion between categories (e.g., cloud ice → snow → graupel) is artificial, parameter-dependent, and physically unjustifiable. Earlier advances — including the two-moment MY2 scheme (Milbrandt and Yau 2005a,b), the Morrison–Grabowski (2008) bulk scheme that separately prognoses rimed and vapor-deposited ice mass, and the prognostic graupel density approach of Milbrandt and Morrison (2013) — progressively moved toward predicting particle properties rather than prescribing them. The P3 scheme generalizes this principle: all ice-phase behavior arises from four physical prognostic quantities, completely eliminating the need for ad hoc conversion processes. The approach is directly inspired by the work of Hashino and Tripoli (2007) in bin schemes and Morrison and Grabowski (2008) in bulk schemes.

## Key Scientific Contributions

### Conceptual/Structural:
- Proposed a new paradigm for ice-phase microphysics parameterization: **predict bulk particle properties** using a single free category with four prognostic variables ($q_i$, $N_i$, $q_{rim}$, $B_{rim}$), rather than partitioning ice into predefined species
- Derived the rime mass fraction $F_r = q_{rim}/q_i$ and predicted rime density $\rho_r = q_{rim}/B_{rim}$ as key predicted properties, from which particle density, size, and fall speed are computed self-consistently
- Developed a four-region ice particle $m$–$D$ relationship spanning: small spherical ice, large unrimed nonspherical ice, partially rimed crystals (with $F_r$-dependent density), and graupel (spherical, with predicted $\rho_g$)
- Implemented physically consistent particle fall speeds via the Re–X approach (Mitchell and Heymsfield 2005) with explicit dependence on the evolving $m$–$D$ and $A$–$D$ relationships

### Computational:
- Achieved computational efficiency through a lookup table approach: $N_0$, $\lambda$, and PSD moments are pre-calculated as a function of $q_i$, $N_i$, $F_r$, and $\rho_r$
- P3 is only ~11% and ~6% slower than the single-moment WSM6 scheme in WRF (squall-line and orographic cases respectively), faster than MY2 (by ~25–35%), despite its more sophisticated physical content

### Demonstrated behaviors:
- P3 simulates a wide variety of ice particle types (dense hail-like particles in convective cores; light, slow-falling aggregates in stratiform regions) with a single ice category, consistent with aircraft observations
- $F_r$ and $\rho_r$ exhibit no simple relationships with temperature, liquid water content, or updraft — owing to horizontal and vertical transport of ice away from its growth conditions — confirming the inadequacy of purely local diagnostic approaches
- For the squall line: representation of rimed-ice fall speed as hail-like (high $\rho_g$, high $V$) is critical for reproducing the narrow, intense leading convective edge; schemes using slower-falling graupel produce fundamentally wrong storm structure
- For orographic precipitation: P3's prediction of rimed-snow fall speed enhancement produces greater windward and less leeward precipitation than most schemes, consistent with observations; this arises from physically consistent prediction of $F_r$

## Methods Summary

**Part I (idealized):** WRF v3.4.1, 2D squall-line configuration, 1-km $\Delta x$, 80 vertical levels, 6-h integrations. Initialized from Weisman–Klemp analytic sounding with convective available potential energy ~2000 J kg$^{-1}$. Five sensitivity tests (BASE, r400, r900, FR0, FR1r400) vary $F_r$ and $\rho_r$ to isolate their impacts.

**Part II (real cases):**
- *Squall line (19–20 June 2007, Oklahoma):* 3D quasi-idealized WRF, 1-km $\Delta x$, 612 × 122 km$^2$, initialized from La mont/Norman, Oklahoma, soundings. Compared to KOUN dual-pol radar and 2DVD disdrometers.
- *Orographic (13–14 December 2001, IMPROVE-2 Pacific Northwest):* 3D real case, 3-km $\Delta x$, 1200 × 830 km$^2$, GFS Final analysis forcing. Compared to WSR-88D Portland, S-Pol radar, P-3 and Convair aircraft (IWC, LWC), and surface precipitation gauges.

Schemes compared: P3, MY2, MOR-G, MOR-H, NSSL, SBU-LIN, Thompson, WSM6, WDM6.

## Key Results

**Part I (idealized):**
- Single ice category in P3 reproduces the expected distribution of particle types in a squall line: dense hail-like ice in convective core ($F_r \approx 1$, $\rho_p \approx 300$–600 kg m$^{-3}$, $V_m \approx 5$–8 m s$^{-1}$), unrimed ice in anvil ($F_r \approx 0$, $\rho_p < 100$ kg m$^{-3}$), with particle characteristics varying continuously and non-locally
- Both $F_r$ and $\rho_r$ have large impacts on storm structure and surface precipitation; sensitivity to $F_r$ is greater than to $\rho_r$
- Setting $F_r = 0$ (FR0) yields unrealistically small fall speeds everywhere ($V_m < 1.7$ m s$^{-1}$), leading to massive ice mass aloft

**Part II (3D cases):**
- *Squall line:* P3 and MOR-H produce the observed narrow, intense convective leading edge; MOR-G and all other graupel-only schemes fail to do so. P3's advantage stems from predicting hail-like ($\rho_g > 700$ kg m$^{-3}$, $V_m > 10$ m s$^{-1}$) ice in the convective region. All schemes underpredict trailing stratiform precipitation.
- *Orographic:* P3 produces less leeward bias (mean lee precipitation ~35 mm vs. observations of 18 mm) compared to MOR-G, MOR-H, MY2 (~50–59 mm). P3's superior performance is directly traced to its prediction of increased fall speeds for lightly to moderately rimed snow on the windward slope.
- P3 is computationally faster than all schemes tested except WSM6 and SBU-LIN; its 7 prognostic variables are fewer than MY2's 12.

## Limitations and Caveats

- Single ice category cannot represent different ice types at the same grid point simultaneously; this limitation is most severe in deep strong updrafts lofting both graupel and newly nucleated ice to high altitudes — planned multiple-free-category extension addresses this
- Rime splintering (Hallett–Mossop process) is neglected to minimize the smearing of category properties
- The scheme must be tested on many more cases; cloud cover and radiative properties have not yet been evaluated
- Some uncertainty remains in parameters for aggregation and riming efficiencies; these are not unique to P3 but are shared with all bulk schemes

## Relation to Author's Research Program

These papers represent the culmination of a long sequence of Milbrandt's work on improving the representation of ice microphysics. The intellectual lineage runs directly through: MY2 Parts I and II (Milbrandt and Yau 2005a,b) → MY2 sensitivity studies (2006, 2010) → sedimentation errors (Milbrandt and McTaggart-Cowan 2010) → snow $m$–$D$ and snow-to-liquid ratio (Milbrandt et al. 2012) → prognostic graupel density (Milbrandt and Morrison 2013) → P3 (2015). The P3 scheme is co-developed with Morrison but Milbrandt brings the MY2 framework and its parameterization details (rime density, $m$–$D$ relations, fall speed approach) directly into the new design. P3 subsequently becomes one of the most widely used modern bulk microphysics schemes. Milbrandt's contribution is especially significant in the physical formulation of the rime volume budget, the density-dependent fall speeds, and the design of the single-category approach as a natural extension of the prognostic-$\rho_g$ work. ⚠ verify specific model implementations of P3 beyond WRF (e.g., GEM, CM1, E3SM).

## Impact and Citations

**Citation count (Part I):** ~511 (Semantic Scholar, retrieved 2026-06-06)
**Citation count (Part II):** ~211 (Semantic Scholar, retrieved 2026-06-06)

The P3 scheme papers are among the most highly cited papers in bulk cloud microphysics parameterization in the past decade. Part I's 511 citations make it one of Milbrandt's most impactful papers — a landmark contribution to the field. The scheme has been adopted in WRF and has been evaluated in numerous multi-scheme intercomparison studies. The P3 approach has influenced subsequent scheme development including the multi-category P3 extension (Milbrandt and Morrison 2016 ⚠ verify) and has been incorporated into the E3SM global climate model ⚠ verify. The scheme has been applied to a wide range of meteorological regimes including convection, orographic precipitation, tropical cyclones, and Arctic clouds. Part II's 211 citations reflect the broader community interest in the practical evaluation and comparison of microphysics schemes in WRF.
