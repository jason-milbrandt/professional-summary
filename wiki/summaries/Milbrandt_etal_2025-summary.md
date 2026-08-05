# Summary: Milbrandt et al. (2025)

**Full citation:** Milbrandt, J. A., H. Morrison, and M. Cholette, 2025: Impacts of predicted liquid fraction and multiple ice-phase categories on the simulation of hail in the Predicted Particle Properties (P3) microphysics scheme. *J. Adv. Model. Earth Syst.*, **17**, e2024MS004404. DOI: 10.1029/2024MS004404
**Journal:** Journal of Advances in Modeling Earth Systems (JAMES)
**Year:** 2025
**Authors:** Jason A. Milbrandt, Hugh Morrison, Mélissa Cholette
**Author's role:** Tier 1 — Lead author; developed and tested the predicted liquid fraction and multi-category hail capabilities in P3

---

## Overview

This paper examines two recent P3 scheme capabilities — predicted liquid fraction for mixed-phase particles and multiple free ice categories — and their impacts on the simulation of hail in idealized 200-m-resolution CM1 supercell simulations. Predicted liquid fraction is shown to improve melting and shedding treatment, reducing mean hail sizes reaching the surface. In contrast, using multiple ice categories mitigates the "property dilution" problem, allowing larger hail sizes. The paper argues that the latest P3 configuration (triple-moment ice, predicted liquid fraction, two ice categories) is now capable of realistically representing the full hail lifecycle — initiation, growth, and decay.

## Context and Motivation

The P3 scheme has evolved substantially since its 2015 introduction: triple-moment ice (Milbrandt et al. 2021) addressed excessive size sorting; predicted liquid fraction (Cholette et al. 2019) enabled mixed-phase particles; multiple free ice categories (Milbrandt and Morrison 2016) allowed coexistence of distinct ice modes. However, the impacts of predicted liquid fraction and multiple categories on hail simulation had not been examined. Johnson et al. (2019) had shown that the original P3 performed poorly for dual-polarization hail signatures; triple-moment ice partially alleviated this. This paper completes the assessment by isolating the remaining two innovations through controlled sensitivity experiments.

## Key Scientific Contributions

- Demonstrates that predicted liquid fraction reduces hail at the surface primarily through its effect on the particle number concentration $N_{i,tot}$ during melting and shedding: liquid fraction on preserves $N_{i,tot}$ during mass transfer to liquid, decreasing mean hail size and increasing melting rate
- Isolates the "constant mean-mass diameter" closure assumption for $(dN/dt)_\text{MELT}$ in the original P3 as the principal driver of differences (via BASE-MOD and LF-MOD1 sensitivity tests)
- Shows that increasing the number of ice categories from 1 to 4 progressively reduces property dilution, increasing simulated hail sizes; diminishing returns beyond 2 categories
- Argues that the two effects (liquid fraction → smaller hail; more categories → larger hail) partially offset each other, and that the LF-2CAT configuration (two categories, liquid fraction, triple-moment ice) is the recommended configuration for realistic hail simulation
- Confirms that all sensitivities observed at 200-m grid spacing are qualitatively reproduced at 1-km grid spacing, validating applicability to current km-scale NWP systems
- Demonstrates computational feasibility of LF-2CAT for operational NWP using scaled flux vector transport (SFVT) advection

## Methods Summary

**Model:** CM1 (Bryan and Fritsch 2002) with 200-m isotropic grid spacing; 1000 × 1000 × 100 grid points; 20-km model top; 5th-order WENO advection.

**Case:** Alberta hailstorm (13 June 2020, Calgary area; billion-dollar event per Joe et al. 2024). Cold cloud base, moderate CAPE, strong mid-to-upper-level shear. Initial sounding from ECCC RDPS 6-hour forecast, adjusted for stability. Also run for Oklahoma 1 June 2008 supercell for comparison (not shown).

**Simulation suite:** 8 configurations (see Table 1 in paper), varying liquid fraction (on/off), SIP (rime splintering on/off), $(dN/dt)_\text{MELT}$ closure, and number of ice categories (1–4). All runs use triple-moment ice.

**Evaluation:** Vertical cross-sections of ice mass, density, mean diameter, $D_{h,\text{max}}$, $Z_e$; accumulated (45–90 min) total and solid precipitation; process rate analysis for melting/shedding sub-terms.

## Key Results

**Predicted liquid fraction (LF vs. BASE):**
- Solid precipitation at surface significantly reduced with liquid fraction on
- $D_{h,\text{max}}$ and mean hail sizes notably smaller in LF
- Mechanism confirmed via BASE-MOD and LF-MOD1 sensitivity tests: the treatment of $N_{i,tot}$ during melting/shedding is the key driver, not the mass transfer treatment
- LF-MOD2 (adds SIP) similar to LF; SIP does not substantially change hail simulation for this case

**Multiple ice categories (LF-2CAT, LF-3CAT, LF-4CAT vs. LF):**
- Each additional ice category increases $D_{h,\text{max}}$ and solid precipitation
- LF-2CAT shows substantial improvement over LF; LF-3CAT and LF-4CAT show diminishing additional gains
- Mechanism: without property dilution, hail can grow and descend without mixing with smaller ascending ice

**Net effect (LF-2CAT vs. BASE):**
- The competing effects of liquid fraction (reduces hail) and multiple categories (increases hail) partially offset each other
- LF-2CAT produces a hail simulation physically more complete than BASE despite being in a different parameter space

## Limitations and Caveats

- Only idealized simulations (no real-data validation against observed hail size distributions or radar data)
- SIP mechanisms limited to rime splintering; other modes (drop fragmentation) not yet included
- Prognostic aerosols not yet implemented in P3; hail embryo type (graupel vs. frozen drops) depends indirectly on aerosols
- Full triple-moment treatment of all microphysical process rates (not just sedimentation) deferred to a forthcoming study
- Optimization of ice initiation and merging between categories in the multi-category configuration not yet addressed

## Relation to Author's Research Program

This paper is the most recent in the P3 development series and represents the synthesis of three major innovations introduced in prior papers (multiple categories: Milbrandt and Morrison 2016; predicted liquid fraction: Cholette et al. 2019; triple-moment ice: Milbrandt et al. 2021). It is the first paper to examine the combined impacts of these features specifically for hail. This work closes the loop on the longstanding weakness of P3 for hail simulation (first identified by Johnson et al. 2019) and positions the current v5 P3 scheme as a research-quality tool for hailstorm process studies. The paper also directly informs future operational implementations of P3 at ECCC and potentially in WRF, CM1, and E3SM ⚠ verify current operational config.

## Impact and Citations

**Citation count:** ~1 (Semantic Scholar, retrieved 2026-06-06)

This paper was published in early 2025 and has just one citation at time of retrieval, consistent with its very recent publication date. As the capstone paper describing the current-generation P3 scheme's hail capabilities, it is expected to become a key reference for the atmospheric modeling community as the scheme continues to be adopted and evaluated. The paper's explicit treatment of computational cost (SFVT advection feasibility) strengthens its case for operational adoption.
