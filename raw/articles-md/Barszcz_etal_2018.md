# Improving the Explicit Prediction of Freezing Rain in a Kilometer-Scale Numerical Weather Prediction Model

**Citation:** Barszcz, A., J. A. Milbrandt, and J. M. Thériault, 2018: Improving the explicit prediction of freezing rain in a kilometer-scale numerical weather prediction model. *Wea. Forecasting*, **33**, 767–782. DOI: 10.1175/WAF-D-17-0136.1

---

## Abstract

A freezing rain event, in which the Meteorological Centre of Canada's 2.5-km numerical weather prediction system significantly underpredicted the quantity of freezing rain, is examined. The prediction system models precipitation types explicitly, directly from the Milbrandt–Yau microphysics scheme. It was determined that the freezing rain underprediction for this case was due primarily to excessive refreezing of rain, originating from melting snow and graupel, in and under the temperature inversion of the advancing warm front ultimately depleting the supply of rain reaching the surface. The refreezing was caused from excessive collisional freezing between rain and graupel. Sensitivity experiments were conducted to examine the effects of a temperature threshold for collisional freezing and on varying the values of the collection efficiencies between rain and ice-phase hydrometeors. It was shown that by reducing the rain–graupel collection efficiency and by imposing a temperature threshold of −5°C, above which collisional freezing is not permitted, excessive rain–graupel collection and graupel formation can be controlled in the microphysics scheme, leading to an improved simulation of freezing rain at the surface.

---

## 1. Introduction

Forecasts of surface precipitation types in winter storms have significant societal impacts (transportation, aviation, public safety). Near-surface temperatures in winter storms can be close to 0°C, leading to mixed-phase precipitation including rain, freezing rain, ice pellets, and snow. Most large-scale NWP systems use diagnostic schemes to determine precipitation type (e.g., Bourgouin 2000 statistical method). Kilometer-scale systems with bulk microphysics schemes (e.g., HRDPS at 2.5 km) can determine precipitation types explicitly from the hydrometeor fields.

HRDPS was implemented by MSC in 2014 and uses the Milbrandt–Yau (MY2) two-moment bulk microphysics scheme with six hydrometeor categories: cloud, rain, ice, snow, graupel, and hail. During winter 2014/15, HRDPS systematically underpredicted freezing rain amounts and extent.

---

## 2. Overview of the Case

### a. Synoptic overview

On 24–25 December 2014, a low pressure system affected Quebec and the Maritime Provinces, producing high amounts of freezing rain. Upper-air soundings show a temperature inversion at ~800 hPa favourable to freezing rain formation. Observed freezing rain amounts: 22–23 mm at Charlevoix (CWIS) and Cap-Chat (CWSG); 1–15 mm at most other Quebec stations.

### b. Performance of operational NWP models

**RDPS (10 km):** Uses the Sundqvist et al. (1989) scheme with the Bourgouin (2000) diagnostic for precipitation types. Predicted up to 15 mm of freezing rain over Quebec — reasonably close to observed.

**HRDPS (2.5 km):** Uses MY2 microphysics with explicit precipitation type partitioning. Predicted less than 2.5 mm of freezing rain over the entire region — a severe underprediction. Both systems forecast 15–50 mm of total accumulated precipitation with similar spatial distributions.

---

## 3. Identification of the Problem

### a. Preliminary analysis

To determine whether the problem was in the microphysics or the diagnostic, two test runs were conducted:
- **EXP1:** MY2 replaced with Sundqvist scheme + Bourgouin diagnostic → freezing rain amounts similar to RDPS and observations
- **EXP2:** MY2 microphysics retained but precipitation types diagnosed using Bourgouin (overriding MY2 explicit types) → freezing rain amounts similar to EXP1

Conclusion: the problem was not in total precipitation amounts but in the partitioning into types by the MY2 scheme.

### b. Vertical distribution of hydrometeors and microphysical processes

Cross sections (perpendicular to the warm front, valid 1800 UTC 24 Dec 2014) reveal:
- Under the temperature inversion (~925 hPa): condensate composed mainly of graupel accumulating at surface at 1–3 mm h$^{-1}$
- Rain mass mixing ratio decreases sharply below the melting layer
- Three-component collisional freezing rates: rain–graupel ($5 \times 10^{-2}$ kg kg$^{-1}$ s$^{-1}$) >> rain–snow ($5 \times 10^{-3}$) >> rain–ice ($8 \times 10^{-4}$)
- Rain–graupel collisions are the dominant source of refreezing, converting rain to graupel beneath the melting layer and suppressing freezing rain at the surface

