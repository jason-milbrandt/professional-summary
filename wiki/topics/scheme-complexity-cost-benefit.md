# Cost–Benefit Guidance for Scheme Complexity (MY Part IV)

**Summary:** MY Part IV (2006b) used the three-moment Pine Lake supercell simulation from [[hail-diagnostics]] as a "truth" control and systematically degraded it one moment at a time, delivering the program's most actionable practical result: the dominant skill gain is from one-moment to two-moment, with a much smaller incremental gain to three moments — except for maximum hail size, which only the full three-moment scheme captures.

**Sources:** [[Milbrandt_Yau_2006ab-summary]] (Part IV)

**Last updated:** 2026-08-05

---

## The experimental design

Six sensitivity runs — two diagnosed-α two-moment configurations (DIAG_A, DIAG_B), two fixed-α two-moment configurations (FIX_0, FIX_3), and two one-moment configurations (SM_A, SM_B) — were run identically to the three-moment control (CNTR) from [[hail-diagnostics]], varying only the scheme version. Because all runs use different versions of the *same* scheme, differences are attributable solely to the treatment of moments and shape parameter, not to formulation differences between schemes — a cleaner test than comparing different schemes outright, which is the confound [[scheme-intercomparisons]] later showed dominates most real-world scheme comparisons.

## The performance ranking

**DIAG_B > DIAG_A > FIX_3 > FIX_0 > SM_B > SM_A.** The diagnosed-α two-moment configuration DIAG_B most closely reproduced the three-moment control across precipitation pattern, hail swath (within ~10%), and peak hail fields. One-moment runs diverged badly: heavy frozen-precipitation bias (~4× the control's solid rates), grossly overpredicted hail swaths (350–490%), and wildly inconsistent maximum hail sizes (4–5 cm in one one-moment configuration, 22–23 cm in the other) against the control's 2–3 cm.

## The practical rule

The dominant skill gain is from **one-moment to two-moment**. Three-moment adds a smaller increment for most fields, **except maximum hail size** — no sensitivity run below three moments reproduced the control's hail size; two-moment configurations either underpredicted (1–2 cm) or overpredicted (8–9 cm) depending on the fixed-α choice. This is the direct practical consequence of the [[spectral-shape-parameter]] finding: fixed-α two-moment schemes face an intrinsic trade-off — fixing α to control size sorting suppresses large hail, while relaxing it permits large hail but produces uncontrolled size sorting. Only a genuinely predicted α (three-moment) escapes the trade-off.

## Why this shaped operational choices

This result underpins the common operational choice of the economical two-moment configuration — see [[milbrandt-yau-scheme]] and [[operational-nwp-scale-adaptation]] — reserving three-moment for applications where hail size specifically matters. It also foreshadows [[p3-scheme]]: the recognized awkwardness of fixed hydrometeor categories, and the specific finding that no lower-complexity configuration can escape the size/quantity trade-off for hail, anticipates the eventual replacement of category-based schemes with continuously evolving particle properties.

## Related pages

- [[hail-diagnostics]] — the three-moment control run this study degrades
- [[spectral-shape-parameter]] — the theoretical basis for the fixed-α trade-off
- [[milbrandt-yau-scheme]] — the scheme whose configurations are being compared
- [[operational-nwp-scale-adaptation]] — where the two-moment-by-default choice plays out operationally
- [[p3-scheme]] — the eventual escape from fixed-category trade-offs
- [[scheme-intercomparisons]] — later work comparing genuinely different schemes, not versions of one scheme
