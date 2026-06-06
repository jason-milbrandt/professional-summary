# Secondary Ice Production Improves Simulations of Freezing Rain

**Citation:** Cholette, M., J. A. Milbrandt, H. Morrison, S. Kirk, and L.-É. Lalonde, 2024: Secondary ice production improves simulations of freezing rain. *Geophys. Res. Lett.*, **51**, e2024GL108490. DOI: 10.1029/2024GL108490

---

## Abstract

Weather forecasts and climate projections of precipitation phase and type in winter storms are challenging due to the complicated underlying microphysical and dynamical processes. In the Canadian numerical weather prediction model, explicit freezing rain (FR) at the surface is often overestimated during the winter season for situations in which snow is observed. For a case study simulated using this model with the Predicted Particle Properties (P3) microphysics scheme, the secondary ice production (SIP) process has a major impact on the surface precipitation type. Parameterized SIP substantially reduces FR due to increased collection of supercooled drops with ice particles formed by rime splintering. Hindcast simulations of 40 winter cases show that these results are systematic, and the decreased frequency of FR leads to improved forecast skill relative to observations. Thus, accounting for SIP in the model is critical for accurately simulating precipitation types.

---

## 1. Introduction

Winter precipitation types (snow, wet snow, ice pellets, FR) are hazardous (icing injuries, grid disruption, transport breakdown) and challenging to predict. HRDPS uses P3 (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016), with the liquid fraction of mixed-phase particles (Cholette et al. 2019, 2023). Despite prior improvements (Barszcz et al. 2018; Cholette et al. 2019, 2020), a systematic FR overestimation persists in HRDPS in snow situations.

Secondary ice production (SIP) — generation of ice particles in excess of primary INPs at temperatures above homogeneous freezing — has received growing attention. The Hallett-Mossop (HM) rime splintering process (Hallett and Mossop 1974) is the best-quantified SIP mechanism: ice splinters (diameter ~10 μm) produced at −3°C to −8°C from accretion of large rain drops onto large, rimed ice particles. Prior SIP studies focused on convection or orographic clouds; no studies had examined SIP impacts on FR specifically.

---

## 2. Methods

### 2.1 Simulations

GEM model in HRDPS configuration: ~2.5-km horizontal grid spacing, 62 vertical levels, 60-s time step, 48-hr forecasts. P3 version: 5 ice-phase prognostic variables per category (total ice mass, rime mass, number, rime volume, liquid mass), i.e., the liquid-fraction-enabled version of Cholette et al. (2019, 2023).

Four configurations (2×2 factorial: {nCat=1, nCat=2} × {HM off, HM on}):
- **nCat1_noHM**: baseline (operational), 1 ice category, no HM
- **nCat1_HM**: 1 ice category, HM on
- **nCat2_noHM**: 2 ice categories, no HM
- **nCat2_HM**: 2 ice categories, HM on (best configuration)

Using 2 categories avoids dilution of particle properties when SIP-generated small ice particles coexist with large pre-existing ice in the same grid volume.

Precipitation-type partitioning in simulations:
- Rain vs. freezing rain: based on temperature at lowest model level ($T_{k,\mathrm{bot}}$)
- Ice pellets: bulk rime mass fraction > 0.5 and rime density > 750 kg m$^{-3}$; otherwise snow

Reference: Bourgouin (2000) diagnostic applied to nCat1_noHM thermodynamic profiles (nCat1_noHM_Bourgouin) for comparison.

### 2.2 Analysis

**Case study**: 27 February 2020 winter storm over eastern Canada/Maritime provinces.

**Hindcast set**: 40 winter cases, January–February 2020. Forecast skill scores: frequency bias index (FBI), equitable threat score (ETS), probability of detection (POD), false alarm ratio (FAR). Focus on FR skill scores; rain and snow scores similar among configurations.

---

## 3. Results

### 3.1 The 27 February 2020 Case

Synoptic situation: surface low (~975 hPa) near Virginia/Kentucky border, aligned with 500-hPa low; 0°C isotherm across central New Brunswick and Nova Scotia; slow-moving system producing mixed precipitation over Maritime provinces.

**Baseline (nCat1_noHM)**: Overestimates FR in northern regions (e.g., YJT) where the temperature profile is entirely below 0°C (no melting layer) — only snow was observed. The FR originates from liquid-phase processes: autoconversion of cloud droplets to rain followed by accretion; without ice to intercept these drops, supercooled rain falls as FR.

**Effect of HM**: For both nCat=1 and nCat=2, adding HM reduces FR and increases snow and IP:
- Reduction in FR accumulation: **65%** (nCat1_HM) and **98%** (nCat2_HM) relative to noHM
- Increase in IP accumulation: 95% (nCat1_HM) and 120% (nCat2_HM)

**Mechanism** (from cross-section analysis, 33-hr forecast time, in region 200–350 km):
- HM produces small ice splinters → ice number and mass increase
- Enhanced deposition (+465% to +1,340%) depletes water vapor for cloud condensation
- Reductions in liquid-phase processes: cloud condensation (−22% to −58%), autoconversion (−46% to −82%), cloud accretion by rain (−55% to −76%), rain condensation (−58% to −73%), rain evaporation (−44% to −95%)
- Greater ice mass and number → increased riming (+100% to +135% on average)
- Together: much less cloud water and rain → less supercooled rain reaching the surface as FR

nCat2_HM is generally closest to METAR precipitation type observations.

Sensitivity test (nCat1_HM with autoconversion off): FR substantially reduced, confirming autoconversion is the main driver of the liquid pathway generating excessive FR.

### 3.2 Forecast Skill Scores (40 Cases)

FBI for FR:
- nCat1_noHM: significantly overestimates FR (FBI >> 1)
- nCat1_HM: reduced FBI, closer to 1
- nCat2_HM: FBI closest to 1, slightly better than Bourgouin diagnostic at both 0.1-mm and 0.5-mm thresholds

ETS for FR:
- Differences among simulations up to 11–17%; nCat2_HM and nCat1_HM generally best
- nCat2_HM gives comparable or slightly better ETS than Bourgouin

POD and FAR: both reduced with nCat2_HM; similar to Bourgouin. Reduction in POD suggests slightly too aggressive a reduction of small FR amounts (identified as topic for future work).

Rain and snow skill scores: similar among all runs, no degradation.

---

## 4. Conclusions

- Hallett-Mossop rime splintering (SIP) critically impacts precipitation phase in winter storms in Canada
- Including HM in HRDPS/P3 systematically reduces excessive FR; FR accumulation reduced by 65–98% vs. no HM
- Best configuration: 2 ice categories + HM (nCat2_HM)
- nCat2_HM matches or slightly exceeds the FR skill of the highly tuned empirical Bourgouin diagnostic algorithm
- The mechanism: SIP → more ice → more deposition and riming → less cloud water and rain → less FR
- Other SIP mechanisms (collisional fragmentation, sublimation fragmentation, frozen drop breakup) likely have similar effects via the same pathway; to be explored in future work
- Results are relevant for climate projections of winter precipitation type

Caveats: Laboratory reproducibility of the original HM experiments has been questioned (Seidel et al. 2023); SIP parameterizations are uncertain; results demonstrate sensitivity and benefit, not that HM is the specific physical mechanism.
