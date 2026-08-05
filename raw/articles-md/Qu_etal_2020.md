# Qu et al. (2020): Simulation of Convective Moistening of the Extratropical Lower Stratosphere

**Full citation:** Qu, Z., Huang, Y., Vaillancourt, P. A., Cole, J. N. S., Milbrandt, J. A., Yau, M. K., Walker, K., and de Grandpré, J., 2020: Simulation of convective moistening of the extratropical lower stratosphere using a numerical weather prediction model. *Atmos. Chem. Phys.*, **20**, 2143–2159. DOI: 10.5194/acp-20-2143-2020

---

## Abstract

Stratospheric water vapour (SWV) is a climatically important atmospheric constituent due to its impacts on the radiation budget and atmospheric chemical composition. Despite the important role of SWV in the climate system, the processes controlling the distribution and variation in water vapour in the upper troposphere and lower stratosphere (UTLS) are not well understood. In order to better understand the mechanism of transport of water vapour through the tropopause, this study uses the high-resolution Global Environmental Multiscale (GEM) model of Environment and Climate Change Canada to simulate a lower stratosphere moistening event over North America. Satellite remote sensing and aircraft in situ observations are used to evaluate the quality of model simulation. The main focus of this study is to evaluate the processes that influence the lower stratosphere water vapour budget, particularly the direct water vapour transport and the moistening due to the ice sublimation.

In the high-resolution simulations with horizontal grid spacing of less than 2.5 km, it is found that the main contribution to lower stratospheric moistening is the upward transport caused by the breaking of gravity waves. In contrast, for the lower-resolution simulation with horizontal grid spacing of 10 km, the lower stratospheric moistening is dominated by the sublimation of ice. In comparison with the aircraft in situ observations, the high-resolution simulations predict the water vapour content in the UTLS well, while the lower-resolution simulation overestimates the water vapour content. This overestimation is associated with the overly abundant ice in the UTLS along with a sublimation rate that is too high in the lower stratosphere. The results of this study affirm the strong influence of overshooting convection on the lower stratospheric water vapour and highlight the importance of both dynamics and microphysics in simulating the water vapour distribution in the UTLS region.

---

## 1. Introduction

Stratospheric water vapour (SWV) strongly influences the Earth radiation budget and stratospheric chemistry. Global climate models (GCMs) generally project an increase in SWV during global warming. The processes controlling the distribution and variation in water vapour in the UTLS are not well understood. Large discrepancies are found between satellite observations and GCMs. One motivation of this study is to investigate the possible causes of such overestimation of water vapour in the UTLS in GCMs and NWP models.

Mechanisms controlling transport of water vapour into the stratosphere differ for tropical and mid-latitude regions. In the extratropical region, vertical transport by mid-latitude convection, although demonstrated to be impactful, remains poorly understood. Previous studies found that transport of water vapour into the stratosphere occurs through gravity wave breaking near overshooting tops.

---

## 2. Method

### 2.1 NWP Model Simulation

The NWP model used in this study is the GEM model of ECCC. For the three high-resolution simulations with 2.5, 1 and 0.25 km horizontal grid spacing, the double-moment version of the bulk cloud microphysics scheme of Milbrandt and Yau (2005a, b; MY2) is used. This scheme predicts mass and number mixing ratio for each of six hydrometeors including non-precipitating liquid droplets, ice crystals, rain, snow, graupel and hail.

Four self-nested domains are used with horizontal grid spacing of 10, 2.5, 1 and 0.25 km, respectively. All simulations use 77 vertical levels, with vertical grid spacing ~250 m in the UTLS region. For the 10 km simulation, the Kain–Fritsch deep convection scheme (KFC) is used; the liquid and solid cloud water content from the KFC scheme are later passed to the MY2 scheme.

### 2.2 In Situ Observation

Water vapour measurements from the NASA SEAC4RS field campaign are used. An ER-2 aircraft provided in situ high-altitude observations in the UTLS region. The ER-2 flight on 27 August 2013 performed four descending–ascending movements between ~20 and ~13 km height crossing the tropopause.

### 2.3 Back-trajectory Simulation

Back trajectories are simulated using the LAGRANTO trajectory model (Sprenger and Wernli, 2015) and GEM-generated wind fields.

---

## 3. Model Results and Analysis

### 3.1 Convective System

GEM successfully predicts a strong convective system near the Great Lakes. The target convective event began at around 18:00 UTC, 25 August. Higher-resolution simulations generate anvil clouds of very similar forms to the observation. The 10 km simulation generates clouds that extend in the northeast–southwest direction and covers a noticeably larger area than what is observed.

