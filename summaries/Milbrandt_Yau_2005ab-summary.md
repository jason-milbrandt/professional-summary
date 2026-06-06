> **Note:** This is a combined summary of a two-part paper series. Individual summaries are also available as Milbrandt_Yau_2005a-summary.md and Milbrandt_Yau_2005b-summary.md.

---

# Summary: Milbrandt and Yau (2005) — Parts I and II

**Full citation (Part I):** Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part I: Analysis of the role of the spectral shape parameter. *J. Atmos. Sci.*, **62**, 3051–3064. DOI: 10.1175/JAS3534.1
**Full citation (Part II):** Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part II: A proposed three-moment closure and scheme description. *J. Atmos. Sci.*, **62**, 3065–3081.
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2005
**Authors:** J. A. Milbrandt, M. K. Yau

---

## Overview

This two-part series introduces the Milbrandt–Yau (MY) multimoment bulk microphysics scheme, one of the most widely adopted parameterizations for cloud microphysics in mesoscale numerical weather prediction. Part I provides the physical and mathematical foundation: a systematic analysis of the spectral shape parameter $\alpha$ of the gamma particle size distribution, demonstrating that $\alpha$ exerts strong control over gravitational size sorting and the accuracy of microphysical growth-rate calculations, and that predicting $\alpha$ — or diagnosing it — substantially outperforms holding it fixed. Part II builds directly on these findings to introduce a mathematically consistent three-moment closure (using radar reflectivity as the third predicted moment), and presents the complete description of the six-category MY scheme in one-, two-, and three-moment variants, validated in kinematic model simulations of a severe hailstorm. Together, the two papers establish both the theoretical rationale and the practical implementation of multimoment bulk microphysics.

---

## Context and Motivation

By the early 2000s, bulk microphysics schemes in NWP models had evolved from single-moment formulations (predicting only hydrometeor mass, following Kessler 1969) toward two-moment schemes that additionally predicted number concentration. Both classes assumed a three-parameter gamma size distribution $N(D) = N_0 D^\alpha e^{-\lambda D}$ but held $\alpha$ fixed — most commonly at zero (the inverse-exponential form). Observational studies showed that $\alpha$ varies substantially in real precipitation (from ~2 in stratiform to ~6 in convective conditions), yet no systematic analysis of the consequences of this simplification had been performed.

A second, related problem was well known to practitioners: two-moment schemes suffered from "excessive size sorting," in which differential sedimentation of mass and number concentration caused unrealistically large mean particle sizes to develop in simulations. The physical mechanism was understood qualitatively, but the dependence on $\alpha$ and its quantitative implications for moment-based source-term calculations had not been rigorously characterized.

On the technical side, while the motivation to predict $\alpha$ as a third prognostic moment was clear, no published scheme had derived the full set of tendency equations for a third moment that is mathematically consistent with all standard microphysical processes. Part I establishes the physical case; Part II closes the gap with a complete derivation and scheme implementation.

---

## Key Scientific Contributions

**From Part I (theoretical analysis):**
- Demonstrated quantitatively that $\alpha$ controls the rate of gravitational size sorting through its effect on the ratio of mass-weighted to number-weighted fall speeds $V_Q/V_N$; larger $\alpha$ reduces excessive size sorting.
- Showed that for fixed two-moment schemes, $\alpha = 3$ substantially outperforms $\alpha = 0$ across all precipitating hydrometeor categories.
- Introduced a diagnostic equation for $\alpha$ as a monotonically increasing function of the mean-mass diameter $D_m$: $\alpha_x = c_{1x} \tanh(c_{2x}(D_{mx} - c_{3x})) + c_{4x}$ (Eq. 13), empirically derived by fitting to three-moment sedimentation results.
- Quantified errors in bulk-computed microphysical source/sink moments as a function of $\alpha$ mismatch — an incorrect $\alpha$ of 0 instead of 5 produces ~700% overestimate in radar reflectivity (sixth moment) and ~15% underestimate in collection growth rate (moment order ~2.6).
- Established a clear performance ranking across scheme types: three-moment (TM) > diagnosed-$\alpha$ two-moment (DIAG) > fixed-$\alpha = 3$ (FIX3) > fixed-$\alpha = 0$ (FIX0) > single-moment (SM).

**From Part II (scheme development):**
- Derived a general three-moment closure: formulated tendency equations for radar reflectivity $Z_x$ for each microphysical process class, including processes where $\alpha$ change is negligible (collection, diffusional growth, melting), initiation processes (nucleation), and category-conversion processes — enabling $\alpha$ to be fully prognostic.
- Presented the complete MY scheme: a six-category (cloud droplets, rain, ice, snow, graupel, hail) parameterization with one-, two-, and three-moment options in a single unified framework.
- Demonstrated through 1D kinematic hailstorm simulations that multi-moment schemes dramatically reduce the unrealistic surface precipitation rates produced by single-moment schemes (peak rate of 340 mm h$^{-1}$ in SM vs. 23–38 mm h$^{-1}$ in multi-moment versions).
- Documented the physical size-sorting mechanism in multi-moment schemes: hailstones with high number concentration (lower fall speeds) are lofted by the updraft while those with low concentration (higher fall speeds) fall through — behavior physically absent in single-moment schemes.
- Successfully implemented the three-moment scheme in the Canadian MC2 mesoscale model, demonstrating operational feasibility at 1-km grid spacing for a severe hailstorm.

---

## Methods Summary

Part I uses an idealized 1D column model isolating pure sedimentation. An initial hail profile (sinusoidal $Q_h$ between 8–10 km, peak 1 g m$^{-3}$) is advected downward using analytically derived moment-weighted bulk fall velocities. Six scheme configurations — SM, FIX0, FIX3, DIAG, TM, and a 5000-bin Lagrangian analytic reference model (ANA) — are compared for vertical profiles and surface precipitation over 40 min, with and without a constant 10 m s$^{-1}$ updraft. Source-term accuracy is evaluated via the ratio of bulk-computed to analytic moments across moment orders $p = 0.6$–$6$ for a range of $\alpha$ values.

