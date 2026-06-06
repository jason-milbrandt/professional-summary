# Summary: Milbrandt and Morrison (2016) — P3 Part III

**Note:** The content of this summary has been merged into the combined P3 series summary (`Morrison_Milbrandt_2015_2016-P3-summary.md`), which now covers Parts I, II, and III together. This standalone file is retained for reference.

**Full citation:** Milbrandt, J. A., and H. Morrison, 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III: Introduction of multiple free categories. *J. Atmos. Sci.*, **73**, 975–995, doi:10.1175/JAS-D-15-0204.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2016
**Authors:** J. A. Milbrandt, H. Morrison
**DOI:** 10.1175/JAS-D-15-0204.1

---

## Overview

This paper extends the P3 bulk microphysics scheme (introduced in Parts I and II) from one free ice-phase category to a user-specified number ($n_{Cat}$) of free categories. The fundamental motivation is to eliminate "property dilution" — the artificial smearing of bulk particle properties that occurs when two physically distinct ice populations (e.g., large rimed graupel and newly nucleated small crystals) are forced into a single category. The multicategory P3 is the first bulk microphysics scheme to use multiple free categories (as opposed to multiple predefined/fixed categories). Idealized 1D and quasi-idealized 3D squall-line simulations demonstrate that the expanded scheme behaves as expected and produces reasonable results in a full dynamical model.

## Context and Motivation

The single-category P3 scheme (Parts I and II) could represent any ice type but only one population at a given grid point. In nature, multiple ice populations with different growth histories coexist: gravitational size sorting brings faster-falling ice from above, rime splintering nucleates tiny crystals in regions of large graupel, and frozen raindrops form alongside vapor-grown crystals. Forcing all of these into one free category smears their bulk properties (mean size, density, fall speed), degrading the subsequent microphysical evolution. This "dilution" problem was identified in Parts I and II as the primary remaining limitation of the single-free-category approach; Part III directly addresses it. Prior work by all other schemes used multiple predefined (fixed) categories with prescribed properties — an approach that introduces unphysical inter-category conversion. Multicategory free categories represent a genuinely new third path.

## Key Scientific Contributions

- **First multiple-free-category bulk microphysics scheme**: $n_{Cat}$ is user-specified; each category can represent any ice type, and different types can coexist at the same grid point simultaneously.
- **New algorithmic elements for multicategory operation**: (1) destination category selection for new ice based on mean-mass diameter difference ($\Delta D_{init}$ threshold); (2) inter-category gravitational collection with a lookup-table double integral; (3) merging of sufficiently similar categories (diameter difference $<150\,\mu$m and density difference $<100$ kg m$^{-3}$) to free capacity for new ice.
- **Rime splintering requires $n_{Cat}\geq2$**: For a single ice category, including rime splintering is actively detrimental due to dilution; with two or more categories the process can be included without degrading the simulation. This resolves the Part I/II decision to disable rime splintering for $n_{Cat}=1$.
- **Solution convergence with $n_{Cat}$**: 1D kinematic simulations show that total ice mass, reflectivity, and precipitation converge as $n_{Cat}$ increases, with convergence at $n_{Cat}\approx3$–4 for strongly forced cases and $n_{Cat}\approx2$ for weakly forced cases.
- **Demonstrated coexistence of distinct ice populations in 3D**: WRF squall-line simulations with $n_{Cat}=3$ show ice in different categories with different $F_{rim}$, $D_i$, $\rho_i$, and $V_i$ at the same grid points.

## Methods Summary

**1D kinematic model (Milbrandt et al. 2014):** Prescribed half-sine-wave updraft profile peaking at 30 min; convective sounding initialization. Tests use $w_{max}=3$ and 10 m s$^{-1}$ to bracket weakly and strongly forced cases. $n_{Cat}$ varied from 1 to 6; $\Delta D_{init}$ varied systematically to determine optimal values. Sensitivity tests isolate effects of rime splintering and inter-category collection efficiency.

**3D dynamical model:** WRF v3.5.1 at 1-km horizontal grid spacing; quasi-idealized squall-line case (19–20 June 2007, Oklahoma; 5900 J kg$^{-1}$ CAPE) identical to that used in Part II. Three simulations: $n_{Cat}=1$ (rime splintering off), $n_{Cat}=2$, $n_{Cat}=3$ (rime splintering on for $n_{Cat}>1$). Compared to KOUN radar observations and radar-derived precipitation rates.