---

## 4. Sensitivity Tests with the Microphysics Scheme

### a. Temperature threshold for three-component freezing

MY2 does not track particle temperature; it assumes particles have the ambient air temperature. In reality, supercooled drops falling through a warm layer take time to cool, and at temperatures just below 0°C they may not freeze spontaneously. A temperature threshold was introduced above which collisional freezing is not permitted.

**Experiment set 3 (EXP3A–EXP3H):** Threshold temperatures ranging from 0° to −9°C.

Key results:
- With threshold ≤ −5°C: significant graupel present only over a region <30 km wide (where warm layer is shallowest); freezing rain represents ~90% of surface precipitation over most of the cross section
- With threshold > −3°C: collisional freezing active, leading to >90% glaciation of precipitation
- The presence of even ~10% graupel is sufficient to glaciate >90% of the precipitation through collisional chain reactions
- Domain-integrated analysis: increasing (decreasing) freezing rain and decreasing (increasing) graupel as threshold temperature decreases (colder), with plateau effect at cold thresholds
- Over 88% of freezing rain and 20% of graupel falls under the melting layer; more than 80% of surface area receiving freezing rain/graupel is outside the melting layer

### b. Collection efficiencies

In MY2, the collection efficiencies $E_{rg}$ (rain–graupel), $E_{ri}$ (rain–ice), $E_{rs}$ (rain–snow) are all set to 1. Laboratory studies show size-dependent values often much less than 1.

**Experiment set 4 (EXP4A–EXP4E):** $E_{rg}$ varied from 0.8 to 0 while $E_{ri} = E_{rs} = 1$.
**Experiment set 5 (EXP5A–EXP5E):** $E_{ri}$ and $E_{rs}$ varied from 0.8 to 0 while $E_{rg} = 1$.

Key results:
- Freezing rain amounts are very sensitive to $E_{rg}$: reducing $E_{rg}$ to 0.4 allows significant freezing rain to reach the surface (>90% of total precipitation along the cross section)
- Varying $E_{ri}$ and $E_{rs}$ has negligible impact — rain–ice and rain–snow collision rates are small compared to rain–graupel
- Domain-wide: higher $E_{rg}$ → lower freezing rain accumulations and smaller surface area; lower $E_{rg}$ → more freezing rain
- Greatest impact of collection efficiency is under the melting layer where most freezing rain forms

---

## 5. Discussion and Conclusions

The systematic HRDPS freezing rain underprediction was traced to nearly complete refreezing of rain below the melting layer due to excessively high rain–graupel collisional freezing rates in MY2.

**Operational fix implemented:** A temperature threshold of −5°C for collisional three-component freezing was added to the MY2 scheme in the real-time HRDPS system. After this modification, freezing rain forecasts improved systematically (A. Rahill, MSC, 2017, personal communication).

**Inherent limitations of bulk formulations:**
- MY2 solves the collection equation analytically with a single bulk collection efficiency — appropriate for widely different fall speeds (e.g., hail–cloud), but problematic for rain–graupel whose fall speeds are similar
- Lookup tables (as in Thompson et al. 2008; Morrison and Milbrandt 2015) are probably preferable
- Partially melted ice is not modeled — melted mass is immediately transferred to rain, preventing proper simulation of ice pellet formation
- Ideally, the microphysics would track liquid fraction on partially melted ice (as in Thériault and Stewart 2010) and properly account for collisional freezing thermodynamics

---

## References

- Baldwin et al. (1994); Benjamin et al. (2016); Bourgouin (2000); Carmichael et al. (2011)
- Caron et al. (2015); Carrera et al. (2009); Cortinas et al. (2004); Côté et al. (1998)
- Girard et al. (2014); Hanesiak and Stewart (1995); Hindmarsh et al. (2003)
- Ikeda et al. (2017); Mailhot et al. (2006); Manikin (2005); Milbrandt and Yau (2005a,b)
- Milbrandt et al. (2016); Mitra et al. (1990); Morrison and Milbrandt (2015)
- Pruppacher and Klett (2012); Ramer (1993); Rauber et al. (2000); Reeves (2016)
- Stewart (1992); Stewart et al. (2015); Sundqvist (1988); Sundqvist et al. (1989)
- Thériault and Stewart (2010); Thompson et al. (2008); Tobin and Kumjian (2017); Zerr (1997)
