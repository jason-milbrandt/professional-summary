# Chosson et al. (2014)

**Full citation:** Chosson, F., P. A. Vaillancourt, J. A. Milbrandt, M. K. Yau, and A. Zadra, 2014: Adapting two-moment microphysics schemes across model resolutions: Subgrid cloud and precipitation fraction and microphysical sub–time step. *J. Atmos. Sci.*, **71**, 2635–2653. DOI: 10.1175/JAS-D-13-0367.1

---

## Abstract

Two-moment multiclass microphysics schemes (BMSs) are very promising for use in high-resolution NWP models, but must be adapted for coarser resolutions. A twofold solution is proposed: (1) a simple representation of subgrid cloud and precipitation fraction (SCPF) and (2) a microphysical sub-time-stepping method. The scheme is easy to implement, allows supersaturation in ice clouds, and exhibits flexibility for adoption across model grid spacings. It is implemented in the Milbrandt and Yau (2005a,b) two-moment scheme (MY2) with prognostic precipitation and tested in a simple 1D kinematic model and in GEM (regional, 15-km grid spacing). Comparison with CALIPSO/CloudSat-derived cloud mask, cloud fraction, and ice water content shows that the proposed solutions significantly improve MY2's behavior at the regional NWP scale.

---

## 1. Introduction

Two-moment multi-hydrometeor class BMSs improve representation of microphysical processes and radiative transfer compared to simpler schemes. However, they are designed for cloud-scale (kilometric) horizontal grid spacings. At coarser scales:
- The cloud is a subgrid phenomenon, potentially leading to significant biases.
- Large time steps cause problems for prognostic sedimentation.

The Third International Workshop on Next-Generation NWP Models (Hong and Dudhia 2012) postulated that 2-moment BMSs are likely for use in next-generation NWP. Two challenges must be addressed: subgrid variability and large time steps.

**Scheme implemented in:** MY2 (Milbrandt and Yau 2005a,b) as modified in Milbrandt et al. (2010), with 6 hydrometeor categories: cloud droplets, rain, small ice (pristine), snow, graupel, hail. Tested in 1D kinematic model and GEM 15-km LAM.

---

## 2. The SCPF Scheme

### 2a. Subgrid Cloud Fraction

A fixed-width top-hat PDF $P(q_t)$ of total water mixing ratio represents subgrid variability, uniformly distributed around the grid-mean value $q_t \pm \Delta q$. The saturated region defines cloud fraction $a$ and mean in-cloud/clear-sky values:

$$a = \frac{q_t + \Delta q - q_s}{2\Delta q}, \quad 0 \le a \le 1$$

$$q_y^{cld} = \frac{q_t + \Delta q + q_s - 2q_c}{2} - \frac{q_c}{a}$$

$$q_y^{clr} = \frac{q_t - \Delta q + q_s}{2}$$

The PDF width is linked to a height-dependent critical relative humidity threshold $U_{00}$:

$$\Delta q = q_s(1 - U_{00}), \quad a = 1 - \sqrt{\frac{1-U}{1-U_{00}}}$$

The $U_{00}$ profile used in GEM's operational Sundqvist scheme is adopted. Snow (large ice particles) is included in cloud condensates, not precipitation condensates, because: (1) it can experience water vapor deposition; (2) it represents the major solid condensate.

### 2b. Subgrid Precipitation Fraction

Precipitation fraction $a_P = a_P^{cld} + a_P^{clr}$ is determined using maximum-random cloud overlap (Geleyn and Hollingsworth 1979). Precipitation falls within the fraction of the grid column overlapped by clouds above.

An alternate parameterization uses $P_{frac}$ — the fraction of the seeding cloud where precipitation is produced:

$$a_{P,k}^{cld} = a_{k-1} + \Delta a_P^{clr/cld} - \Delta a_P^{cld/clr}$$

Reducing $P_{frac}$ decreases grid-averaged evaporation and increases precipitation production (shown by sensitivity tests).

### 2c. Implementation in MY2

Local values within cloud fraction ($a$) and precipitation fraction ($a_P$):
- Cloud condensates ($x$ = ice, snow, cloud): $N_x^{local} = N_x/a$, $q_x^{local} = q_x/a$
- Precipitation condensates ($x$ = rain, graupel, hail): $N_x^{local} = N_x/a_P$, $q_x^{local} = q_x/a_P$

Grid-volume mean source/sink terms obtained by multiplying local terms by respective fractions. Example (collection of cloud droplets by graupel):

$$\frac{dq_g}{dt}\bigg|_{col} = f\left(\frac{N_c}{a}, \frac{N_g}{a_P}\right) \times a_P^{cld}$$

---

## 3. 1D Kinematic Model Tests

### 3a. Model Setup

