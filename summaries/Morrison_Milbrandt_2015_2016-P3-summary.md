# Summary: Morrison and Milbrandt (2015a), Morrison et al. (2015b), and Milbrandt and Morrison (2016) — P3 Parts I, II & III

**Note:** This is a combined summary for the three-part P3 series. Parts I and II were submitted together, accepted together, and published in the same journal issue (January 2015). Part III (2016) directly extends the scheme introduced in Parts I and II to multiple free ice categories, resolving the primary limitation identified in the earlier papers. All three form a single coherent contribution introducing, evaluating, and extending the P3 scheme.

---

## Part I

**Full citation:** Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311, doi:10.1175/JAS-D-14-0065.1.
**Authors:** H. Morrison, J. A. Milbrandt

## Part II

**Full citation:** Morrison, H., J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II: Case study comparisons with observations and other schemes. *J. Atmos. Sci.*, **72**, 312–339, doi:10.1175/JAS-D-14-0066.1.
**Authors:** H. Morrison, J. A. Milbrandt, G. H. Bryan, K. Ikeda, S. A. Tessendorf, G. Thompson

## Part III

**Full citation:** Milbrandt, J. A., and H. Morrison, 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III: Introduction of multiple free categories. *J. Atmos. Sci.*, **73**, 975–995, doi:10.1175/JAS-D-15-0204.1.
**Authors:** J. A. Milbrandt, H. Morrison

**Journal:** Journal of the Atmospheric Sciences
**Years:** 2015 (Parts I & II), 2016 (Part III)
**DOI Part I:** 10.1175/JAS-D-14-0065.1
**DOI Part II:** 10.1175/JAS-D-14-0066.1
**DOI Part III:** 10.1175/JAS-D-15-0204.1
**Author's role:** Tier 1 (co-lead) for Parts I & II — co-developed the P3 scheme on equal intellectual footing with Morrison, contributing the MY2 framework, rime-volume budget formulation, and density-dependent fall-speed approach; Morrison's first authorship for Parts I and II is nominal. Tier 1 (lead) for Part III — first author; developed the multiple-free-category extension and all associated algorithmic design choices.

---

## Overview

These three companion papers introduce and extend the **Predicted Particle Properties (P3) microphysics scheme**, a fundamentally new approach to bulk ice-phase microphysics parameterization. Instead of partitioning ice into predefined categories (cloud ice, snow, graupel, hail) with prescribed characteristics, P3 uses one or more "free" ice-phase categories with four conserved prognostic variables each — total ice mass, rime mass, rime volume, and number — allowing the physical properties of ice particles to evolve freely in time and space.

**Part I** describes the single-category scheme and presents idealized 2D squall-line tests. **Part II** evaluates P3's practical performance in 3D WRF simulations against two well-observed cases (a midlatitude squall line and a winter orographic event) with intercomparison against nine other schemes. **Part III** resolves the primary limitation of the single-category design — "property dilution" — by extending P3 to a user-specified number of free categories ($n_{Cat}$), enabling distinct ice populations to coexist at the same grid point without artificial blending of their bulk properties.

## Context and Motivation

The ice-phase parameterization problem in bulk microphysics schemes is inherently ill-posed when using predefined categories: each category has fixed prescribed characteristics (density, fall speeds, $m$–$D$ relations) that cannot accurately represent the full range of ice types in nature. Conversion between categories (e.g., cloud ice → snow → graupel) is artificial, parameter-dependent, and physically unjustifiable. Earlier advances — including the two-moment MY2 scheme (Milbrandt and Yau 2005a,b), the Morrison–Grabowski (2008) bulk scheme that separately prognoses rimed and vapor-deposited ice mass, and the prognostic graupel density approach of Milbrandt and Morrison (2013) — progressively moved toward predicting particle properties rather than prescribing them. The P3 scheme generalizes this principle: all ice-phase behavior arises from four physical prognostic quantities, completely eliminating the need for ad hoc conversion processes. The approach is directly inspired by the work of Hashino and Tripoli (2007) in bin schemes and Morrison and Grabowski (2008) in bulk schemes.

