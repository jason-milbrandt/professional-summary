# Combining Triple-Moment Ice With Prognostic Liquid Fraction in the P3 Microphysics Scheme: Impacts on a Simulated Squall Line

**Citation:** Cholette, M., J. A. Milbrandt, H. Morrison, D. Paquin-Ricard, and D. Jacques, 2023: Combining triple-moment ice with prognostic liquid fraction in the P3 microphysics scheme: Impacts on a simulated squall line. *J. Adv. Model. Earth Syst.*, **15**, e2022MS003328. DOI: 10.1029/2022MS003328

---

## Abstract

The Predicted Particle Properties (P3) bulk microphysics scheme has been recently modified to combine two major innovations. The triple-moment approach to represent ice, allowing for a freely evolving spectral dispersion of the size distribution, is combined with the predicted liquid fraction, which enables an explicit representation of mixed-phase particles. The impacts of this combination are examined in the context of high-resolution (1-km horizontal grid spacing) simulations of an observed mid-latitude squall line using the Global Environmental Multiscale atmospheric model. The simulation of mixed-phase particles results in a faster squall line propagation speed and stronger cold pool due to greater cooling from sublimation, melting, and evaporation. There is a reduction in the mass of ice reaching the surface resulting from a decrease in the mean size of melting ice particles aloft with the predicted liquid fraction. Compared to the original double-moment configuration, triple-moment P3 results in larger mean ice sizes at the surface. The reflectivity structure is improved with the new version, now with a more pronounced bright band in the melting zone with the predicted liquid fraction.

---

## 1. Introduction

P3 has evolved considerably since its introduction in Morrison and Milbrandt (2015). Two major independent developments:
1. **Predicted liquid fraction** (Cholette et al. 2019 = C19): adds $q_{i,\mathrm{liq}}$ to represent mixed-phase particles
2. **Triple-moment ice** (Milbrandt et al. 2021 = M21): adds $Z_{i,\mathrm{tot}}$ (6th moment) so spectral shape parameter $\mu$ evolves freely

This paper combines both innovations for the first time and tests the combined version in a real-case squall-line simulation.

The bright band (enhanced radar reflectivity in the melting layer) arises from the change in scattering properties of mixed-phase particles; bulk schemes without predicted liquid fraction cannot capture it directly.

P3 is used operationally in ECCC's HRDPS (2.5-km) and is publicly available in WRF.

---

## 2. The Modified P3 Scheme

### 2.1 Prognostic Variables

Each ice category now has up to **6 prognostic variables**: $q_{i,\mathrm{tot}}$, $N_{i,\mathrm{tot}}$, $q_{i,\mathrm{liq}}$ (optional, from C19), $q_{i,\mathrm{rim}}$, $B_{i,\mathrm{rim}}$, $Z_{i,\mathrm{tot}}$ (optional, from M21). Setting the optional variables enables either or both of the new configurations.

### 2.2 Combining Triple-Moment Ice With Predicted Liquid Fraction

When $q_{i,\mathrm{liq}}$ is predicted, processes acting on the whole mixed-phase particle (collection, wet growth, collision-aggregation, refreezing, shedding, vapor condensation/evaporation) use $q_{i,\mathrm{tot}}$, $N_{i,\mathrm{tot}}$, and $Z_{i,\mathrm{tot}}$ to obtain size distribution parameters. Processes acting on the ice core only (sublimation/deposition and melting) use a modified ice-core distribution. Closure assumption for $\mu$ during mixed-phase processes: $\mu$ is constant during the time step (simplified; refinements deferred to future work).

### 2.3 Reflectivity Calculation

Updated equivalent reflectivity for mixed-phase particles ($0 < F_{i,\mathrm{liq}} < 1$) based on the WRF approach but with P3's predicted (rather than diagnosed) liquid fraction. Accounts for the change in dielectric properties of the liquid shell surrounding the ice core.

---

## 3. Model Configuration and Analysis

