# Three-Moment Representation of Rain in a Bulk Microphysics Model

**Full citation:** Paukert, M., J. Fan, P. J. Rasch, H. Morrison, J. A. Milbrandt, J. Shpund, and A. Khain, 2019: Three-moment representation of rain in a bulk microphysics model. *J. Adv. Model. Earth Syst.*, **11**. DOI: 10.1029/2018MS001512

**Authors:** Marco Paukert, Jiwen Fan, Philip J. Rasch, Hugh Morrison, Jason A. Milbrandt, Jacob Shpund, Alexander Khain  
**Journal:** Journal of Advances in Modeling Earth Systems  
**Year:** 2019

---

## Abstract

A bulk three-moment representation for rain microphysics is developed and implemented in the Predicted Particle Properties (P3) microphysics scheme. In addition, a new parameterization for rain self-collection and collisional breakup (RSCB) is presented using a lookup table approach, based on the Spectral-Bin Model (SBM). To quantify the impacts of sedimentation, evaporation, and RSCB on drop size distributions (DSDs), a rain shaft model is applied to a wide range of atmospheric scenarios and compared against results from the SBM. DSD shapes are mainly determined by both sedimentation and evaporation, except in heavy rain where the impact of RSCB on DSD shape becomes more important than evaporation. The new parameterization for RSCB has a considerable impact on the mean drop size, improving the agreement between P3 and SBM. Only 4% of the original two-moment rainshaft simulations have mean drop sizes and rain rates within ±20% of the SBM results, but this increases to more than 95% agreement when the three-moment rain representation is used together with the new parameterization for RSCB. Generally, the improvement is more significant for heavy rain than for light drizzle. Remaining differences between bin and bulk model are attributable to treatments of evaporation, and the restriction to gamma DSDs in P3.

---

## 1. Introduction

Rain is characterized fundamentally by drop size distributions (DSDs). In the widely used two-moment approach for bulk microphysics schemes (e.g., Milbrandt and Yau 2005; Morrison et al. 2009), the zeroth and third moments ($M_0$, $M_3$) of $f(D)$ are predicted. This leaves the shape parameter $\mu$ undetermined — typically $\mu = 0$ (exponential DSD) is assumed. However, constant $\mu = 0$ causes excessive size sorting: separate number-weighted and mass-weighted fall speeds lead to spatial separation of large and small drops, yielding mean drop sizes too large at the leading edge of precipitation (Wacker and Seifert 2001; Milbrandt and McTaggart-Cowan 2010).

Three-moment bulk schemes add a prediction of the sixth moment ($M_6$, proportional to radar reflectivity for spherical particles) to predict $\mu$. Milbrandt and Yau (2005b) first developed a three-moment representation for all hydrometeor classes. Breakup of raindrops has not been considered explicitly in existing three-moment bulk schemes.

The Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015) offers a new approach to representing ice particle evolution. The ultimate goal of this work is to apply a full three-moment version of P3 to the U.S. DOE Energy Exascale Earth System Model (E3SM).

---

## 2. Development of Three-Moment Rain Microphysics

### 2.1 Prognostic moments

The three-moment scheme prognoses $M_0$ (number mixing ratio $N_r$), $M_3$ (proportional to mass mixing ratio $Q_r$), and $M_6$ (proportional to radar reflectivity $Z_r$). The shape parameter $\mu$ is then predicted (rather than diagnosed from an empirical relation as in two-moment P3).

The gamma DSD:
$$f(D) = N_0 D^\mu e^{-\lambda D}$$

where $N_0$ is the intercept, $\mu$ is the shape parameter, and $\lambda$ is the slope. With three prognostic moments, all three DSD parameters ($N_0$, $\mu$, $\lambda$) are uniquely determined.

### 2.2 Processes contributing to M₆ budget

The budget of $M_6$ includes contributions from:
- **Sedimentation**: Dominant process for shaping the DSD; creates narrower DSDs (larger $\mu$) by size sorting
- **Evaporation**: Counteracts size sorting; tends to broaden the DSD (smaller $\mu$); treated assuming constant mean volume diameter (MVD) during evaporation
- **Rain self-collection and collisional breakup (RSCB)**: Important for heavy rain; shifts $\mu$ toward equilibrium

