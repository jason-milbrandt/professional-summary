# Summary: Milbrandt and Yau (2005b)

**Full citation:** Milbrandt, J. A., and M. K. Yau, 2005: A Multimoment Bulk Microphysics Parameterization. Part II: A Proposed Three-Moment Closure and Scheme Description. *Journal of the Atmospheric Sciences*, **62**, 3065–3081.
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2005
**Authors:** J. A. Milbrandt, M. K. Yau
**DOI:** Not available in print; paper identified on Semantic Scholar (paperId: 2da38a47aa7e984a7251087e8ba2914c7ddf143c)
**Author's role:** Tier 1 — Lead author; developed the three-moment closure and full six-category MY scheme description

---

## Overview

This paper (Part II of a two-part series) introduces a novel three-moment closure for bulk microphysics parameterizations. The key innovation is a prognostic equation for radar reflectivity as the third predicted moment of the hydrometeor size distribution, which allows the spectral shape parameter $\alpha$ of the gamma distribution to be fully prognostic rather than fixed or diagnosed. The paper also presents the complete description of a new six-category multimoment bulk microphysics scheme — the Milbrandt–Yau (MY) scheme — in one-moment, two-moment, and three-moment versions, with 1D kinematic model simulations demonstrating that multi-moment approaches substantially outperform single-moment schemes.

## Context and Motivation

Two-moment bulk microphysics schemes of the era used a three-parameter gamma size distribution but fixed the shape parameter $\alpha$, limiting their physical realism. Part I (Milbrandt and Yau 2005a) showed that $\alpha$ significantly affects sedimentation and growth rates and that diagnosing $\alpha$ from predicted moments improved simulations. However, the ideal approach — treating $\alpha$ as an independent prognostic variable — required a mathematically consistent closure for a third predicted moment. No such closure existed in published bulk schemes at the time. This paper fills that gap by deriving tendency equations for radar reflectivity (the sixth moment of the size distribution) consistent with all existing microphysical process parameterizations, making a fully three-moment scheme feasible.

## Key Scientific Contributions

- **Three-moment closure**: Derived a general formulation for computing source/sink terms of the radar reflectivity $Z_x$ for each microphysical process, classified into three types: (1) processes where $\alpha$ change is negligible (collection, diffusional growth, melting), (2) initiation processes (nucleation), and (3) conversion processes between categories. Together these allow $\alpha$ to be fully prognostic.
- **Complete MY scheme description**: Presented a new six-category (cloud, rain, ice, snow, graupel, hail) multimoment bulk microphysics scheme with one-, two-, and three-moment options. This became a widely referenced scheme used in NWP and research models including WRF and MC2/GEM ⚠ verify.
- **Three-moment superiority demonstrated**: 1D kinematic hailstorm simulations showed that the three-moment scheme most realistically reproduced hydrometeor distributions and surface precipitation evolution; the two-moment (diagnosed-$\alpha$) version was substantially better than single-moment but still showed notable differences from three-moment, particularly in surface precipitation timing and peak rates.
- **Size-sorting mechanism**: Documented that multi-moment schemes allow hail size sorting — particles with high number concentrations (lower fall velocities) are lofted, while those with low concentrations (higher fall velocities) fall through the updraft — a physically important behavior absent in single-moment schemes.
- **MC2 implementation**: Successfully implemented the full three-moment scheme into the Canadian MC2 (Mesoscale Compressible Community) model and demonstrated successful simulation of a severe hailstorm at 1-km grid spacing.

## Methods Summary

The paper derives analytic tendency equations for radar reflectivity $Z_x$ for each microphysical process by differentiating the gamma distribution closure relation from Part I. A new bulk microphysics scheme is constructed with six hydrometeor categories and three optional configurations (1-moment, 2-moment with fixed or diagnosed $\alpha$, 3-moment). Source/sink terms for warm-rain processes are adapted from Cohard and Pinty (2000a); ice-phase processes from Cotton et al. (1986), Ferrier (1994), Kong and Yau (1997), Lin et al. (1983), Meyers et al. (1997), and Murakami (1990). Testing is performed using a 1D kinematic column model with a prescribed sinusoidal updraft (peak 20 m s$^{-1}$) and a conditionally unstable initial sounding, 240-m vertical spacing, and 20-s time steps. Three simulations (SM, DIAG, TM) are compared for hydrometeor mass profiles at 20 and 30 min and surface precipitation rate over 50 min.

