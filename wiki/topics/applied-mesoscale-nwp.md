# Applied Mesoscale NWP — the Starting Point (2001)

**Summary:** The Saguenay flood study (Milbrandt & Yau 2001) predates Milbrandt's microphysics focus entirely — it is a dynamical-meteorology case study using piecewise potential-vorticity inversion and factor separation to decompose the causes of a catastrophic 1996 Quebec flood. Its significance is contextual: it establishes the modeling environment, the collaborator, and the applied-NWP motivation from which the microphysics research program grew.

**Sources:** [[Milbrandt_Yau_2001-summary]]

**Last updated:** 2026-08-05

---

## The study

A 48-hour mesoscale simulation of the 19–21 July 1996 Saguenay flood cyclone — at the time the most catastrophic flood in Canadian history (10 deaths, ~CAD $800 million in damage) — using the Canadian MC2 model at 20-km resolution with Kong–Yau (1997) explicit cold microphysics. Piecewise PV inversion decomposed the cyclone's explosive deepening into contributions from an upper-level dry PV anomaly (47%), a low-level moist PV anomaly from latent heating (41%), and surface baroclinicity (12%). Factor-separation experiments isolating the Saguenay valley and an adjacent mountain range showed orography contributed roughly 20–24% of the regional 48-hour accumulated precipitation, with local contributions exceeding 30%.

## Why it belongs in this wiki

This is Milbrandt's earliest published work and his only paper in applied dynamical meteorology rather than microphysics parameterization — a graduate contribution from his McGill doctoral studies under M. K. Yau. Two things about it matter for the research arc that follows:

- **The modeling framework.** The simulation used the Kong–Yau explicit microphysics scheme within MC2 — the same environment from which the [[milbrandt-yau-scheme]] emerged four years later. Demonstrating the importance of explicit (rather than simplified) microphysics for mesoscale precipitation simulation here is the empirical backdrop against which Milbrandt's own scheme development is motivated.
- **The collaborator.** The paper establishes the long-running Milbrandt–Yau collaboration that produced the four-part MY series (2005–2006) — see [[milbrandt-yau-scheme]], [[hail-diagnostics]], and [[scheme-complexity-cost-benefit]].

## Position in the arc

Everything else in this wiki follows from a decision this paper doesn't directly make but sets up the conditions for: that getting cloud and precipitation microphysics right is a first-order factor in mesoscale forecast skill, not a secondary detail. The tools (piecewise PV inversion, factor separation) and the applied-NWP motivation carried forward, even though the specific scientific focus — explicit microphysics parameterization — only crystallized in the work that followed.

## Related pages

- [[milbrandt-yau-scheme]] — the scheme that emerged from the same MC2/Kong–Yau modeling environment
- [[hail-diagnostics]] — the first 3D application of the MY scheme, in the same MC2 framework
