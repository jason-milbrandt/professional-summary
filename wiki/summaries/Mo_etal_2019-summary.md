# Summary: Mo et al. (2019)

**Full citation:** Mo, R., Brugman, M. M., Milbrandt, J. A., Goosen, J., Geng, Q., Emond, C., Bau, J., and Erfani, A., 2019: Impacts of hydrometeor drift on orographic precipitation: Two case studies of landfalling atmospheric rivers in British Columbia, Canada. *Wea. Forecasting*, **34**, 1211–1237. DOI: 10.1175/WAF-D-18-0176.1
**Journal:** Weather and Forecasting
**Year:** 2019
**Authors:** Ruping Mo, Melinda M. Brugman, Jason A. Milbrandt, James Goosen, Quanzhen Geng, Christopher Emond, Jonathan Bau, Amin Erfani
**DOI:** 10.1175/WAF-D-18-0176.1
**Author's role:** Tier 3 — Contributed microphysics expertise as the author of both MY2 (Milbrandt-Yau, 2005) and P3 schemes; the paper documents a systematic bias in MY2 and the P3 improvement for orographic spillover prediction; Milbrandt also co-authored the HRDPS system description (Milbrandt et al., 2016) referenced throughout (3rd of 8 authors)

---

## Overview

This paper investigates two severe winter AR storms over British Columbia (January 2016 and January 2017) to characterize how hydrometeor drift — the wind-driven advection of condensed water that causes precipitation to spill over mountain crests onto leeward slopes — affects orographic QPF. The authors demonstrate that the HRDPS-2.5km with a prognostic microphysics scheme substantially outperforms two coarser-resolution diagnostic systems, but that the MY2 microphysics scheme used in HRDPS had a systematic bias toward overpredicting precipitation spillover. The paper shows that the P3 scheme corrects this bias, and proposes two postprocessing approaches to partially compensate for the missing hydrometeor drift in diagnostic schemes.

## Context and Motivation

Operational forecasters in BC face a challenging problem: diagnostic precipitation schemes in the GDPS and RDPS (covering 25 km and 10 km, respectively) systematically overpredict precipitation on windward slopes and underpredict spillover into rain-shadow regions — the opposite error to what the HRDPS makes. During the January 2016 storm, the coarse-resolution models predicted 85 and 74 mm at Vancouver Airport when only 28 mm fell; meanwhile, East Vancouver Island (a rain-shadow area that received > 100 mm) was not included in the initial warning. Understanding and correcting these systematic QPF biases has direct public safety implications.

## Key Scientific Contributions

- Demonstrated using atmospheric water balance analysis that hydrometeor drift (convergence of integrated condensed water flux) is 3–20× smaller than moisture convergence across most of southern BC, but is locally comparable over and downwind of mountain crests — making it a significant contributor to the spatial distribution of AR-enhanced orographic precipitation
- Quantified the forecast advantage of HRDPS-2.5km (prognostic microphysics) over GDPS/RDPS (diagnostic schemes) for two landfalling AR events: HRDPS RMSE = 24.1 mm vs. RDPS 39.4 mm and GDPS 35.8 mm (24-h QPF, 2016 storm, 171 stations)
- Identified and mechanistically explained a systematic bias in the MY2 microphysics scheme toward overpredicting leeward spillover: in light riming situations, MY2 increases snow mass but not fall speed (because conversion to faster-falling graupel requires a threshold), causing hydrometeors to drift farther than observed
- Showed that P3 corrects this bias: P3 leeward RMSE = 10.3 mm vs. RDPS 14.2 mm and GDPS 17.1 mm; RSS whole domain P3 = 0.84 vs. MY2 ~0.50 (2017 storm)
- Proposed the Hydrometeor Drift Calibration (HDC) postprocessing scheme as a practical tool to improve QPFs from diagnostic precipitation systems (RSS 0.42 vs. GDPS 0.38 for the 2016 storm)

## Methods Summary

