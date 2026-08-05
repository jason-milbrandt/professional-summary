# Summary: Cholette et al. (2019)

**Full citation:** Cholette, M., H. Morrison, J. A. Milbrandt, and J. M. Thériault, 2019: Parameterization of the bulk liquid fraction on mixed-phase particles in the predicted particle properties (P3) scheme: Description and idealized simulations. *J. Atmos. Sci.*, **76**, 561–582. DOI: 10.1175/JAS-D-18-0278.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2019
**Authors:** Mélissa Cholette, Hugh Morrison, Jason A. Milbrandt, Julie M. Thériault
**DOI:** 10.1175/JAS-D-18-0278.1
**Author's role:** Tier 2 — Co-supervisor and microphysics domain expert; the P3 scheme (Milbrandt's) is extended; Milbrandt provided the scheme framework, guided the scientific design, and co-supervised Cholette (PhD student)

---

## Overview

This paper extends the P3 bulk microphysics scheme by adding a new prognostic variable — the bulk liquid mass fraction on ice ($F_{i,\mathrm{liq}}$, tracked via $q_{i,\mathrm{liq}}$) — to represent mixed-phase particles explicitly. The modified scheme (P3_MOD) adds physical processes for refreezing, condensation/evaporation of the liquid component, and modified melting and shedding formulations. Idealized 1D simulations show that P3_MOD can explicitly predict wet snow and ice pellets, precipitation types that the original P3 scheme (P3_ORIG) cannot produce, and generates more realistic latent heating and fall speed profiles near 0°C.

## Context and Motivation

Nearly all bulk microphysics schemes, including the original P3 scheme, treat ice and liquid as fully separate categories: melted mass from ice is immediately transferred to rain, and there is no concept of a mixed-phase particle. This prevents the explicit simulation of wet snow (partially melted snowflakes) and ice pellets (partially melted ice that refreezes below a warm layer). These precipitation types are important for surface weather prediction, particularly in warm-front scenarios. Earlier work by Thériault and Stewart (2010) showed this could be done in the Milbrandt–Yau scheme, but at the cost of defining fixed new hydrometeor categories. The flexible P3 framework — with continuously evolving particle properties — is a natural candidate for a cleaner implementation using a single additional prognostic variable.

## Key Scientific Contributions

- Added $q_{i,\mathrm{liq}}$ as a fifth prognostic variable to P3, enabling explicit tracking of the bulk liquid fraction $F_{i,\mathrm{liq}}$ on mixed-phase particles
- Derived new process formulations for refreezing, condensation/evaporation of the liquid component, and modified melting and shedding, all parameterized via linear interpolation in $F_{i,\mathrm{liq}}$ between dry-ice and liquid-drop limits
- Validated P3_MOD melting rates against a Lagrangian benchmark model (Mitra et al. 1990), with agreement in $F_{i,\mathrm{liq}}$ within 0.15 at all depths below 0°C
- Demonstrated explicit wet snow formation (Case 1: melting layer near surface): P3_ORIG produces only rain; P3_MOD produces a mixture of rain and partially melted ice ($F_{i,\mathrm{liq}} \approx 0.98$) at the surface
- Demonstrated explicit ice pellet formation (Case 2: melting layer aloft + refreezing layer): P3_MOD produces ice pellets as the dominant surface type when $F_{i,\mathrm{rim}} > 0.65$; P3_ORIG produces only freezing rain
- Showed that P3_MOD ice pellets suppress freezing rain by collecting supercooled rain in the cold layer, consistent with the diagnosis of Barszcz et al. (2018)

## Methods Summary

Scheme description and process derivations (analytical, integrated offline into lookup tables indexed by $q_{i,\mathrm{tot}}/N_{i,\mathrm{tot}}$, $\rho_{i,\mathrm{rim}}$, $F_{i,\mathrm{rim}}$, $F_{i,\mathrm{liq}}$). Validation via comparison to a Lagrangian model (M90 parameterization, 10,000 discrete particle sizes, 1-m vertical steps, 1-s time step). Idealized simulations using a 1D kinematic model (50 levels, 60-m spacing, 2-h duration, 1-s time step) driven by two observed thermodynamic profiles representing (1) a near-surface melting layer (SNOW-V10 campaign, Whistler 2010) and (2) a melting-layer-aloft plus refreezing-layer scenario (St. John's, NL, 1992). Sensitivity to specified $F_{i,\mathrm{rim}}$ at domain top examined for both cases.

## Key Results

- P3_MOD and Lagrangian benchmark agree in $F_{i,\mathrm{liq}}$ within 0.15; total melting distance nearly identical; differences attributed to ventilation coefficient parameterization differences
- Case 1 (near-surface melting): P3_MOD produces wet snow ($F_{i,\mathrm{liq}} \approx 0.98$) for low $F_{i,\mathrm{rim}}$; P3_ORIG produces only rain; larger mean density and fall speed in P3_MOD accelerate melting
- Case 2 (refreezing layer): for $F_{i,\mathrm{rim}} > 0.65$, P3_MOD gives ice pellets as dominant surface type; P3_ORIG gives freezing rain; refreezing warms the cold layer in P3_MOD, while melting slightly cools the warm layer more than in P3_ORIG
- A single additional prognostic variable per ice category suffices to capture the key mixed-phase behavior; computational overhead is small

## Limitations and Caveats

- Observational validation against real 3D storm simulations deferred to future work
- $F_{i,\mathrm{liq}}$ is assumed uniform across the PSD (constant with particle size); more physically, large particles carry more liquid
- Sublimation/deposition and condensation/evaporation are treated as mutually exclusive depending on $F_{i,\mathrm{liq}}$; the threshold $F_{i,\mathrm{liq}} = 0$ is a simplification
- Wet growth regime for hail mentioned as a future application; hail validation not included

## Relation to Author's Research Program

This paper is a direct extension of the P3 scheme (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016). The original P3 scheme — Milbrandt's primary contribution from 2015 onward — had a known gap: it could not represent mixed-phase particles. Cholette's thesis work fills this gap under Milbrandt's co-supervision. Milbrandt provided the P3 framework and guided the scheme design; Cholette drove the implementation and testing. This paper is the first in a series of four (Cholette et al. 2019, 2023, 2024, 2025) that progressively develop, validate, and operationalize the liquid-fraction extension of P3. The 2019 paper establishes the theoretical and algorithmic foundation on which all subsequent Cholette papers build.

## Impact and Citations

**Citation count:** ~28 (Semantic Scholar, retrieved 2026-06-06)

A well-cited scheme-development paper for a specialized audience. The 28 citations reflect genuine uptake in the mixed-phase microphysics community — a niche area where this paper represents the state of the art for bulk-scheme treatment of partially melted ice. The work directly addresses the limitation noted in Barszcz et al. (2018) and the long-standing problem of ice pellet simulation in bulk schemes, and it forms the foundation for the subsequent operational implementation papers in this series ⚠ verify uptake in NWP systems beyond the Cholette follow-on work.
