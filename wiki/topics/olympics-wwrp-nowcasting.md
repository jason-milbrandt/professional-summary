# Winter Olympics and WWRP Nowcasting / Field Projects (Tier 3)

**Summary:** Eight papers documenting Milbrandt's contribution of high-resolution GEM-LAM/HRDPS NWP capability — using MY2 microphysics — to a series of World Weather Research Programme field projects and Olympic forecast demonstration projects: Vancouver 2010, Sochi 2014, the Canadian Arctic Weather Science project, and the 25-year WWRP nowcasting retrospective.

**Sources:** [[Isaac_etal_2012-summary]], [[Mailhot_etal_2012-summary]], [[Mo_etal_2012-summary]], [[Theriault_2012-summary]], [[Kiktev_etal_2017-summary]], [[Joe_etal_2020-summary]], [[Joe_etal_2025-summary]], [[Taylor_etal_2011-summary]]

**Last updated:** 2026-08-05

---

## Vancouver 2010: SNOW-V10

**Isaac et al. (2012)** is the project overview for SNOW-V10, a WWRP project that combined an unprecedented observational network in complex mountain terrain with real-time NWP and nowcast blending during the Games. **Mailhot et al. (2014)** describes the experimental high-resolution GEM-LAM system built for the Olympics — nested 15/2.5/1-km grids — documenting what the paper calls the first operational-style use of a full two-moment scheme (MY2) in this kind of forecast system, and introducing the snow-to-liquid-ratio diagnostic derived directly from MY2's predicted hydrometeor fields (see [[ice-phase-modernization]] for the SLR paper itself). The 1-km configuration essentially eliminated the operational system's wind-speed bias and reduced 2-m temperature errors by over 1°C.

Three companion papers use the same GEM-LAM/MY2 system to study specific Olympic-venue weather phenomena: **Mo et al. (2012)** characterizes "Harvey's Cloud," a recurring mid-mountain cloud hazard at Whistler, attributing it to the interaction of channeled upslope flow with leeward subsidence, with the 1-km MY2-based model resolving the driving mesoscale flow structures. **Thériault et al. (2012)** analyzes a 13–14 February 2010 near-0°C storm and shows diabatic cooling from melting snow — not synoptic warm advection — dominated the observed rain/snow transition, a finding structurally related to the melting-layer physics in [[process-studies]] (Thériault et al. 2015). Both papers document real biases in the operational-style GEM-LAM/MY2 configuration (valley temperature underprediction, wind-direction errors) alongside its successes.

## Sochi 2014: FROST-2014

**Kiktev et al. (2017)** documents FROST-2014, the WWRP project for the Sochi Olympics, in which ECCC contributed the GEM-LAM system (using MY2, the same system described in [[operational-nwp-scale-adaptation]]'s Milbrandt et al. 2016) at 2.5-, 1-, and 0.25-km grid spacing. The hectometric 0.25-km configuration was the standout performer for a critical low-visibility event, correctly forecasting a brief clearing window that was used operationally to reschedule the women's biathlon mass start — a concrete example of NWP output directly informing a live operational decision.

## Canadian Arctic Weather Science and the 25-year retrospective

**Joe et al. (2020)** introduces the CAWS project's Iqaluit reference observation site, using [[operational-nwp-scale-adaptation]]'s HRDPS (with P3 microphysics) as the NWP system under evaluation for Arctic-specific challenges — high blowing-snow frequency, persistent blizzards, and systematic wind-direction disagreement between HRDPS and multi-instrument profiling observations. **Joe et al. (2025)** is a 38-author, 25-year retrospective review of WWRP nowcasting and mesoscale-research field projects (Sydney 2000 through PyeongChang 2018), synthesizing cross-cutting lessons on technology transfer, verification challenges, and the expansion of nowcasting from summer convection to winter, aviation, and urban applications — with Milbrandt's contribution reflecting ECCC's participation across this entire project series, most directly through Vancouver 2010.

## A non-Olympic field project: UNSTABLE 2008

**Taylor et al. (2011)** describes a pilot severe-thunderstorm field campaign in the Alberta foothills, where Milbrandt's contribution was the microphysics component of the supporting GEM-LAM NWP runs (single-moment MY2005 at 2.5 km, double-moment at 1 km). The paper documents the region's severe-storm risk and an early spurious-convection problem in the 1-km configuration later resolved via a vertical-coordinate change.

## Position in the arc

This cluster is the applied, high-visibility face of [[milbrandt-yau-scheme]] and [[operational-nwp-scale-adaptation]]: the same GEM-LAM/MY2 (later HRDPS/P3) system built for daily Canadian forecasting repeatedly deployed and stress-tested in complex mountain terrain under the highest possible public scrutiny — the Olympics — and in sustained field-project settings (UNSTABLE, CAWS) that generated observational datasets used elsewhere in the research program, including [[process-studies]]'s valley-flow study.

## Related pages

- [[milbrandt-yau-scheme]] — MY2, the scheme deployed in all these GEM-LAM systems
- [[operational-nwp-scale-adaptation]] — HRDPS, the successor system evaluated in CAWS
- [[process-studies]] — the Thériault et al. (2015) valley-flow study building on the same Whistler 2010 event
- [[ice-phase-modernization]] — the snow-to-liquid-ratio diagnostic introduced via the Olympic system
