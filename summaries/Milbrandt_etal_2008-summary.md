# Summary: Milbrandt et al. (2008) — IMPROVE-2 Part I

**Full citation:** Milbrandt, J. A., M. K. Yau, J. Mailhot, and S. Bélair, 2008: Simulation of an orographic precipitation event during IMPROVE-2. Part I: Evaluation of the control run using a triple-moment bulk microphysics scheme. *Mon. Wea. Rev.*, **136**, 3873–3893.
**Journal:** *Monthly Weather Review*
**Year:** 2008
**Authors:** J. A. Milbrandt, M. K. Yau, J. Mailhot, S. Bélair
**DOI:** 10.1175/2008MWR2197.1

---

## Overview

This paper presents the **first evaluation of the Milbrandt–Yau (MY) multimoment bulk microphysics scheme against in situ microphysical measurements**. The full triple-moment version of the scheme is used in the Canadian GEM model (nested to 4- and 1-km grids) to simulate the well-observed 13–14 December 2001 orographic precipitation event over the Oregon Cascades from the IMPROVE-2 field campaign. Simulated reflectivity, vertical motion, accumulated precipitation, and aircraft-measured hydrometeor fields are compared against observations. The scheme reproduces a realistic spatial precipitation pattern and realistic mean-mass particle sizes, but systematically overpredicts precipitation quantity and snow mass aloft while underpredicting cloud liquid water — biases attributed in part to the scheme itself. This is Part I of a two-part study; it also defines the control run for the moment-number sensitivity experiments of Part II (Milbrandt et al. 2010 ⚠ verify — Part II citation/year).

## Context and Motivation

Until this study, the MY scheme had been tested only in a case of strong convection (the 2006 Pine Lake supercell), where no in situ microphysical measurements were available (only radar-estimated surface precipitation) and where the strong forcing of deep convection can mask subtleties in bulk-scheme behavior. A rigorous evaluation required a weather system with detailed in-cloud observations. The IMPROVE-2 campaign (organized by the University of Washington to improve bulk schemes through observational verification; Stoelinga et al. 2003) provided exactly this: the 13–14 December 2001 Oregon Cascades case was intensely observed by radar, rain gauges, and two instrumented aircraft, and had already been simulated by others using MM5 with the Reisner-2 scheme (Garvert et al. 2005a,b; Colle et al. 2005), enabling direct scheme-to-scheme comparison under identical initial/boundary conditions. Orographic forcing also activates a wide variety of microphysical processes, making it a stringent test.

## Key Scientific Contributions

- Provided the **first validation of the MY scheme against in situ aircraft microphysical measurements** (mass contents, particle sizes, cloud liquid water), complementing the earlier convective-storm test that lacked such data.
- Demonstrated that the triple-moment MY scheme in GEM produces a **realistic spatial distribution of orographic precipitation** and reflectivity structure across prefrontal, stratiform, and postfrontal stages of the event.
- Showed that, despite a large overprediction of snow *mass*, the scheme reproduced **realistic mean-mass particle diameters** and correctly captured the observed trend of **increasing snow size with decreasing altitude** — demonstrating that the independent prediction of mass and number (a multimoment capability) lets the mass-to-number ratio, and hence mean size, evolve realistically through riming, deposition, aggregation, and size sorting.
- Isolated a **microphysics-attributable difference from MM5/Reisner-2**: the MY scheme did *not* produce the pronounced leeside precipitation overprediction characteristic of the single-moment Reisner-2 runs ⚠ verify (relative leeside behavior of the two schemes), since both models used identical forcing.
- Identified concrete deficiencies in the MY scheme's current configuration — **overprediction of snow mass aloft (up to a factor of 7 in leg-averaged values) and underprediction of cloud liquid water mass and vertical extent** on the windward slope — motivating later scheme refinements.
- Introduced modified, more stringent hail-initiation conditions (Appendix) to suppress spurious "hail" (really ice pellets, mean diameter ≤1 mm) in weakly-forced conditions.

## Methods Summary

The limited-area GEM model (fully compressible; TKE-based PBL; detailed land-surface and interactive radiation packages) was initialized at 0000 UTC 13 December 2001 from the modified NCEP-AVN analysis and successively nested through 36-, 12-, 4-, and 1-km grids (49 vertical levels), following the Sixth WMO Cloud Modeling Workshop guidelines used by the MM5 study of Garvert et al. (2005a,b) to enable direct comparison. The 4- and 1-km grids used the full triple-moment MY05 scheme (six categories: cloud, rain, ice, snow, graupel, hail; ~50 processes). Simulated fields were compared to NCAR S-Pol and Portland radar reflectivity, P-3 and dual-Doppler vertical-velocity measurements, 145 rain gauges (18-h accumulation), and in situ hydrometeor measurements from the NOAA P-3 and UW Convair-580 aircraft during the 2300–0100 UTC stratiform period. Mean-mass diameters were diagnosed from predicted mass and number concentration via $D_x = (\rho q_x / c_x N_{Tx})^{1/d_x}$.

