# Makar et al. (2015a): Feedbacks Between Air Pollution and Weather, Part 1: Effects on Weather

**Full citation:** Makar, P.A., Gong, W., Milbrandt, J., Hogrefe, C., Zhang, Y., Curci, G., Žabkar, R., Im, U., Balzarini, A., Baró, R., Bianconi, R., Cheung, P., Forkel, R., Gravel, S., Hirtl, M., Honzak, L., Hou, A., Jiménez-Guerrero, P., Langer, M., Moran, M.D., Pabla, B., Pérez, J.L., Pirovano, G., San José, R., Tuccella, P., Werhahn, J., Zhang, J., and Galmarini, S. (2015): Feedbacks between air pollution and weather, Part 1: Effects on weather. *Atmospheric Environment*, **115**, 442–469. DOI: 10.1016/j.atmosenv.2014.12.003

**Journal:** Atmospheric Environment
**Year:** 2015 (received June 2014, accepted December 2014)
**Authors:** P.A. Makar, W. Gong, J. Milbrandt (3rd of 28 authors)
**DOI:** 10.1016/j.atmosenv.2014.12.003
**Part of:** AQMEII-2 (Air Quality Model Evaluation International Initiative, Phase 2) special issue. Companion paper: Makar et al. (2015b) — Part 2: Effects on chemistry.

---

## Abstract

The meteorological predictions of fully coupled air-quality models running in "feedback" versus "no-feedback" simulations were compared against each other and observations as part of Phase 2 of the Air Quality Model Evaluation International Initiative. In the "no-feedback" mode, the aerosol direct and indirect effects were disabled. In the "feedback" mode, model-generated aerosols modified radiative transfer and/or cloud formation parameterizations. Annual simulations with and without feedbacks were conducted for domains over North America (2006 and 2010) and Europe (2010).

The incorporation of feedbacks resulted in systematic changes to forecast predictions of meteorological variables, with the largest impacts in summer and near large pollution sources. Models incorporating only the aerosol direct effect predicted feedback-induced reductions in temperature, downward shortwave radiation, precipitation, and PBL height. Models incorporating both direct and indirect effects showed larger and more variable feedback responses, suggesting the implementation details of the indirect effect have a large impact on results. Model-to-model differences exceeded the within-model performance changes associated with feedbacks. However, feedback implementation improved forecasts of surface temperature and precipitation.

---

## 1. Introduction and Context

AQMEII-2 is the second phase of a large international intercomparison of air-quality forecast models. Phase 1 compared mainly offline models (meteorology provided a priori by weather models). Phase 2 focuses on fully coupled "online" models in which chemistry can feed back to alter the model's meteorology through:

1. **Aerosol direct effect**: aerosols modify radiative transfer
2. **Aerosol indirect effect**: aerosols act as cloud condensation nuclei (CCN), modifying cloud microphysics and hence radiation and precipitation

The physical mechanism distinguishing the two modes of coupling is whether the model-generated aerosols are allowed to influence the meteorological component. In "no-feedback" mode, aerosol properties revert to climatologies. The cross-model comparison allows isolation of feedback effects and identification of where parameterization improvements are most needed.

---

## 2. Models and Methodology

Multiple international modeling groups contributed simulations; the key models are summarized in a comprehensive table. The Canadian contribution used **GEM-MACH** (Moran et al. 2010), Environment Canada's online air-quality forecast model. For cloud microphysics, GEM-MACH used the **Milbrandt–Yau (MY2) scheme** (Milbrandt and Yau 2005a,b):

- **No-feedback CCN activation:** Cohard et al. (1998)
- **Feedback CCN activation:** Abdul-Razzak and Ghan (2002)

GEM-MACH was run at 15-km resolution, driven by CMC regional operational analyses. Aerosol representation: sectional, 12 bins. Simulated years: 2006 and 2010 (NA domain); 2010 (EU domain).

Other models included WRF-CHEM and WRF-CMAQ systems from US and European groups, using various convective, PBL, and microphysics parameterizations.

Simulation domains:
- North America: annual runs for 2006 and 2010
- Europe: annual runs for 2010

Observation comparisons used networks of surface meteorological and air-quality stations across NA and EU.

---

## 3. Key Results

### Summary table of feedback impacts

Broadly summarized across models:

| Model type | Temperature | Shortwave radiation | Precipitation | PBL height |
|------------|------------|---------------------|---------------|------------|
| Direct effect only | Decreases | Decreases (down), increases (up) | Decreases | Decreases |
| Direct + indirect | Variable (model-dependent) | Variable | Variable | Variable |

### Key findings:

- **Direct effect feedbacks** produced consistent systematic responses across all models and domains: reductions in surface temperature, downward shortwave radiation, precipitation, and PBL height
- **Indirect effect feedbacks** varied significantly across models, suggesting the implementation details of the aerosol-CCN-cloud interaction is a critical uncertainty
- Direct and indirect effects were often in **competition**: changes associated with feedbacks often changed sign between models with direct-effect-only vs. both effects
- Feedback responses were **largest in summer** and **near large pollution sources** (where aerosol loading is highest)
- Model-to-model differences in performance were **larger than the within-model performance change** associated with feedbacks — the model framework matters more than whether feedbacks are included
- **Feedback implementation improved forecasts** of 2-m surface temperature and precipitation when comparing feedback vs. no-feedback simulations of the same model

---

## 4. Conclusions

- Fully coupled feedback models produce systematic changes to meteorological forecasts, particularly in summer and near pollution sources
- The aerosol indirect effect is likely the dominant feedback process but remains the greatest source of model uncertainty
- Improving the implementation of the aerosol indirect effect (CCN activation and cloud microphysics coupling) is the highest-priority target for future development
- Meteorological forecasts may be improved through fully coupled feedback models or through spatially/temporally/speciation-resolved aerosol climatologies
- Part 2 (companion paper) examines feedback effects on predicted chemistry

---

## References (key)

- Milbrandt, J.A. and Yau, M.K. (2005a,b): A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, 62.
- Moran, M.D. et al. (2010): GEM-MACH model description
- Abdul-Razzak, H. and Ghan, S. (2002): CCN activation parameterization
- Cohard, J.-M. et al. (1998): CCN activation from spectra

[All figures: spatial maps of feedback impacts, time series of verification statistics — images not reproducible in markdown]
