# Summary: Milbrandt and Yau (2005a)

**Full citation:** Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part I: Analysis of the role of the spectral shape parameter. *J. Atmos. Sci.*, **62**, 3051–3064. DOI: 10.1175/JAS3534.1
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2005
**Authors:** J. A. Milbrandt, M. K. Yau
**DOI:** 10.1175/JAS3534.1
**Author's role:** Tier 1 — Lead author; developed the spectral shape parameter analysis framework and the multimoment bulk microphysics parameterization concept

---

## Overview

This paper examines the role of the spectral shape parameter $\alpha$ in the gamma particle size distribution used by bulk cloud microphysics schemes. The authors compare one-moment, two-moment (with fixed and diagnostically varying $\alpha$), and three-moment bulk schemes against a high-resolution analytic bin model for idealized sedimentation of hail. The central finding is that $\alpha$ strongly controls the rate of gravitational size sorting and the accuracy of microphysical growth-rate calculations, and that allowing $\alpha$ to vary — either diagnostically or prognostically — yields substantial improvements over holding it constant. This paper is Part I of a two-part series; Part II (Milbrandt and Yau 2005b) describes the full multimoment scheme built on these findings.

## Context and Motivation

Prior to this work, virtually all operational and research bulk microphysics schemes either predicted one moment (mass only, following Kessler 1969) or two moments (mass and number concentration). In both classes of schemes, the shape parameter $\alpha$ of the three-parameter gamma distribution $N(D) = N_0 D^\alpha e^{-\lambda D}$ was held constant, most commonly at $\alpha = 0$ (inverse-exponential). Observational studies (e.g., Uijlenhoet et al. 2003) showed that $\alpha$ varies substantially in real precipitation — from ~2 in stratiform to ~6 in convective conditions — yet no systematic analysis of the consequences of this simplification had been performed. The paper also addresses a known pathology of two-moment schemes: "excessive size sorting," in which differential sedimentation of mass and number concentration causes unrealistically large mean particle sizes to develop over time, a problem that is sensitive to $\alpha$.

## Key Scientific Contributions

- Demonstrated quantitatively that $\alpha$ controls the rate of gravitational size sorting in bulk schemes via its effect on the ratio of mass-weighted to number-weighted fall speeds $V_Q/V_N$; larger $\alpha$ reduces excessive size sorting.
- Showed that for a fixed two-moment scheme, $\alpha = 3$ substantially outperforms $\alpha = 0$ for all precipitating hydrometeor categories, regardless of category type.
- Introduced a diagnostic equation for $\alpha$ as a monotonically increasing function of the mean-mass diameter $D_m$ [$\alpha_x = c_{1x} \tanh(c_{2x}(D_{mx} - c_{3x})) + c_{4x}$, Eq. 13], derived by fitting to three-moment sedimentation results.
- Quantified errors in the instantaneous moments governing microphysical source/sink terms (collection, diffusional growth, melting) as a function of $\alpha$ mismatch; for $\alpha_\text{corr} = 5$ vs. $\alpha_\text{est} = 0$, the radar reflectivity moment $M(6)$ is overestimated by ~700%.
- Established the three-moment scheme (where $\alpha$ is prognostic via the radar reflectivity $Z$) as clearly superior to all two-moment variants for both sedimentation and source-term accuracy.

## Methods Summary

The study uses an idealized 1D column model to isolate sedimentation from other processes. An initial population of hail particles (sinusoidal $Q_h$ profile between 8–10 km, peak 1 g m$^{-3}$; $N_{0h} = 4 \times 10^4$ m$^{-4}$, $\alpha_h = 0$) is advected downward using moment-weighted bulk fall velocities derived analytically from the gamma distribution. Six schemes are compared: one-moment (SM), two-moment with $\alpha = 0$ (FIX0), two-moment with $\alpha = 3$ (FIX3), two-moment with diagnosed $\alpha$ (DIAG), three-moment (TM), and a Lagrangian analytic bin model with 5000 size bins (ANA). An additional test includes a constant 10 m s$^{-1}$ updraft. The error analysis for source terms uses the ratio $r(p, \alpha_\text{est}, \alpha_\text{corr})$ of bulk-computed moments to analytic moments across a range of moment orders $p = 0.6$–$6$.

