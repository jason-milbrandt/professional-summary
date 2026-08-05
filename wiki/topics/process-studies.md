# Process Studies Enabled by the Schemes (Tier 2)

**Summary:** Two Tier 2 papers use Milbrandt's schemes as research instruments to answer questions beyond scheme development itself: how CCN concentration affects deep convection through ice-phase (not just warm-phase) pathways, and how melting snow drives valley-flow reversal in complex terrain.

**Sources:** [[Jouan_Milbrandt_2019-summary]], [[Theriault_etal_2015-summary]]

**Last updated:** 2026-08-05

---

## CCN sensitivity of deep convection (Jouan & Milbrandt 2019)

Using [[milbrandt-yau-scheme]] (MY2) in GEM at 1-km resolution to simulate an MC3E squall line, this study shows that a storm's response to cloud condensation nuclei (CCN) loading acts not only through the well-understood warm-phase pathway (droplet size, autoconversion) but also through the ice phase — specifically, the collection efficiency between graupel and cloud droplets, which is strongly modulated by CCN-driven changes in mean droplet size. The paper demonstrates that this indirect pathway is only visible with a properly two-moment, prognostic-density treatment of graupel: using prognostic graupel density (from Milbrandt & Morrison 2013, see [[ice-phase-modernization]]) roughly halves the magnitude of the CCN-driven ice-phase response compared to fixed density, and reducing graupel to one-moment eliminates most of the CCN sensitivity entirely, because the size-sorting mechanism that mediates the effect is absent. The result directly supports the case for property-based schemes over category-based ones — i.e., for [[p3-scheme]] over MY2 — since the sensitivity depends on exactly the kind of continuously evolving particle property P3 was designed to represent.

## Melting-snow valley flow (Thériault et al. 2015)

A semi-idealized 2D WRF study of the 13–14 February 2010 Whistler/Callaghan Valley event during the Vancouver 2010 Winter Olympics (see [[olympics-wwrp-nowcasting]] for the broader Olympics context), building on a 1D companion paper (Milbrandt et al. 2014). The central finding: melting-induced cooling from snow is both necessary and sufficient to reverse the valley's airflow — suppressing the cooling feedback eliminates the reversal in every microphysics scheme tested (MY2, Thompson, and a bin-resolving scheme). Melting increases the moist non-dimensional mountain height from 1.9 to 3.3, moving the flow into a dynamical regime where stagnation and reversal are strongly favored. Milbrandt contributed MY2 as the control scheme and his snow-melting expertise; the study found MY2 produces faster cooling than the Thompson scheme due to differences in snow fall speed and melting-process formulation — a reminder that even in a fundamentally dynamical problem, microphysical scheme choice still matters quantitatively.

## Why these count as "process studies"

Both papers use an existing, validated scheme as a diagnostic instrument to answer a question that isn't primarily about the scheme itself — CCN–aerosol interaction in one case, valley dynamics in the other. This is a distinct role from scheme *development* papers ([[ice-phase-modernization]], [[p3-scheme]]) or system *documentation* papers ([[operational-nwp-scale-adaptation]]): here the microphysics scheme's fidelity is what makes the underlying physical question answerable at all.

## Related pages

- [[milbrandt-yau-scheme]] — the MY2 scheme used as the research instrument in both studies
- [[ice-phase-modernization]] — the prognostic graupel-density work central to the CCN result
- [[p3-scheme]] — the property-based alternative the CCN study's findings support
- [[olympics-wwrp-nowcasting]] — the Vancouver 2010 field-project context for the valley-flow study
