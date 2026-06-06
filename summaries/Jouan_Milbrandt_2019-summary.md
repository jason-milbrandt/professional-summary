# Summary: Jouan and Milbrandt (2019)

**Full citation:** Jouan, C., and J. A. Milbrandt, 2019: The importance of the ice-phase microphysics parameterization for simulating the effects of changes to CCN concentrations in deep convection. *J. Atmos. Sci.*, **76**, 1727–1752, https://doi.org/10.1175/JAS-D-18-0168.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2019
**Authors:** Caroline Jouan, Jason A. Milbrandt
**DOI:** 10.1175/JAS-D-18-0168.1

---

## Overview

This paper examines how the details of ice-phase microphysics parameterization influence the simulated response of a deep convective system (a squall line observed during MC3E) to changes in cloud condensation nuclei (CCN) concentrations. Using the two-moment Milbrandt–Yau (MY2) scheme in the GEM model at 1-km grid spacing, the study demonstrates that the simulated storm's sensitivity to CCN is not merely through direct warm-phase effects (autoconversion, droplet size) but also through indirect effects on graupel growth rates. The proper two-moment treatment of graupel and a realistic representation of its density are shown to be necessary for correctly capturing CCN-driven changes in storm structure.

## Context and Motivation

Conflicting results in previous modeling studies of aerosol–cloud–precipitation interactions in mesoscale convective systems (MCSs) had been attributed in part to differences in microphysics parameterization. While the direct impact of CCN on cloud droplet sizes and warm-rain processes is well understood, the indirect effects on ice-phase processes — particularly graupel — were less clear. This study was motivated by the observation (Milbrandt and Morrison 2013) that CCN ultimately affects rime density and hence graupel simulations, and by the practical need to understand sensitivity in the MY2 scheme used operationally in ECCC's HRDPS.

## Key Scientific Contributions

- Demonstrated that simulated squall-line structure is sensitive to CCN concentration not only through direct warm-phase effects but also through changes in ice-phase growth rates (particularly graupel riming)
- Quantified the relative importance of microphysical processes via budget analysis: condensation (~78–86% of WVL), graupel deposition (~17% in CLN), and snow deposition (~8% in POL) are dominant pathways
- Showed that the bulk collection efficiency $E_{cg}$ between graupel and cloud droplets (parameterized as a function of the dimensionless Stokes parameter) is a key mediator of CCN effects on graupel growth
- Demonstrated that using prognostic graupel density (Milbrandt and Morrison 2013) produces quantitatively different, more physically realistic responses to CCN loading
- Demonstrated that reducing graupel from two-moment to one-moment eliminates most of the CCN sensitivity in the ice-phase distribution, because the size-sorting effect (where $q_g$ sediments faster than $N_{Tg}$) is absent
- Results support the case for abandoning predefined ice-phase categories in favor of particle property-based approaches (i.e., P3; Morrison and Milbrandt 2015)

## Methods Summary

- **Model:** GEM (Global Environmental Multiscale) model with nested domains at 2.5 km (D1) and 1 km (D2)
- **Microphysics:** MY2 (Milbrandt and Yau 2005a,b; Milbrandt and Morrison 2013) — two-moment, six-category bulk scheme
- **Case study:** 20 May 2011 squall line from MC3E, simulated for 18 h
- **CCN treatment:** Prescribed activated CCN concentrations of $N_\mathrm{act}$ = 100 cm$^{-3}$ (CLN) or 4000 cm$^{-3}$ (POL)
- **Sensitivity experiments:** 9 simulations varying autoconversion, collection efficiency, prognostic graupel density, and number of graupel moments (Table 2)
- **Microphysical budget:** Following Colle and Zeng (2004); process rates normalized by WVL and time-averaged over the mature squall-line phase (0600–1200 UTC)

## Key Results

- Domain-averaged precipitation varied by only a factor of 1.19 between CLN and POL — no significant aerosol effect on total precipitation, consistent with prior studies
- In POL vs. CLN: $q_c$, $q_i$, $q_s$ increase; $q_g$ decreases significantly; $q_h$ slightly increases; graupel shifts downward in the vertical profile
- Autoconversion is completely suppressed in POL (CN$_{cr}$ = 0%), driven by smaller droplet sizes reducing the standard deviation of the droplet diameter below the 15-µm threshold in MY2
- The collection efficiency $E_{cg}$ is strongly reduced in POL due to smaller mean droplet diameter $D_{mc}$, reducing graupel riming rate by ~20% despite more available $q_c$
- With prognostic $\rho_g$ (CLN_3A/POL_3A): CCN changes produce roughly half the magnitude of ice-phase response compared to fixed $\rho_g$, because higher rime density leads to more efficient graupel fallout, limiting ice accumulation aloft
- With one-moment graupel (CLN_3B/POL_3B): CCN sensitivity of the ice-phase distribution is largely eliminated

## Limitations and Caveats

- Constant, horizontally/vertically uniform $N_\mathrm{act}$ prescribed — does not capture the real spatial heterogeneity of CCN
- Single autoconversion parameterization (Berry and Reinhardt 1974); other formulations might alter quantitative results
- MY2 has known weaknesses in graupel–rain collection (use of analytic SCE solution problematic for similar fall speeds)
- Single case study; a single microphysics scheme
- The piggyback method (Grabowski 2014, 2015) was not used, so dynamical and microphysical feedbacks cannot be fully separated

## Relation to Author's Research Program

This paper sits at the intersection of two major threads in Milbrandt's research: (1) the ongoing development and evaluation of the MY2 scheme (Milbrandt and Yau 2005a,b; 2006; Milbrandt and Morrison 2013), and (2) the scientific motivation for the P3 scheme (Morrison and Milbrandt 2015; Morrison et al. 2015b; Milbrandt and Morrison 2016). The finding that predefined ice-phase category thresholds and moment-treatment choices materially affect the response to CCN loading directly supports the argument that a particle property-based approach (P3) — which avoids these arbitrary category boundaries — is scientifically preferable. The study also documents a real-world application of the MY2 scheme in the HRDPS context, linking scheme-development work to operational NWP practice at ECCC.

## Impact and Citations

**Citation count:** ~11 (Semantic Scholar, retrieved 2026-06-06)

A specialized study on aerosol–cloud–precipitation interactions with a focus on microphysics parameterization sensitivity. The citation count of 11 is modest, reflecting the paper's somewhat niche focus at the intersection of aerosol effects and bulk microphysics scheme design. The paper's primary significance lies in providing scientific support for the transition from category-based microphysics to property-based approaches (P3), a direction that has since gained traction in the modeling community ⚠ verify. The work also has operational relevance as context for the HRDPS system described in Milbrandt et al. (2016).