## Key Results

- **1D, $w_{max}=10$ m s$^{-1}$:** With $n_{Cat}=1$ the majority of ice mass reaches the melting layer at ~90 min; with $n_{Cat}=2$ this is reduced to ~70 min due to reduced dilution and larger ice (higher fall speeds) in category 1. Approximate convergence at $n_{Cat}=3$–4 using optimal $\Delta D_{init}=f(n_{Cat})$.
- **1D, rime splintering:** For $n_{Cat}=1$, rime splintering off gives results much closer to multicategory simulations than rime splintering on, confirming that exclusion of this process is the correct choice for single-category configurations.
- **3D squall line:** Peak near-surface convective precipitation rates are approximately **89%, 80%, and 68%** of observed for $n_{Cat}=1,2,3$ respectively. All runs underpredict stratiform precipitation (~one-third of observed, consistent with other schemes). Increasing $n_{Cat}$ broadens the convective high-reflectivity region and reduces gaps in the stratiform region.
- **3D category properties:** In the anvil, category 1 ice ($F_{rim}\approx0.2$, $D_i\approx67\,\mu$m, $V_i\approx16$ cm s$^{-1}$) coexists with category 2 ice ($F_{rim}\approx0$, $D_i\approx167\,\mu$m, $V_i\approx46$ cm s$^{-1}$) — demonstrably distinct populations at the same location.
- For this strongly forced case, the $n_{Cat}=1$ simulation (rime splintering off) produced similar overall results to the multicategory runs; larger impacts of multiple categories were found in GEM tests (not shown) for other cases.

## Limitations and Caveats

- The $\Delta D_{init}$ parameter and the merging thresholds are calibrated subjectively using the 1D model for a specific forcing scenario; they may not be optimal for all case types or model configurations.
- Collection efficiency $E_{j,k}$ among different ice categories is poorly constrained observationally; its value affects the degree of dilution and sedimentation distribution, though the extremes simply revert P3 to one-category behavior.
- Radiative transfer with multiple ice modes was not evaluated; many radiation schemes assume a single ice mode, requiring care when coupling.
- The 3D evaluation is limited to a single (strongly forced) squall-line case; other weather regimes (weak convection, stratiform, orographic) were not formally tested in 3D.
- Additional computational cost scales as $4 \times (n_{Cat}-1)$ advected variables per category, though this can be substantially reduced by the linear-scaling advection approach referenced from a companion Morrison et al. (submitted) paper.

## Relation to Author's Research Program

Part III is a direct and natural continuation of the P3 series: Milbrandt and Morrison recognized the dilution limitation of the one-category scheme in Parts I and II, and this paper resolves it. The work also completes a conceptual arc that begins with the MY2 scheme (Milbrandt and Yau 2005a,b), which used multiple fixed categories, and arrives at a scheme with multiple free categories — combining the flexibility of P3 with the multi-population capability of traditional multi-category schemes, but without the unphysical category conversions. The insight that rime splintering requires multiple categories to be correctly included is a specific and testable scientific conclusion that directly feeds back into the recommendations for operational use of P3 in Environment Canada's forecast systems. The paper also reports on Milbrandt's role in testing P3 operationally in GEM (Environment Canada's 2.5-km deterministic forecast system) and at the 2014 and 2015 NOAA/HWT spring experiments. ⚠ verify the scope of operational testing of multicategory P3 in GEM at the time of publication.

## Impact and Citations

**Citation count:** ~131 (Semantic Scholar, retrieved 2026-06-06)

Part III has 131 citations — roughly one-quarter of Part I's count, reflecting its role as a more specialized technical extension rather than the foundational paper. It is nonetheless a key reference for any implementation of P3 with more than one ice category, which has become the recommended configuration for operational and research NWP. The paper is cited in the literature on multi-category microphysics benchmarking and in studies evaluating P3 in WRF and other models. Its principal scientific legacy is establishing the multi-free-category paradigm and the specific algorithmic design choices (destination category selection, inter-category collection, merging) that subsequent implementations build on. ⚠ verify downstream citations specifically crediting the Part III multi-category extension.
