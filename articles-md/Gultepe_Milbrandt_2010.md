# Gultepe and Milbrandt (2010) — Probabilistic Parameterizations of Visibility Using Observations of Rain Precipitation Rate, Relative Humidity, and Visibility

**Full citation:** Gultepe, I., and J. A. Milbrandt, 2010: Probabilistic Parameterizations of Visibility Using Observations of Rain Precipitation Rate, Relative Humidity, and Visibility. *J. Appl. Meteor. Climatol.*, **49**, 36–46. DOI: 10.1175/2009JAMC1927.1

**Journal:** Journal of Applied Meteorology and Climatology  
**Year:** 2010  
**Authors:** I. Gultepe, J. A. Milbrandt

---

## Abstract

This study analyzes the occurrence of visibility (Vis) versus precipitation rates (PR) for rain and versus relative humidity (RH) from surface observations collected during the Fog Remote Sensing and Modeling (FRAM) field project (Toronto, ON, winter 2005/06; Lunenburg, NS, summers 2006 and 2007). Main observations: PR and Vis from Vaisala FD12P; RH and temperature from Campbell HMP45. The study shows that large variability in Vis (up to one order of magnitude) exists for a fixed PR, and that statistical relationships applied to percentiles (probabilistic approach) offer a feasible alternative to single-curve (deterministic) parameterizations for model applications, especially for extreme-weather conditions.

---

## 1. Introduction

Existing NWP visibility parameterizations (as a function of RHw and/or PR, e.g., Kunkel 1984; Stoelinga and Warner 1999) are derived from few measurements and include large uncertainties. Earlier work (Gultepe and Isaac 2006) showed that Vis values from existing parameterizations differ markedly from observations, particularly near saturation. This study develops new Vis parameterizations from FRAM observations using both deterministic (mean-curve) and probabilistic (percentile-curve) approaches, with the goal of providing improved tools for NWP model applications including aviation, transportation, and search-and-rescue.

---

## 2. Observations

**FRAM-C:** Centre for Atmospheric Research Experiment (CARE) site, Toronto, ON — winter 2005/06  
**FRAM-L1:** Lunenburg, NS — summer 2006  
**FRAM-L2:** Lunenburg, NS — summer 2007  

Instruments:
- Vaisala FD12P present-weather sensor — visibility, PR (liquid + solid), precipitation type
- YES TPS-3100 hot plate — total precipitation rate (validation)
- Ott Parsivel optical disdrometer — drop size distributions, velocity (32 size/velocity classes)
- Campbell HMP45 — RHw, temperature

Snow PR measurements excluded (unknown particle density/shape). PRR uncertainty > 75% when PRR < 0.5 mm h⁻¹ (drizzle conditions). Data filtered to RHw > 95% and PR > 0.1 mm h⁻¹ for Vis–PRR analysis (to isolate precipitation effect on Vis).

---

## 3. Analysis: Probabilistic vs. Deterministic Approach

**Deterministic approach:** single best-fit curve to mean or binned values of Vis vs. RHw or PRR. Problematic because data scatter can span an order of magnitude.

**Probabilistic approach:** fits applied to the 5th, 50th (median), and 95th percentiles of Vis for a given RHw or PRR. Allows for application-specific use:
- 5% curve: lowest expected Vis (useful for aviation hazard applications — only 5% of observations fall below this line)
- 50% curve: most-likely Vis
- 95% curve: highest expected Vis (useful for light precipitation conditions)

---

## 4. Results

### 4a. Visibility vs. RHw

New relationships (Table 1):

| Label | Equation | Conditions |
|-------|----------|------------|
| VisRUC | $60 \exp[-2.5(R_\text{Hw} - 15)/80]$ | RUC model |
| VisFRAM-C | $-41.5 \ln(R_\text{Hw}) + 192.30$ | RHw > 30% |
| VisAIRS | $-0.0177 R_\text{Hw}^2 + 1.46 R_\text{Hw} + 30.80$ | RHw > 30% |
| VisFRAM-L (5%) | $-0.000114 R_\text{Hw}^{2.70} + 27.45$ | RHw > 30% |
| VisFRAM-L (50%) | $-5.19 \times 10^{-10} R_\text{Hw}^{5.44} + 40.10$ | RHw > 30% |
| VisFRAM-L (95%) | $-9.68 \times 10^{-14} R_\text{Hw}^{7.19} + 52.20$ | RHw > 30% |

The RUC Vis near RHw = 100% is significantly larger than observations from this work; for RHw < 95%, RUC Vis is significantly smaller. The 50% FRAM-L curve compared favorably with a 27 June 2006 case, tracking the Vis trend without precipitation.

### 4b. Visibility vs. Precipitation Rate (rain)

New relationships (Table 2):

| Label | Equation | Conditions |
|-------|----------|------------|
| Rain (mean) | $-4.12 \text{PR}^{0.176} + 9.01$ | mean values |
| Rain (50%) | $-2.65 \text{PR}^{0.256} + 7.65$ | 50th percentile |
| Rain (5%) | $-0.45 \text{PR}^{0.394} + 2.28$ | 5th percentile |
| Rain (95%) | $-863.26 \text{PR}^{0.003} + 874.19$ | 95th percentile |
| Drizzle (mean) | $-2.66 \text{PR}^{0.526} + 6.54$ | drizzle only |

Key results:
- At PRR = 10 mm h⁻¹, Vis ranges from 1.5 km (5%) to 5 km (95%).
- Drizzle (drops 100–500 μm, PR < ~2 mm h⁻¹) can reduce Vis by at least a factor of 2 relative to rain.
- Vis–PRR relationships are not unique; raindrop size distribution (DSD) variability and total $N_d$ should be considered.
- Ott Parsivel data show that $\text{Vis} \sim f(\text{PR}/N_d)$, confirming that $N_d$ is an important independent variable.

### 4c. Integrated Visibility: Fog + Rain + RHw

An integrated extinction approach combines contributions from all three sources:

$$\beta_\text{int} = \beta_{R_\text{Hw}} + \beta_\text{LWC} + \beta_R$$

Final Vis is computed from $\beta_\text{int}$ via $\text{Vis} = -\ln(0.05)/\beta_\text{int}$.

A case study (11 February 2009 fog+rain event) showed that integrated Vis using GEM NWP model outputs for LWC, RHw, and PRR compared well with observations between 1400 and 1830 UTC.

---

## 5. Conclusions

1. Existing NWP Vis–RHw parameterizations (especially RUC) overestimate Vis near saturation and underestimate it at subsaturation.
2. Large variability in Vis for fixed PRR means deterministic parameterizations are inadequate; probabilistic (percentile-based) approaches are preferable.
3. New percentile-based Vis parameterizations derived from FRAM observations can be adopted in NWP models, with the choice of percentile depending on application.
4. Drizzle effect on Vis is significant and often underrepresented in previous parameterizations.
5. When fog and rain co-occur, integrated Vis strongly depends on the accuracy of simulated fog LWC, RHw, and PR.