Five GEM simulations of a mid-latitude squall line (18 August 2019, Iowa, USA):
- **3MOM_LF_2.5KM**: operational HRDPS configuration at 2.5 km, 3-moment + liquid fraction; provides IC/LBCs for 1-km runs
- **2MOM_noLF**: 1 km, baseline 2-moment, no liquid fraction
- **3MOM_noLF**: 1 km, 3-moment, no liquid fraction
- **2MOM_LF**: 1 km, 2-moment + liquid fraction
- **3MOM_LF**: 1 km, 3-moment + liquid fraction

1-km runs: 9-hour simulation (03–12 UTC), no deep convection parameterization, nested in the 2.5-km run. Analysis: reflectivity vs. BALTRAD/KARX/KDVN radars; precipitation vs. StageIV/MRMS; cold pool analysis over Iowa subdomain.

---

## 4. The Squall Line Case

The squall line developed a trailing stratiform structure. At the mature stage (08–10 UTC), the convective line was ~630 km long, oriented W-E across Iowa. Well reproduced by 3MOM_LF_2.5KM in terms of timing and location; reflectivity slightly overestimated at 1 km in the convective and stratiform regions.

---

## 5. Analysis of the 1-km Simulations

### 5.1 Temperature and Precipitation

- LF simulations are colder by ~1–1.5°C below 4 km in convective regions; 2MOM_noLF is relatively warmer
- LF squall lines propagate ~1–1.5 m s$^{-1}$ faster than noLF for both 2MOM and 3MOM; 3MOM is ~0.5 m s$^{-1}$ faster than 2MOM for both LF and noLF
- LF produces more total precipitation accumulation in southern Iowa because the faster-moving squall line reaches farther south
- **Ice accumulation at surface**: 3MOM > 2MOM (both LF and noLF); but LF < noLF for both 2MOM and 3MOM — LF reduces ice accumulation because particles have smaller mean mass-weighted diameter during melting
- Between 3 and 4 km (peak melting region): in LF, mean mass-weighted fall speed increases and mean diameter decreases; in noLF, both are nearly constant

### 5.2 Reflectivity and Cold Pool

- **Bright band**: Only visible in LF simulations; 3MOM_LF has lower bright-band reflectivity than 2MOM_LF (consistent with smaller ice aloft in 3MOM), agreeing better with observations
- **Cold pool speed**: 3MOM_LF fastest (~66 km h$^{-1}$), 2MOM_noLF slowest (~60 km h$^{-1}$); LF is 1–1.5 m s$^{-1}$ faster than noLF
- **Cold pool temperature**: LF simulations are colder by 0.2–0.9°C in mean potential temperature perturbation
- **Cooling processes**: In noLF, two distinct peaks (sublimation ~4 km; melting ~3 km). In LF, smoother single peak (~3.5 km) from combination of sublimation + melting + mixed-phase evaporation; mixed-phase evaporation contributes 5–15% of total cooling in the melting region
- Sensitivity tests: allowing ice sublimation/deposition above 0°C in noLF moves results toward LF; removing mixed-phase evaporation from LF has little impact by itself

### Key quantitative results:
- Propagation speed: 60–66 km h$^{-1}$ (2MOM_noLF to 3MOM_LF); LF adds ~1–1.5 m s$^{-1}$ over noLF
- Cold pool speed $C$: 0.5–2 m s$^{-1}$ higher in 3MOM_LF vs. others
- Mean precipitation accumulation: 8.62, 8.85, 8.86, 8.99, 9.39 mm for 2MOM_noLF, 3MOM_noLF, 2MOM_LF, 3MOM_LF, 3MOM_LF_2.5KM respectively

---

## 6. Conclusions

- The combined 3MOM+LF version of P3 is now the operational P3 configuration in HRDPS
- Predicted liquid fraction: stronger cold pools, faster squall lines, reduced ice surface accumulation, explicit bright band in reflectivity
- Triple-moment ice: larger mean ice sizes at surface, smaller ice aloft in stratiform region, less ice and rain reflectivity (closer to observations) than 2MOM
- Reflectivity calculation updated to account for mixed-phase particle scattering
- Computationally competitive: P3 is well-suited to "scaled flux vector transport" advection method, limiting additional cost of extra prognostic variables

---

## Appendices

- **Appendix A**: Full symbol table
- **Appendix B**: Complete description of baseline P3 configuration and evolution history (versions 1–5)
- **Appendix C**: Reflectivity calculation for P3, including mixed-phase update
