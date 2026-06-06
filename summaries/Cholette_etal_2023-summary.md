# Summary: Cholette et al. (2023)

**Full citation:** Cholette, M., J. A. Milbrandt, H. Morrison, D. Paquin-Ricard, and D. Jacques, 2023: Combining triple-moment ice with prognostic liquid fraction in the P3 microphysics scheme: Impacts on a simulated squall line. *J. Adv. Model. Earth Syst.*, **15**, e2022MS003328. DOI: 10.1029/2022MS003328
**Journal:** Journal of Advances in Modeling Earth Systems (JAMES)
**Year:** 2023
**Authors:** Mélissa Cholette, Jason A. Milbrandt, Hugh Morrison, Danahé Paquin-Ricard, Dominik Jacques
**DOI:** 10.1029/2022MS003328
**Author's role:** Tier 2 — Co-supervisor and key contributor to P3 development; the triple-moment ice scheme (M21) is Milbrandt's direct prior work; Milbrandt guided the scientific design and integration of both innovations

---

## Overview

This paper describes the latest major version of the P3 microphysics scheme, which combines two previously independent developments: the triple-moment ice parameterization (Milbrandt et al. 2021) and the predicted bulk liquid fraction on mixed-phase particles (Cholette et al. 2019). The combined scheme is evaluated in 1-km simulations of a real mid-latitude squall line (Iowa, August 2019) using the GEM model. The new configuration — which is now the operational P3 version in ECCC's HRDPS system — produces stronger cold pools, faster squall line propagation, reduced ice accumulation at the surface, and an improved radar reflectivity bright band compared to the original double-moment P3.

## Context and Motivation

P3 had two important but previously separate upgrades: the predicted liquid fraction (Cholette et al. 2019, enabling mixed-phase particle representation) and triple-moment ice (Milbrandt et al. 2021, enabling freely evolving spectral shape). Neither had been combined, and neither had been tested in the context of deep convection (the liquid fraction work was validated only for winter precipitation). This paper fills both gaps simultaneously, documenting the combined scheme and testing it in a convective case that allows evaluation of cold pool dynamics and radar structure — two diagnostics that are critical for operational NWP.

## Key Scientific Contributions

- Combined triple-moment ice ($Z_{i,\mathrm{tot}}$ as 6th prognostic) with predicted liquid fraction ($q_{i,\mathrm{liq}}$ as 5th prognostic) in P3 for the first time, enabling up to 6 prognostic variables per ice/mixed-phase category
- Updated reflectivity calculation to account for scattering by mixed-phase particles (liquid shell around ice core), producing an explicit bright band in the melting layer
- Showed that predicted liquid fraction (LF) makes squall lines propagate ~1–1.5 m s$^{-1}$ faster and produces stronger cold pools (~0.2–0.9°C colder), driven by enhanced cooling from combined ice sublimation and mixed-phase particle evaporation below 0°C
- Showed that LF reduces ice accumulation at the surface by decreasing the mean mass-weighted diameter of melting particles (particles shrink instead of converting immediately to rain)
- Showed that triple-moment ice reduces ice aloft in the stratiform region and lowers reflectivity closer to observed values
- The combined 3MOM_LF configuration is now the operational P3 version in HRDPS ⚠ verify exact deployment date

## Methods Summary

Five GEM simulations of an observed squall line (18 August 2019, Iowa): one at 2.5-km spacing (operational HRDPS configuration, used for IC/LBCs) and four at 1-km spacing forming a 2×2 factorial design over {2-moment, 3-moment} × {no liquid fraction, with liquid fraction}. Single-category P3 throughout. Reflectivity validated against BALTRAD mosaic and KARX/KDVN radar cross-sections; precipitation against StageIV and MRMS; cold pool speed and depth from a buoyancy-integral method applied over the Iowa subdomain.

## Key Results

- Squall line propagation: 60–66 km h$^{-1}$ across the four 1-km runs; LF adds ~1–1.5 m s$^{-1}$; 3MOM adds ~0.5 m s$^{-1}$; combined effect is largest in 3MOM_LF
- Cold pool: LF simulations 0.2–0.9°C colder; cold pool speed 0.5–2 m s$^{-1}$ higher in 3MOM_LF vs. others; mixed-phase evaporation contributes 5–15% of total latent cooling in the melting region
- Ice at surface: LF < noLF for both 2MOM and 3MOM; 3MOM > 2MOM for both; the competing effects partially offset
- Bright band: explicit and realistic only in LF simulations; 3MOM_LF bright band agrees better with observations than 2MOM_LF (lower reflectivity above, consistent with smaller ice aloft)
- Cooling structure: noLF has two distinct cooling peaks (sublimation ~4 km, melting ~3 km); LF has a smoother single merged peak, physically more realistic

## Limitations and Caveats

- Single case study (one squall line); generality of results not established
- Closure assumption for $\mu$ (shape parameter) during mixed-phase processes is simplified (constant during time step); refinements deferred
- Reflectivity parameterization does not account for attenuation
- Impacts of the new scheme on hail (wet growth, shedding) are deferred to future work
- No claim that overall model performance is improved — sensitivity to microphysics changes is demonstrated

## Relation to Author's Research Program

This paper sits at the convergence of Milbrandt's two most recent P3 innovations: the triple-moment ice scheme (Milbrandt et al. 2021, Tier 1) and the liquid fraction extension developed with Cholette (2019, Tier 2). Cholette is the lead author and primary investigator; Milbrandt's role is as co-supervisor, P3 scheme owner, and HRDPS context provider. The paper is effectively the integration paper — bringing together the two threads of P3 development into the version that is currently operational. It also marks the transition of the liquid fraction capability from idealized 1D tests (Cholette 2019) to operational-scale real-case testing. The subsequent Cholette 2024 and 2025 papers continue this trajectory toward full operational validation.

## Impact and Citations

**Citation count:** ~13 (Semantic Scholar, retrieved 2026-06-06)

Recent paper (2023) with 13 citations, which is solid uptake for a specialized microphysics scheme paper in its first two years. The operational significance is larger than the citation count implies: the described configuration is the current operational P3 in HRDPS, meaning its impacts are embedded in daily operational NWP across Canada ⚠ verify. The bright-band reflectivity improvement and cold pool results have direct implications for both operational forecast verification and research uses of P3 in convective-scale modeling.