Case study analysis of two landfalling AR events: 26–28 January 2016 and 16–18 January 2017, over southern British Columbia. Observed precipitation from 176 weather stations (validated against temperature data to exclude solid-precipitation gauge errors). NWP guidance from GDPS-25km, RDPS-10km, and HRDPS-2.5km (MY2 for 2016; MY2 and a parallel P3 run for 2017). Atmospheric water balance analysis applied to GDPS-25km model output using vertically integrated water vapor flux (IWVF) and condensed water flux (ICWF). QPF verification metrics: RMSE, correlation, bias, and relative skill score (RSS). Leeward/windward analysis performed by stratifying stations by distance from the Vancouver Island and Coast–Cascade Mountain crests.

## Key Results

- **Windward QPF:** HRDPS-2.5km best on windward slopes for both storms; GDPS and RDPS overforecast windward amounts and underforecast leeward spillover
- **Leeward QPF (MY2):** Paradoxically, GDPS-25km outperformed HRDPS-2.5km on leeward slopes for both storms — a combination of resolution-induced smoothing simulating apparent spillover and the MY2 systematic overestimation of spillover
- **Leeward QPF (P3):** P3 dramatically improved leeward performance: RMSE 10.3 mm (P3) vs. 14.2 mm (RDPS) vs. 17.1 mm (GDPS)
- **Metro Vancouver:** HRDPS correctly predicted heavy precipitation close to the North Shore Mountains (not the lowlands), while GDPS/RDPS incorrectly placed high QPFs in the lowlands — the distinction that matters most for public warning decisions
- **AWB scheme:** Limited improvement due to systematic errors from hourly data; improved leeward QPF slightly but degraded coastal QPF
- **HDC scheme:** Modest but consistent improvement over GDPS raw QPFs; more practical for real-time application; further improvement expected with sub-hourly model output

## Limitations and Caveats

- Only two case studies — broader statistical assessment of hydrometeor drift impacts across many AR events is needed
- AWB and HDC schemes were tested using 1-hourly GDPS output, which introduces substantial tendency errors; higher-frequency output (5–10 min) would improve both schemes
- On leeward slopes, gauge density is low and solid precipitation measurement errors are significant, adding uncertainty to the verification
- The leeward QPF over-prediction identified in HRDPS-MY2 may have been partially masked in previous evaluations by the canceling effects of the bias with limited station coverage
- The paper notes that any NWP system with predefined ice categories (not just MY2) may face similar biases, depending on which category (snow vs. graupel) is favored

## Relation to Author's Research Program

This paper is directly relevant to Milbrandt's research program in two ways. First, it documents an operationally significant limitation of MY2 — the scheme he co-developed in 2005 — in the specific context of orographic precipitation over complex terrain during light riming conditions. Second, it provides independent external validation that P3 addresses this limitation, complementing prior idealized and case-study evaluations of P3 by Morrison et al. (2015) for the Oregon Cascades. Milbrandt contributed as the microphysics domain expert and author of both schemes, providing the P3 parallel-run output for the 2017 storm comparison and informing the interpretation of the categorical ice-phase conversion bias. The HRDPS-2.5km is also his operationally deployed system (Milbrandt et al., 2016), so this paper directly evaluates that system's performance and traces its operational improvement to the September 2018 MY2→P3 upgrade.

## Impact and Citations

**Citation count:** ~31 (Semantic Scholar, retrieved 2026-06-06)

This paper has gathered a solid citation count for a 2019 WAF paper, reflecting its relevance to the atmospheric river and orographic precipitation communities. It is a useful reference for groups comparing prognostic vs. diagnostic precipitation schemes in NWP, and for the operational forecasting community dealing with QPF in complex terrain along the North American west coast. Its documentation of the MY2 spillover bias and P3 improvement is cited in the McTaggart-Cowan et al. (2019) physics modernization paper as a justification for the MY2→P3 upgrade in the HRDPS. ⚠ verify any additional downstream citations specifically attributing the P3 operational adoption to this paper's findings.

## Related topics
- [[nwp-system-development]]
