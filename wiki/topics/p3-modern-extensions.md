# Modern P3 Extensions: Moments, Phase, and Hail (2019–2025)

**Summary:** Six papers (2019–2025) systematically add back capabilities the original P3 framework lacked — triple-moment ice for physical size-sorting control, predicted liquid fraction for mixed-phase particles, secondary ice production for freezing-rain correction, and the combined effects on hail — without reintroducing the fixed-category assumptions P3 was built to escape.

**Sources:** [[Milbrandt_etal_2021-summary]], [[Cholette_etal_2019-summary]], [[Cholette_etal_2023-summary]], [[Cholette_etal_2024-summary]], [[Cholette_etal_2025-summary]], [[Milbrandt_etal_2025-summary]]

**Last updated:** 2026-08-05

---

## Triple-moment ice (Milbrandt et al. 2021)

The original two-moment [[p3-scheme]] prescribed the shape parameter μ via a diagnostic relation tied to the slope parameter, preventing μ from evolving independently and requiring an artificial 2-mm size limiter to prevent runaway size sorting — the direct P3 analog of the fixed-α problem [[spectral-shape-parameter]] identified for the original MY scheme two decades earlier. Adding a fifth prognostic variable per ice category ($Z_{i,tot}$, the sixth PSD moment) lets μ vary freely, physically narrowing the distribution as mean size grows and controlling size sorting without the artificial limiter. In idealized CM1 supercell simulations this produced larger, more realistic mean and maximum hail sizes and reflectivity — directly answering the hail-signature weakness in P3 that [[scheme-intercomparisons]] (Johnson et al. 2019) had flagged. The paper also established that advecting a normalized quantity ($Z_{advect} = Z_{i,tot}/Q_{i,tot}$, per Morrison et al. 2016) rather than $Z_{i,tot}$ directly preserves the PSD parameters during transport.

## Predicted liquid fraction: the Cholette series (2019–2025)

A four-paper thread led by Mélissa Cholette (PhD student co-supervised by Milbrandt) progressively developed, validated, and operationalized a bulk liquid-fraction variable in P3:

- **2019** established the theoretical foundation: adding $q_{i,liq}$ as a prognostic variable lets P3 represent mixed-phase particles explicitly, enabling wet snow and ice pellets — precipitation types no standard bulk scheme (including original P3) can produce, since melted ice mass is normally transferred to rain instantaneously.
- **2023** combined liquid fraction with triple-moment ice for the first time and tested the merged scheme on a real squall line in GEM — producing stronger cold pools, faster propagation, reduced surface ice, and an explicit, realistic radar bright band. This combined `3MOM_LF` configuration is the operational P3 in HRDPS.
- **2024** used the liquid-fraction framework's implied physics to fix a *different* bias: secondary ice production via Hallett–Mossop rime splintering, enabled by having two ice categories (see [[sip-hiwc-mixed-phase]]), cut excessive HRDPS freezing-rain accumulation by up to 98% and matched or beat the long-standing empirical Bourgouin diagnostic over 40 winter hindcasts — see [[precipitation-type-prediction]] for the freezing-rain thread this closes.
- **2025** provided the first 3D NWP evaluation of P3's liquid-fraction capability for wet snow, against ICE-POP 2018 (South Korea) observations, showing liquid fraction produces wet snow where the standard scheme produces rain and captures the observed coast-to-mountain density gradient.

## Combined hail capabilities (Milbrandt et al. 2025)

The capstone paper isolates the separate effects of predicted liquid fraction and multiple ice categories on hail in idealized CM1 supercells. Liquid fraction *reduces* surface hail size (by preserving total ice number during melt/shed, following the closure-assumption analysis in the paper); multiple categories *increase* hail size (by avoiding "property dilution" — see [[p3-scheme]] Part III). The two effects partially offset. The recommended `LF-2CAT` configuration (triple-moment ice + liquid fraction + two categories) is argued to realistically represent the full hail lifecycle — initiation, growth, and decay — closing the hail weakness first identified by Johnson et al. (2019) in [[scheme-intercomparisons]].

## Position in the arc

This cluster is where P3's original limitations, exposed by early community evaluation (see [[scheme-intercomparisons]]) and by the operational freezing-rain bias (see [[precipitation-type-prediction]]), get systematically resolved — each extension adding a physical degree of freedom rather than a fixed assumption, the same design philosophy traced back to [[spectral-shape-parameter]].

## Related pages

- [[p3-scheme]] — the base scheme these papers extend
- [[spectral-shape-parameter]] — the original "predict, don't fix" insight this generalizes
- [[scheme-intercomparisons]] — Johnson et al. (2019), source of the hail-weakness diagnosis
- [[sip-hiwc-mixed-phase]] — the SIP observational and mechanistic context
- [[precipitation-type-prediction]] — the freezing-rain bias this work closes
