# Han et al. (2019): Cloud-Resolving Model Intercomparison of an MC3E Squall Line Case: Part II. Stratiform Precipitation Properties

**Full citation:** Han, B., Fan, J., Varble, A., Morrison, H., Williams, C. R., Chen, B., Dong, X., Giangrande, S. E., Khain, A., Mansell, E., Milbrandt, J. A., Shpund, J., and Thompson, G. (2019): Cloud-resolving model intercomparison of an MC3E squall line case: Part II. Stratiform precipitation properties. *Journal of Geophysical Research: Atmospheres*, **124**. DOI: 10.1029/2018JD029596

**Companion paper:** Fan et al. (2017), https://doi.org/10.1002/2017JD026622 (Part I, convective properties)

---

## 1. Introduction

Mesoscale convective systems (MCSs) produce a large proportion of precipitation in tropical and midlatitude regions. Accurately simulating stratiform precipitation of MCSs has been a long-standing challenge. Underestimation of stratiform precipitation area and rate is common in cloud-resolving models (CRMs). The causes of consistent underestimation of stratiform precipitation are not well understood.

This paper is Part II of a two-part CRM intercomparison study. Part I (Fan et al., 2017) focused on convective properties of the same MC3E squall line event. This paper evaluates simulated stratiform precipitation properties against observations using 8 different cloud microphysics schemes in the WRF model.

---

## 2. Observations

The squall line event occurred on 20 May 2011 during the Midlatitude Continental Convective Clouds Experiment (MC3E) field campaign. The event passed over the ARM Southern Great Plains (SGP) Central Facility in north central Oklahoma.

Observations used:
- 16 Parsivel disdrometers and one 2D video disdrometer (2DVD) for surface rain rate and raindrop size distribution (RSD)
- S-band and UHF vertical profiling radars (VPR) for stratiform rain properties
- Multi-Doppler radar 3-D wind field retrievals
- Citation II aircraft in situ measurements for stratiform ice properties (1335–1515 UTC, temperatures below freezing)
- NEXRAD-retrieved ice water content (IWC) data
- NEXRAD National Mosaic QPE (NMQ Q2), bias-corrected Q2 (Q2_GAUGE), and ABRFC hourly products

---

## 3. Simulations

The Advanced Research WRF (ARW) model version 3.4.1 is used with four nested domains; the innermost domain has 1-km horizontal grid spacing (601 km × 511 km). Eight microphysics schemes:

| Scheme | Approach | Prognostic variables |
|--------|----------|---------------------|
| MORR | Two-moment | Qc,Qr,Qi,Qs,Qh,Nr,Ni,Ns,Nh |
| MY2 | Two-moment | Qc,Qr,Qi,Qs,Qg,Qh,Nr,Ni,Ns,Ng,Nh |
| WSM6 | One-moment | Qc,Qr,Qi,Qs,Qg |
| FSBM | Bin-resolved | Qc,Qr,Qi,Qs,Qh,Nc,Nr,Ni,Ns,Nh |
| NSSL | Two-moment | Qc,Qr,Qi,Qs,Qg,Qh,Nc,Nr,Ni,Ns,Ng,Nh,Vg,Vh |
| P3 | Two-moment | Qc,Qr,Qi_tot,Qi_rim,Bi_rim,Nr,Ni_tot |
| THOM | Hybrid one-/two-moment | Qc,Qr,Qi,Qs,Qg,Nr,Ni |
| FSBM_NEW | Bin-resolved (modified) | Qc,Qr,Qi,Qs,Qh,Nc,Nr,Ni,Ns,Nh |

MY2 references: Milbrandt and Yau (2005a, 2005b), Milbrandt and McTaggart-Cowan (2010), and Milbrandt et al. (2012). P3 references: Morrison and Milbrandt (2015).

Lateral boundary conditions from Domain 3 were provided every 3 hr using a one-way nested approach. Analysis period for observations: 1100–1400 UTC; simulations: 1000–1300 UTC (1-hr lag justified in Part I).

---

## 4. Intercomparison Methodology

### 4.1. Analysis Period and Domain

The stratiform precipitation region was active from 1100–1400 UTC. The analysis region is a parallelogram-shaped domain aligned with the northeast–southwest orientation of the squall line.

### 4.2. Stratiform Identification

