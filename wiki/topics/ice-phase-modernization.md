# Benchmarking and Ice-Phase Modernization (2011–2013)

**Summary:** The conceptual hinge of Milbrandt's career: a benchmarking study that *diagnosed* the dominant ice-phase uncertainty in bulk schemes (the graupel-vs-hail choice), followed by snow-category modernization and the prognostic graupel-density paper that *fixed* the most rigid ice assumptions — explicitly framing the "paradigm shift toward adding physical degrees of freedom" that [[p3-scheme]] then realized for all ice.

**Sources:** [[Morrison_Milbrandt_2011-summary]], [[Milbrandt_etal_2012_snowmelting-summary]], [[Milbrandt_etal_2012_snowdensity-summary]], [[Milbrandt_Morrison_2013-summary]]

**Last updated:** 2026-08-05

---

## Diagnosis: schemes don't converge (2011)

The **Morrison–Milbrandt intercomparison (2011; ~210 citations)** ran an idealized WRF supercell with two structurally similar two-moment schemes (MOR and MY2) and found they still diverge substantially — and that the single dominant source of inter-scheme difference is the **choice of graupel vs. hail** as the rimed-ice category. Drop breakup mattered for the MOR cold pool; more complexity did not bring convergence. The most-cited paper of the early corpus, it established that the rigid-category design itself, not any particular parameter setting, was the problem to solve.

## Fix 1: modernizing the snow category (2012)

Two papers updated the most-used ice category:

- **1D snow melting ([[Milbrandt_etal_2012_snowmelting-summary]]; ~15 citations)** identified the inability of bulk schemes to represent *partial melting* as a fundamental structural limitation and proposed a 1D model as a forecaster tool. (Also filed as [[Milbrandt_etal_2012_PAAG-summary]] — same paper.) The partial-melting gap was eventually closed by the predicted-liquid-fraction work in [[p3-modern-extensions]].
- **Snow-to-liquid ratio ([[Milbrandt_etal_2012_snowdensity-summary]]; ~26 citations)** delivered the first explicit SLR prediction from a bulk scheme via new MY2 snow updates ($d_s \approx 2$, faster $V$–$D$ relation, constrained $\lambda_{s,\min}$, reduced capacitance). Deployed in the ECCC experimental system for the 2010 Vancouver Winter Olympics ([[Mailhot_etal_2012-summary]]) — Milbrandt's first operational deployment of a new scheme feature; see [[olympics-wwrp-nowcasting]].

## Fix 2: prognostic graupel density — the bridge to P3 (2013)

**Milbrandt & Morrison (2013; ~62 citations)** added bulk rime volume $B_g = q_g/\rho_g$ as a new prognostic variable, giving graupel a *predicted* density and density-dependent fall speeds via a Re–$X$ formulation — so a single rimed-ice category can span lightly rimed snow to hail-like ice. The paper explicitly frames itself as "part of a paradigm shift... toward adding physical degrees of freedom for a given hydrometeor type." $B_g$ is the direct ancestor of P3's rime-volume variable $B_{rim}$; the density-prediction method was later independently ported into WRF's WDM6 scheme by a Korean group ([[Park_etal_2024-summary]]) — see [[precipitation-type-prediction]].

## Position in the arc

This phase sits between the validation work of 2008–2010 ([[observational-validation-sedimentation]]), which confirmed the multimoment thesis of the [[milbrandt-yau-scheme]] while exposing its rigid-category deficiencies, and the [[p3-scheme]] (2015–2016), which generalized property prediction to all ice. The sequence — diagnose the dominant uncertainty (2011), fix the snow category (2012), predict a particle property (2013), free all particle properties (2015) — is the cleanest illustration of the research program's method: each advance is motivated by a concrete, demonstrated failure of the previous fixed assumption.

## Related pages

- [[p3-scheme]] — where the paradigm shift landed
- [[milbrandt-yau-scheme]] — the scheme being modernized
- [[observational-validation-sedimentation]] — the validation phase that exposed the deficiencies
- [[scheme-complexity-cost-benefit]] — earlier guidance on where scheme complexity pays off
- [[olympics-wwrp-nowcasting]] — the Vancouver 2010 operational deployment of SLR
- [[precipitation-type-prediction]] — downstream adoption of the density-prediction method
