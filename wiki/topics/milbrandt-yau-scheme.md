# The Milbrandt–Yau (MY) Multimoment Scheme

**Summary:** The MY scheme is Milbrandt's foundational contribution: a six-category (cloud, rain, ice, snow, graupel, hail) bulk microphysics scheme with selectable one-, two-, and three-moment configurations, introduced in a four-part 2005–2006 series. Its two-moment configuration (MY2) became the operational microphysics of ECCC's HRDPS in 2014 and is also used in WRF and GEM-MACH.

**Sources:** [[Milbrandt_Yau_2005ab-summary]] (Parts I–II), [[Milbrandt_Yau_2006ab-summary]] (Parts III–IV), [[Milbrandt_etal_2016-summary]] (HRDPS deployment)

**Last updated:** 2026-08-05

---

## The three-moment closure (Part II, 2005b)

Building directly on the shape-parameter analysis of [[spectral-shape-parameter]] (Part I), Part II derived the first complete bulk scheme to fully prognose α for all precipitating categories: a mathematically consistent tendency equation for radar reflectivity (the third moment, $Z_x$) across every microphysical process class — collection, diffusional growth, melting, nucleation, and category conversion. This closure is what allows α to evolve freely rather than being diagnosed after the fact.

The resulting **six-category scheme with unified one-/two-/three-moment options** — built from warm-rain parameterizations adapted from Cohard and Pinty (2000) and ice-phase processes from Cotton et al. (1986), Ferrier (1994), and Lin et al. (1983) — is the central artifact of the first half of Milbrandt's career. Validated in 1D kinematic hailstorm simulations, it showed multi-moment configurations dramatically reduce the unrealistic surface precipitation rates (340 mm h⁻¹ in a single-moment run vs. 23–38 mm h⁻¹ in multi-moment versions) produced when hail sediments as if uniform.

## Operational deployment: MY2

The two-moment configuration (MY2) is the version that reached daily forecasting. It became the operational microphysics scheme when ECCC's kilometer-scale High Resolution Deterministic Prediction System (HRDPS) went operational in November 2014 — see [[operational-nwp-scale-adaptation]] for the system-level story and its documented moist bias traceable to MY2's excessive snow sublimation. MY2 is also available as a two-moment option in the community WRF model, and is the cloud-microphysics component of ECCC's coupled air-quality model GEM-MACH — see [[gem-mach-air-quality]].

## Where the scheme's limits showed up

Two threads of the research program are direct responses to structural limits exposed by the MY scheme's fixed-category design:

- **Rigid hydrometeor categories.** Six categories with fixed densities and discrete conversion thresholds cannot represent the continuous nature of rimed-ice growth. This is the limitation [[ice-phase-modernization]] diagnosed and began fixing (2011–2013), and that [[p3-scheme]] ultimately replaced with continuously evolving particle properties.
- **Operational precipitation-type errors.** MY2's collisional-freezing formulation caused a systematic freezing-rain underprediction in HRDPS, diagnosed and fixed in [[precipitation-type-prediction]].

## Position in the arc

The MY scheme is the scientific and institutional foundation everything else in the program builds on: its multimoment framework, rime-density thinking (via [[ice-phase-modernization]]), and operational deployment pattern (via [[operational-nwp-scale-adaptation]]) all carry forward into [[p3-scheme]], which Milbrandt co-developed a decade later as MY2's structural successor.

## Related pages

- [[spectral-shape-parameter]] — the theoretical analysis the three-moment closure answers
- [[hail-diagnostics]] — the 3D validation of the three-moment scheme
- [[scheme-complexity-cost-benefit]] — practical guidance on which MY configuration to run
- [[ice-phase-modernization]] — the fixed-category limitation and its fix
- [[p3-scheme]] — the structural successor to MY2 in HRDPS
- [[operational-nwp-scale-adaptation]] — HRDPS and MY2's operational deployment
- [[gem-mach-air-quality]] — MY2 as the microphysics component of GEM-MACH
