# Coupled Air-Quality/Weather Modeling — GEM-MACH (Tier 3)

**Summary:** Four papers where Milbrandt provided the MY2 (and later P3) cloud-microphysics component of ECCC's online coupled air-quality model GEM-MACH, enabling the aerosol indirect effect — aerosol loading modifying cloud droplet number and hence cloud radiative and precipitation-scavenging behavior — in an operational chemistry-weather system.

**Sources:** [[Gong_etal_2015-summary]], [[Makar_etal_2015a-summary]], [[Makar_etal_2015b-summary]], [[Makar_etal_2021-summary]]

**Last updated:** 2026-08-05

---

## Why a two-moment scheme was required

The aerosol indirect effect — the pathway by which aerosols act as cloud condensation nuclei and modify cloud droplet number concentration ($N_d$), and through it cloud optical properties, precipitation, and scavenging — can only be represented by a microphysics scheme that predicts $N_d$ as a prognostic variable. GEM-MACH's operational single-moment schemes could not do this. [[milbrandt-yau-scheme]] (MY2), predicting both mass and number for six hydrometeor categories, was the natural fit, and its adoption in GEM-MACH is a clean example of the scheme being used well outside its original NWP microphysics design brief.

## The demonstration and evaluation (Gong et al. 2015; Makar et al. 2015a,b)

**Gong et al. (2015)** implemented a two-way aerosol–cloud feedback in GEM-MACH by coupling on-line, size-resolved aerosol information to MY2 via the Abdul-Razzak–Ghan activation scheme. Evaluated against ICARTT 2004 aircraft observations of a stratocumulus deck downwind of Chicago, the feedback dramatically improved predicted cloud droplet number (from <10 cm⁻³ in the no-feedback base case to ~150–200 cm⁻³, matching observations), with downstream effects on surface ozone and PM2.5 sulphate through cloud-radiative and aqueous-chemistry pathways.

**Makar et al. (2015a, 2015b)** used the same MY2-in-GEM-MACH configuration as the Canadian contribution to AQMEII-2, a major international intercomparison of aerosol–weather feedback effects across ~6 modeling platforms and two continents. Part 1 (meteorological effects) found the direct aerosol effect produces consistent cooling and precipitation reduction across models, while the indirect effect — the one MY2's two-moment structure enables — is larger but far more model-dependent, the most uncertain feedback mechanism identified. Part 2 (chemical effects) found feedback-induced ozone forecasts improved but PM2.5 forecasts degraded, pointing to gaps in cloud-scavenging parameterization rather than in the cloud microphysics itself.

## Forest-fire aerosol feedbacks (Makar et al. 2021)

A 2.5-km resolution study of forest-fire aerosol–weather feedbacks over western North America during the 2019 fire season, using [[p3-scheme]] (rather than MY2) as the double-moment scheme representing the aerosol indirect effect — evidence that P3's property-prediction structure serves the same coupling role its predecessor did. The paper introduced the first online forest-fire plume-rise scheme embedded in an NWP-coupled system, letting fire-modified meteorology feed back into plume injection height in real time. Feedback-inclusive forecasts improved 35 of 48 air-quality metrics and most meteorological metrics at 90% confidence, with a documented mechanism: smoke increases near-surface stability, retains more aerosol aloft as CCN, increases droplet number, and cools the sub-cloud layer. Milbrandt's role was providing updates to the indirect-effect implementation and advice on realizing it within P3.

## Position in the arc

This cluster shows both [[milbrandt-yau-scheme]] and [[p3-scheme]] operating as general-purpose two-moment infrastructure — not just precipitation-forecasting tools but the enabling component for any application requiring a physically grounded link between aerosol loading and cloud microphysics. It sits alongside [[fog-visibility]] as evidence of the schemes' portability beyond their original convective/orographic design context.

## Related pages

- [[milbrandt-yau-scheme]] — MY2, the scheme enabling the aerosol indirect effect in the 2015 papers
- [[p3-scheme]] — P3, used for the same purpose in the 2021 forest-fire study
- [[fog-visibility]] — another domain where the schemes' multimoment structure enabled applications beyond precipitation forecasting
