# Summary: Paukert et al. (2019)

**Full citation:** Paukert, M., J. Fan, P. J. Rasch, H. Morrison, J. A. Milbrandt, J. Shpund, and A. Khain, 2019: Three-moment representation of rain in a bulk microphysics model. *J. Adv. Model. Earth Syst.*, **11**. DOI: 10.1029/2018MS001512
**Journal:** Journal of Advances in Modeling Earth Systems
**Year:** 2019
**Authors:** Marco Paukert, Jiwen Fan, Philip J. Rasch, Hugh Morrison, Jason A. Milbrandt, Jacob Shpund, Alexander Khain
**DOI:** 10.1029/2018MS001512
**Author's role:** Tier 3 — Contributing co-author; provided the P3 microphysics scheme implementation and bulk microphysics expertise; the three-moment rain representation was developed within and tested in the P3 framework

---

## Overview

This paper develops a three-moment bulk rain microphysics representation within the P3 microphysics scheme, adding prediction of the sixth moment of the raindrop size distribution (DSD) to allow the DSD shape parameter ($\mu$) to evolve prognostically. It also presents a novel parameterization of rain self-collection and collisional breakup (RSCB) using spectral bin model (SBM) lookup tables. Testing in a 1D rain shaft model shows that the combination of three-moment prediction and the new RSCB parameterization increases agreement with the SBM benchmark from 4% to over 95% in terms of mean drop sizes and rain rates, a dramatic improvement over the original two-moment scheme.

## Context and Motivation

In standard two-moment bulk schemes (including P3), the shape parameter $\mu$ of the gamma DSD is either fixed ($\mu = 0$) or diagnosed from an empirical shape-slope relationship. Fixing $\mu = 0$ causes excessive size sorting during sedimentation: large drops fall faster than small ones, and without a narrowing DSD, mean drop sizes at the leading edge of precipitation become unrealistically large. A three-moment approach (predicting $M_0$, $M_3$, $M_6$) allows $\mu$ to be a true prognostic variable, enabling physically consistent DSD narrowing through sedimentation. Prior three-moment schemes (Milbrandt and Yau 2005b) had not explicitly treated RSCB as a process modifying $M_6$; this paper addresses that gap.

## Key Scientific Contributions

- First implementation of a three-moment rain scheme within the P3 framework, predicting the zeroth ($N_r$), third ($Q_r$), and sixth ($Z_r$) moments of the gamma DSD
- Novel RSCB parameterization using SBM-derived lookup tables, indexed by ($\mu$, $D_n$), providing physically consistent treatment of collisional breakup effects on DSD shape
- Systematic decomposition of the relative contributions of sedimentation, evaporation, and RSCB to DSD shape evolution across a wide range of rain regimes
- Quantitative demonstration that two-moment P3 agrees with SBM in only 4% of cases within ±20%, increasing to >95% with the full three-moment + RSCB scheme
- Proof of concept that the gamma DSD assumption, not the RSCB treatment, is the limiting factor in remaining discrepancies (via SBM-Γ comparison)

## Methods Summary

A 1D rain shaft model is used as the testing framework. Initial conditions span a wide range: rain rates 0.01–100 mm/h, $\mu$ from −1 to 20. A cloud-free column is assumed. Simulations run for 3600 s. Configurations tested range from the two-moment baseline (2m) through progressively more complete three-moment schemes (3m-sed; 3m-sed+evap; 3m-full with RSCB lookup tables) against the SBM benchmark and SBM-Γ (SBM constrained to gamma DSD, isolating the effect of the gamma assumption itself). RSCB lookup tables are created from 33-bin SBM one-step simulations initialized with three-parameter gamma DSDs spanning all relevant ($\mu$, $\lambda$) combinations. Bulk RSCB rates are stored as functions of ($\mu$, $D_n$).

## Key Results

- Sedimentation and evaporation are the dominant processes shaping the DSD in most regimes; RSCB becomes dominant for heavy rain (rate ≳ 5 mm/h)
- The new RSCB lookup table parameterization reduces mean drop sizes substantially compared to the default (no RSCB), primarily through reducing the rain drop number
- Applying the new RSCB only to the two-moment scheme yields modest improvement: mean drop sizes improve but diagnosed $\mu$ still yields discrepancies in rain rates
- The full three-moment + RSCB scheme (3m-full) brings P3 into agreement with SBM in >95% of rainshaft cases, compared to 4% for two-moment P3
- Remaining differences between 3m-full and SBM are attributable to: (1) P3's assumption of constant MVD during evaporation (overestimates mean sizes in light rain); (2) the gamma DSD assumption itself (confirmed by discrepancies between 3m-full and SBM-Γ in light rain)

## Limitations and Caveats

- Testing limited to 1D rain shaft; 3D real-case impacts were not evaluated in this paper (though noted as ongoing work)
- The gamma DSD assumption introduces biases for light rain that cannot be corrected within the bulk framework
- Evaporation treatment (constant MVD assumption) identified as a remaining source of bias
- RSCB lookup tables based on SBM physics which itself has uncertainties in breakup kernels
- Autoconversion and rain initiation were not addressed

## Relation to Author's Research Program

Milbrandt is the fifth of seven authors. His primary contribution was providing the P3 scheme infrastructure within which the three-moment rain development was implemented and tested. The paper directly extends the P3 scheme (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016), which is the foundation of Milbrandt's most recent microphysics development work. The three-moment rain capability developed here is a component of the broader P3 development trajectory toward a full three-moment scheme for the E3SM and GEM models. This paper is relevant to Milbrandt's program as evidence of the P3 scheme's extensibility and ongoing development by the broader community.

## Impact and Citations

**Citation count:** ~38 (Semantic Scholar, retrieved 2026-06-06)

This paper has garnered moderate citations (~38) reflecting its focused contribution to an active subfield. It is cited in subsequent three-moment scheme development work, P3-related studies, and papers addressing rain DSD parameterization more broadly. The proof-of-concept result — showing >95% agreement with SBM using the full three-moment scheme — is a strong quantitative benchmark that has influenced subsequent bulk rain microphysics development.

## Related topics
- [[scheme-intercomparisons]]