The remaining limitation of the single-category design (Parts I & II) was that only one ice population could exist at a given grid point. In nature, multiple ice populations with different growth histories coexist: gravitational size sorting brings faster-falling ice from above, rime splintering nucleates tiny crystals in regions of large graupel, and frozen raindrops form alongside vapor-grown crystals. Forcing all of these into one free category smears their bulk properties (mean size, density, fall speed), degrading subsequent microphysical evolution. Part III directly addresses this "dilution" problem by introducing multiple free categories — a third path distinct from both single-category P3 and traditional multi-predefined-category schemes.

## Key Scientific Contributions

### Parts I & II — Conceptual/Structural:
- Proposed a new paradigm for ice-phase microphysics parameterization: **predict bulk particle properties** using a single free category with four prognostic variables ($q_i$, $N_i$, $q_{rim}$, $B_{rim}$), rather than partitioning ice into predefined species
- Derived the rime mass fraction $F_r = q_{rim}/q_i$ and predicted rime density $\rho_r = q_{rim}/B_{rim}$ as key predicted properties, from which particle density, size, and fall speed are computed self-consistently
- Developed a four-region ice particle $m$–$D$ relationship spanning: small spherical ice, large unrimed nonspherical ice, partially rimed crystals (with $F_r$-dependent density), and graupel (spherical, with predicted $\rho_g$)
- Implemented physically consistent particle fall speeds via the Re–X approach (Mitchell and Heymsfield 2005) with explicit dependence on the evolving $m$–$D$ and $A$–$D$ relationships

### Parts I & II — Computational:
- Achieved computational efficiency through a lookup table approach: $N_0$, $\lambda$, and PSD moments are pre-calculated as a function of $q_i$, $N_i$, $F_r$, and $\rho_r$
- P3 is only ~11% and ~6% slower than the single-moment WSM6 scheme in WRF (squall-line and orographic cases respectively), faster than MY2 (by ~25–35%), despite its more sophisticated physical content

### Part III — Multiple Free Categories:
- **First multiple-free-category bulk microphysics scheme**: $n_{Cat}$ is user-specified; each category can represent any ice type, and different types can coexist at the same grid point simultaneously
- **New algorithmic elements for multicategory operation**: (1) destination category selection for new ice based on mean-mass diameter difference ($\Delta D_{init}$ threshold); (2) inter-category gravitational collection with a lookup-table double integral; (3) merging of sufficiently similar categories (diameter difference $<150\,\mu$m and density difference $<100$ kg m$^{-3}$) to free capacity for new ice
- **Rime splintering requires $n_{Cat}\geq2$**: For a single ice category, including rime splintering is actively detrimental due to dilution; with two or more categories the process can be included without degrading the simulation — resolving the Part I/II decision to disable it
- **Solution convergence with $n_{Cat}$**: 1D kinematic simulations show convergence at $n_{Cat}\approx3$–4 for strongly forced cases and $n_{Cat}\approx2$ for weakly forced cases

## Methods Summary

**Part I (idealized):** WRF v3.4.1, 2D squall-line configuration, 1-km $\Delta x$, 80 vertical levels, 6-h integrations. Initialized from Weisman–Klemp analytic sounding with convective available potential energy ~2000 J kg$^{-1}$. Five sensitivity tests (BASE, r400, r900, FR0, FR1r400) vary $F_r$ and $\rho_r$ to isolate their impacts.

**Part II (real cases):**
- *Squall line (19–20 June 2007, Oklahoma):* 3D quasi-idealized WRF, 1-km $\Delta x$, 612 × 122 km$^2$, initialized from Lamont/Norman, Oklahoma, soundings. Compared to KOUN dual-pol radar and 2DVD disdrometers.
- *Orographic (13–14 December 2001, IMPROVE-2 Pacific Northwest):* 3D real case, 3-km $\Delta x$, 1200 × 830 km$^2$, GFS Final analysis forcing. Compared to WSR-88D Portland, S-Pol radar, P-3 and Convair aircraft (IWC, LWC), and surface precipitation gauges.
- Schemes compared: P3, MY2, MOR-G, MOR-H, NSSL, SBU-LIN, Thompson, WSM6, WDM6.

