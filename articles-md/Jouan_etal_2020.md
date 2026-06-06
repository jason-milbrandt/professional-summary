# Jouan et al. (2020)

**Full citation:** Jouan, C., J. A. Milbrandt, P. A. Vaillancourt, F. Chosson, and H. Morrison, 2020: Adaptation of the Predicted Particle Properties (P3) microphysics scheme for large-scale numerical weather prediction. *Wea. Forecasting*, **35**, 2541–2565. DOI: 10.1175/WAF-D-20-0111.1

---

## Abstract

A parameterization for the subgrid-scale cloud and precipitation fractions (SCPF) has been incorporated into the P3 microphysics scheme for use in atmospheric models with relatively coarse horizontal resolution. The modified scheme was tested in a simple 1D kinematic model and in GEM using a 25-km global NWP configuration. A series of 5-day forecast simulations was run using P3 and the operational Sundqvist condensation scheme as benchmark. Even without recalibration, P3 with SCPF showed significant improvements in temperature and geopotential height bias throughout the troposphere out to day 5, but with degradation in error standard deviation toward the end. Sensitivity tests on convective detrainment showed further improvements when using a prescribed volume-mean ice radius of 60 µm. Results show that modified P3 holds promise for use in coarse-resolution NWP systems.

---

## 1. Introduction

Cloud and precipitation parameterizations in NWP models must be adapted across a wide range of grid spacings. At MSC (ECCC), P3 was implemented in HRDPS (2.5 km) in late 2018 (Morrison and Milbrandt 2015; Milbrandt et al. 2016). All other MSC NWP systems (RDPS ~10 km, GDPS ~25 km, ensemble, seasonal) use the Sundqvist condensation scheme. Known issues with Sundqvist in GEM include:
- Systematic upwind displacement of precipitation.
- Underprediction of IWC aloft.
- Fixed effective ice crystal radius of 15 µm for radiation.

This paper documents modifications to P3 for use in the 25-km GEM GDPS configuration and examines forecast performance.

**Terminology clarification:** A gridscale condensation scheme consists of (1) subgrid cloud fraction (SCF/macrophysics), (2) microphysics scheme, and (3) precipitation scheme. These must all be considered together.

---

## 2. Description of the Modified P3 Scheme

### 2a. Overview of P3

The P3 scheme (Morrison and Milbrandt 2015) uses one freely evolving ice-phase category with four prognostic variables: total ice mass $q_{i,tot}$, rime mass $q_{i,rim}$, total ice number $N_{i,tot}$, and bulk rime volume $B_{i,rim}$. The PSD is described by a complete gamma function; particle properties evolve continuously.

### 2b. SCPF Component

The SCPF approach of Chosson et al. (2014) is applied to P3. A fixed-width top-hat PDF of total water mixing ratio $q_t \pm \Delta q$ is used to diagnose cloud fraction $a$ and mean in-cloud/clear-sky values:

$$a = \frac{q_t + \Delta q - q_{sat}}{2\Delta q}, \quad 0 \le a \le 1$$

$$q_y^{cld} = \frac{q_t + \Delta q + q_{sat}}{2} - \frac{q_{cond}}{a}$$

$$q_y^{clr} = \frac{q_t - \Delta q + q_{sat}}{2}$$

The PDF width is linked to the critical relative humidity threshold $RH_{cr}$ (same profile as Sundqvist in GEM):

$$\Delta q = q_{sat}(1 - RH_{cr})$$

**Implementation:** Cloud droplets and ice particles are uniformly distributed within the cloud fraction $a$; rain is distributed within the precipitation fraction (set equal to $a$ in this work to avoid exacerbating already-positive precipitation biases). Maximum-random overlap assumption is used.

Sub-stepping (microphysics called multiple times per main time step, max 60 s per sub-step) is also implemented per Chosson et al. (2014).

### 2c. Coupling with Deep Convection

The Kain–Fritsch deep convection scheme in GEM detrains condensate mass to P3. Since P3 is two-moment, assumptions about number mixing ratios are required:
- Liquid: prescribed CCN concentration (80 cm⁻³) or, if cloud water already present, existing mean droplet size.
- Ice: temperature-dependent nucleation (Cooper 1986), or if ice already present, existing mean size. Detrained ice is assumed to be frozen drops: $q_{i,rim} = q_{i,tot}$, $B_{i,rim}$ set to give bulk density of 917 kg m⁻³.

The sensitivity to volume-mean ice radius $r_{m,i}$ prescribed for detrainment was explored through three additional experiments: P3_SCPF_Rmi20, P3_SCPF_Rmi40, P3_SCPF_Rmi60 (20, 40, 60 µm).

---

## 3. Data and Methodology

### 3a. GEM Configuration

- 25-km horizontal grid spacing (4×417 grid points), 84 staggered vertical levels.
- Time step: Dt = 720 s; SCPF sub-stepped at max 60 s.
- Shallow convection: Bechtold scheme; Deep convection: Kain–Fritsch.
- Radiation: Li–Barker correlated-k distribution (called every 1 h).
- Yin-yang global grid.