### 2.3 New RSCB parameterization via lookup tables

A unique feature of this scheme: RSCB processes affecting $M_0$ and $M_6$ are parameterized using lookup tables derived from SBM simulations, with dependencies on DSD properties ($\mu$, mean diameter $D_n$). The SBM 33-bin version solves the quasi-stochastic collection equation and uses the Seifert et al. (2005) breakup scheme. One-second SBM time steps are used to produce instantaneous RSCB rates. Two lookup tables are created: $\text{table}(μ, D_n)^{Nr}$ for bulk number and $\text{table}(μ, D_n)^{M6}$ for the sixth moment. Mass is conserved during RSCB.

---

## 3. Rain Shaft Model Setup

A 1D rain shaft model is used to test the scheme over a wide range of atmospheric scenarios: initial rain rates from 0.01 to 100 mm/h, $\mu$ from -1 to 20, and various vertical profiles. A cloud-free column is assumed. Simulations run for 3600 s.

Configurations tested:
- **SBM**: Full 33-bin spectral bin model (benchmark)
- **SBM-Γ**: Bin model constrained to evolve a gamma DSD (tests the gamma assumption itself)
- **2m**: Two-moment P3 (original)
- **3m-sed**: Three-moment, sedimentation only for $M_6$
- **3m-sed+evap**: Three-moment, sedimentation + evaporation for $M_6$
- **3m-full**: Three-moment, all processes including RSCB lookup tables

---

## 4. Results

### 4.1 Dominant processes

- **Sedimentation and evaporation** are the dominant processes determining DSD shape in most regimes
- **RSCB** becomes more important than evaporation for heavy rain (rain rate ≳ 5 mm/h), affecting $\mu$ and mean drop size

### 4.2 Improvement over two-moment scheme

Only 4% of two-moment (2m) rainshaft simulations have mean drop sizes and rain rates within ±20% of SBM results. The three-moment full scheme (3m-full) increases this to >95% agreement. Improvement is more significant for heavy rain than for light drizzle.

### 4.3 Contribution of RSCB

The new RSCB lookup table parameterization makes major contributions to improved agreement with SBM, primarily through its impact on rain drop number mixing ratios: drop mean sizes are smaller compared to the default (no RSCB) parameterization. Applying the new RSCB approach to the two-moment scheme yields only small benefits — despite improved mean sizes, the diagnosed shape parameter still yields discrepancies in simulated rain rates.

### 4.4 Remaining differences

1. Evaporation parameterization differs between P3 and SBM: P3 assumes constant MVD during evaporation, which contributes to overestimated mean sizes particularly in light rain
2. The gamma DSD assumption introduces biases in light rain compared to the freely evolving DSD in SBM; heavy rain is well represented

### 4.5 Comparison: SBM vs. SBM-Γ

Good agreement between 3m-full and SBM-Γ configurations can be regarded as proof of concept for the lookup table approach. Remaining discrepancies between 3m-full and SBM are mostly attributable to the gamma DSD assumption itself.

---

## 5. Conclusions and Discussion

1. The three-moment rain representation substantially improves DSD simulations compared to the two-moment scheme
2. Sedimentation and evaporation are the dominant processes; RSCB becomes important in heavy rain
3. The new RSCB lookup table parameterization considerably improves mean drop sizes
4. Remaining differences attributable to evaporation treatment and gamma DSD restriction

**Future work:** Merge three-moment rain scheme with ongoing three-moment ice microphysics developments in P3 to provide a full three-moment scheme for weather and climate modeling.

---

## Appendix A: Lookup Tables of RSCB

RSCB rates are derived by running SBM for one time step initialized with a three-parameter gamma DSD, spanning all relevant combinations of DSD parameters. Lookup tables are indexed by $\mu$ and $D_n$ (normalized mean diameter), implicitly representing variability in all three DSD parameters.

---

## References

[Key references: Milbrandt and Yau (2005a,b), Morrison and Milbrandt (2015), Milbrandt and Morrison (2016), Milbrandt and McTaggart-Cowan (2010), Khain et al. (2004), Naumann and Seifert (2016), Seifert (2005, 2008), Seifert et al. (2005), Wacker and Seifert (2001)]
