# Operational NWP System Development, Modernization, and Evaluation (Tier 3)

**Summary:** Five papers documenting or evaluating ECCC's GEM/HRDPS forecast systems, where Milbrandt contributed the microphysics component (MY2 → P3 transition) and related domain expertise — the institutional record of how his schemes moved through Canadian operational NWP.

**Sources:** [[McTaggart-Cowan_etal_2019-summary]], [[RPN_report-summary]], [[Mo_etal_2019-summary]], [[Qu_etal_2018-summary]], [[Qu_etal_2020-summary]]

**Last updated:** 2026-08-05

---

## The physics modernization (McTaggart-Cowan et al. 2019)

The comprehensive documentation of a multiyear physics upgrade across ECCC's entire NWP suite (GDPS, RDPS, REPS), addressing an overactive global hydrological cycle and unphysical vertical-resolution sensitivity. Among its many components, the paper documents [[p3-scheme]] replacing [[milbrandt-yau-scheme]] (MY2) in HRDPS — a milestone explicitly flagged in [[operational-nwp-scale-adaptation]]'s 2016 HRDPS paper as the intended direction — showing improved spatial distribution of orographic precipitation attributable to P3's continuous rather than category-based treatment of riming-induced fall-speed change. This is the formal institutional record of the MY2→P3 operational transition.

## The institutional retrospective (Ritchie et al. 2022 / "RPN report")

A six-decade review of Recherche en Prévision Numérique's contributions to NWP, published for the Meteorological Service of Canada's 150th anniversary. It documents that MY2 was the operational HRDPS microphysics scheme for nearly a decade (2014–2018) and records the September 2018 P3 upgrade as improving precipitation skill scores in mountainous regions — an institutional acknowledgment, alongside [[operational-nwp-scale-adaptation]]'s Milbrandt et al. (2016), of the scheme's operational significance within RPN's broader history.

## Diagnosing a specific MY2 operational weakness (Mo et al. 2019)

Using two landfalling atmospheric-river storms over British Columbia, this paper identified a systematic MY2 bias toward overpredicting orographic-precipitation spillover onto leeward slopes — a mechanistic finding tied to MY2's category-conversion threshold between snow and graupel: in light-riming conditions snow mass increases without a corresponding increase in fall speed, so hydrometeors drift farther downwind than observed before falling out. A parallel P3 run for the second storm showed the bias substantially corrected (leeward RMSE improved from ~17 mm with the diagnostic schemes to 10.3 mm with P3), providing independent, real-case confirmation of the mechanism that motivated [[p3-scheme]]'s rejection of fixed category-conversion thresholds in the first place. This finding is cited directly in [[McTaggart-Cowan_etal_2019-summary]] as justification for the operational MY2→P3 upgrade.

## Cloud- and moisture-representation evaluation (Qu et al. 2018, 2020)

Two studies use GEM with MY2 to evaluate specific representational weaknesses at cloud-resolving resolution. **Qu et al. (2018)** compared GEM cloud fields against CloudSat, GOES-13, and dual-aircraft in situ data for a tropical mesoscale convective system, finding excess mid-level graupel/snow attributable to MY2's lack of secondary ice production — a gap later addressed for a different application (freezing rain) via SIP in [[p3-modern-extensions]]. **Qu et al. (2020)** used nested GEM/MY2 simulations at resolutions from 10 km to 250 m to show that gravity-wave breaking near overshooting convective tops, not the mean updraft, dominates cross-tropopause water-vapor transport — and that coarse-resolution convective parameterizations produce a spurious stratospheric moist bias because they fail to represent the "trapping" of ice in cold overshooting tops, a microphysical/dynamical process unresolvable below ~1-km grid spacing.

## Position in the arc

This cluster is the diagnostic and institutional-memory complement to [[operational-nwp-scale-adaptation]]'s direct system-building papers: where Milbrandt et al. (2016) and Jouan et al. (2020) build and deploy the systems, this cluster documents their evaluation, weaknesses, and the formal record of the MY2→P3 transition across ECCC's operational suite.

## Related pages

- [[operational-nwp-scale-adaptation]] — the HRDPS build-and-deploy papers this cluster evaluates
- [[milbrandt-yau-scheme]] — MY2, the scheme diagnosed and replaced across this cluster
- [[p3-scheme]] — P3, the replacement scheme whose benefits are independently confirmed here
- [[p3-modern-extensions]] — the SIP-based fix related to the graupel/snow bias found in Qu et al. (2018)
