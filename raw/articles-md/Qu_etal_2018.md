# Evaluation of a High-Resolution NWP Model's Simulated Clouds Using Observations from CloudSat, GOES-13 and In Situ Aircraft

**Full citation:** Qu, Z., H. W. Barker, A. V. Korolev, J. A. Milbrandt, I. Heckman, S. Bélair, S. Leroyer, P. A. Vaillancourt, M. Wolde, A. Schwarzenböck, D. Leroy, J. W. Strapp, J. N. S. Cole, L. Nguyen, and A. Heidinger, 2018: Evaluation of a high-resolution numerical weather prediction model's simulated clouds using observations from CloudSat, GOES-13 and in situ aircraft. *Quart. J. Roy. Meteor. Soc.*, **144**, 1–14. DOI: 10.1002/qj.3318

**Authors:** Zhipeng Qu, Howard W. Barker, Alexei V. Korolev, Jason A. Milbrandt, Ivan Heckman, Stéphane Bélair, Sylvie Leroyer, Paul A. Vaillancourt, Mengistu Wolde, Alfons Schwarzenböck, Delphine Leroy, J. Walter Strapp, Jason N. S. Cole, Louis Nguyen, Andrew Heidinger  
**Journal:** Quarterly Journal of the Royal Meteorological Society  
**Year:** 2018  
**Pages:** 1–14

---

## Abstract

This study aimed to assess tropical cloud properties predicted by Environment and Climate Change Canada's Global Environmental Multiscale (GEM) model when run with the Milbrandt–Yau double-moment cloud microphysical scheme and one-way nesting that culminated at a (~300 km)² inner domain with 0.25 km horizontal grid spacing. The assessment utilized satellite and in situ data collected during the High Ice Water Content (HIWC) and High Altitude Ice Crystals (HAIC) projects for a mesoscale convective system on 16 May 2015 over French Guiana. Data from CloudSat's cloud-profiling radar and GOES-13's imager were compared to data either simulated directly by GEM or produced by operating on GEM's cloud data with both the CFMIP Observation Simulator Package (COSP) instrument simulator and a three-dimensional Monte Carlo solar radiative transfer model. In situ observations were made from research aircraft — Canada's National Research Council Convair-580 and the French SAFIRE Falcon-20. Spatial and temporal shifts of clouds simulated by GEM compared well to GOES-13 imagery. There are, however, differences between simulated and observed amounts of high and low cloud. While GEM did well at predicting ranges of ice-water content (IWC) near 11 km altitude (Falcon-20), it produces too much graupel and snow near 7 km (Convair-580). This produced large differences between CloudSat's and COSP-generated radar reflectivities and two-way attenuations. On the other hand, CloudSat's inferred values of IWC agree well with in situ samples at both altitudes. Generally, GEM's visible reflectances exceeded GOES-13's on account of having produced too much low-level liquid cloud. It is expected that GEM's disproportioning of cloud hydrometeors will improve once it includes a better representation of secondary ice production.

---

## 1. Introduction

When jet aircraft encounter large numbers of small ice crystals, notably at cruising altitudes in mesoscale convective systems (MCS), they are at risk of engine damage and power loss (high ice water content, HIWC, hazard). Quantifying and forecasting HIWC events requires accurate prediction of cloud microphysical properties in NWP models. However, model evaluation for tropical MCS clouds at high spatial resolution (cloud-resolving scale) is challenging due to the spatially and temporally heterogeneous nature of these systems.

The High Ice Water Content (HIWC) and High Altitude Ice Crystals (HAIC) projects provided a unique dataset for evaluating models. This study uses multi-source data from a single MCS event on 16 May 2015 over French Guiana.

---

## 2. Model Configuration

### 2.1 GEM model setup

The Global Environmental Multiscale (GEM) model is used with one-way nesting: outer domain at ~2.5 km, inner domain at 0.25 km horizontal grid spacing (a ~300 × 300 km² area). 

**Microphysics:** The Milbrandt–Yau (MY) double-moment bulk scheme. This scheme predicts mass and number mixing ratios for six hydrometeor categories: cloud droplets, rain, ice crystals, snow, graupel, and hail. The two-moment treatment allows the PSD to evolve prognostically.

### 2.2 Observation operators

- **COSP (CFMIP Observation Simulator Package):** Produces CloudSat-equivalent reflectivity and attenuation from GEM's cloud fields
- **3D Monte Carlo solar radiative transfer:** Produces GOES-13-equivalent visible reflectances from GEM
- **CloudSat CPR:** W-band (94 GHz) cloud-profiling radar; provides vertical profiles of reflectivity and IWC retrievals
- **GOES-13:** Imager providing visible reflectance
- **In situ:** NRC Convair-580 (at ~7 km altitude, ~0°C level) and French SAFIRE Falcon-20 (at ~11 km altitude, well above freezing level)

---

## 3. Results

### 3.1 Cloud spatial and temporal distribution (GOES-13 comparison)

Spatial and temporal shifts of clouds simulated by GEM compared well to GOES-13 imagery — the MCS was correctly placed and its evolution was broadly captured. However:
- GEM produced too much high cloud (thick cirrus anvil)
- GEM produced too much low-level liquid cloud, causing visible reflectances to exceed GOES-13 observations

### 3.2 Ice water content (in situ comparison)

- **At 11 km (Falcon-20):** GEM did well at predicting ranges of IWC — the MY scheme correctly represented upper-level ice crystal populations in the anvil region
- **At 7 km (Convair-580):** GEM produces too much graupel and snow near the 0°C level

### 3.3 Radar reflectivity (CloudSat/COSP comparison)

The overabundance of graupel and snow at 7 km (near the melting level) produced large differences between CloudSat observations and COSP-generated synthetic reflectivities:
- COSP reflectivities were too large near 7 km
- Two-way attenuation was also too large

CloudSat's inferred IWC values agree well with in situ samples at both altitudes, providing consistency between radar-based and direct in situ measurements.

### 3.4 Root cause diagnosis

The primary deficiency identified is GEM's disproportioning of cloud hydrometeors:
- Too much graupel/snow in the mixed-phase region (~7 km)
- Too much low-level liquid cloud
- Expected improvement would come from better representation of **secondary ice production** mechanisms (e.g., Hallett-Mossop rime splintering), which are not included in the MY scheme as configured. Secondary ice production would convert some supercooled liquid water and graupel into smaller ice crystals more realistically.

---

## 4. Discussion and Conclusions

This study demonstrates a comprehensive multi-source evaluation framework for NWP cloud microphysics at cloud-resolving scales (0.25 km), combining:
- CloudSat radar observations + COSP instrument simulator
- GOES-13 visible imagery + 3D Monte Carlo radiative transfer
- In situ aircraft (dual aircraft at two altitude levels)

Key findings:
1. GEM/MY correctly captures the large-scale cloud structure and temporal evolution of the MCS
2. IWC at upper levels (11 km) is well represented
3. GEM overestimates graupel/snow at midlevels (~7 km), producing too-large simulated radar reflectivities
4. GEM overestimates low-level liquid cloud, causing too-large visible reflectances
5. The identified deficiencies are attributed primarily to missing secondary ice production in the MY scheme configuration

The study provides a benchmark for evaluating the MY scheme in tropical convective environments and identifies a specific physical process (secondary ice production) as a priority for improving the scheme's performance.

---

## References

[Key references include: Morrison and Milbrandt (2015), Milbrandt and Yau (2005a,b), Barker et al. (2008, 2012, 2017) for Monte Carlo radiative transfer, Bodas-Salcedo et al. (2011) for COSP, various HIWC/HAIC project papers, CloudSat algorithm documentation]