**Part III:**
- *1D kinematic model (Milbrandt et al. 2014):* Prescribed half-sine-wave updraft profile peaking at 30 min; convective sounding initialization. Tests use $w_{max}=3$ and 10 m s$^{-1}$ to bracket weakly and strongly forced cases. $n_{Cat}$ varied from 1 to 6; $\Delta D_{init}$ varied systematically.
- *3D dynamical model:* WRF v3.5.1 at 1-km horizontal grid spacing; quasi-idealized squall-line case (19–20 June 2007, Oklahoma — same as Part II). Three simulations: $n_{Cat}=1$ (rime splintering off), $n_{Cat}=2$, $n_{Cat}=3$ (rime splintering on for $n_{Cat}>1$).

## Key Results

**Part I (idealized):**
- Single ice category in P3 reproduces the expected distribution of particle types in a squall line: dense hail-like ice in convective core ($F_r \approx 1$, $\rho_p \approx 300$–600 kg m$^{-3}$, $V_m \approx 5$–8 m s$^{-1}$), unrimed ice in anvil ($F_r \approx 0$, $\rho_p < 100$ kg m$^{-3}$), with particle characteristics varying continuously and non-locally
- Both $F_r$ and $\rho_r$ have large impacts on storm structure and surface precipitation; sensitivity to $F_r$ is greater than to $\rho_r$
- Setting $F_r = 0$ (FR0) yields unrealistically small fall speeds everywhere ($V_m < 1.7$ m s$^{-1}$), leading to massive ice mass aloft

**Part II (3D cases):**
- *Squall line:* P3 and MOR-H produce the observed narrow, intense convective leading edge; MOR-G and all other graupel-only schemes fail to do so. P3's advantage stems from predicting hail-like ($\rho_g > 700$ kg m$^{-3}$, $V_m > 10$ m s$^{-1}$) ice in the convective region. All schemes underpredict trailing stratiform precipitation.
- *Orographic:* P3 produces less leeward bias (mean lee precipitation ~35 mm vs. observations of 18 mm) compared to MOR-G, MOR-H, MY2 (~50–59 mm). P3's superior performance is directly traced to its prediction of increased fall speeds for lightly to moderately rimed snow on the windward slope.
- P3 is computationally faster than all schemes tested except WSM6 and SBU-LIN; its 7 prognostic variables are fewer than MY2's 12.

**Part III (multiple free categories):**
- *1D, $w_{max}=10$ m s$^{-1}$:* With $n_{Cat}=1$ the majority of ice mass reaches the melting layer at ~90 min; with $n_{Cat}=2$ this is reduced to ~70 min due to reduced dilution and larger ice (higher fall speeds) in category 1. Approximate convergence at $n_{Cat}=3$–4 using optimal $\Delta D_{init}=f(n_{Cat})$.
- *1D, rime splintering:* For $n_{Cat}=1$, rime splintering off gives results much closer to multicategory simulations than rime splintering on, confirming that exclusion of this process is the correct choice for single-category configurations.
- *3D squall line:* Peak near-surface convective precipitation rates are approximately **89%, 80%, and 68%** of observed for $n_{Cat}=1,2,3$ respectively. All runs underpredict stratiform precipitation (~one-third of observed, consistent with other schemes). Increasing $n_{Cat}$ broadens the convective high-reflectivity region and reduces gaps in the stratiform region.
- *3D category properties:* In the anvil, category 1 ice ($F_{rim}\approx0.2$, $D_i\approx67\,\mu$m, $V_i\approx16$ cm s$^{-1}$) coexists with category 2 ice ($F_{rim}\approx0$, $D_i\approx167\,\mu$m, $V_i\approx46$ cm s$^{-1}$) — demonstrably distinct populations at the same location.

