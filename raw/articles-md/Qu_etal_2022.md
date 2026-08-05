# Qu et al. (2022): The Impacts of Secondary Ice Production on Microphysics and Dynamics in Tropical Convection

**Full citation:** Qu, Z., Korolev, A., Milbrandt, J. A., Heckman, I., Huang, Y., McFarquhar, G. M., Morrison, H., Wolde, M., and Nguyen, C., 2022: The impacts of secondary ice production on microphysics and dynamics in tropical convection. *Atmos. Chem. Phys.*, **22**, 12287–12310. DOI: 10.5194/acp-22-12287-2022

---

## Abstract

Secondary ice production (SIP) is an important physical phenomenon that results in an increase in the ice particle concentration and can therefore have a significant impact on the evolution of clouds. In this study, idealized simulations of a mesoscale convective system (MCS) were conducted using a high-resolution (250 m horizontal grid spacing) mesoscale model and a detailed bulk microphysics scheme in order to examine the impacts of SIP on the microphysics and dynamics of a simulated tropical MCS. The simulations were compared to airborne in situ and remote sensing observations collected during the "High Altitude Ice Crystals – High Ice Water Content" (HAIC-HIWC) field campaign in 2015. It was found that the observed high ice number concentration can only be simulated by models that include SIP processes. The inclusion of SIP processes in the microphysics scheme is crucial for the production and maintenance of the high ice water content observed in tropical convection. It was shown that SIP can enhance the strength of the existing convective updrafts and result in the initiation of new updrafts above the melting layer. Agreement between the simulations and observations highlights the impacts of SIP on the maintenance of tropical MCSs in nature and the importance of including SIP parameterizations in models.

---

## 1. Introduction

Secondary ice production (SIP) is recognized as a fundamental cloud microphysical process. SIP is different from primary ice production (PIP), which commences by the nucleation of ice homogeneously in strongly supercooled droplets or heterogeneously on ice-nucleating particles. Seven mechanisms are recognized as sources of secondary ice: fragmentation of freezing droplets (FFD), rime splintering (Hallett–Mossop process, HM), fragmentation due to ice–ice collisions, ice fragmentation due to thermal shock, fragmentation of sublimating ice, activation of INPs in transient supersaturation around freezing drops, and break-up of freezing water drops on impact with ice particles.

High IWC (>1 g m⁻³) poses a hazard for civil aviation. Previous modelling studies using traditional fixed-ice-category microphysics schemes pointed to inaccuracies in estimation of cloud PSD, IWC, and ice category compared with observations.

This study examines the effects of SIP on the microphysics and dynamics of a simulated tropical MCS using the P3 multi-category microphysics scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016) in the GEM model.

---

## 2. Observational Data

In situ data were collected from the NRC Convair 580 and SAFIRE Falcon 20 research aircraft during the HAIC-HIWC campaign (May 2015, Cayenne, French Guiana). Measurements of particle size distributions (PSDs) were performed by three particle probes: CDP (2–50 µm), 2D-S (10–1250 µm), and PIP (100 µm–6.4 mm). Bulk IWC was measured by an isokinetic probe (IKP) with upper limit of 10 g m⁻³. Model results are also compared with reflectivity and Doppler velocity from the NRC aircraft X-band radar.

---

## 3. Model Configuration

### 3.1 Atmospheric Model and Initialization

The GEM model (ECCC) was used in a quasi-idealized configuration with 250 m horizontal grid spacing in a 160 km × 160 km domain with 83 vertical levels. Vertical grid spacings of approximately 100 m were used between altitudes of 4 and 7.5 km. The atmospheric initial conditions were based on an initial sounding taken from the operational global GEM analysis at 12:00 UTC on 15 May 2015 at 6.769°N, 49.551°W (CAPE = 1697 J kg⁻¹). Convection was initiated by the updraft nudging method of Naylor and Gilmore (2012).

### 3.2 Cloud Microphysics Scheme

All cloud microphysical processes were represented by the P3 two-moment bulk microphysics scheme with up to four (free) ice categories. For each ice category, there are four prognostic mixing ratio variables: total ice mass, rime mass, bulk volume, and total number. A complete gamma function represents the size distribution of each category. The liquid-phase component of P3 consists of two-moment categories for cloud droplets and rain.

### 3.3 Parameterization of SIP

Two SIP mechanisms were examined:
- **Rime splintering (HM)**: produces a maximum of 350 ice crystals per milligram of collected liquid water, with crystals of 10 µm size, during riming within -3°C > T > -8°C, peak at -5°C
- **Fragmentation of freezing droplets (FFD)**: applied for raindrops (100 µm < D < 3500 µm) nucleated by ice particles (D < 100 µm), active in the temperature range -25°C < T < -2°C

---

## 4. Key Results

- In the control simulation (no SIP), simulated ice number concentrations at 6–7 km were about 2 orders of magnitude lower than values from in situ measurements; the frequency of encountering high-IWC conditions was about 1/2 to 1/500 of the observed frequency
- With SIP mechanisms activated, results dramatically improved: ice concentrations increased by up to 3 orders of magnitude at 6–7 km
- SIP resulted in smaller mean ice particle size with lower fall speeds, allowing ice to be transported to higher altitudes, sustaining cloud regions with high IWC
- SIP can enhance the strength of existing convective updrafts and initiate new updrafts above the melting layer through increased latent heat release during vapour deposition on numerous secondary ice particles
- Aggregation of ice particles is very sensitive to the parameterization of ice collection efficiency, which remains uncertain
- A minimum of three ice categories in P3 are necessary to examine SIP in detail; four categories were used for most simulations

---

## 5. Conclusions

SIP processes play a critical role in the formation and maintenance of high IWC with low reflectivity at upper levels in MCSs. The conclusions regarding the importance of including SIP processes in models have implications for operational NWP systems providing numerical guidance for civil aviation.

**Author contributions:** ZQ, AK, and JAM conceptualized the research goals and aims. ZQ, JAM, and AK designed the experiments with the support from YH, GMM, and HM. ZQ performed the simulations and analysis with the help from AK, JAM, IH, MW, and CN. ZQ prepared the manuscript with contributions from all co-authors.

---

## References

[Selected key references]

- Morrison, H. and Milbrandt, J. A., 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Milbrandt, J. A. and Morrison, H., 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III: Introduction of multiple free categories. *J. Atmos. Sci.*, **73**, 975–995.
- Milbrandt, J. A. and Yau, M. K., 2005a,b: A multi-moment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3081.
- Korolev, A. and Leisner, T., 2020: Review of experimental studies of secondary ice production. *Atmos. Chem. Phys.*, **20**, 11767–11797.
- Milbrandt, J. A., Morrison, H., Dawson II, D. T., and Paukert, M., 2021: A triple-moment representation of ice in the P3 microphysics scheme. *J. Atmos. Sci.*, **78**, 439–458.
