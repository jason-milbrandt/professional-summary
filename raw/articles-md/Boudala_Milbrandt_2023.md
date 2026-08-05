# Boudala, F.S. and J.A. Milbrandt, 2023: Solid Precipitation and Visibility Measurements at the Centre for Atmospheric Research Experiments in Southern Ontario and Bratt's Lake in Southern Saskatchewan. *Remote Sensing*, **15**, 4079. DOI: 10.3390/rs15164079

---

## Abstract

Accurate measurement of solid precipitation (S) is critical for the hydrological cycle, NWP model validation, and developing parameterizations of visibility (Vis). Wind effects on gauge catch efficiency are the primary challenge. This study analyzes datasets from two sites — CARE (Egbert, Ontario) and Bratt's Lake (Saskatchewan) — using several instruments including DFAR-shielded Geonor gauges, double Alter shielded (DAS) and single Alter shielded (SAS) gauges, a HotPlate, a PARSIVEL2 disdrometer, and an FD12P present weather sensor. Transfer functions (TF) for catch efficiency as functions of wind speed and fall velocity were developed. For U < 6 m s⁻¹, DAS and SAS have similar collection efficiency (~70%). The TF including fall velocity outperformed wind-speed-only versions. The CARE TF tested at Bratt's Lake showed R = 0.86 but overestimated accumulation by ~12%. A strong correlation (R = 0.9) between DFAR precipitation intensity and visibility supports aviation application parameterizations.

---

## 1. Introduction

Solid precipitation measurement is challenging due to wind-induced undercatch. Standard reference: Double Fence Automated Reference (DFAR) system. Prior transfer functions mainly based on coarse-resolution (daily/hourly) or limited datasets. Fall velocity is an underexplored predictor of catch efficiency. Visibility-snowfall parameterizations for aviation rely on accurate precipitation data.

---

## 2. Materials and Methods

### Sites

- **CARE** (Center for Atmospheric Research Experiments): Egbert, Ontario (44.23°N, 79.78°W, 251 m ASL). Data from 2012–2013 SPICE project. Generally sheltered, low-wind environment.
- **Bratt's Lake**: Southern Saskatchewan (50.16°N, 104.68°W, 585 m ASL). Open field, windy, mean wind = 4.4 m s⁻¹. Data from 2021–2022. Used as independent test dataset.

### Instruments

- **DFAR Geonor T-200B3**: reference standard (three-wire vibrating transducer gauge inside double fence)
- **DAS Geonor**: double Alter shielded gauge
- **SAS Pluvio2**: single Alter shielded OTT Pluvio2 gauge
- **FD12P** (Vaisala): present weather sensor measuring precipitation type, intensity, and visibility
- **PARSIVEL2** (OTT): optical disdrometer; measures size and fall velocity distributions
- **HotPlate** (Yankee): heat-transfer-based precipitation rate; self-correcting for forced convection

### Transfer Function Forms

$CE(U) = 1 - a \exp\left(-\frac{b}{U}\right)$ (wind speed only)

$CE(U,V) = \exp(-c U^d + eV - f)$ (wind speed + fall velocity)

---

## 3. Results

### Catch Efficiency

- DAS Geonor and SAS Pluvio2: both ~70% CE for U < 6 m s⁻¹ at CARE; DAS Pluvio at Bratt's Lake ~66%.
- DAS TF(U) adjusts undercatch to within 6%; DAS TF(U,V) improves to no bias.
- Universal SAS TF (SPICE multi-site) overestimates CE at low/high wind; slightly underestimates accumulation by 3%.
- Marshall-site DAS TF underestimates CE at U < 3 m s⁻¹; adjusts undercatch with ~8% error.
- CARE DAS TF applied to Bratt's Lake: R = 0.86, but overestimates accumulation by ~12%.

### Non-Traditional Sensors

| Instrument | Bias vs. DFAR | Wind dependence |
|-----------|----------------|-----------------|
| FD12P | −32% | None |
| PARSIVEL2 | +28% | Some |
| HotPlate | −3.4% | Some at U > 3 m s⁻¹ |

HotPlate best matches DFAR reference.

### Visibility–Snowfall Parameterization

- Tight correlation (R = 0.9) between observed VIS and DFAR precipitation intensity at CARE.
- New Vis–S relationship derived; consistent with Boudala and Isaac (2009).
- Adding temperature to the parameterization does not significantly improve performance.
- LWE thresholds from new parameterization agree better with SAE de-icing standards than prior work.

---

## 4. Conclusions

DAS and SAS gauges have similar catch efficiency (~70%). Transfer functions including fall velocity outperform wind-speed-only TFs. TFs are site-specific: CARE-derived TF overestimates at Bratt's Lake by 12%. HotPlate is the best non-traditional sensor. Strong VIS–S correlation supports aviation applications. New visibility parameterizations are applicable for NWP model validation.

---

## Author Contributions

Boudala: all scientific work (project administration, funding, conceptualization, methodology, validation, analysis, data curation, original draft). Milbrandt: writing (review and editing) only.
