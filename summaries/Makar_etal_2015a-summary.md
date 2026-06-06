# Summary: Makar et al. (2015a)

**Full citation:** Makar, P.A., Gong, W., Milbrandt, J., Hogrefe, C., Zhang, Y., Curci, G., Žabkar, R., Im, U., Balzarini, A., Baró, R., Bianconi, R., Cheung, P., Forkel, R., Gravel, S., Hirtl, M., Honzak, L., Hou, A., Jiménez-Guerrero, P., Langer, M., Moran, M.D., Pabla, B., Pérez, J.L., Pirovano, G., San José, R., Tuccella, P., Werhahn, J., Zhang, J., and Galmarini, S. (2015): Feedbacks between air pollution and weather, Part 1: Effects on weather. *Atmospheric Environment*, **115**, 442–469. DOI: 10.1016/j.atmosenv.2014.12.003
**Journal:** Atmospheric Environment
**Year:** 2015
**Authors:** P.A. Makar, W. Gong, J. Milbrandt (3rd), et al. (28 total)
**DOI:** 10.1016/j.atmosenv.2014.12.003
**Author's role:** Tier 3 — Contributed the GEM-MACH model's cloud microphysics component (MY2 scheme); co-responsible for the Canadian (NA) GEM-MACH simulations in the AQMEII-2 intercomparison

---

## Overview

This paper is Part 1 of a two-part study examining how aerosol–weather feedbacks in fully coupled air-quality/weather models affect forecast accuracy — Part 1 focuses on meteorological impacts, Part 2 on chemistry. Conducted under AQMEII-2, a major international model intercomparison, the study compared "feedback" and "no-feedback" model configurations from multiple groups across North American (2006, 2010) and European (2010) domains. Key finding: aerosol–weather feedbacks produce systematic but model-dependent changes to meteorological forecasts, with the aerosol indirect effect being the dominant but most uncertain feedback mechanism.

## Context and Motivation

Most operational NWP models treat aerosol properties as fixed climatologies, ignoring the two-way interaction between air pollution and weather. Fully coupled models allow aerosols to modify radiative transfer (direct effect) and cloud formation via CCN activation (indirect effect). AQMEII-2 was designed to systematically quantify these feedbacks across multiple state-of-the-art modeling platforms — the first such intercomparison of this type — providing benchmark data for the next generation of coupled weather/chemistry models.

## Key Scientific Contributions

- Quantified the systematic meteorological response to aerosol–weather feedbacks across ~6 international modeling platforms and two continental domains, establishing that feedback effects are real, consistent in sign for the direct effect, but highly model-dependent for the indirect effect
- Showed that models implementing only the direct effect produce consistent reductions in temperature, downward shortwave radiation, precipitation, and PBL height
- Demonstrated that models incorporating both direct and indirect effects show larger but more variable feedback responses than direct-effect-only models, implying the indirect effect (CCN-cloud coupling) is the dominant but most uncertain process
- Documented that feedback implementation improves forecasts of 2-m temperature and precipitation vs. no-feedback within the same model, supporting the case for operational coupled weather/chemistry systems

## Methods Summary

GEM-MACH (Environment Canada's coupled model) contributed the Canadian NA simulations using MY2 cloud microphysics. The intercomparison used annual simulations for NA (2006, 2010) and EU (2010). Each group ran paired "feedback" and "no-feedback" versions of their model with harmonized emissions and boundary conditions. Comparisons were made against surface meteorological networks. GEM-MACH used sectional aerosol representation (12 size bins) and the Abdul-Razzak and Ghan (2002) CCN activation scheme in feedback mode.

## Key Results

- Direct effect feedbacks produced consistent decreases in surface temperature, downward shortwave radiation, precipitation, and PBL height across all models
- Indirect effect feedbacks produced larger but inconsistent responses — sign of changes sometimes differed between models
- Feedback-induced changes in summer were much larger than in other seasons, and much larger near large pollution sources
- Model-to-model performance differences were larger than within-model feedback performance changes — the choice of modeling platform matters more than whether feedbacks are included
- Including feedbacks improved forecasts of surface temperature and precipitation vs. the no-feedback configuration

## Limitations and Caveats

- GEM-MACH ran at relatively coarse 15-km resolution, which may not resolve local aerosol concentration maxima
- Not all modeling groups were able to contribute both feedback and no-feedback simulations, limiting the comparison for some models and domains
- The aerosol indirect effect implementation varied widely across models, making the inter-model comparison of indirect effects difficult to interpret mechanistically
- Process-level attribution of feedback differences was not performed; only integrated model outputs were compared

## Relation to Author's Research Program

Milbrandt's contribution was providing GEM-MACH with the MY2 microphysics scheme, which handled the cloud-microphysical coupling needed for the aerosol indirect effect (via CCN activation modifying droplet number concentration and hence cloud radiative properties). This paper demonstrates MY2 being used in a scientific context outside of pure microphysics scheme evaluation — embedded within a fully coupled air-quality/weather model for a global intercomparison study. The cloud microphysics component was essential because the indirect effect requires a two-moment scheme (which MY2 provides) to realistically relate aerosol loading to cloud droplet number concentration. This paper is part of the same AQMEII-2 effort as Makar et al. (2015b).

## Impact and Citations

**Citation count:** ~137 (Semantic Scholar, retrieved 2026-06-06)

This is a highly cited paper in the air-quality/NWP coupling literature, reflecting the significance of the AQMEII-2 intercomparison as a community benchmark. It is among the most-cited papers in this batch, consistent with the broader scope of the study (28 authors, multiple international modeling systems, two continental domains). The framework established by AQMEII-2 has been used as a reference point for subsequent coupled atmosphere-chemistry model development and operational implementation.
