# Summary: Milbrandt and Yau (2006) — Parts III and IV

> **Note:** This is a combined summary of two papers published together as a natural pair (Parts III and IV of the four-part Milbrandt–Yau series). Individual summaries are also available as `Milbrandt_Yau_2006a-summary.md` (Part III) and `Milbrandt_Yau_2006b-summary.md` (Part IV). Parts III and IV share a single hailstorm simulation — Part III describes and validates the three-moment control run; Part IV uses it as the benchmark for a suite of sensitivity experiments — and are best understood together.

**Full citation (Part III):** Milbrandt, J. A., and M. K. Yau, 2006: A multimoment bulk microphysics parameterization. Part III: Control simulation of a hailstorm. *J. Atmos. Sci.*, **63**, 3114–3136. DOI: 10.1175/JAS3816.1
**Full citation (Part IV):** Milbrandt, J. A., and M. K. Yau, 2006: A multimoment bulk microphysics parameterization. Part IV: Sensitivity experiments. *J. Atmos. Sci.*, **63**, 3137–3159. DOI: 10.1175/JAS3817.1
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2006
**Authors:** J. A. Milbrandt, M. K. Yau
**Author's role:** Tier 1 — Lead author on both parts; designed and ran the 3D three-moment hailstorm control simulation and the full suite of moment-sensitivity experiments

---

## Overview

This two-part sequence completes the four-paper series that introduced the Milbrandt–Yau (MY) multimoment bulk microphysics scheme. Where Parts I and II (2005) built the theory and the three-moment closure and validated them in idealized 1D kinematic frameworks, Parts III and IV take the scheme into a full 3D cloud-resolving simulation of a real severe hailstorm — the 14 July 2000 "Pine Lake" Alberta supercell — and rigorously assess what the additional predicted moments actually buy. **Part III** presents the simulation itself: it is, to the authors' knowledge, the first cloud-resolving simulation ever run with a three-moment bulk scheme, and it shows the scheme reproduces a realistic supercell while introducing a new method to infer physically observable maximum hail size from the predicted size distribution. **Part IV** holds that three-moment run up as a control ("truth") and compares six one- and two-moment versions of the same scheme against it, distilling a practical cost–benefit message: the biggest improvement comes from one- to two-moment, with a diagnostic-$\alpha$ two-moment scheme capturing most of the three-moment benefit at lower cost.

## Context and Motivation

By 2006 the MY scheme existed and had been shown, in 1D, to outperform simpler schemes — but two things were untested. First, would the three-moment method (in which the spectral shape parameter $\alpha$ evolves independently via a predicted radar reflectivity moment) behave well when fully coupled to 3D model dynamics, with all the feedbacks between microphysics, latent heating, cold pools, and storm circulation? Second, given that every additional predicted moment adds a prognostic variable to advect and a set of source/sink terms to compute, *how much does the extra complexity actually matter*, and is it worth the cost? Part III answers the first question by building and validating the 3D control simulation; Part IV answers the second by systematically degrading the scheme one moment at a time, with a clean experimental design in which all runs use different versions of the *same* scheme so that differences are attributable solely to the treatment of the moments and shape parameter.

## Key Scientific Contributions

**From Part III (control simulation):**
- First 3D cloud-resolving simulation using a fully three-moment bulk microphysics scheme, coupled to the Canadian MC2 mesoscale model and nested from 12 km to 1 km using real synoptic initial conditions.
- Showed the three-moment MY scheme reproduces a realistic HP supercell — bounded weak echo region, hook echo, mesocyclone, suspended overhang, correct propagation, and quantitatively accurate radar reflectivity (model core 50–60 dBZ vs observed 51–54 dBZ).
- Introduced two diagnostic parameters for inferring physically observable maximum hail size from a bulk scheme: $N_h^*\{D^*\}$, the number concentration of hail larger than $D^*$, and $R_h^*\{D^*\}$, its surface flux, with proposed observability thresholds ($N^*_{CRIT}=10^{-4}$ m⁻³; $R^*_{CRIT}=10^{-3}$ m⁻² s⁻¹).
- Established that the mean-mass diameter alone is a poor indicator of large hail and that the higher moments of a three-moment scheme are needed to identify it.
- Gave a mechanistic, threefold explanation (advection, microphysical source/sink terms, sedimentation) of how $\alpha$ can locally *decrease* in a three-moment scheme — behavior structurally impossible in fixed- or diagnosed-$\alpha$ schemes.