### 3b. Verification

**Upper-air skill scores:** Bias and standard deviation of temperature, dewpoint depression, geopotential height, and wind against 80 reference radiosonde cases (40 winter, 40 summer), 5-day integrations, evaluated at 24-h intervals.

**Precipitation:** Frequency bias index (FBI) of 24-h accumulated precipitation over North America, compared to CaPA analysis.

**Tendency diagnostic:** Temperature and moisture tendencies from all physics parameterizations, averaged in time and space globally. State variable profiles (CWC, IWC, CF) as seen by radiation scheme. TOA/SFC radiative fluxes and planetary albedo (PA).

---

## 4. Impacts of Using P3 (and SCPF) in a Global Model

### 4a. Effects on Clouds

- P3 (without SCPF): Significant overestimation of cirrus anvil cover in convective areas of tropics; IWC excessive at mid-upper troposphere; cold bias below 500 hPa, warm bias above.
- P3+SCPF: Reduced CF (lower PA from 0.387 in P3 to 0.306, closer to observed 30–33%); warm bias over most of column at lower levels similar or better than SUND; deterioration at mid-upper levels (warm bias accentuated vs. P3).
- P3+SCPF produces considerably more surface precipitation than P3 and SUND (a known issue with SCPF component).

### 4b. Key Scores

| Configuration | Temperature bias direction | Geopotential | Precipitation |
|---|---|---|---|
| P3 | Cold below 500 hPa, warm above | Deteriorated in tropics | Slightly improved low thresholds |
| P3_SCPF | Warm bias overall, reduced below 500 hPa | Some improvement except tropics | Much higher |
| P3_SCPF_Rmi60 | Dramatically improved bias at 24 h | Clear improvement | Still excessive |

### 4c. Model Tendencies and Radiation

- P3 and P3_SCPF produce higher IWC than SUND at mid-upper levels (consistent with SUND underpredicting IWC — shown by Chosson et al. 2014).
- P3_SCPF reduces CWC compared to P3 (higher precipitation efficiency).
- SCPF component reduces CF, rebalancing PA toward reality.
- P3 (all configs): excessive warming from shortwave/longwave absorption by optically thick cirrus layers in tropics.

---

## 5. Sensitivity to Detrained Anvil Cirrus Properties

### 5a. Motivation

Simulation results are sensitive to assumptions about number mixing ratios of detrained ice. Observations suggest: ice number concentration in cirrus ~5–500 L⁻¹; $r_{m,i}$ ≈ 30–60 µm in anvil cirrus (Frey et al. 2011; Jensen et al. 2009).

### 5b. Results

- Increasing $r_{m,i}$ (fewer, larger detrained ice particles) reduces IWC at mid-upper levels (less ice nucleated from same mass) and lowers CF.
- P3_SCPF_Rmi60: dramatic improvement in T and Z_g biases at 24 h compared to P3_SCPF; also clearest improvement compared to SUND at 24 h (some degradation in Z_g standard deviation at upper levels).
- Anvil cirrus coverage in tropics moves closer to observed with Rmi60.
- PA: 0.288 with Rmi60, slightly below observed range but much improved over P3 (0.387).
- By day 5: mixed improvements/degradations; precipitation still excessive.

---

## 6. Summary and Discussion

Modified P3 for large-scale NWP includes: (1) SCPF parameterization (Chosson et al. 2014 approach applied to P3), (2) microphysical sub-stepping at max 60 s, (3) modified convective detrainment interface.

Key results (5-day forecasts vs. SUND control):
- P3 without SCPF: degraded (expected — designed for kilometric scale, no calibration).
- P3+SCPF: improved T bias at lower levels; degraded Z_g and upper-level T; PA closer to reality.
- P3_SCPF_Rmi60: dramatic improvement in T and Z_g biases at 24 h; encouraging for eventual operational use.
- Remaining issues: excessive precipitation; upper-level degradations toward day 5; physics not yet recalibrated.

The full recalibration of the physics suite (moist schemes + radiation) for P3 use in large-scale models remains a necessary future step. Despite the lack of calibration, results are encouraging enough to justify further development.

---

## References (selected)

- Chosson, F., P. A. Vaillancourt, J. A. Milbrandt, M. K. Yau, and A. Zadra, 2014: Adapting two-moment microphysics schemes across model resolutions. *J. Atmos. Sci.*, **71**, 2635–2653.
- McTaggart-Cowan, R., and Coauthors, 2019: Modernization of atmospheric physics parameterization in Canadian NWP. *J. Adv. Model. Earth Syst.*, **11**, 3593–3635.
- Milbrandt, J. A., and Coauthors, 2016: The pan-Canadian High Resolution (2.5 km) Deterministic Prediction System. *Wea. Forecasting*, **31**, 1791–1816.
- Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.

[Figure captions not reproduced — see original paper for Figs. 1–20 and Tables 1–4]
