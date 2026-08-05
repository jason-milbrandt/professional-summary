# Wiki Index

**Summary:** Content catalog of every page in this wiki. Updated on every ingest and every page creation.

**Last updated:** 2026-08-05

---

## Main page

- [[professional-summary]] (`../professional-summary.md`) — the aggregated synthesis of all 68 papers: author profile, intellectual through-line, chronological arc, thematic contributions, per-paper table, tier system, Tier 3 related contributions.

## Topic pages (`topics/`)

Thematic pages synthesizing across papers. Seeded from `professional-summary.md` sections 4.1–4.12 and 8.1–8.7.

### Tier 1/2 themes

- [[spectral-shape-parameter]] — the gamma-PSD shape parameter α: size sorting, source-term errors, the scheme-skill hierarchy
- [[milbrandt-yau-scheme]] — the MY multimoment scheme: three-moment closure, six categories, the operational MY2
- [[hail-diagnostics]] — 3D validation and maximum-hail-size diagnostics (N*_h, R*_h)
- [[scheme-complexity-cost-benefit]] — one→two→three moments: where the skill gain actually is
- [[observational-validation-sedimentation]] — IMPROVE-2 aircraft validation and the theory of sedimentation errors
- [[ice-phase-modernization]] — benchmarking, snow-category updates, prognostic graupel density: the bridge to P3
- [[p3-scheme]] — the Predicted Particle Properties scheme, Parts I–III
- [[p3-modern-extensions]] — triple-moment ice, predicted liquid fraction, SIP, combined hail capabilities
- [[operational-nwp-scale-adaptation]] — HRDPS, subgrid cloud fraction, P3 for global scales
- [[process-studies]] — CCN sensitivity, melting-snow valley flow: the schemes as research instruments
- [[precipitation-type-prediction]] — freezing-rain diagnosis/fixes and density prediction adopted abroad
- [[applied-mesoscale-nwp]] — the 1996 Saguenay flood study: the program's starting point

### Tier 3 themes

- [[scheme-intercomparisons]] — MY2/P3 as community reference schemes in intercomparisons and process studies
- [[sip-hiwc-mixed-phase]] — secondary ice production, high ice water content, mixed-phase cloud observations
- [[gem-mach-air-quality]] — the MY2/P3 microphysics component of ECCC's coupled air-quality model
- [[olympics-wwrp-nowcasting]] — Vancouver 2010, Sochi 2014, and WWRP field-project NWP support
- [[fog-visibility]] — fog, ice fog, visibility parameterization, and instrumentation collaborations
- [[nwp-system-development]] — GEM/HRDPS system documentation, modernization, and evaluation
- [[winter-precipitation-type]] — winter precipitation phase/type studies enabled by the schemes

## Source summaries (`summaries/`)

One structured summary per paper. Tier = Milbrandt's authorship role (see `../professional-summary.md` §7).

### Tier 1 — lead contributor

