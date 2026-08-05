# Summary: Milbrandt and McTaggart-Cowan (2010)

**Full citation:** Milbrandt, J. A., and R. McTaggart-Cowan, 2010: Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2010
**Authors:** J. A. Milbrandt, R. McTaggart-Cowan
**DOI:** 10.1175/2010JAS3541.1
**Author's role:** Tier 1 — Lead author; identified and characterized sedimentation-induced errors in bulk microphysics schemes and proposed diagnostic corrections

---

## Overview

This paper provides a rigorous, comprehensive analysis of the errors introduced by hydrometeor sedimentation in one-, two-, and three-moment bulk microphysics schemes (BMSs), generalizing and extending the sedimentation analysis of Milbrandt and Yau (2005a, MY05a). Using a 1D idealized framework with an analytic bin-model reference and no other microphysical processes active, the authors examine how errors in both prognostic and non-prognostic moments (from $M_0$ to $M_7$) depend on the number of predicted moments and on the specific choice of which moments to predict. Two practical remedies are proposed and evaluated for the dominant failure mode — uncontrolled size sorting in fixed-shape-parameter two-moment schemes — that are easy to add to any existing two-moment BMS.

## Context and Motivation

MY05a established that (1) two-moment schemes with a constant shape parameter $m$ (relative dispersion) suffer from "excessive size sorting" due to a fixed, unfavorable ratio of moment-weighted bulk fall velocities; (2) diagnosing $m = f(D_m)$ largely controls this problem; and (3) a three-moment scheme (adding radar reflectivity as a prognostic variable) is fundamentally superior. However, MY05a only examined the "standard" combinations of prognostic moments ($M_3$ alone; $M_0$-$M_3$; $M_0$-$M_3$-$M_6$). Wacker and Lüpkes (2009, WL09) began to explore alternative moment choices in fixed-$m$ two-moment schemes, finding large "overshooting" errors in moments outside the range of the prognostic ones. No comprehensive study had examined: (a) alternative moment choices in two-moment schemes with variable $m$; (b) alternative choices in three-moment schemes; or (c) practical remedies generalizable beyond the specific $M_0$-$M_3$ pair. This paper fills all three gaps, providing guidance for both new and existing BMSs.

## Key Scientific Contributions

- Provided a comprehensive ranking of bulk scheme configurations — covering one-, two-, and three-moment schemes across a wide range of prognostic moment combinations — via a normalized mean absolute error metric applied to moments $M_0$–$M_7$. The optimal configuration found is the three-moment **$M_1$-$M_3$-$M_5$** scheme (error score 0.2548), outperforming the standard $M_0$-$M_3$-$M_6$ scheme (0.4137).
- Demonstrated that the **standard two-moment $M_0$-$M_3$, fixed-$m = 0$ scheme** performs catastrophically on the broad error metric (score ~1000), worse than even the standard one-moment scheme — due to uncontrolled size sorting and severe overprediction of high-order moments (including radar reflectivity $M_6$).
- Showed that in **three-moment schemes**, the variable $m$ inherently prevents the catastrophic overshooting found in two-moment schemes, and errors are much less sensitive to the choice of prognostic variables.
- **Generalized the diagnostic-$m$ approach** (first proposed in MY05a for the $M_0$-$M_3$ pair) to any pair of prognostic moments by deriving a new diagnostic parameterization:
  $$m = 11.84\left[1000\left(\frac{M_k}{M_j}\right)^{1/(k-j)} - 0.75\right]^2 + 2$$
  This is applicable to any two-moment scheme regardless of which moments are prognosed.
- **Proposed a second, independent fix for fixed-$m$ schemes** (e.g., schemes hard-coded for inverse-exponential PSDs): a diagnostic $V_k/V_j$ ratio approach in which only the computation of the lower-moment fall velocity is modified, causing it to approach the higher-moment fall velocity as $D_m$ increases, without changing $m$ elsewhere in the BMS. Both approaches greatly reduce sedimentation errors and are easily implemented in existing schemes.
- Showed that **existing two-moment $M_0$-$M_3$ schemes could be modified to use alternative moment pairs for sedimentation** without requiring any changes to the microphysical source/sink terms (which can remain formulated for $M_0$ and $M_3$), providing a practical pathway for improving operational schemes.

## Methods Summary

