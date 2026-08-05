# The P3 Scheme (Predicted Particle Properties)

**Summary:** The P3 scheme — Milbrandt's most highly cited body of work, co-developed with H. Morrison — abandons predefined ice categories (cloud ice, snow, graupel, hail) in favor of one or more "free" ice categories whose physical properties evolve continuously via conserved prognostic variables. Introduced in a three-part series (2015–2016), it is the operational microphysics scheme in ECCC's HRDPS.

**Sources:** [[Morrison_Milbrandt_2015_2016-P3-summary]] (combined Parts I–III), [[Milbrandt_Morrison_2016-summary]] (Part III), [[Milbrandt_Morrison_2013-summary]] (conceptual precursor), [[McTaggart-Cowan_etal_2019-summary]] (operational transition)

**Last updated:** 2026-08-05

---

## The core idea

Traditional bulk schemes partition ice into predefined categories with prescribed characteristics — fixed densities, mass–diameter ($m$–$D$) relations, and fall speeds — and convert mass between them (cloud ice → snow → graupel) through artificial, parameter-dependent processes with no physical justification. P3 inverts this: a single **free ice category** carries four conserved prognostic variables — total ice mass $q_i$, number $N_i$, rime mass $q_{rim}$, and rime volume $B_{rim}$ — from which the **rime mass fraction** $F_r = q_{rim}/q_i$ and **predicted rime density** $\rho_r = q_{rim}/B_{rim}$ follow. A four-region $m$–$D$ relation and Re–$X$ fall speeds (Mitchell and Heymsfield 2005) make particle density, size, and fall speed mutually self-consistent. Ice type is no longer *declared*; it *emerges*.

The design descends directly from the prognostic graupel-density work of Milbrandt & Morrison (2013), whose bulk rime volume $B_g$ is the direct ancestor of $B_{rim}$ — see [[ice-phase-modernization]] — and inherits the [[milbrandt-yau-scheme]] framework for its warm-phase and multimoment machinery.

## The three-part series

- **Part I (Morrison & Milbrandt 2015a; ~511 citations)** — scheme description and idealized 2D squall-line tests. A single free category reproduces the expected particle-type distribution: dense hail-like ice in the convective core ($F_r \approx 1$), unrimed low-density ice in the anvil ($F_r \approx 0$), varying continuously. Crucially, $F_r$ and $\rho_r$ show *no* simple relationship with local temperature, liquid water content, or updraft — transport makes diagnostic approaches unreliable, so the properties must be prognosed.
- **Part II (Morrison et al. 2015b; ~211 citations)** — 3D WRF evaluation against two well-observed cases and nine schemes. For the Oklahoma squall line, P3 (like MOR-H) reproduces the narrow, intense convective leading edge that graupel-only schemes miss, because it predicts hail-like ($\rho_g > 700$ kg m⁻³) fall speeds in the core. For the IMPROVE-2 orographic case, P3 reduces the leeside precipitation bias via enhanced fall speeds for lightly rimed snow — vindicating the mechanism identified in [[observational-validation-sedimentation]]. Computationally efficient: faster than MY2, only ~11% slower than single-moment WSM6, with 7 prognostic variables vs. MY2's 12.
- **Part III (Milbrandt & Morrison 2016; ~131 citations)** — Milbrandt first-authored. Extends P3 to $n_{Cat}$ user-specified free categories, eliminating **property dilution** (distinct ice populations — size-sorted large ice, rime-splintered crystals, frozen drops — smeared into one category's bulk properties). New algorithmic elements: destination-category selection ($\Delta D_{init}$ threshold), inter-category collection via lookup-table double integrals, and category merging. Convergence at $n_{Cat} \approx 3$–4 (strong forcing) or 2 (weak); rime splintering is *detrimental* with one category and beneficial only with $n_{Cat} \geq 2$. The first multiple-free-category bulk scheme.

**Authorship note:** Morrison's first authorship on Parts I & II is nominal; Milbrandt is co-lead (Tier 1), contributing the MY2 framework, the rime-volume budget, and the density-dependent fall-speed approach.

## Operational status and adoption

P3 replaced MY2 in the operational HRDPS as part of ECCC's physics modernization ([[McTaggart-Cowan_etal_2019-summary]]), with the goal of unifying ECCC microphysics on P3 across all model scales — see [[operational-nwp-scale-adaptation]]. It is used in research models including WRF, CM1, and GEM (E3SM adoption ⚠ verify), and serves as a community reference scheme in intercomparisons — see [[scheme-intercomparisons]]. Its original weaknesses (notably hail, first flagged by [[Johnson_etal_2019-summary]]) drove the modern extension program — triple-moment ice, predicted liquid fraction, combined hail capabilities — covered in [[p3-modern-extensions]].

## Why it matters in the research arc

P3 is the culmination of the through-line running from the [[spectral-shape-parameter]] work onward: replace fixed assumptions with predicted physical degrees of freedom. MY (2005) predicted more *moments* of the size distribution; the 2013 graupel-density paper predicted a *property* within a category; P3 generalizes property prediction to all ice, and Part III restores multi-population capability without reintroducing fixed categories.

## Related pages

- [[ice-phase-modernization]] — the 2011–2013 work that diagnosed the problem and built the conceptual bridge
- [[p3-modern-extensions]] — triple-moment ice, liquid fraction, SIP, hail (2019–2025)
- [[operational-nwp-scale-adaptation]] — HRDPS and the path to unified ECCC microphysics
- [[milbrandt-yau-scheme]] — the predecessor scheme and framework donor
- [[scheme-intercomparisons]] — P3/MY2 as community reference schemes
- [[sip-hiwc-mixed-phase]] — observational campaigns informing the ice-phase physics