## Key Results

- **Single-moment peak precipitation rate**: 340 mm h$^{-1}$ — unrealistically large due to the monotonic relationship between hail fall velocity and hail mass content, causing an accumulation zone at low levels.
- **Two-moment (diagnosed-$\alpha$) peak rate**: 23 mm h$^{-1}$ — much more realistic, as size sorting allows hail with lower fall velocities to be advected aloft.
- **Three-moment peak rate**: 38 mm h$^{-1}$ — between SM and DIAG but qualitatively similar to DIAG in hydrometeor distribution.
- **Hydrometeor mass profiles**: The two-moment (diagnosed-$\alpha$) version's vertical profiles of mass content are much closer to the three-moment than to the one-moment version at 20 and 30 min.
- **Surface precipitation evolution**: Notable differences remain between TM and DIAG in timing and peak values of surface precipitation, demonstrating skill gained by the prognosed-$\alpha$ approach.
- **Computational cost**: The three-moment approach requires one additional prognostic variable per category; the two-moment diagnosed-$\alpha$ approach requires no additional prognostic variables but adds gamma-function evaluations at every grid point and time step.

## Limitations and Caveats

- Testing was limited to a 1D kinematic column model; the authors explicitly note that sedimentation and source/sink feedbacks require examination in a full 3D dynamical model to assess the overall impact of multi-moment approaches.
- The diagnostic $\alpha$ relations (from Part I) were derived primarily from sedimentation behavior; other processes will also act to change $\alpha$ in a three-moment scheme but are not independently validated.
- The classification of frozen particles into fixed density categories (ice, snow, graupel, hail) introduces abrupt transitions at conversion thresholds that may not reflect the continuous nature of rimed-ice growth; this limitation motivated later development of the P3 scheme.
- Initial values of $\alpha$ for newly nucleated/converted particles (e.g., $\alpha = 0$ for new ice crystals) are prescribed rather than derived from first principles.

## Relation to Author's Research Program

This paper is the central technical contribution of Milbrandt's doctoral work and represents the formal introduction of the Milbrandt–Yau (MY) multimoment bulk microphysics scheme — arguably the most significant single contribution to his research program. It directly establishes his reputation as an expert in bulk microphysics scheme development. The MY scheme went on to be widely implemented and evaluated in mesoscale NWP models (notably WRF and MC2/GEM), and the framework presented here — predictive equations for number concentration and radar reflectivity alongside mass — became a template for subsequent multimoment schemes including Morrison and Milbrandt (2011) ⚠ verify. The limitations of the fixed-category approach documented here (particularly the treatment of rimed ice) directly motivated Milbrandt's later development of the Predicted Particle Properties (P3) scheme (introduced in Morrison and Milbrandt 2015), which replaced discrete categories with a continuous representation of ice-particle properties. The scheme described in this paper is also the basis for the MY scheme currently used operationally in ECCC's GEM model ⚠ verify, directly linking Milbrandt's research contributions to operational NWP.

## Impact and Citations

**Citation count:** ~556 (Semantic Scholar, retrieved 2026-05-25)

This paper has had substantial and sustained impact on the NWP microphysics community. With over 550 citations, it is one of the most-cited bulk microphysics scheme papers from the 2000s ⚠ verify. The MY scheme has been implemented in WRF and MC2/GEM and has served as a comparison benchmark in numerous studies ⚠ verify. Key comparative evaluations include Dawson et al. (2010), who showed improved cold pool structure in tornadic thunderstorm simulations with MY relative to single-moment schemes, and Morrison and Milbrandt (2011), who benchmarked MY against other two-moment schemes for supercell simulations ⚠ verify. The three-moment closure formulation described here remains the only published bulk scheme to fully prognose the shape parameter $\alpha$ for all precipitating categories, and the scheme description continues to be cited as a methodological reference for radar-reflectivity-based moment closures ⚠ verify.

## Related topics
- [[milbrandt-yau-scheme]]
