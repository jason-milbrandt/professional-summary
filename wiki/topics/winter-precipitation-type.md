# Winter Precipitation Phase and Type (Tier 3)

**Summary:** Two papers applying Milbrandt's schemes to winter precipitation-type simulation — an application directly enabled by the schemes' explicit ice-phase and, later, liquid-fraction capabilities. Thériault et al. (2006) is an early McGill-era extension of the original MY scheme; Cholette et al. (2020) is the first real-case 3D test of the P3 liquid-fraction extension on one of Canada's most severe ice storms.

**Sources:** [[Theriault_etal_2006-summary]], [[Cholette_etal_2020-summary]]

**Last updated:** 2026-08-05

---

## Extending MY to semimelted particles (Thériault et al. 2006)

A 1D cloud-model study, built directly on the double-moment [[milbrandt-yau-scheme]] framework and extended with new semimelted hydrometeor categories (wet snow, slush, refrozen wet snow), examining how six precipitation types — freezing rain, ice pellets, snow, slush, wet snow, and refrozen wet snow — form as snow falls through a temperature-inversion structure. The central finding: without semimelted categories the model can only produce four precipitation types; with them, up to eight, and semimelted particles turn out to be the dominant pathway for ice-pellet formation in many scenarios (via slush refreezing, not just direct rain refreezing) — a mechanistic result that anticipates the entire liquid-fraction research thread a decade later. Milbrandt was a McGill co-author at the time, alongside PhD supervisor M. K. Yau, providing the scheme foundation for lead student Thériault's thesis work.

## The 1998 Ice Storm test of predicted liquid fraction (Cholette et al. 2020)

The first real-case, full-3D application of P3's predicted-liquid-fraction extension (introduced in [[p3-modern-extensions]]'s Cholette et al. 2019), simulating the catastrophic January 1998 North American Ice Storm in WRF at 3-km resolution. Predicting the bulk liquid fraction on mixed-phase particles — rather than transferring all melted mass instantaneously to rain, as the original P3 does — reduced freezing-rain accumulation by up to ~30% in mixed ice-pellet/freezing-rain regions and let the model produce ice pellets and wet snow explicitly, precipitation types the original scheme cannot distinguish. The paper also flagged a specific limitation: total solid accumulation was underpredicted near Montreal, attributed in part to the single-ice-category P3 configuration's inability to represent secondary ice production — the same gap that [[p3-modern-extensions]]'s Cholette et al. (2024) later closed for a different freezing-rain bias using two ice categories.

## Position in the arc

These two papers bookend the liquid-fraction research thread at a 14-year remove: Thériault et al. (2006) demonstrates *conceptually*, in 1D and with an ad hoc extension to the original MY scheme, that semimelted particles are essential for realistic winter precipitation-type diversity; Cholette et al. (2020) delivers the same insight as a proper prognostic capability in P3, tested against a real, high-impact 3D case. Together they frame the "why this matters" and "here's how we actually built it" halves of the same scientific argument, with [[p3-modern-extensions]] carrying the capability to full operational maturity in between.

## Related pages

- [[milbrandt-yau-scheme]] — the original scheme extended in the 2006 paper
- [[p3-modern-extensions]] — the operational liquid-fraction and SIP capability this cluster's 2020 paper tests
- [[precipitation-type-prediction]] — the Tier 2 freezing-rain diagnosis/fix papers this cluster's findings parallel