## Limitations and Caveats

**Parts I & II:**
- Single ice category cannot represent different ice types at the same grid point simultaneously (resolved in Part III)
- Rime splintering (Hallett–Mossop process) is neglected to minimize the smearing of category properties (enabled in Part III with $n_{Cat}\geq2$)
- The scheme must be tested on many more cases; cloud cover and radiative properties have not yet been evaluated
- Some uncertainty remains in parameters for aggregation and riming efficiencies; these are shared with all bulk schemes

**Part III:**
- The $\Delta D_{init}$ parameter and the merging thresholds are calibrated subjectively using the 1D model for a specific forcing scenario; they may not be optimal for all case types
- Collection efficiency $E_{j,k}$ among different ice categories is poorly constrained observationally
- Radiative transfer with multiple ice modes was not evaluated; many radiation schemes assume a single ice mode, requiring care when coupling
- The 3D evaluation is limited to a single (strongly forced) squall-line case

## Relation to Author's Research Program

These three papers represent the culmination of a long sequence of Milbrandt's work on improving the representation of ice microphysics. The intellectual lineage runs directly through: MY2 Parts I and II (Milbrandt and Yau 2005a,b) → MY2 sensitivity studies (2006, 2010) → sedimentation errors (Milbrandt and McTaggart-Cowan 2010) → snow $m$–$D$ and snow-to-liquid ratio (Milbrandt et al. 2012) → prognostic graupel density (Milbrandt and Morrison 2013) → P3 Parts I–III (2015–2016).

Parts I & II are co-led by Morrison, but Milbrandt brings the MY2 framework and its parameterization details (rime density, $m$–$D$ relations, fall speed approach) directly into the new design. Milbrandt's contribution is especially significant in the physical formulation of the rime volume budget, the density-dependent fall speeds, and the design of the single-category approach as a natural extension of the prognostic-$\rho_g$ work.

Part III is first-authored by Milbrandt, who led the algorithmic development of the multicategory extension. The work completes a conceptual arc that began with the MY2 scheme (multiple fixed categories) and arrives at multiple free categories — combining the flexibility of P3 with the multi-population capability of traditional multi-category schemes, without unphysical category conversions. The insight that rime splintering requires multiple categories is a specific, testable conclusion that directly feeds into operational recommendations for P3 in Environment Canada's forecast systems. Part III also reports on Milbrandt's role in testing P3 in GEM and at the 2014 and 2015 NOAA/HWT spring experiments. ⚠ verify specific model implementations of P3 beyond WRF (e.g., GEM, CM1, E3SM) and the scope of operational testing of multicategory P3 in GEM at the time of publication.

## Impact and Citations

**Citation count (Part I):** ~511 (Semantic Scholar, retrieved 2026-06-06)
**Citation count (Part II):** ~211 (Semantic Scholar, retrieved 2026-06-06)
**Citation count (Part III):** ~131 (Semantic Scholar, retrieved 2026-06-06)

The P3 series is among the most impactful contributions to bulk cloud microphysics parameterization in the past decade. Part I's 511 citations make it one of Milbrandt's most cited papers — a landmark contribution to the field. The scheme has been adopted in WRF and evaluated in numerous multi-scheme intercomparison studies across a wide range of meteorological regimes including convection, orographic precipitation, tropical cyclones, and Arctic clouds. Part II's 211 citations reflect broad community interest in practical multi-scheme evaluation. Part III's 131 citations reflect its role as a more specialized technical extension, but it is a key reference for any implementation of P3 with more than one ice category — which has become the recommended configuration for operational and research NWP. The principal scientific legacy of Part III is establishing the multi-free-category paradigm and the specific algorithmic design choices (destination category selection, inter-category collection, merging) that subsequent implementations build on. ⚠ verify downstream citations specifically crediting the Part III multi-category extension and model implementations of P3 beyond WRF.