## Key Results

- **Reflectivity:** Structure and values compared favorably across all three precipitation stages; the 1-km run best captured narrow postfrontal bands (>45 dBZ), though peak simulated values were somewhat too large.
- **Vertical motion:** The quasi-stationary mountain-wave pattern was correctly simulated; peak $w$ along P-3 leg 2 was ±1.6 m s⁻¹ vs observed ±3 m s⁻¹, but matched the 1.33-km MM5 values, and the strong lee downdraft (~−3.5 vs −3.0 m s⁻¹ observed) was well captured. Forcing was realistic but slightly weak, so hydrometeor errors are attributable in part to the BMS.
- **Precipitation:** Correct spatial pattern (coastal, windward Cascades, reduced leeside) but systematic overprediction of quantity in both 4- and 1-km runs; crucially, no leeside overprediction (unlike MM5/Reisner-2).
- **Cloud liquid water:** Reasonable at low levels but strongly underpredicted (often ~0) at higher elevations, underestimating the vertical extent of windward cloud pockets — consistent with too-weak low-level $w$.
- **Snow mass:** Overpredicted aloft by up to a factor of 7 (leg-averaged), and overpredicted at lower levels as well.
- **Particle sizes:** Mean-mass diameters of all categories were realistic, and the observed increase in snow size toward lower altitudes was well reproduced.

## Limitations and Caveats

- A single case study; the authors note that comparing in situ point measurements to bulk grid-box fields involves intrinsic scale-mismatch and spatial/temporal variability difficulties, and that small phase/magnitude errors in the forcing can affect the hydrometeor comparison independently of the BMS.
- Upper-level (above 750 hPa) model moisture was overpredicted, complicating attribution of the snow-mass bias purely to the scheme (it may partly reflect the forcing).
- Low-level vertical velocity was too weak, partly accounting for the underpredicted cloud water — again entangling forcing error with scheme error.
- The comparison of particle sizes is explicitly described as qualitative, not highly quantitative (observed sizes are estimates from best-fit inverse-exponential curves and sample images).
- The study evaluates only the triple-moment configuration; the role of the number of predicted moments is deferred to Part II.

## Relation to Author's Research Program

This paper marks the transition in Milbrandt's program from *developing* the MY scheme (the 2005–2006 four-part series) to **rigorously validating it against the most demanding observational benchmark — in situ aircraft microphysics**. It delivers on the explicit promise made in the 2006 papers that an orographic snowstorm case with in situ measurements was "underway." The collaboration broadens beyond Yau to include ECCC modellers Mailhot and Bélair ⚠ verify (their roles/affiliations), reflecting Milbrandt's move into the operational-NWP setting at ECCC and the use of the GEM model rather than the research MC2/MM5 frameworks. Scientifically, the paper's identification of the snow-mass overprediction and the rigidity of the fixed snow category as key deficiencies feeds directly into Milbrandt's subsequent work on snow/ice representation — the snow-density and melting studies around 2012 ⚠ verify (which later papers address this) and, ultimately, the Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015), which replaces fixed ice-phase categories with continuously evolving particle properties. The demonstration that the multimoment scheme captures realistic mean sizes via the mass-to-number ratio is a concrete observational confirmation of the central thesis of the 2005 Part I paper.

## Impact and Citations

**Citation count:** ~40 (Semantic Scholar, retrieved 2026-06-06)

As a single-case validation/application paper, this work is cited less than the foundational MY scheme-description papers, consistent with its role as an evaluation study ⚠ verify (relative citation positioning). Its niche significance is as the first in situ microphysical validation of the MY scheme and as a contribution to the IMPROVE-2 model-intercomparison literature on orographic precipitation ⚠ verify (characterization of citing literature), where it documents both the strengths (realistic particle sizes, no leeside overprediction) and the snow-mass/cloud-water biases of the scheme. The identified biases informed subsequent refinements to the treatment of the ice phase in bulk schemes ⚠ verify (downstream influence on scheme development). It is paired with Part II (Milbrandt et al. 2010 ⚠ verify), which uses these control runs to isolate the effect of the number of predicted moments.