Single-column model initialized with NARR sounding for a winter case near the central United States on 20 December 2008. 61 vertical levels at 245-m spacing; top at 15 km. Time step 10 s, duration 360 min. Prescribed weak large-scale updraft followed by downdraft.

### 3b. Results

Three schemes compared: MY2 (original, cloud fraction binary 0/1), MY2+SCPF, SUND (Sundqvist operational scheme).

- MY2+SCPF allows condensation before grid-mean saturation is achieved, producing earlier cloud formation and extended cloud lifetime vs. MY2.
- MY2+SCPF maintains supersaturation with respect to ice (physically realistic), whereas SUND limits saturation to ≤100%.
- Peak water paths increase with SCPF; surface precipitation comparable to SUND.
- Sensitivity to $P_{frac}$: lower values increase precipitation production (more precipitation confined within cloud fraction, enhanced collection).
- Strong forcing (2 m/s sinusoidal updraft): MY2 and MY2+SCPF yield similar results, confirming SCPF is not disruptive at kilometric resolution.

---

## 4. Microphysical Sub-Time Step

### 4a. The Problem

With large time steps (300–720 s in regional/global NWP), prognostic sedimentation in MY2 fails: at 120–480 s, no rain reaches the surface. SUND (diagnostic precipitation) is also sensitive to time step.

### 4b. Solution

Microphysical sub-stepping: call microphysics $n$ times per main time step with sub-step $dt$ ≈ 60 s. Tested in GEM LAM at 15-km, Dt = 450 s, Arctic domain, 31-day July 2008 series.

Results: MY2 with sub-stepping (Dt = 450 s, dt = 60 s) achieves nearly the same surface precipitation as MY2 with Dt = 60 s, at much lower computational cost (sub-stepping was 4.39× faster than the short-time-step equivalent).

---

## 5. Test of SCPF in GEM

### 5a. Case Study Setup

Winter event, 20 December 2008, GEM global LAM at 15-km grid spacing, Dt = 450 s. Three configurations: MY2, MY2+SCPF, SUND (control). Both MY2 runs use sub-stepping (dt = 60 s). DARDAR-Cloud (radar/lidar combined) products used for validation.

### 5b. Cloud Masks

All three simulations capture the general cloud distribution. SUND exhibits too much mixed-phase cloud at high altitudes due to ill-defined liquid-ice partition function. MY2 and MY2+SCPF produce realistic partition of cloud types and mixed-phase clouds. SCPF improves high-altitude ice cloud fraction (thin cirrus present in MY2+SCPF and SUND, absent in MY2).

### 5c. Ice Water Content

MY2 and MY2+SCPF produce much more realistic IWC than SUND; DARDAR IWC is considerably underestimated by SUND. SCPF scheme does not affect IWC significantly when grid-mean saturation is achieved.

### 5d. Mean Profiles

- Cloud fraction: MY2 without SCPF drops to 0 above ~12 km; MY2+SCPF maintains good agreement with DARDAR up to 14 km.
- IWC: Both MY2 configurations agree well with DARDAR; slight overestimate 7–12 km, underestimate below 7 km.
- In-cloud IWC: MY2+SCPF fits DARDAR well up to 5 km and above (where cloud fraction is maintained by SCPF).
- SUND total cloud condensate lower than DARDAR IWC retrievals.

---

## 6. Discussion

The SCPF and sub-time-step method together allow MY2 to be used across model resolutions. Key points:
1. SCPF preserves MY2's performance at kilometric resolution while considerably improving it at coarser scales.
2. The technique allows supersaturation in ice clouds, which is physically realistic and important for cirrus representation.
3. Minimal tuning parameters needed; the same $U_{00}$ profile as Sundqvist is used.
4. Sub-stepping achieves short-time-step accuracy at large-time-step cost.
5. SUND appears to have an ill-defined liquid-ice partition function that produces too much mixed-phase cloud and too-low solid condensate.

Future work: investigate scale dependence of $U_{00}$ and $P_{frac}$ parameters; extend to more cases and longer time periods; study cloud radiative properties.

---

## References (selected)

- Milbrandt, J. A., and M. K. Yau, 2005a,b: A multimoment bulk microphysics parameterization. Parts I and II. *J. Atmos. Sci.*, **62**, 3051–3064 and 3065–3081.
- Milbrandt, J. A., and Coauthors, 2010: [GEM modifications to MY2]. Referenced but not fully cited in text.
- Sundqvist, H., and Coauthors, 1989: Condensation and cloud parameterization studies with a mesoscale NWP model. *Mon. Wea. Rev.*, **117**, 1641–1657.
- Delanoe¨, J., and R. J. Hogan, 2008, 2010: DARDAR-Cloud products. *J. Geophys. Res.*

[Figure captions not reproduced — see original paper for Figs. 1–12 and appendices A–B]