- [[Milbrandt_Yau_2001-summary]] — MC2 simulation + PV-inversion/factor-separation diagnosis of the 1996 Saguenay flood.
- [[Milbrandt_Yau_2005a-summary]] — MY Part I: theory of the shape parameter α; size-sorting and source-term errors; scheme-skill hierarchy.
- [[Milbrandt_Yau_2005b-summary]] — MY Part II: three-moment closure (predicted reflectivity); the full six-category scheme.
- [[Milbrandt_Yau_2005ab-summary]] — combined summary of MY Parts I & II.
- [[Milbrandt_Yau_2006a-summary]] — MY Part III: first 3D three-moment simulation (Pine Lake hailstorm); N*_h/R*_h hail diagnostics.
- [[Milbrandt_Yau_2006b-summary]] — MY Part IV: sensitivity tests; one→two moments is the dominant gain; only 3-moment captures max hail size.
- [[Milbrandt_Yau_2006ab-summary]] — combined summary of MY Parts III & IV.
- [[Milbrandt_etal_2008-summary]] — IMPROVE-2 Part I: first aircraft validation of MY; realistic sizes, overpredicted snow mass.
- [[Milbrandt_McTaggart-Cowan_2010-summary]] — sedimentation errors: ranks all moment configurations; diagnostic-m / V_k/V_j fixes.
- [[Milbrandt_etal_2010-summary]] — IMPROVE-2 Part II: scheme identity > moment count for the orographic case; leeside-overprediction mechanism.
- [[Milbrandt_etal_2012_snowmelting-summary]] — 1D snow melting: partial-melting limitation of bulk schemes; 1D forecaster tool.
- [[Milbrandt_etal_2012_PAAG-summary]] — duplicate of the same paper; see [[Milbrandt_etal_2012_snowmelting-summary]] (authoritative).
- [[Milbrandt_etal_2012_snowdensity-summary]] — snow-to-liquid ratio: first explicit SLR from a bulk scheme; Vancouver 2010 deployment.
- [[Milbrandt_Morrison_2013-summary]] — prognostic graupel density: adds B_g = q_g/ρ_g; density-dependent fall speeds; the bridge to P3.
- [[Morrison_Milbrandt_2015_2016-P3-summary]] — combined summary of P3 Parts I–III (Morrison & Milbrandt 2015a; Morrison et al. 2015b; Milbrandt & Morrison 2016).
- [[Milbrandt_Morrison_2016-summary]] — P3 Part III: multiple free ice categories; ends property dilution.
- [[Milbrandt_etal_2016-summary]] — HRDPS: description/verification of Canada's operational 2.5-km system (GEM + MY2).
- [[Milbrandt_etal_2021-summary]] — triple-moment ice in P3: adds Z_i,tot; physical size-sorting control; better hail.
- [[Milbrandt_etal_2025-summary]] — P3 hail: liquid fraction (smaller hail) vs. multi-category (larger hail); LF-2CAT full hail lifecycle.

### Tier 2 — key co-author

- [[Morrison_Milbrandt_2011-summary]] — MOR vs. MY intercomparison: graupel-vs-hail is the dominant inter-scheme difference.
- [[Chosson_etal_2014-summary]] — scale-adaptive MY2: subgrid cloud/precipitation fraction; two-moment microphysics at coarse resolution.
- [[Theriault_etal_2015-summary]] — melting-snow valley flow: melting-induced cooling necessary and sufficient for flow reversal.
- [[Barszcz_etal_2018-summary]] — freezing-rain fix: excess rain–graupel collisional freezing; −5 °C threshold deployed operationally.
- [[Cholette_etal_2019-summary]] — P3 liquid fraction: adds q_i,liq; explicit wet snow and ice pellets.
- [[Jouan_Milbrandt_2019-summary]] — CCN and ice phase: CCN response acts through graupel riming; supports property-based schemes.
- [[Jouan_etal_2020-summary]] — P3 for global NWP: SCPF applied to P3 at 25 km; path to unified ECCC microphysics.
- [[Cholette_etal_2023-summary]] — triple-moment + liquid fraction in P3: stronger cold pools, explicit bright band; operational HRDPS config.
- [[Park_etal_2024-summary]] — predicted density in WDM6: independent Korean port of the MM2013 density method.
- [[Cholette_etal_2024-summary]] — SIP for freezing rain: Hallett–Mossop + 2 categories cuts freezing-rain bias up to 98%.
- [[Cholette_etal_2025-summary]] — wet snow in orographic terrain: first 3D NWP evaluation of P3 liquid fraction vs. ICE-POP 2018.

### Tier 3 — contributing co-author

