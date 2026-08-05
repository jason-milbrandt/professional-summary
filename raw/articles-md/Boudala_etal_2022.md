# Boudala, F.S., J.A. Milbrandt, and G.A. Isaac, 2022: Evaluation of CanESM Cloudiness, Cloud Type and Cloud Radiative Forcing Climatologies Using the CALIPSO-GOCCP and CERES Datasets. *Remote Sensing*, **14**, 3668. DOI: 10.3390/rs14153668

---

## Abstract

Annual and seasonal climatologies of cloud fraction (CF) and cloud type simulated by the Canadian Environmental System Models (CanESM5 and CanESM2) at coupled and AMIP configurations were validated against CALIPSO-GOCCP satellite data. COSP simulator-based CF from CanESMs was also evaluated. Shortwave, longwave, and net cloud radiative forcing (CRF) from AMIP-CanESM5 were validated against CERES EBAF4.1 datasets. All models showed negative bias in total CF globally (2–7.1%), with CanESM5 performing better than CanESM2. Regional biases exceed 40% in some locations. AMIP-CanESM5 simulated global mean CRF reasonably well but showed geographic biases up to ±40 W m⁻².

---

## 1. Introduction

Clouds are a dominant source of uncertainty in GCM-based climate projections. The CanESM5 model, used in CMIP6, shows higher climate sensitivity than prior versions. Evaluation of cloud fraction and cloud radiative forcing against modern satellite products (CALIPSO-GOCCP for cloud properties; CERES for radiation) is needed to identify model deficiencies and guide improvements.

---

## 2. Methods

### Satellite Data

- **CALIPSO-GOCCP**: lidar-based CF products (2007–2019); 40 vertical levels, 2°×2° grid; cloud types classified by height (low, mid, high) and phase (liquid, ice, undefined).
- **CERES EBAF4.1**: top-of-atmosphere (TOA), surface, and atmospheric radiation fluxes; energy-balanced and gap-filled.

### Models Evaluated

| Configuration | Description |
|---------------|-------------|
| Coupled-CanESM5/2 | Fully coupled ocean-atmosphere mode |
| AMIP-CanESM5/2 | Prescribed SST atmospheric mode |
| COSP-AMIP-CanESM5/2 | AMIP + CALIPSO satellite simulator (COSP) |

---

## 3. Key Results

### Cloud Fraction Biases (global mean)

| Model | Total CF bias |
|-------|--------------|
| Coupled-CanESM5 | −2.0% |
| AMIP-CanESM5 | −2.4% |
| COSP-AMIP-CanESM5 | −3.9% |
| Coupled-CanESM2 | −6.4% |
| AMIP-CanESM2 | −5.6% |
| COSP-AMIP-CanESM2 | −7.1% |

- RMSE for total CF: 10–12% across all models; CanESM5 consistently smaller.
- COSP simulator: slightly reduces RMSE but COSP-based models show larger negative biases.
- Little difference between coupled and AMIP versions; atmospheric dynamics and microphysics are the primary source of discrepancy.

### Regional Biases

- **Positive bias**: ITCZ region, Indo-Pacific warm pool, polar regions (especially Antarctica). HLC overestimated in tropics.
- **Negative bias**: Marine stratocumulus regions (southeastern Pacific, Atlantic, Indian Oceans, northeastern Pacific). LLC and MLC underestimated.
- Largest biases exceed ±40% CF regionally.

### Cloud Type Biases (CanESM5, COSP)

- LLC: −2.4%, MLC: −7.6%, HLC: −1.4%. MLC most strongly underestimated.
- Liquid phase LLC underestimated; CanESM5 liquid clouds vertically shallower than GOCCP.

### Cloud Radiative Forcing (AMIP-CanESM5 vs. CERES)

- Global mean CRF at TOA and surface: slight negative biases in NetCRF consistent with positive CF bias in some regions but inconsistent with negative global CF bias — may reflect optical property parameterization errors.
- NetCRF geographic distribution: biases up to ±40 W m⁻²; strongly correlated with CF biases in LL and HL clouds.

---

## 4. Summary and Conclusions

CanESM5 outperforms CanESM2 in cloud fraction simulation. Coupled vs. AMIP configurations show similar biases, pointing to atmospheric dynamics and cloud microphysics as the root cause. COSP simulator reduces some biases but increases others. Key regional problems: overestimation of tropical HLC and LLC underestimation in stratocumulus regions. MLC is the most poorly simulated cloud type. CRF biases are geographically significant and tied to CF biases.

---

## Author Contributions

Boudala: methodology, validation, formal analysis, visualization, data curation, original draft. Milbrandt and Isaac: writing (review and editing) only.
