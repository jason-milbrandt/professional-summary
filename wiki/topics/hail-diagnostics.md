# 3D Validation and Hail Diagnostics (MY Part III)

**Summary:** MY Part III (2006a) delivered the first-ever cloud-resolving simulation using a fully three-moment bulk microphysics scheme — a 3D reproduction of the 14 July 2000 Pine Lake, Alberta supercell — and introduced diagnostic parameters that let a bulk scheme report a physically meaningful maximum hail size rather than a misleading mean diameter.

**Sources:** [[Milbrandt_Yau_2006ab-summary]] (Part III)

**Last updated:** 2026-08-05

---

## The simulation

Coupled to the Canadian MC2 mesoscale model and nested from 12 km down to 1 km using real synoptic initial conditions, the three-moment [[milbrandt-yau-scheme]] reproduced a realistic HP supercell: bounded weak-echo region, hook echo, mesocyclone, correct propagation speed (48–52 km h⁻¹ vs. observed 46–52), and quantitatively accurate core reflectivity (50–60 dBZ modeled vs. 51–54 dBZ observed). This was, to the authors' knowledge, the first cloud-resolving simulation ever run with a three-moment bulk scheme.

## The hail-size diagnostics

The paper's most durable methodological contribution: since mean-mass diameter alone is a poor indicator of large hail, Part III introduced two new diagnostic parameters computable from a three-moment scheme's higher moments — $N_h^*\{D^*\}$ (the number concentration of hail larger than a threshold size $D^*$) and $R_h^*\{D^*\}$ (its surface flux) — with proposed observability thresholds. These let a bulk scheme report a physically observable maximum hail size rather than a mean that washes out the small population of large stones that actually matters for damage. The method correctly identified a significant flux of grape- and walnut-sized hail (2–3 cm) with negligible golf-ball-sized hail, matching the observed event.

## Why three moments were necessary here

Part III also gave the first mechanistic account of how the shape parameter α can locally *decrease* in a fully coupled 3D simulation — through advection, source/sink terms, and sedimentation acting together — a behavior structurally impossible in the fixed- or diagnosed-α schemes analyzed in [[spectral-shape-parameter]]. This is the concrete 3D demonstration of the theoretical case that paper made: only a genuinely prognostic α can capture this behavior, and [[scheme-complexity-cost-benefit]] later showed that maximum hail size is specifically the field that requires it — no lower-moment configuration reproduced it in the companion sensitivity study.

## Legacy

The $N_h^*/R_h^*$ diagnostic framework is a lasting, self-contained methodological contribution — cited independently of the specific MY scheme implementation, and directly extended in [[p3-modern-extensions]], where the same hail-diagnosis logic (via triple-moment ice in P3, Milbrandt et al. 2021) resolves the analogous hail-signature weakness identified for P3 by Johnson et al. 2019 — see [[scheme-intercomparisons]].

## Related pages

- [[spectral-shape-parameter]] — the theory this simulation validates in 3D
- [[milbrandt-yau-scheme]] — the three-moment scheme being tested
- [[scheme-complexity-cost-benefit]] — the companion sensitivity study using this run as the control
- [[p3-modern-extensions]] — where the hail-diagnosis lineage continues in P3
- [[scheme-intercomparisons]] — Johnson et al. (2019), which first flagged P3's analogous hail weakness