### 3.2 Overshooting Tops and Gravity Wave Breaking

In 1 and 0.25 km simulations, similar structures of jumping cirrus are generated. Two overshooting tops are identified. The overshooting tops carry air mass of different horizontal velocity into the lower stratosphere and act to block the pre-existing horizontal flow there, creating a situation similar to air flow passing a mountain range and inducing gravity waves. In our simulations, the jumping cirrus can extend to 2 to 3 km above the tropopause (~14.5 km). High water vapour concentrations up to 20 ppmv are found around the jumping cirrus.

The occurrence of gravity wave breaking depends on the intensity of the overshooting strength. The magnitude of the horizontal speed perturbation is linked to the vertical wind speed perturbation, which in this case is related to the overshooting strength. Gravity wave breaking and jumping cirrus are frequently observed in the 0.25 and 1 km simulations, and are visible in the 2.5 km simulation, but are not found in the 10 km simulation because the grid size cannot resolve the process.

### 3.3 Humidity and Ice Field

All simulations show irregular moisture profiles near 16 km, where the vertical trend of the humidity profiles bends and produces "bumps" above the tropopause. The low-resolution (10 km) simulation predicts the highest water vapour content in a large part of the UTLS. Comparison with MLS satellite data and ER-2 aircraft in situ observations shows that the 2.5 km model predicts the aircraft measurements well while the 10 km simulation generally overestimates the water vapour contents in the UTLS region.

### 3.4 Budget Analysis

Reynolds decomposition is applied to diagnose the direct vertical transport of water vapour. For the 1 km simulation, the eddy term (from wave breaking) represents 59% of total vertical transport, while the mean updraft term represents 39%. In total, the direct vertical transport of water vapour contributes to 40% of the total transport at the tropopause level for the 2.5 km simulation and makes up 89% for the 1.0 km simulation.

Large discrepancies in the contribution of ice sublimation exist between high-resolution and 10 km simulations. Ice sublimation is the primary source of moistening of the UTLS in the 10 km simulation. For the 1 and 2.5 km simulations, only 2% and 6% of transported ice is sublimated. In contrast, in the 10 km simulation, 21% (or 75% when evaluated at the higher tropopause of the 10 km simulation) of ice is sublimated.

The high ice sublimation efficiency in the 10 km simulation results from different distribution of ice water contents: in the high-resolution cases, the majority of ice is "trapped" in cold overshooting tops with high relative humidity, limiting contact with surrounding drier stratospheric air. In the 10 km simulation, ice is distributed over larger areas with warmer temperatures, leading to significantly larger contact areas with dry air and higher sublimation.

---

## 4. Conclusions

- High-resolution simulations (dx ≤ 1 km) can properly resolve key dynamical features of overshooting convection: overshooting tops, gravity wave breaking, and jumping cirrus
- Overshooting convection may significantly elevate water contents (both vapour and ice) up to 1–2 km above the tropopause
- Coarse-resolution simulations (dx ≥ 10 km) cannot resolve these features, resulting in a moister UTLS due to parameterization artifacts
- The gravity wave breaking eddy transport accounts for 59% of the direct vertical transport of water vapour in 1 km simulations
- The higher sublimation rate in 10 km simulation is due to: (1) more abundant ice from the KFC convective scheme, and (2) poor spatial distribution of ice that increases contact area with dry stratospheric air

**Author contributions:** YH, PAV, JNSC, MKY and KW conceptualized the research goals and aims. ZQ and YH designed the experiments and ZQ carried them out. ZQ developed the model code, performed the simulations and prepared the manuscript with contributions from all co-authors.

---

## References

[Selected key references]

- Milbrandt, J. A. and Yau, M. K., 2005a: A multi-moment bulk microphysics parameterization. Part I. *J. Atmos. Sci.*, **62**, 3051–3064.
- Milbrandt, J. A. and Yau, M. K., 2005b: A multi-moment bulk microphysics parameterization. Part II. *J. Atmos. Sci.*, **62**, 3065–3081.
- Milbrandt, J. A., Bélair, S., Faucher, M., Vallée, M., Carrera, M. L., and Glazer, A., 2016: The pan-Canadian high resolution (2.5 km) deterministic predictions system. *Weather Forecast.*, **31**, 1791–1816.
- Sprenger, M. and Wernli, H., 2015: The LAGRANTO Lagrangian analysis tool – version 2.0. *Geosci. Model Dev.*, **8**, 2569–2586.
