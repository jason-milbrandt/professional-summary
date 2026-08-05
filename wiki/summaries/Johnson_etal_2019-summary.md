# Summary: Johnson et al. (2019)

**Full citation:** Johnson, M., Y. Jung, J. A. Milbrandt, H. Morrison, and M. Xue, 2019: Effects of the Representation of Rimed Ice in Bulk Microphysics Schemes on Polarimetric Signatures. *Mon. Wea. Rev.*, **147**, 3785–3809.
**Journal:** Monthly Weather Review
**Year:** 2019
**Authors:** Marcus Johnson, Youngsun Jung, Jason A. Milbrandt, Hugh Morrison, Ming Xue
**DOI:** 10.1175/MWR-D-18-0398.1
**Author's role:** Tier 3 — Contributing co-author (3rd of 5 authors); Milbrandt is co-developer of both the MY2 and P3 schemes that are the primary subjects of evaluation; his contribution was likely expert interpretation of scheme behavior and review of the analysis ⚠ verify

---

## Overview

This paper uses idealized supercell simulations in WRF to evaluate how three two-moment bulk microphysics schemes — Milbrandt–Yau (MY2), NSSL, and the two-category P3 (P3–2) — represent rimed ice and whether their differences explain key polarimetric radar signatures observed in real supercells. Specifically, the study evaluates each scheme's ability to produce the differential reflectivity ($Z_{DR}$) arc and the hail signature in the forward-flank downdraft, using a polarimetric radar forward operator. The paper reveals specific structural limitations in all three schemes — including a restrictive rain PSD slope bound in P3 that suppresses the $Z_{DR}$ arc and excessive downstream hail advection in MY2 — providing actionable guidance for scheme improvement.

## Context and Motivation

Polarimetric radar observations provide rich information about hydrometeor type and size that can serve as an objective diagnostic for bulk microphysics scheme evaluation. The $Z_{DR}$ arc (a low-level maximum of differential reflectivity on the storm's southern flank, caused by size sorting of hydrometeors) and the hail signature in the forward-flank downdraft (low $Z_{DR}$ / $\rho_{HV}$ due to resonance-sized hailstones) are particularly sensitive to rimed-ice parameterization. Prior work (Dawson et al. 2014) had established that the $Z_{DR}$ arc is driven primarily by rimed-ice size sorting rather than rain size sorting. This study asks whether current two-moment schemes can reproduce these signatures, and if not, why.

## Key Scientific Contributions

- Identifies a restrictive minimum rain PSD slope bound ($\Lambda_{r,min}$) in P3 as the primary reason the scheme fails to simulate the $Z_{DR}$ arc: it prevents the presence of large raindrops on the storm's southern flank
- Demonstrates that MY2 large hail sediments well downstream of the updraft — inconsistent with observations — due to smaller mass-weighted fall speeds than NSSL hail
- Shows that NSSL best reproduces the hail signature location in the forward-flank downdraft among the three schemes evaluated
- Reveals that P3's restrictive maximum ice number-weighted mean diameter ($D_{ni}$ = 2 mm default) prevents large rimed ice from reaching the surface, limiting the scheme's ability to reduce $Z_{DR}$ near the surface
- Provides sensitivity tests (relaxed $\Lambda_{r,min}$ and $D_{ni}$ limits) that isolate the specific scheme parameters controlling these signatures

## Methods Summary

Idealized supercell simulations using WRF v3.9.1 with a standard supercell sounding. Three two-moment BMPs are compared: MY2 (separate graupel and hail categories), NSSL (graupel-to-hail conversion with $N_t$ modification to suppress excessive size sorting), and P3–2 (two "free" ice categories, not predefined as graupel/hail). Simulated polarimetric variables ($Z_H$, $Z_{DR}$, $\rho_{HV}$) are computed via a polarimetric forward operator applied to model output at $t = 100$ min. Contoured frequency by altitude diagrams (CFADs) of rain and ice mass-weighted mean diameter are used to analyze size sorting systematically.

## Key Results

- **$Z_{DR}$ arc**: MY2 and NSSL produce enhanced surface $Z_{DR}$ bands consistent with size sorting, but neither fully reproduces the observed arc morphology. P3–2 (default) produces a nearly homogeneous forward-flank $Z_{DR}$ field; relaxing $\Lambda_{r,min}$ by a factor of 0.2 improves the gradient but the arc extends unrealistically far east of the updraft.
- **Hail signature**: Only NSSL correctly places the hail signature in the forward-flank downdraft. MY2 hail appears on the southern flank rather than in the forward flank. P3–2 (default) ice rarely reaches the surface; relaxing the $D_{ni}$ limiter allows larger ice to sediment but produces an excessively large forward-flank hail zone.
- **Rain CFADs**: MY2 and NSSL show clear rain drop size sorting with decreasing height; P3–2 rain melted from ice falls into a very narrow $D_{mr}$ bin (~3.0–3.25 mm), confirming no effective size sorting in the default scheme.
- MY2 graupel and hail have smaller fall speeds than NSSL counterparts, enhancing downstream advection of rimed ice.

## Limitations and Caveats

- Only a single idealized supercell environment is examined; results may vary with storm type, thermodynamic environment, and shear profile.
- The two P3–2 ice categories cannot be directly compared to the graupel/hail categories in MY2 and NSSL; the comparison is inherently not "apples-to-apples."
- The paper acknowledges that further investigation of both $\Lambda_{r,min}$ and maximum $D_{ni}$ limits in P3 is needed.
- The polarimetric forward operator assumptions (spheroid shape, water fraction treatment) introduce uncertainties in the simulated polarimetric fields.
- MY2's melting option (used in this paper) amplifies reflectivity noise because wet graupel doesn't compensate for reduced reflectivity from small melted graupel transferring to rain.

## Relation to Author's Research Program

Milbrandt is the 3rd author on this paper. As the co-developer of both the MY2 scheme (Milbrandt and Yau 2005a,b) and the P3 scheme (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016), his schemes are the primary subjects of the study. His contribution was almost certainly providing expert interpretation of the schemes' behavior and guidance on the physical mechanisms responsible for the simulated polarimetric signatures. The paper is directly relevant to Milbrandt's research program because it provides an independent, observationally motivated evaluation of his schemes' rimed-ice treatment — specifically identifying $\Lambda_{r,min}$ and $D_{ni}$ limiter issues in P3 that could inform future scheme improvements. The finding that P3's default $\Lambda_{r,min}$ suppresses the $Z_{DR}$ arc is a concrete, actionable structural critique of the scheme.

## Impact and Citations

**Citation count:** ~14 (Semantic Scholar, retrieved 2026-06-06)

This is a moderately cited study within the polarimetric microphysics evaluation literature. The 14 citations reflect its specialized audience (researchers evaluating BMPs using polarimetric observational constraints) and the niche intersection of supercell simulation, scheme intercomparison, and radar forward modeling. The identification of specific P3 scheme limiters ($\Lambda_{r,min}$, $D_{ni}$) has practical implications for P3 developers and users running supercell simulations with WRF.

## Related topics
- [[scheme-intercomparisons]]
