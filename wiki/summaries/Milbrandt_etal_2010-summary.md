# Summary: Milbrandt et al. (2010) — IMPROVE-2 Part II

**Full citation:** Milbrandt, J. A., M. K. Yau, J. Mailhot, S. Bélair, and R. McTaggart-Cowan, 2010: Simulation of an orographic precipitation event during IMPROVE-2. Part II: Sensitivity to the number of moments in the bulk microphysics scheme. *Mon. Wea. Rev.*, **138**, 625–642.
**Journal:** *Monthly Weather Review*
**Year:** 2010
**Authors:** J. A. Milbrandt, M. K. Yau, J. Mailhot, S. Bélair, R. McTaggart-Cowan
**DOI:** 10.1175/2009MWR3121.1
**Author's role:** Tier 1 — Lead author; designed and ran the moment-sensitivity experiments for IMPROVE-2 Part II

---

## Overview

This paper, the companion and sequel to Milbrandt et al. (2008, Part I), investigates how sensitive the IMPROVE-2 orographic precipitation simulation is to the number of predicted moments in the bulk microphysics scheme. Using the triple-moment MY control simulation of Part I as a baseline, the authors compare double-moment (MY-2) and single-moment (MY-1) versions of the same scheme and a separate single-moment scheme (Kong–Yau 1997, KY). The central result is that the change from three to two moments makes very little difference for this case, while changing from the triple-moment MY scheme to the single-moment KY scheme produces qualitatively different behaviour — particularly a dramatic leeside precipitation overprediction — attributable to specific formulation differences rather than the number of moments per se.

## Context and Motivation

Part I established that the triple-moment MY scheme produced a realistic orographic precipitation distribution, but overpredicted snow mass and underpredicted cloud water — and notably did *not* produce the pronounced leeside precipitation overprediction seen in the MM5/Reisner-2 and Kong–Yau simulations. Part II was motivated by two open questions: (1) How much of the Part I behaviour is genuinely due to predicting three moments rather than one or two? And (2) What exactly causes the leeside overprediction in the KY/Reisner-2 runs that the MY scheme avoids? The IMPROVE-2 case is particularly useful because the same GEM model is run with all schemes under identical forcing, so differences are cleanly attributable to the microphysics. This also allows a direct comparison of the moment-sensitivity result with that of MY06b (deep convection), where three-to-one moment degradation was catastrophic for storm structure.

## Key Scientific Contributions

