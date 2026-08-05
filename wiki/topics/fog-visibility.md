# Fog, Visibility, and Instrumentation (Tier 3)

**Summary:** Six collaborations, chiefly with I. Gultepe and F. Boudala, on fog microphysics, visibility parameterization, and surface-instrument evaluation — a domain where Milbrandt's schemes and NWP expertise enabled applications well outside precipitation forecasting.

**Sources:** [[Gultepe_Milbrandt_2007-summary]], [[Gultepe_Milbrandt_2010-summary]], [[Gultepe_etal_2014_BAMS-summary]], [[Boudala_etal_2021-summary]], [[Boudala_etal_2022-summary]], [[Boudala_Milbrandt_2023-summary]]

**Last updated:** 2026-08-05

---

## Fog visibility parameterization enabled by multimoment microphysics

**Gultepe & Milbrandt (2007)** derived a new fog-visibility parameterization depending on both liquid water content and droplet number concentration — an improvement over existing schemes using LWC alone, since droplet number can vary two orders of magnitude at fixed LWC. Demonstrating it in an NWP context specifically required a scheme that predicts droplet number independently of mass: Milbrandt ran the MC2 model with the triple-moment [[milbrandt-yau-scheme]] to show the parameterization could be applied operationally, producing simulated visibility (50–500 m) consistent with FRAM project observations (30–500 m). This is a direct illustration of the "predict, don't fix" design philosophy at the core of [[spectral-shape-parameter]] paying off in an unanticipated application domain.

**Gultepe & Milbrandt (2010)** derived probabilistic (percentile-based) visibility relationships as functions of rain rate and relative humidity from multi-year FRAM observations, finding existing operational (RUC) visibility schemes show systematic biases near saturation. This paper did not use MY2; Milbrandt's contribution was NWP context and a GEM-based case-study demonstration of an integrated visibility approach combining fog, humidity, and rain effects.

## Arctic ice fog (Gultepe et al. 2014)

The FRAM–Ice Fog project at Yellowknife documented ice crystal concentrations exceeding 1000 L⁻¹ — an order of magnitude above what GEM/MY2 predicts (~100 L⁻¹) — and non-spherical crystal shapes at −35°C, contradicting assumptions used in the scheme's ice nucleation parameterization (Meyers et al. 1992, identified as inappropriate for Arctic conditions). A new ice-fog visibility parameterization was proposed, again requiring a scheme — MY2 — that predicts both ice water content and ice number concentration independently. This paper is direct evidence that the multimoment design enabling fog work in temperate climates ([[Gultepe_Milbrandt_2007-summary]]) breaks down under Arctic conditions, flagging Arctic-specific ice nucleation as an open gap in the scheme.

## Instrumentation and measurement evaluation (Boudala et al. 2021, 2022; Boudala & Milbrandt 2023)

Three later papers, all with Milbrandt in a writing-review-only role (explicitly stated in the author-contributions statements), evaluate surface instrumentation relevant to NWP model validation: automated visibility/ceiling/humidity sensors at Cold Lake, Alberta (2021); CanESM5 cloud fraction and radiative forcing against CALIPSO-GOCCP and CERES satellite products (2022); and solid-precipitation gauge transfer functions and visibility-snowfall parameterizations at two Canadian sites (2023). These papers are peripheral to Milbrandt's core microphysics development — his contribution was ECCC-affiliation-based domain expertise and manuscript review rather than scientific leadership — but they are part of the broader observational infrastructure (Boudala's ongoing program) that supports validation of models built on his schemes.

## Position in the arc

The two Gultepe collaborations and the 2014 Arctic ice-fog paper are genuine extensions of the multimoment design philosophy into a new application domain; the three Boudala instrumentation papers are lower-involvement contributions reflecting institutional collaboration rather than a distinct research thread.

## Related pages

- [[spectral-shape-parameter]] — the "predict, don't fix" design that fog visibility work exploits
- [[milbrandt-yau-scheme]] — MY2, the scheme used in the fog and ice-fog demonstrations
- [[gem-mach-air-quality]] — another domain where the schemes' multimoment structure enabled applications beyond precipitation forecasting
