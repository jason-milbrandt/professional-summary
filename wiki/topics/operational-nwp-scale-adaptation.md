# Operational NWP and Scale Adaptation (2014–2020)

**Summary:** Three papers carry Milbrandt's microphysics schemes from research into daily forecasting and adapt them across model scales: the HRDPS system-description paper (2016), the subgrid cloud-fraction method that lets two-moment schemes run at coarse resolution (Chosson et al. 2014), and its extension to P3 for global-scale NWP (Jouan et al. 2020).

**Sources:** [[Milbrandt_etal_2016-summary]], [[Chosson_etal_2014-summary]], [[Jouan_etal_2020-summary]]

**Last updated:** 2026-08-05

---

## HRDPS: the operational deployment (Milbrandt et al. 2016)

The definitive description and verification of Canada's pan-national 2.5-km operational NWP system, which went operational in November 2014, built on the GEM model with [[milbrandt-yau-scheme]] (MY2) microphysics. The paper documents HRDPS's improved skill over the coarser 10-km RDPS, the hydrometeor "hot start" that reduces spin-up time, and — notably — a moist bias in the mid-to-lower troposphere traceable specifically to MY2's excessive snow sublimation. It also documents the −5°C freezing-rain fix to MY2 (see [[precipitation-type-prediction]]) and explicitly states the plan to replace MY2 with [[p3-scheme]] in a future HRDPS version, making this the primary reference for the operational MY2 configuration and the bridge document to the P3 transition.

## Scale-adaptive microphysics (Chosson et al. 2014)

Two-moment schemes like MY2 are designed for cloud-resolving (~1 km) grid spacing and fail at coarser resolutions: cloud fraction and ice water content are systematically underpredicted because clouds become subgrid phenomena, and prognostic sedimentation catastrophically fails with the long time steps needed at coarse resolution (surface precipitation vanishes above ~120-second time steps). Chosson et al. (2014) — with Milbrandt as co-developer of the target scheme — solved both problems: a subgrid cloud and precipitation fraction (SCPF) parameterization using a top-hat PDF of total water, and a microphysical sub-time-stepping method. Validated against CALIPSO/CloudSat satellite retrievals at 15-km resolution, MY2+SCPF substantially improved cloud fraction and ice water content relative to both unmodified MY2 (which loses cloud fraction above ~12 km) and the operational Sundqvist scheme (which underestimates ice water content throughout the troposphere).

## Extending scale-adaptation to P3 (Jouan et al. 2020)

Applies the Chosson et al. SCPF approach — originally built for MY2 — to [[p3-scheme]] in ECCC's 25-km global GEM model, the first step toward replacing the decades-old Sundqvist scheme across *all* ECCC model scales with unified P3 microphysics. Uncalibrated P3 alone produced an excessively high planetary albedo (0.387 vs. observed ~30–33%) from excess cloud fraction and ice water content; adding SCPF corrected this (albedo 0.306). A further refinement — prescribing a larger ice radius for convectively detrained anvil ice — dramatically improved temperature and geopotential-height biases relative to the operational Sundqvist scheme, without recalibrating any other physics. Milbrandt is second author and senior scientist on this paper, extending work he led in HRDPS toward a genuinely global-scale application.

## Position in the arc

This cluster is the operationalization thread running parallel to the scientific development of [[milbrandt-yau-scheme]] and [[p3-scheme]]: it is where scheme design meets the practical constraints of running at a specific grid spacing and time step in a production forecast system, and it traces the explicit institutional goal — stated outright in the 2016 and 2020 papers — of eventually unifying ECCC's microphysics on P3 across all scales.

## Related pages

- [[milbrandt-yau-scheme]] — the scheme operationalized in HRDPS
- [[p3-scheme]] — the intended unified replacement across scales
- [[precipitation-type-prediction]] — the freezing-rain fix documented in the HRDPS paper
- [[p3-modern-extensions]] — further P3 development informing the unification goal
- [[nwp-system-development]] — Tier 3 companion papers on GEM/HRDPS system documentation
