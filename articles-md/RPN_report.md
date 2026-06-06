# Ritchie et al. (2022): Recherche en Prévision Numérique Contributions to Numerical Weather Prediction

**Full citation:** Ritchie, H., Bélair, S., Bernier, N. B., Buehner, M., Charron, M., Fortin, V., Garand, L., Houtekamer, P., Husain, S., Laroche, S., Lemieux, J.-F., Lin, H., McTaggart-Cowan, R., Milbrandt, J., Mitchell, H., Pellerin, P., Pudykiewicz, J., Separovic, L., Smith, G. C., Tanguay, M., and Vaillancourt, P. A., 2022: Recherche en Prévision Numérique Contributions to Numerical Weather Prediction. *Atmosphere-Ocean*, **60**(1), 35–64. DOI: 10.1080/07055900.2022.2038071

---

## Abstract

This is a review article invited by Atmosphere-Ocean to document the contributions of Recherche en Prévision Numérique (RPN) to Numerical Weather Prediction (NWP). It is structured as a historical review and documents RPN's contributions to numerical methods, numerical modelling, data assimilation, and ensemble systems, with a look ahead to potential future systems. Through this review, the evolution of RPN's contributions is highlighted, beginning with early NWP efforts and continuing through to environmental predictions with a broad range of applications. This synthesis is intended to be a helpful reference, consolidating developments and generating broader interest for future work on NWP in Canada.

---

## 1. Introduction

This article reviews the history of NWP development at RPN (Recherche en Prévision Numérique), a group within the Meteorological Research Division of Environment and Climate Change Canada (ECCC) co-located with the Canadian Meteorological Centre (CMC). RPN has been at the forefront of NWP innovations since the establishment of the Dynamic Prediction Research (DPR) unit in 1959 in Montréal. The first operational NWP model in Canada was implemented in July 1963, led by André Robert.

---

## 2. First Operational Forecast Models

### a. Filtered Models

The first successful numerical weather forecast (Charney et al., 1950) used a barotropic model. Canada's first operational NWP model was implemented in July 1963 — a non-divergent barotropic atmospheric model constructed by André Robert, run on a 1709-point octagonal grid with 381 km grid length. The barotropic model was replaced in 1968 by a four-level baroclinic model. A seven-level filtered baroclinic model was implemented in 1975.

### b. Primitive-Equation Models

The development of efficient time integration methods — notably the semi-implicit algorithm proposed by André Robert (Kwizak & Robert, 1971) — enabled the transition to primitive-equation models. By mid-1971, a five-level semi-implicit primitive-equation model was under development. The 1980s saw a golden era of NWP with Robert (1981, 1982) developing semi-Lagrangian and semi-implicit schemes that have since been used worldwide.

---

## 3. Early Data Assimilation and Model Initialization

Successive data assimilation techniques developed at RPN include: Objective Analysis (OI), 3D-Var, and 4D-Var. These techniques provide the initial conditions from which models produce forecasts.

---

## 4. Evolution of the GEM Model

The Global Environmental Multiscale (GEM) model emerged from decades of development at RPN. GEM can be run as a global model or limited-area model and uses non-hydrostatic primitive equations with a terrain-following hybrid vertical grid. Semi-Lagrangian, semi-implicit time differencing enables large time steps and excellent scalability.

Key GEM developments:
- Global spectral models in the 1980s
- Introduction of variable-resolution grids
- Replacement of the global lat–lon structure with a Yin–Yang grid (December 2015)
- Coupling with an ice–ocean model for medium-range forecasts (November 2017)
- Development of ensemble systems
- Current move toward height-based terrain-following coordinates for sub-kilometre applications

---

## 5. Current Deterministic Modelling Systems

### a. Global Deterministic Prediction System (GDPS)

CMC is one of nine World Meteorological Organization Global Producing Centres for deterministic, ensemble, and long-range global forecasts at ~25 km grid spacing.

### b. Regional Deterministic Prediction System (RDPS)

The RDPS horizontal resolution has been successively refined over decades (24 km in 1998, 15 km in 2004, 10 km in 2012) with increasing vertical levels (28 to 84) and upgraded physical parameterizations.

### c. High-Resolution Regional Deterministic Prediction System (HRDPS)

ECCC has been at the forefront of convection-scale NWP. The HRDPS (2.5 km grid spacing) became officially operational in December 2017 (pan-Canadian domain). In September 2018, a major physics upgrade:

1. **Microphysics**: The detailed Milbrandt and Yau (2005) (MY2) scheme, which had been used in the HRDPS for nearly a decade, was replaced with the single ice-category configuration of the Predicted Particle Properties (P3) scheme (Morrison & Milbrandt, 2015). P3 was co-developed by scientists at RPN and NCAR and uses a fundamentally new approach to represent ice-phase hydrometeors. In the HRDPS, P3 improved precipitation skill scores generally and in mountainous regions particularly.

2. **Urban canopy**: The Town Energy Balance (TEB) urban canopy model was implemented, improving near-surface temperature forecasts in urban areas.

---

## 6. Ensemble Systems

The development of ensemble data assimilation and ensemble prediction systems at RPN is reviewed, including the Canadian Global Ensemble Prediction System (GEPS) and the Regional Ensemble Prediction System (REPS). Ensemble methods have extended NWP beyond deterministic forecasting, providing uncertainty quantification and probabilistic guidance.

---

## 7. Future Directions

Future priorities include: improved dynamical cores (height-based terrain-following coordinates for sub-kilometre applications), scalable numerical methods, improved atmospheric physics, expanded earth system modelling (atmosphere–ice–ocean–land coupling), and environmental prediction applications beyond weather (air quality, marine, ice prediction).

---

## 8. Summary

RPN's contributions to NWP span six decades, from André Robert's early barotropic model through the GEM model and current operational systems. Key scientific milestones include the development of semi-Lagrangian semi-implicit time integration, successive generations of global and regional NWP models, advanced data assimilation systems, and ensemble prediction. The development of cloud microphysics parameterizations — including the MY2 scheme and the P3 scheme — are highlighted as part of the physics development history.

---

## References

[Selected key references]

- Milbrandt, J. A. and Yau, M. K., 2005: A multi-moment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.
- Milbrandt, J. A., Bélair, S., Faucher, M., Vallée, M., Carrera, M. A., and Glazer, A., 2016: The Pan-Canadian High Resolution (2.5-km) Deterministic Prediction System. *Weather Forecast.*, **31**, 1791–1816.
- Morrison, H. and Milbrandt, J. A., 2015: Parameterization of ice microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Robert, A., 1981, 1982: Development of efficient time integration methods for the primitive equations (semi-Lagrangian and semi-implicit schemes).
- Côté, J., Gravel, S., Méthot, A., Patoine, A., Roch, M., and Staniforth, A., 1998: The operational CMC–MRD global environmental multiscale (GEM) model. Part I. *Mon. Weather Rev.*, **126**, 1373–1395.
