# Observational Validation and Sedimentation Theory (2008–2010)

**Summary:** Three papers confronted the Milbrandt–Yau scheme with real aircraft data for the first time and generalized the theory of sedimentation errors to arbitrary bulk-scheme configurations: the two-part IMPROVE-2 orographic evaluation (2008, 2010) and the comprehensive sedimentation-error study with McTaggart-Cowan (2010).

**Sources:** [[Milbrandt_etal_2008-summary]] (IMPROVE-2 Part I), [[Milbrandt_etal_2010-summary]] (IMPROVE-2 Part II), [[Milbrandt_McTaggart-Cowan_2010-summary]] (sedimentation errors)

**Last updated:** 2026-08-05

---

## IMPROVE-2 Part I: first in situ validation (2008)

Until this study, the [[milbrandt-yau-scheme]] had only been tested against a convective case (Pine Lake, see [[hail-diagnostics]]) with no in situ microphysical measurements. The IMPROVE-2 campaign's 13–14 December 2001 Oregon Cascades orographic event — intensely observed by radar, rain gauges, and two instrumented aircraft — provided the first opportunity to validate the scheme against real particle-size and mass-content measurements, and allowed direct comparison against MM5/Reisner-2 simulations of the same case published by other groups.

Running the full triple-moment scheme in GEM at 1-km resolution, the simulation reproduced a realistic spatial precipitation pattern and, critically, **realistic mean-mass particle diameters** that correctly captured the observed trend of increasing snow size with decreasing altitude — direct observational confirmation of the multimoment thesis from [[spectral-shape-parameter]]: independently predicting mass and number lets the mass-to-number ratio (and hence mean size) evolve realistically. The paper also isolated a **microphysics-attributable difference**: unlike the single-moment Reisner-2 scheme, MY did *not* produce a pronounced leeside precipitation overprediction. Concrete deficiencies were also identified — overpredicted snow mass aloft (up to 7× in places) and underpredicted cloud liquid water — that directly motivated the snow-category work in [[ice-phase-modernization]].

## The sedimentation-error theory (2010)

Milbrandt & McTaggart-Cowan (2010) generalized the [[spectral-shape-parameter]] sedimentation analysis from the specific $M_0$–$M_3$ moment pair examined in MY Part I to *any* combination of prognostic moments across one-, two-, and three-moment schemes. Using an idealized 1D framework with an analytic bin-model reference, the paper delivered a comprehensive error ranking: the standard two-moment $M_0$–$M_3$ fixed-shape scheme performs catastrophically (error score ~1000, worse than even a one-moment scheme), while three-moment schemes are far more robust to moment choice. Two practical, easily implementable fixes were proposed for existing two-moment schemes — a generalized diagnostic-shape-parameter relation, and a diagnostic fall-speed-ratio approach — both dramatically reducing sedimentation errors without redesigning the scheme's source/sink terms.

## IMPROVE-2 Part II: isolating the moment count (2010)

The companion paper used the Part I triple-moment run as a control and compared double-moment (with diagnostic α) and single-moment configurations, plus a separate single-moment scheme (Kong–Yau), against it. The central result: **double-moment with diagnostic α closely reproduces triple-moment** for this orographic case — confirming, in a real-data setting, the [[scheme-complexity-cost-benefit]] finding that a diagnosed-α two-moment configuration captures most of the three-moment benefit. It also pinpointed the specific process-level causes of the leeside-overprediction bias seen in other schemes: the absence of a latent-heat-effect term in snow deposition, and instantaneous rather than explicit snow melting — mechanistic findings later relevant to the melting-and-phase-transition work in [[process-studies]].

## Position in the arc

This phase sits between the foundational MY series ([[milbrandt-yau-scheme]], [[hail-diagnostics]], [[scheme-complexity-cost-benefit]]) and [[ice-phase-modernization]]: it is where the multimoment thesis first met real observations, confirmed the scheme's core claims, and exposed the specific ice-phase deficiencies (snow mass, rigid categories) that the 2011–2013 modernization work then addressed.

## Related pages

- [[spectral-shape-parameter]] — the theory this validates observationally
- [[milbrandt-yau-scheme]] — the scheme being evaluated
- [[scheme-complexity-cost-benefit]] — the moment-count finding confirmed here in a real case
- [[ice-phase-modernization]] — where the identified snow-mass deficiency was addressed
- [[process-studies]] — later work on melting-layer physics building on the leeside mechanism findings