The idealized 1D framework follows WL09 closely: initial square-wave profile of rain (LWC $= 0.5 \times 10^{-3}$ kg m⁻³, $N_T = 3 \times 10^3$ m⁻³, inverse-exponential PSD) placed between 6500–8000 m. The analytic spectral bin model (5000 bins, 0–10 mm) with a power-law fall velocity relation ($V(D) = 130 D^{0.5}$ m s⁻¹) provides the reference solution. Bulk model simulations are initialized identically, with PSDs constrained to a three-parameter gamma function and sedimentation solved via the box-Lagrangian advection scheme (12.5 m vertical grid, 0.25 s time step). All combinations of integer prognostic moments from $M_0$ to $M_9$ are tested for one-, two-, and three-moment configurations. Errors are visualized as 2D plots (altitude vs moment number, color-coded overprediction/underprediction) and summarized as NMAE scores over a 2000-s integration, with equal weight given to $M_0$–$M_7$, $M_0$–$M_3$, and the prognostic moments.

## Key Results

- **One-moment schemes:** No size sorting possible; all moments monotonically related to the single prognostic moment.
- **Standard two-moment ($M_0$-$M_3$, $m=0$):** Catastrophically large errors (score ~1000) from uncontrolled size sorting; high-order moments severely overpredicted.
- **Two-moment schemes with diagnostic $m$:** Both the MY05a relation and the newly proposed generalized relation [Eq. (10)] dramatically reduce errors; the proposed relation ranks better than several three-moment configurations (score 0.7188).
- **Two-moment schemes with diagnostic $V_k/V_j$:** Slightly better score than the diagnostic-$m$ approach (0.6539) and easy to apply to hard-coded fixed-$m$ schemes.
- **Three-moment $M_0$-$M_3$-$M_6$:** Relatively good performance (score 0.4137) but outperformed by alternative three-moment configurations ($M_1$-$M_3$-$M_5$: 0.2548; $M_0$-$M_2$-$M_4$: 0.2782).
- **Best overall:** Three-moment $M_1$-$M_3$-$M_5$.

## Limitations and Caveats

- The study is confined to pure sedimentation; no other microphysical processes (collection, diffusional growth, melting) are active. The relative performance of different moment configurations in a full-physics 3D BMS may differ, since other processes also act to change the shape of the PSD.
- Only integer moment combinations between $M_0$ and $M_9$ are considered, though any positive real-valued moment is possible.
- The NMAE metric weights all moments $M_0$–$M_7$ equally; for applications not concerned with high-order moments (e.g., those not assimilating radar reflectivity), the catastrophic performance of the standard two-moment $M_0$-$M_3$ scheme may be less problematic.
- The proposed diagnostic-$m$ parameterization [Eq. (10)] was derived from the pure sedimentation reference solution; it does not account for the effects of other processes (such as coalescence and evaporation for rain) on the PSD shape, which were part of the basis for the Seifert (2008) relation.
- The diagnostic $V_k/V_j$ approach introduces a modest inconsistency between the $m$ value used for computing the fall velocity ratio and the $m$ used in the rest of the BMS.

## Relation to Author's Research Program

This paper is a theoretical companion to the MY Part I sedimentation study (2005a), deepening and completing its analysis in two key ways: (1) it provides the first comprehensive treatment of arbitrary prognostic moment combinations across all scheme tiers, and (2) it produces two practical fixes — the generalized diagnostic-$m$ and the diagnostic $V_k/V_j$ approaches — that can be applied to any existing BMS without redesigning the microphysical process equations. The collaboration with McTaggart-Cowan ⚠ verify (his specific contributions) reflects Milbrandt's role within ECCC's Meteorological Research Division. The result that the standard $M_0$-$M_3$-$M_6$ three-moment scheme is suboptimal — that $M_1$-$M_3$-$M_5$ would be better for sedimentation accuracy — is a notable finding with potential implications for future scheme design ⚠ verify (whether this has been acted on in subsequent MY or P3 configurations). More broadly, this paper reinforces the core theme of Milbrandt's program: that the *representation of the PSD shape* — not just mass and number — is the dominant source of error in bulk scheme sedimentation, and that this can be addressed pragmatically within a two-moment framework, though the three-moment approach remains fundamentally superior.

## Impact and Citations

**Citation count:** ~110 (Semantic Scholar, retrieved 2026-06-06)

With 110 citations, this is the most-cited of Milbrandt's non-foundational-MY-series papers processed so far, reflecting its value as both a diagnostic tool (the comprehensive moment-error ranking) and as a practical resource (the two proposed fixes are directly applicable to existing BMSs) ⚠ verify (characterization of citing literature). The paper is cited in the microphysics parameterization literature in contexts including scheme design and the theoretical analysis of sedimentation behavior ⚠ verify. The proposed diagnostic-$m$ generalization and the diagnostic-$V$ approach are tools that bulk-scheme developers working with two-moment configurations can apply without significant code restructuring ⚠ verify (extent of uptake).

## Related topics
- [[spectral-shape-parameter]]
- [[observational-validation-sedimentation]]