- Showed that **double-moment MY (with diagnostic $\alpha$) closely reproduces triple-moment MY** for this orographic case — confirming the Part I/MY06b result that the diagnostic-$\alpha$ approach captures most of the benefit of a full three-moment scheme in terms of QPF and hydrometeor fields.
- Established that **the choice of single-moment scheme matters more than the number of moments**: KY produces qualitatively different results from MY-1 despite both being single-moment, demonstrating that scheme formulation differences can outweigh the one-vs-three moment difference.
- Identified two specific process-level mechanisms responsible for the leeside overprediction in KY (and G05a,b's Reisner-2): (1) **absence of the latent heat effect term** in the snow diffusional growth rate equation, which controls deposition in regions of accretion; and (2) **instantaneous rather than explicit snow melting**, which concentrates precipitation on the immediate lee side by preventing snow from being advected further downstream before falling.
- Provided a detailed analysis of how the number of moments affects the **snow size distribution and depositional growth rate**: the narrower snow spectra (larger $\alpha_s$) in MY-2/MY-3 produce larger deposition rates than the broader spectra in MY-1, explaining the higher snow mass in the multimoment runs despite similar or slower sedimentation.
- Showed that the **sensitivity to the number of moments is regime-dependent**: for orographic forcing (large-scale, quasi-steady), the sensitivity is much smaller than for deep convection, where the microphysics–dynamics feedback through cold-pool strength and storm propagation amplifies scheme differences.
- Demonstrated that the snow mass overprediction in multimoment configurations is **correctable by constraining $N_{0,s}$** with an upper limit — multimoment configurations can be easily calibrated while retaining the benefits of variable $\alpha$.

## Methods Summary

Four GEM simulations (identical model setup to Part I, nested 36/12/4/1-km grids) were compared: MY-3 (triple-moment, reproduced from Part I), MY-2 (double-moment, diagnostic $\alpha_x$, equivalent to DIAG_B in MY06b), MY-1 (single-moment, fixed $\alpha_x = 0$, constant intercepts), and KY (Kong–Yau 1997, single-moment, four categories). Two additional process-level sensitivity runs were performed with MY-2: MY-2_S1 (latent heat effect term in snow deposition shut off) and MY-2_S2 (instantaneous snow melting imposed). Comparisons used rain gauge 18-h precipitation accumulations, precipitation bias scores across threshold values, and in situ aircraft mass contents from the P-3 (cloud water along five legs) and Convair-580 (snow along four legs) during the 2300–0100 UTC stratiform period.

## Key Results

- **MY-2 ≈ MY-3**: Precipitation patterns and all hydrometeor fields (snow, cloud, rain, graupel, $Z_e$) were very similar. MY-3 had slightly larger $Z_e$ in some regions due to a wider rain spectrum, but the differences were minor.
- **MY-1 shows moderate changes**: Larger precipitation overprediction (+>20 mm along coast and windward slope), slight upwind shift, more ice mass (Cooper 1986 ice nucleation), much less snow (broader snow spectrum → lower deposition rates), deeper cloud pockets, similar graupel.
- **MY-1 snow closer to observations**: While all runs overpredicted snow mass, MY-1 was closer to the aircraft-measured snow mass concentrations along both aircraft tracks.
- **KY shows large leeside overprediction**: >80 mm more precipitation than MY-3 on the immediate lee side — matching the G05a,b/Reisner-2 pattern. KY also produced trace graupel only (strict conversion threshold) and deep, abundant cloud water.
- **Mechanism 1 (latent heating)**: Shutting off the latent-heat-effect term in MY-2 (MY-2_S1) produced leeside precipitation closely matching the KY pattern — confirming this is the dominant factor.
- **Mechanism 2 (instantaneous melting)**: Imposing instantaneous snow melting in MY-2 (MY-2_S2) also increased leeside precipitation, though less dramatically than mechanism 1.

## Limitations and Caveats

- Single case study; conclusions about the regime-dependence of moment-sensitivity are based on comparison to the one deep-convection case from MY06b.
- No in situ observations above ~6 km for this case, so it is uncertain which scheme best simulated upper-level ice crystal fields.
- The snow mass overprediction affects all runs to varying degrees; the authors acknowledge this likely reflects a real bias in the scheme (possibly related to overestimated crystal capacitances or the spherical-particle approximation for snow) as well as possible model moisture biases.
- The factor-of-7 snow overprediction (Part I) is improved but not fully resolved here; the authors note that modernization of the snow category (using a mass–diameter exponent of ~2 rather than 3, and improved capacitances) is underway.

## Relation to Author's Research Program

This paper closes the IMPROVE-2 two-part series and delivers three advances for Milbrandt's program. First, it **confirms in an orographic setting** (complementing the convective setting of MY06b) that double-moment with diagnostic $\alpha$ is nearly equivalent to triple-moment — strengthening the robustness of this result across weather regimes. Second, it **diagnoses specific process errors** in the snow category — the latent heat effect term and melting rate — that directly motivated subsequent work on snow representation ⚠ verify (confirm these issues are addressed in later 2012 snow/density papers). Third, the closing comment that "modernization of the MY05a,b scheme... is currently underway and will be reported in a forthcoming paper" directly announces the 2012 snow-density and 1D-melting papers ⚠ verify. The collaboration now includes McTaggart-Cowan ⚠ verify (confirm his role in the follow-on work), who co-authored the sedimentation-error paper (2010b) published in the same year. Together, IMPROVE-2 Parts I and II represent the most rigorous observational evaluation of the MY scheme published, and they set the stage for the ice-phase refinements that culminated in the P3 scheme.

## Impact and Citations

**Citation count:** ~52 (Semantic Scholar, retrieved 2026-06-06)

Cited comparably to Part I (~40 citations), this paper contributes to the IMPROVE-2 model-intercomparison literature and to the broader literature on the importance of BMS formulation choices for orographic precipitation ⚠ verify. The process-level explanation of the leeside overprediction mechanism (latent heat effect + instantaneous melting) is the most novel finding and is likely the basis for its citations in snow-parameterization and orographic-QPF studies ⚠ verify. The result that scheme-identity differences outweigh moment-count differences is a practically important finding for operational NWP modellers choosing or calibrating schemes ⚠ verify.

## Related topics
- [[observational-validation-sedimentation]]