**From Part IV (sensitivity experiments):**
- First systematic 3D comparison of one-, two-, and three-moment versions of a single self-consistent bulk scheme on a real storm, isolating the effect of the number of predicted moments.
- Established the performance ranking (best→worst): **DIAG_B > DIAG_A > FIX_3 > FIX_0 > SM_B > SM_A** (diagnosed-$\alpha$ two-moment > fixed-$\alpha$ two-moment > one-moment).
- Demonstrated that the dominant skill gain is from one- to two-moment, with a smaller incremental gain from two to three moments for most fields — the key exception being maximum hail size, which only the three-moment scheme captured.
- Identified an intrinsic limitation of fixed-$\alpha$ two-moment schemes: accurate hail *quantity* and accurate hail *size* cannot both be achieved (fixed $\alpha_h=3$ controls size-sorting but suppresses large hail; fixed $\alpha_h=0$ permits large hail but produces uncontrolled size-sorting).
- Showed sedimentation treatment is the key mechanism behind most inter-scheme differences and linked microphysical complexity to storm dynamics (one-moment cold-pool errors altered storm propagation and regime).

## Methods Summary

Both papers center on a single simulation of the 14 July 2000 Pine Lake supercell using the fully compressible, nonhydrostatic MC2 model with one-way self-nesting through three domains (12, 3, 1 km), initialized from the CMC regional GEM analysis. The 1-km three-moment control run (**CNTR**) covered 2:00–8:00 P.M. local time.

*Part III* validated CNTR against C-band radar observations (reflectivity structure, VIL as a large-hail surrogate, storm track, accumulated precipitation), compared simulated hydrometeor fields to published microphysical measurements from other storms (no in situ data were available for Pine Lake), and applied the new $N_h^*$/$R_h^*$ hail-size diagnostics at the time of peak hailfall.

*Part IV* added six sensitivity runs — two-moment **DIAG_A**, **DIAG_B** (diagnostic $\alpha_x=f(D_{mx})$), **FIX_0**, **FIX_3** (fixed $\alpha_x=0,3$), and one-moment **SM_A** (constant $N_{0h}$), **SM_B** (diagnosed $N_{0h}=f(\lambda_h)$) — all identical to CNTR except for the scheme version. Differences in precipitation, storm dynamics, and hail fields were evaluated against CNTR using subjective closeness thresholds.

## Key Results

- The simulated storm propagated at 48–52 km h⁻¹ (observed 46–52), reproduced BWER/hook echo/mesocyclone, and matched observed core reflectivity; peak precipitation rates were 185/166/87 mm h⁻¹ (total/liquid/solid).
- Part III's $R_h^*$ method yielded a significant surface flux of grape- and walnut-sized hail (2–3 cm) but negligible golf ball–sized hail — i.e., max simulated hail size 2–3 cm vs observed golf ball–sized, a reasonable agreement.
- In Part IV, **DIAG_B most closely reproduced CNTR** across precipitation pattern/quantity, hail swath (within ~10%), and peak hail fields ($Q_h$ 5.58 vs 5.51 g m⁻³; $D_{mh}$ 11.2 vs 14.9 mm).
- One-moment runs diverged strongly: heavy frozen-precipitation bias (solid rates ~4× CNTR), grossly overpredicted hail swaths (~350–490%), and extreme max hail sizes (SM_A 4–5 cm; SM_B 22–23 cm) versus CNTR's 2–3 cm.
- No sensitivity run reproduced CNTR's maximum hail size; the diagnosed/FIX_3 two-moment runs underpredicted (1–2 cm) and FIX_0 overpredicted (8–9 cm), confirming that maximum hail size is the distinctive payoff of the full three-moment scheme.
- Size sorting was absent in one-moment runs, uncontrolled in FIX_0, and properly controlled in FIX_3 and the diagnosed-$\alpha$ runs.

