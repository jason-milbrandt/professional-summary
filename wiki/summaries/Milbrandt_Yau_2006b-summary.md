# Summary: Milbrandt and Yau (2006b) — Part IV

**Full citation:** Milbrandt, J. A., and M. K. Yau, 2006: A multimoment bulk microphysics parameterization. Part IV: Sensitivity experiments. *J. Atmos. Sci.*, **63**, 3137–3159.
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2006
**Authors:** J. A. Milbrandt, M. K. Yau
**DOI:** 10.1175/JAS3817.1
**Author's role:** Tier 1 — Lead author; designed and ran the sensitivity experiments quantifying the cost–benefit of additional moments

---

## Overview

This paper, the fourth and final in the series introducing the Milbrandt–Yau (MY) multimoment bulk microphysics scheme, quantifies the practical benefit of predicting additional moments of the hydrometeor size distribution. Using the three-moment hailstorm simulation of Part III as a control ("truth"), the authors run six sensitivity experiments with one- and two-moment versions of the *same* scheme and compare them. The central finding is that the largest gain comes from moving from one-moment to two-moment schemes, with a smaller (though real) further gain from two to three moments — and that a two-moment scheme with a diagnostic shape parameter can reproduce most aspects of the three-moment simulation except the maximum hail sizes.

## Context and Motivation

Part I established theoretically, and in 1D, that more predicted moments improve bulk schemes; Part III demonstrated that the full three-moment scheme produces a realistic 3D hailstorm. But two practical questions remained: (1) *How much* does predicting three independent moments actually matter for the simulated microphysical fields, precipitation, and storm dynamics in 3D? and (2) Given that each extra moment adds substantial computational cost, is the benefit worth it? Because three-moment schemes are expensive, modelers need guidance on the cost–benefit trade-off. The clean experimental design — every run is a different version of the *same* scheme, with all other model settings identical — allows differences to be attributed unambiguously to the treatment of the moments and shape parameter, rather than to confounding scheme differences.

## Key Scientific Contributions

- Provided the first systematic 3D comparison of one-, two-, and three-moment versions of a single self-consistent bulk scheme on a real convective storm, isolating the effect of the number of predicted moments.
- Established a clear performance ranking of the seven configurations (best to worst): **DIAG_B > DIAG_A > FIX_3 > FIX_0 > SM_B > SM_A** — i.e., diagnosed-$\alpha$ two-moment > fixed-$\alpha$ two-moment > one-moment.
- Demonstrated quantitatively that the **dominant improvement is from one-moment to two-moment**, with a smaller incremental gain from two-moment to three-moment for most fields (the exception being maximum hail size).
- Showed that a two-moment scheme with a diagnostic shape parameter ($\alpha = f(D_m)$, the DIAG_B relation) reproduces the spatial pattern, quantity, and phase of surface precipitation, overall storm structure, propagation, cold-pool strength, and peak hydrometeor values of the three-moment control.
- Identified an intrinsic limitation of fixed-$\alpha$ two-moment schemes: **accurate hail quantity and accurate hail size cannot both be achieved** — fixing $\alpha_h = 3$ controls excessive size-sorting but forces narrow distributions (too little large hail), while fixing $\alpha_h = 0$ allows large hail but produces uncontrolled size-sorting and excessive reflectivity/diameters.
- Showed that sedimentation treatment is the key mechanism behind most inter-scheme differences (vertical redistribution of condensate, cold-pool strength, storm propagation), linking back to the 1D analysis of Part I.
- Connected microphysics to storm dynamics: one-moment cold-pool errors (SM_A too strong, SM_B too weak) changed storm propagation speed and pushed the marginally-supercellular regime toward multicellular.

## Methods Summary