- [[Theriault_etal_2006-summary]] — winter precipitation types simulated on the MY (2005) double-moment foundation.
- [[Gultepe_Milbrandt_2007-summary]] — warm-fog microphysics + MC2/MY simulation demonstrating a fog-visibility parameterization.
- [[Gultepe_Milbrandt_2010-summary]] — probabilistic visibility parameterizations; NWP/GEM context.
- [[Taylor_etal_2011-summary]] — UNSTABLE 2008 severe-thunderstorm experiment; 1-km GEM-LAM with MY2.
- [[Isaac_etal_2012-summary]] — SNOW-V10 Vancouver 2010 Olympics nowcasting; GEM-LAM NWP capability.
- [[Mailhot_etal_2012-summary]] — Vancouver 2010 experimental high-resolution forecast system; MY2 + SLR diagnostic.
- [[Mo_etal_2012-summary]] — mid-mountain clouds at Whistler during Vancouver 2010; MY2 in nested GEM-LAM.
- [[Theriault_2012-summary]] — precipitation phase/intensity processes during Vancouver 2010; MY2 in GEM-LAM.
- [[Gultepe_etal_2014_BAMS-summary]] — Arctic ice fog (FRAM–Ice Fog); GEM context and MY scheme.
- [[Gong_etal_2015-summary]] — aerosol–cloud interaction in fully coupled GEM-MACH; MY double-moment scheme.
- [[Makar_etal_2015a-summary]] — air-pollution/weather feedbacks Part 1 (effects on weather); GEM-MACH/MY2, AQMEII-2.
- [[Makar_etal_2015b-summary]] — companion Part 2 (effects on chemistry).
- [[Dawson_etal_2016-summary]] — buoyancy analysis of the 3 May 1999 OKC tornadic supercell; MY scheme provided.
- [[Morrison_etal_2016-summary]] — advection of coupled hydrometeor quantities (SFVT); developed with P3/MY.
- [[Fan_etal_2017-summary]] — MC3E squall-line intercomparison Part I (convective updrafts); MY2 one of eight schemes.
- [[Jensen_2017-summary]] — ice-shape evolution (ISHMAEL scheme); P3 and graupel-density work as precursors.
- [[Kiktev_etal_2017-summary]] — FROST-2014 Sochi Olympics project; GEM-LAM at 2.5/1/0.25 km.
- [[Qu_etal_2018-summary]] — GEM simulated clouds vs. CloudSat/GOES-13/aircraft; MY scheme and interpretation.
- [[Han_etal_2019-summary]] — MC3E intercomparison Part II (stratiform precipitation); MY2 and P3 among eight schemes.
- [[Johnson_etal_2019-summary]] — rimed-ice representation and polarimetric signatures; first flagged P3's hail weakness.
- [[McTaggart-Cowan_etal_2019-summary]] — modernization of Canadian NWP physics; documents the operational MY2→P3 transition.
- [[Mo_etal_2019-summary]] — hydrometeor drift in orographic precipitation; MY2 bias and P3 improvement.
- [[Paukert_etal_2019-summary]] — three-moment rain developed and tested within the P3 framework.
- [[Stanford_etal_2019-summary]] — stochastic ice-microphysics framework built on P3.
- [[Joe_etal_2020-summary]] — Canadian Arctic Weather Science project (Iqaluit); HRDPS/GEM expertise.
- [[Korolev_etal_2020-summary]] — environmental conditions for secondary ice production; cloud-microphysics expertise.
- [[Morrison_etal_2020-summary]] — community review of cloud/precipitation microphysics modeling; highest-cited Tier 3 paper.
- [[Qu_etal_2020-summary]] — convective moistening of the extratropical lower stratosphere; GEM/MY2 infrastructure.
- [[Cholette_etal_2020-summary]] — predicted liquid fraction and the 1998 Ice Storm; P3 code base provided.
- [[Boudala_etal_2021-summary]] — surface visibility/ceiling/humidity instrument performance (Cold Lake).
- [[Huang_etal_2021-summary]] — high ice water content in tropical convection (HAIC-HIWC); P3 one of four schemes.
- [[Makar_etal_2021-summary]] — forest-fire aerosol–weather feedbacks; aerosol indirect effect in P3.
- [[Boudala_etal_2022-summary]] — CanESM cloud/cloud-radiative-forcing climatologies vs. CALIPSO/CERES.
- [[Korolev_Milbrandt_2022-summary]] — "How are mixed-phase clouds mixed?"; co-conceptualization with Korolev.
- [[Qu_etal_2022-summary]] — impacts of secondary ice production on tropical convection; P3/GEM expertise.
- [[RPN_report-summary]] — invited review of RPN's NWP contributions; microphysics-parameterization sections.
- [[Boudala_Milbrandt_2023-summary]] — solid precipitation and visibility measurements (CARE & Bratt's Lake).
- [[Joe_etal_2025-summary]] — insights from WWRP nowcasting/mesoscale working-group projects.
