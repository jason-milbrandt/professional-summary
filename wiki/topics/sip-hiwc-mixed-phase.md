# Secondary Ice Production, HIWC, and Mixed-Phase Cloud Observations

**Summary:** A cluster of Tier 3 collaborations — largely tied to ECCC's Convair-580 aircraft and the HAIC-HIWC campaign — on secondary ice production (SIP), high ice water content, and mixed-phase cloud structure, where Milbrandt provided cloud-microphysics expertise and his schemes for the modeling components. The observational findings feed directly back into the parameterization program.

**Sources:** [[Korolev_etal_2020-summary]], [[Korolev_Milbrandt_2022-summary]], [[Huang_etal_2021-summary]], [[Qu_etal_2022-summary]]

**Last updated:** 2026-08-05

---

## The papers

- **Korolev et al. (2020; ~122 citations)** — environmental conditions favorable to secondary ice production, from ECCC airborne campaigns. Milbrandt contributed cloud-microphysics expertise (Convair-580 campaign role ⚠ verify).
- **Korolev & Milbrandt (2022; ~50 citations)** — *"How are mixed-phase clouds mixed?"* From 10 years of Convair-580 data across seven campaigns: mixed-phase clouds are **not** homogeneously mixed but highly spatially intermittent, with ice/liquid segment lengths following power-law distributions from ~100 km down to the 100-m instrument limit, and theoretical minimum cluster scales of 0.1–10 m (ice) and mm (droplets) — far below any model resolution. The "genuine" vs. "conditional" mixed-phase distinction matters because spatial separation suppresses the Wegener–Bergeron–Findeisen process, slowing glaciation and altering precipitation. Milbrandt co-contributed conceptualization and methodology; Korolev led data and analysis.
- **Huang et al. (2021; ~21 citations)** — microphysical processes producing high ice water contents in tropical convection (HAIC-HIWC); P3 one of four schemes evaluated.
- **Qu et al. (2022; ~32 citations)** — impacts of SIP on tropical-convection microphysics and dynamics; Milbrandt co-conceptualized and co-designed experiments and provided P3/GEM expertise. *(Borderline Tier 2/3 — the author-contributions statement notes co-conceptualization; retained as Tier 3, confirmation pending — see the open items in the main page.)*

## Why this cluster matters to the parameterization program

These papers are observations-first, but each touches an active front of the scheme-development work:

- **SIP** became a *prognostic capability*: Hallett–Mossop rime splintering with two free ice categories is exactly the mechanism [[Cholette_etal_2024-summary]] used to cut HRDPS freezing-rain overprediction by up to 98% — and the requirement that rime splintering needs $n_{Cat} \geq 2$ was established in P3 Part III ([[p3-scheme]]).
- **Subgrid mixed-phase structure** is an unconstrained assumption in every bulk scheme: whether liquid and ice coexist or are separated within a grid cell changes glaciation, precipitation, and radiation. Korolev & Milbrandt (2022) provides the observational statistics against which subgrid phase-heterogeneity treatments — e.g. the SCPF approach in [[operational-nwp-scale-adaptation]] — can eventually be validated. The mixed-phase representation problem is also the motivation for the predicted liquid fraction in [[p3-modern-extensions]].
- **HIWC evaluation** exercises P3 in tropical deep convection, a regime far from the midlatitude cases of its original development — part of the scheme's community stress-testing alongside [[scheme-intercomparisons]].

## Related pages

- [[p3-modern-extensions]] — liquid fraction and SIP as prognostic capabilities
- [[p3-scheme]] — the multi-category prerequisite for rime splintering
- [[precipitation-type-prediction]] — the freezing-rain application of SIP
- [[scheme-intercomparisons]] — the broader community-evaluation cluster
- [[operational-nwp-scale-adaptation]] — subgrid cloud-fraction treatments