A surface rain rate threshold (1–10 mm/hr for hourly scale; 1–15 mm/hr for instantaneous) is used to identify stratiform columns, rather than conventional reflectivity-based convective-stratiform separation methods.

---

## 5. Results

### 5.1. Comparison with Observations

**Stratiform precipitation area and rate:**
- Most schemes underestimate total stratiform precipitation, primarily due to underestimation of stratiform precipitation area
- All schemes underestimate frequency of moderate 2–6 mm/hr rain rates
- MY2 and P3 have the largest mean stratiform precipitation rates, exceeding observations for 6–10 mm/hr rain rate frequencies
- WSM6 and FSBM have low biases in large raindrop concentration at the surface

**Raindrop size distributions:**
- Most schemes capture the observed mean raindrop size at the surface reasonably but fail to reproduce observed frequencies of moderate rain rates
- Low-biased ice number and mass concentrations for 0.2–2 mm diameter particles above the melting level likely cause underestimated moderate rain rates

**Rain water content and vertical structure:**
- Simulations generally underestimate rain water content (RWC) above 1-km altitude for a given rain rate
- Simulations underestimate the descending motion in the stratiform rain region below 3 km, possibly due to differences in the rear inflow jet structure

**Ice water content:**
- Most simulations overestimate IWC above 7 km (where temperatures < −20°C) but underestimate IWC just above the melting level
- This opposite trend (decrease vs. observed increase of IWC approaching melting level) leads to underestimation of stratiform RWC below 3 km
- IWC overestimation at upper levels linked to excessive convective detrainment height shown in Part I
- Simulated ice particle aggregation is weaker than observed: observed number and mass of large particles (>2 mm) increase between 6.7 and 5.8 km, while simulations show only slight changes

### 5.2. Causes for Model Spread

- Stratiform precipitation spread (~factor of 1.5) is primarily driven by variability in ice particle downward mass fluxes above the melting level
- Ice mass flux variability depends on both IWC (related to convective condensate detrainment flux) and ice mass-weighted mean fall speed (related to proportions of ice types)
- MY2 and P3 produce the largest rain mass fluxes; MY2 produces the largest amount of rimed precipitating ice particles (fast-falling), P3 shows good transition from unrimed ice at upper levels to rimed particles at middle levels
- Stratiform precipitation area positively correlates with convective condensate detrainment flux (correlation coefficient = 0.78)
- Stratiform precipitation area is also sensitive to lateral boundary condition update frequency: increasing from every 3 hr to every 1 hr increases stratiform area by ~17–25% for MORR, NSSL, and P3 schemes

---

## 6. Conclusions

1. Most simulations underestimate total stratiform precipitation, mainly due to underestimation of stratiform precipitation area
2. Low-biased moderate stratiform rain rates may result from low-biased ice number and mass concentrations for 0.2–2 mm particles just above the melting level
3. Most simulations overestimate IWC above 7 km but underestimate IWC just above the melting level — opposite to observed trend
4. Simulated stratiform precipitation area increases ~17–25% with more frequent (1-hr vs. 3-hr) boundary condition updates
5. Stratiform precipitation spread across schemes (~factor of 1.5) is primarily a result of variability in convective condensate detrainment flux
6. Accurate simulation of convective regions is critical for better stratiform precipitation simulation
7. Increasing from single-moment (WSM6) to double-moment parameterization helps improve model performance; advantage of bin schemes over two-moment is less clear for this ice-microphysics-dominated case

---

## References (selected)

- Fan, J., et al. (2017): Cloud-resolving model intercomparison of an MC3E squall line case: Part I. *J. Geophys. Res. Atmos.*, **122**, 9351–9378. DOI: 10.1002/2017JD026622
- Milbrandt, J. A., and Yau, M. K. (2005a, 2005b): A multimoment bulk microphysics parameterization. Parts I & II. *J. Atmos. Sci.*, **62**, 3051–3081.
- Milbrandt, J. A., and McTaggart-Cowan, R. (2010): Sedimentation-induced errors in bulk microphysics schemes. *J. Atmos. Sci.*, **67**, 3931–3948.
- Milbrandt, J. A., et al. (2012): Predicting the snow-to-liquid ratio. *Mon. Wea. Rev.*, **140**, 2461–2476.
- Morrison, H., and Milbrandt, J. A. (2015): P3 Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Morrison, H., Milbrandt, J. A., et al. (2015): P3 Part II. *J. Atmos. Sci.*, **72**, 312–339.