Part II derives analytic tendency equations for $Z_x$ by differentiating the gamma distribution closure, then assembles the full MY scheme using warm-rain parameterizations adapted from Cohard and Pinty (2000a) and ice-phase processes from Cotton et al. (1986), Ferrier (1994), Lin et al. (1983), and others. Validation uses a 1D kinematic column model with a prescribed sinusoidal updraft (peak 20 m s$^{-1}$), conditionally unstable sounding, 240-m vertical resolution, and 20-s time steps. Three configurations (SM, DIAG, TM) are compared for hydrometeor mass profiles and surface precipitation over 50 min.

---

## Key Results

Part I's sedimentation experiments show that FIX0 produces excessive size sorting and unrealistically high surface radar reflectivity (~80 dBZ vs. ~25 dBZ in the reference bin model) within 5 min. FIX3 substantially reduces this pathology. DIAG best reproduces the surface precipitation peak rate, while TM best reproduces the timing and vertical profiles, with near-exact $Z_{eh}$ profiles vs. a ~5 dBZ constant bias in FIX3/DIAG. In the updraft experiment, FIX3 significantly underpredicts mass throughout the column at 40 min; DIAG and TM perform much better.

Part II's kinematic hailstorm simulations sharpen the contrast between moment approaches. The single-moment scheme produces a peak surface precipitation rate of 340 mm h$^{-1}$ — physically unrealistic — because all hail falls at the same size-dependent velocity tied directly to mass content, accumulating at low levels. The two-moment (DIAG) scheme yields 23 mm h$^{-1}$ and the three-moment scheme 38 mm h$^{-1}$; both are qualitatively more realistic, with vertical hydrometeor mass profiles that closely resemble each other but differ substantially from the single-moment result. Timing and peak values of surface precipitation still differ between TM and DIAG, confirming additional skill from the fully prognostic $\alpha$.

---

## Limitations and Caveats

- The Part I analysis centers on hail sedimentation; results for other hydrometeor categories are inferred by extension rather than directly demonstrated.
- The 1D kinematic framework used in both papers isolates individual processes (sedimentation, then combined microphysics) but does not capture the feedbacks between dynamics and microphysics present in a full 3D simulation — the authors explicitly noted that 3D evaluation was needed.
- The diagnostic $\alpha$ relation from Part I is empirically derived from sedimentation behavior; its performance under active convective growth or other process-dominated regimes was not independently validated.
- The classification of frozen particles into fixed density categories (ice, snow, graupel, hail) with discrete conversion thresholds does not reflect the continuous nature of rimed-ice growth in real clouds — a limitation the authors acknowledged as motivating future work.
- Initial $\alpha$ values for newly nucleated or converted particles (e.g., $\alpha = 0$ for new ice crystals) are prescribed rather than physically derived.
- The three-moment approach adds one prognostic variable per category, increasing computational cost; the Part II results demonstrate feasibility but do not provide a full cost-benefit analysis in a 3D operational context.

---

## Relation to Author's Research Program

This two-part series is the foundational contribution of Milbrandt's research program in bulk cloud microphysics parameterization. Part I establishes the physical rationale for multimoment approaches, and Part II delivers the first complete three-moment bulk scheme with a mathematically consistent closure — directly originating from Milbrandt's doctoral work with M. K. Yau at McGill University.

The MY scheme introduced here was subsequently implemented in WRF and MC2/GEM, and has been widely used in both operational NWP and research contexts ⚠ verify. It established Milbrandt's reputation as a leading developer of bulk microphysics parameterizations and seeded a research program that produced two significant successor efforts: Morrison and Milbrandt (2011) ⚠ verify, which benchmarked and extended the multimoment framework for supercell simulations, and the Predicted Particle Properties (P3) scheme, introduced in Morrison and Milbrandt (2015). P3 directly addresses the fixed-category limitation identified in Part II by replacing discrete ice-phase categories with a single ice category whose physical properties (bulk density, fall speed, capacitance) evolve continuously — a conceptual advance made possible only after the multimoment foundation established here demonstrated the limits of fixed-category approaches.

The MY scheme remains in use operationally in ECCC's GEM model ⚠ verify, making this two-paper series the direct ancestor of an operational NWP component at Milbrandt's home institution.

---

## Impact and Citations

**Citation count:** Part I ~665, Part II ~556 (Semantic Scholar, retrieved 2026-05-25)

Together, the two papers have accumulated over 1,200 citations, placing them among the most-cited works in bulk cloud microphysics parameterization from the 2000s ⚠ verify. The combined citation record reflects widespread adoption and evaluation of the MY scheme across the NWP and cloud physics communities. Part I is the more heavily cited of the two, likely because its analysis of shape-parameter sensitivity and size-sorting errors has value as a standalone reference independent of the specific MY scheme implementation.

Key downstream impacts include Dawson et al. (2010), who showed that the MY scheme produced substantially more realistic cold-pool structure in tornadic thunderstorm simulations relative to single-moment schemes; Morrison and Milbrandt (2011), who used the MY framework as a benchmark in a comparative evaluation of two-moment schemes for supercell simulations; and the P3 scheme (Morrison and Milbrandt 2015), which cites the limitations of the MY fixed-category approach as direct motivation ⚠ verify. The three-moment closure described in Part II remains the only published bulk scheme to fully prognose $\alpha$ for all precipitating categories, and the scheme continues to be cited as a methodological reference for radar-reflectivity-based moment formulations ⚠ verify.