## Limitations and Caveats

- Both papers rest on a single case study of one severe hailstorm with no in situ microphysical observations; the authors repeatedly caution that more cases are needed (results are consistent with, but do not independently confirm beyond, the 1D analysis of Part I).
- Part IV's "errors" are measured against the three-moment run treated as truth, not against observations — a lower-moment field could in principle be closer to reality.
- The control's own microphysical validation was limited to order-of-magnitude comparison with other storms; the cloud-seeding of the observed storm was not modeled.
- The two one-moment runs used deliberately extreme hail-intercept values, not representative averages; a calibrated one-moment scheme could do better, though the authors argue tuning cannot fully close the gap for deep convection.
- The marginally-supercellular environment (~20 m s⁻¹ shear) amplified sensitivity; the observability thresholds for the hail-size diagnostics are acknowledged as subjective; detailed process-budget analysis was deferred to future work.

## Relation to Author's Research Program

Parts III and IV are the capstone of the foundational MY series that emerged from Milbrandt's doctoral work with M. K. Yau at McGill. They convert the theory of Parts I–II into a validated, practically usable tool and provide the cost–benefit guidance that governed how the scheme was actually deployed: the strong endorsement of at least a two-moment scheme — and the finding that a diagnosed-$\alpha$ two-moment configuration is "nearly as good" as a three-moment scheme for most purposes — explains why operational and research models frequently run the more economical two-moment MY variant, while the three-moment version remains the reference for applications where hail size matters ⚠ verify.

Several threads here feed directly into Milbrandt's later work. The observation that a scheme need not be uniformly multimoment for all categories (e.g., three-moment only for hail) anticipates targeted-complexity designs and the three-moment ice work of Milbrandt et al. (2021) ⚠ verify. The hail-size diagnostics ($N_h^*$, $R_h^*$) are a lasting methodological contribution tied to the unique information content of a three-moment scheme. Most importantly, the recurring difficulty of the rigid hydrometeor categories — fixed densities, discrete conversion thresholds, and a hail category that awkwardly spans small frozen drops to large stones — is exactly the limitation that motivates the Predicted Particle Properties (P3) scheme of Morrison and Milbrandt (2015), which replaces discrete ice categories with continuously evolving particle properties. In this sense Parts III and IV both demonstrate the success of the multimoment approach and expose the structural limits that defined the next phase of Milbrandt's research program.

## Impact and Citations

**Citation count:** Part III ~62, Part IV ~84 (Semantic Scholar, retrieved 2026-06-06)

The two 2006 papers are cited considerably less than the foundational Parts I and II (which together exceed 1,200 citations), consistent with their role as the application and evaluation papers of the series rather than the theory papers. Part IV is the more-cited of the two, reflecting the broad practical relevance of its central conclusion — that the one- to two-moment jump yields the largest skill gain and that a diagnostic-$\alpha$ two-moment scheme captures most of the three-moment benefit at lower cost — a result frequently invoked to justify the choice of two-moment schemes in operational and research NWP ⚠ verify. Part III holds a more specialized niche as the first 3D cloud-resolving simulation with a three-moment bulk scheme and as the origin of the $N_h^*$/$R_h^*$ hail-size diagnostics, cited particularly in the hail-modeling and bulk-scheme-verification literature. Together the pair documents the real-world behavior of the MY scheme that was subsequently implemented in community models including WRF and GEM ⚠ verify.