## Key Results

- The one-moment scheme (SM) cannot represent size sorting at all; $D_m$ is always tied to $Q_h$.
- FIX0 produces excessive size sorting and unrealistically high $Z_{eh}$ (~80 dBZ near surface vs. ~25 dBZ in ANA) within 5 min of sedimentation.
- FIX3 substantially reduces excessive size sorting; surface precipitation timing and peak rates are much better than FIX0.
- DIAG best reproduces the surface precipitation peak rate; TM best reproduces the timing of first precipitation arrival and the vertical profiles of all moments, particularly $Z_{eh}$ (nearly exact at 40 min vs. ~5 dBZ constant bias for FIX3/DIAG).
- In the updraft experiment, FIX3 significantly underpredicts mass throughout the column at 40 min; DIAG and TM perform much better.
- For source-term moments: at 2 min and early times (broad spectra), TM achieves moment ratios close to 1.0 throughout the column; DIAG improves over FIX3 below ~8.5 km; SM is worst. Ranking at all times: TM > DIAG > FIX3 > FIX0 > SM.
- An incorrect $\alpha$ (e.g., 0 instead of 5) produces ~700% overestimate in $M(6)$ (reflectivity) and ~15% underestimate in $M(2.6)$ (collection growth rate).

## Limitations and Caveats

- All sedimentation experiments are for hail only; results for other hydrometeor categories (rain, snow, graupel, ice) are inferred by extension, not directly demonstrated.
- The 1D idealized setup isolates sedimentation from the full suite of microphysical interactions (collection, diffusion, melting) that occur simultaneously in a real storm — the actual performance differences in a full 3D simulation may differ.
- The diagnostic relation for $\alpha$ (Eq. 13) was derived empirically from three-moment sedimentation experiments; it is not physically derived and its generalizability to non-sedimentation-dominated situations (e.g., active convective growth) was not tested.
- The role of $\alpha$ for the cloud droplet spectrum (autoconversion) was explicitly excluded from the analysis.
- Only the hail category was used for quantitative sedimentation comparisons; constants in Table 1 for other categories were set by analogy.

## Relation to Author's Research Program

This paper is the theoretical foundation of the Milbrandt–Yau (MY) multimoment bulk microphysics scheme, which became one of Milbrandt's most significant scientific contributions. Part I establishes the physical and mathematical justification for moving beyond the conventional fixed-$\alpha$ two-moment approach — motivating the diagnostic-$\alpha$ two-moment and the full three-moment options that are described operationally in Part II. The MY scheme was subsequently implemented in NWP models including WRF and ECCC's GEM model and has been widely used in operational and research settings ⚠ verify. This paper also sets out the conceptual framework (moments, size sorting, fall-speed ratios) that underlies Milbrandt's later work on the Predicted Particle Properties (P3) scheme, which replaces fixed hydrometeor categories with a single ice-phase category whose properties evolve freely — a direction directly motivated by the limitations of fixed-category multimoment schemes identified here.

## Impact and Citations

**Citation count:** ~665 (Semantic Scholar, retrieved 2026-05-25)

This paper has been highly cited for a cloud microphysics parameterization paper, reflecting the widespread adoption of the Milbrandt–Yau scheme and its influence on NWP model development. Together with Part II, it established the scientific basis for predicting the radar reflectivity as a third moment in bulk schemes — a design choice later adopted or adapted in several operational and research models ⚠ verify. It is routinely referenced in evaluations of bulk microphysics schemes and in the development of successor schemes (including the P3 scheme by Morrison and Milbrandt 2015) ⚠ verify. The paper's analysis of size-sorting errors and shape-parameter sensitivity remains a standard reference for the bulk microphysics community ⚠ verify.

## Related topics
- [[spectral-shape-parameter]]
- [[milbrandt-yau-scheme]]