Seven 1-km simulations of the 14 July 2000 Pine Lake storm were compared: the three-moment control (CNTR) from Part III plus six sensitivity runs. All used different versions of the MY scheme with identical model settings otherwise. The two-moment runs were **DIAG_A** and **DIAG_B** (diagnostic $\alpha_x = f(D_{mx})$, differing in whether $\alpha$ can approach 0 for small particles) and **FIX_0** and **FIX_3** (fixed $\alpha_x = 0$ and $3$). The one-moment runs were **SM_A** (constant hail intercept $N_{0h}$) and **SM_B** (diagnosed $N_{0h} = f(\lambda_h)$). Differences in precipitation (instantaneous and accumulated), storm dynamics (updraft, downdraft, vorticity, propagation, cold pool), and hail fields (reflectivity, mass, number, mean diameter, $N_h^*\{1\text{cm}\}$, max surface hail size from Part III's $R_h^*$ method) were evaluated against CNTR using subjective closeness thresholds (Table 5 in the paper).

## Key Results

- **Precipitation:** DIAG_B best reproduced CNTR's total precipitation pattern and quantity. One-moment runs were heavily biased toward frozen precipitation (solid rates ~4× CNTR) and overpredicted accumulated precipitation (SM_A ~⅓ more, SM_B ~double).
- **Hail swath:** Best reproduced by DIAG_B (within ~10%); under/over-predicted by the other two-moment runs; grossly overpredicted by the one-moment runs (~350% SM_A, ~490% SM_B).
- **Peak hail fields at 4:30 h:** DIAG_B most closely matched CNTR's peak $Q_h$ (5.58 vs 5.51 g m⁻³), $D_{mh}$ (11.2 vs 14.9 mm), and $N_h^*\{1\text{cm}\}$.
- **Maximum surface hail size:** None of the sensitivity runs reproduced CNTR's 2–3 cm range. The diagnosed/FIX_3 two-moment runs underpredicted (1–2 cm); FIX_0 overpredicted (8–9 cm); the one-moment runs were extreme (SM_A 4–5 cm; SM_B 22–23 cm).
- **Storm dynamics:** Two-moment runs closely tracked CNTR's updraft, downdraft, mesocyclone, propagation, and cold pool; one-moment runs diverged substantially (SM_A much stronger cold pool, faster, more multicellular; SM_B weaker cold pool, slower).
- **Size sorting:** Absent in one-moment runs (peak $D_{mh}$ collocated with peak $Q_h$); uncontrolled in FIX_0; properly controlled in FIX_3 and the diagnosed-$\alpha$ runs.

## Limitations and Caveats

- Conclusions are based on a single case study of one severe hailstorm; the authors repeatedly caution that more cases are needed to generalize (though results are consistent with the 1D analysis of Part I).
- The control simulation itself was validated with very limited microphysical data (see Part III), so "errors" of the lower-moment runs are measured against a three-moment run treated as truth, not against observations — a lower-moment field could in principle be closer to reality.
- The two one-moment runs used deliberately *extreme* values of the hail intercept parameter (not representative averages); a calibrated one-moment scheme could perform better, though the authors argue tuning cannot fully close the gap for deep convection.
- The marginally-supercellular environment amplified sensitivity; the authors suggest future studies select more clearly supercellular or multicellular regimes.
- Detailed process-budget analysis of the differences was outside the paper's scope (flagged for future work).

## Relation to Author's Research Program

Part IV completes the four-paper foundation of Milbrandt's research program and delivers its most actionable practical guidance: a cost–benefit framework for choosing the number of predicted moments in a bulk microphysics scheme. The strong endorsement of at least a two-moment scheme — and the demonstration that a diagnosed-$\alpha$ two-moment scheme is "nearly as good" as a three-moment scheme for most purposes — directly shaped how the MY scheme was deployed in practice (operational models often run the more economical two-moment configuration) ⚠ verify. The paper's closing discussion anticipates two later directions in Milbrandt's work: (1) the idea that a scheme need not be uniformly multimoment for all categories (e.g., three-moment only for hail) presages targeted-complexity designs, and the three-moment hail concept itself reappears in Milbrandt et al. (2021) ⚠ verify; and (2) the awkwardness of fixed hydrometeor categories with discrete conversion thresholds motivates the Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015). The cold-pool/dynamics sensitivity findings also connect to the broader literature (e.g., Dawson et al. 2010) on how microphysics complexity controls simulated storm structure ⚠ verify.

## Impact and Citations

**Citation count:** ~84 (Semantic Scholar, retrieved 2026-06-06)

Part IV is the most-cited of the two 2006 papers, reflecting the wide practical relevance of its core message — that the jump from one- to two-moment schemes yields the largest improvement, and that a diagnostic-$\alpha$ two-moment scheme captures most of the benefit of a full three-moment scheme at lower cost. This finding is frequently invoked in the microphysics literature to justify the choice of two-moment schemes for operational and research NWP, and the paper is a standard citation in comparative studies of bulk-scheme complexity for convective storms ⚠ verify. Together with Part III it documents the real-world behavior of the MY scheme that was subsequently implemented in community models including WRF and GEM ⚠ verify.
