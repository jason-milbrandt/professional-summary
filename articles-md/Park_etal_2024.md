# Park et al. (2024)

**Full citation:** Park, S.-Y., K.-S. S. Lim, K. Kim, G. Lee, and J. A. Milbrandt, 2024: Introducing graupel density prediction in Weather Research and Forecasting (WRF) double-moment 6-class (WDM6) microphysics and evaluation of the modified scheme during the ICE-POP field campaign. *Geosci. Model Dev.*, **17**, 7199–7218. DOI: 10.5194/gmd-17-7199-2024

---

## Abstract

The WRF double-moment 6-class (WDM6) scheme was modified by incorporating predicted graupel density. Predicted graupel density modifies the fall velocity–diameter ($V_G$–$D$) and mass–diameter ($M_G$–$D$) relationships of graupel. The modified WDM6 was evaluated in a 2D idealized squall line and ICE-POP 2018 winter snowfall events over the Korean Peninsula. From the squall line simulation, varying graupel densities from low (anvil) to high (convective core) were reproduced. In the snowfall simulations, modified WDM6 increased graupel amounts at the surface and decreased graupel aloft (faster sedimentation). The modified scheme mitigates the surface precipitation bias in the original WDM6 over the mountainous region, improving RMSE scores. The modified WDM6 reasonably captures the observed $\rho_G$–$V_G$ relationship from 2DVD measurements, emphasizing the necessity of predicted graupel density for realistic representation of graupel microphysics.

---

## 1. Introduction

Ice-phase particle parameterization in bulk microphysics schemes traditionally uses predefined categories with fixed density parameters. Several studies have shown simulation results are sensitive to the categorization approach (Morrison and Milbrandt 2011; Bryan and Morrison 2012). Key prior work on predicted graupel density:
- Morrison and Grabowski (2008): predicted rime mass fraction and particle dimension.
- Mansell et al. (2010) and Milbrandt and Morrison (2013, MM13): predicted graupel density via prognostic volume mixing ratio.
- Morrison and Milbrandt (2015): P3 scheme predicts rime mass fraction and density for a single generic ice category.
- Jensen et al. (2023): predicted density graupel in Thompson–Eidhammer scheme.

WDM6 (Lim and Hong 2010) uses a fixed graupel density of 500 kg m⁻³. Studies show WDM6 produces excess graupel; Li et al. (2019) showed simulated precipitation is sensitive to graupel density in WDM6.

This study introduces a new prognostic variable (graupel volume mixing ratio $B_G$) to predict $\rho_G$ in WDM6, following MM13.

---

## 2. New Prediction Variable: Graupel Density in WDM6

### Conservation Equation for $B_G$

$$\frac{\partial B_G}{\partial t} = -\mathbf{V} \cdot \nabla B_G - \frac{1}{\rho_a}\frac{\partial}{\partial z}(\rho_a B_G V_{BG}) + S_{BG}$$

where $S_{BG}$ contains source/sink terms proportional to mass mixing ratio and density of specific hydrometeors.

The predicted density:

$$\rho_G = \frac{q_G}{B_G}$$

### Updated $M_G$–$D$ and $V_G$–$D$ Relationships

$M_G(D) = c_G D^{d_G}$ where $c_G = \frac{\pi}{6}\rho_G$ (sphere) varies with predicted $\rho_G$.

Fall velocity–diameter relationship derived from the Reynolds number–Best number approach (Mitchell 1996; Khvorostyanov and Curry 2002):

$$V_G = a_G D^{b_G}$$

where $a_G$ and $b_G$ are derived at the predicted $\rho_G$ at intervals of 100 kg m⁻³ (100–900 kg m⁻³) using least-squares fitting in log-log space over $D_G = 0.3$–20 mm.

**Fitted parameters** (Table 2 in paper): for $\rho_G = 100$ kg m⁻³, $a_G = 54.92$ m$^{1-b}$s⁻¹, $b_G = 0.545$; for $\rho_G = 500$ kg m⁻³, $a_G = 111.7$, $b_G = 0.530$; for $\rho_G = 900$ kg m⁻³, $a_G = 146.0$, $b_G = 0.526$.

Original WDM6 uses fixed $a_G = 330$ m$^{1-b}$s⁻¹, $b_G = 0.8$ — substantially different.

Affected processes: $P_{gmlt}$, $P_{gacw}$, $P_{gdep}$, $P_{gevp}$ (through $V_G$–$D$); also $P_{gmlt}$, $P_{gaci}$, $P_{gacr}$, $P_{gdep}$, $P_{gevp}$, $P_{gacw}$, $N_{gaci}$, $N_{gacr}$, $N_{geml}$, $N_{gacw}$ (through $M_G$–$D$).

The modified WDM6 extends an existing scheme that incorporates prognostic cloud ice number concentration (Park and Lim 2023). Computational overhead: 4.3% more CPU time than original WDM6.

---

## 3. Experimental Setup

### 3a. 2D Idealized Squall Line

Follows Lim and Hong (2010) design. 601 grid points at 1-km spacing, 80 vertical layers. Warm bubble (4-km radius, +3 K at center), 12 m s⁻¹ base-state wind to 2.5 km then 0. No Coriolis or friction. Integration: 6 h, dt = 5 s.

Two experiments: WDM6_FD (fixed density, original) and WDM6_PD (predicted density).

### 3b. ICE-POP 2018 Snowfall Cases

Eight snowfall events from ICE-POP 2018, classified as cold low (CL), warm low (WL), or air–sea interaction. Two representative cases selected: Case 1 (CL, 24 Nov–26 Nov 2017) and Case 2 (WL, 23–24 Dec 2017). All 8 cases used for statistical evaluation.

**WRF version 4.1.3**, three nested domains (9, 3, 1 km). ERA-Interim initial/LBCs. Physics: Kain–Fritsch convection (9-km domain only), revised MM5 surface layer, RRTMG radiation, YSU PBL, Noah-MP land surface.

Verification: AWS precipitation (604 stations), 2DVD and MASC measurements at MHS supersite (MayHills, 289 m MSL) to compare simulated vs. observed $\rho_G$–$V_G$ relationship.

---

## 4. Results

### 4a. 2D Idealized Squall Line

Both WDM6_FD and WDM6_PD reproduce typical squall line structure (strong convective core, trailing stratiform). WDM6_PD shows stronger maximum reflectivity in both regions.

Vertical profiles of mass mixing ratios: WDM6_PD shows significant decrease in graupel throughout all layers and increase in snow (especially above 3 km). Total graupel+snow: lower below 7 km, higher above 7 km in WDM6_PD.

Graupel density in WDM6_PD: lower-density graupel (~550–800 kg m⁻³) in updraft core at developing stage; lower-density graupel transported to anvil at 4 h. WDM6_FD produces more abundant graupel reaching higher vertical levels.

Key mechanism: faster sedimentation of lower-density graupel in WDM6_PD → inefficient graupel deposition → surplus water vapor → more efficient snow deposition → higher snow mass mixing ratio.

### 4b. ICE-POP 2018 Snowfall Cases

**Precipitation distributions:**
- CL case: WDM6_PD reduces surface snow (93% reduction in domain-averaged snow, from 0.80 to 0.75 mm) and increases surface graupel (124%, from 0.51 to 0.64 mm). Better spatial distribution; RMSE improved for both CL cases.
- WL case: WDM6_PD reduces surface snow significantly (92% domain-averaged) and increases surface graupel slightly. RMSE improved for all WL cases; bias improved except Case 5.

**Statistical skill scores (Table 4):** WDM6_PD improves RMSE for 7 of 8 cases. ETS scores are similar between WDM6_FD and WDM6_PD.

**Mechanisms (WL case):** Faster graupel sedimentation → more Pgdep at higher levels → less water vapor available → reduced Psdep at corresponding levels → less snow in atmosphere and at surface.

### 4c. Observed vs. Simulated $\rho_G$–$V_G$ Relationship (Case 6, WL)

2DVD observations: $\rho_G$ ranges 43.6–1267 kg m⁻³; peak frequency at 300–400 kg m⁻³; frequent counts between 100–400 kg m⁻³.

WDM6_FD: single value $\rho_G = 500$ kg m⁻³; much narrower range of $V_G$.

WDM6_PD: $\rho_G$ range 100–900 kg m⁻³; majority at lower values (~150 kg m⁻³); captures the wide observed range. Fall velocities in WDM6_PD are slightly larger than observed but much more realistic than WDM6_FD.

---

## 5. Summary and Conclusion

A prognostic graupel density was introduced into WDM6 by adding $B_G$ as a new variable, following the MM13 approach. Key findings:

1. Squall line: modified WDM6 can simulate varying graupel densities (low in anvil, high in convective core). Lower-density graupel falls faster via the new $V_G$–$D$ relationship, leading to more efficient sedimentation and more snow in the atmosphere.

2. ICE-POP 2018 snowfall: original WDM6 has positive surface precipitation bias. Modified WDM6 reduces surface snow and increases surface graupel (via faster sedimentation), mitigating the bias and improving RMSE scores for most cases.

3. $\rho_G$–$V_G$ validation: modified WDM6 captures the observed relationship better than original WDM6, though simulated lower-density range is underestimated and fall velocities are slightly overestimated.

**Limitations:** Simulated $\rho_G$ still mostly below observed median (150 vs. 300–400 kg m⁻³); $V_G$–$D$ relationship could be refined with broader observational data including diverse graupel habits.

---

## References (selected)

- Lim, K.-S. S., and S.-Y. Hong, 2010: Development of an effective double-moment cloud microphysics scheme with prognostic cloud condensation nuclei (CCN) for weather and climate models. *Mon. Wea. Rev.*, **138**, 1587–1612.
- Milbrandt, J. A., and H. Morrison, 2013: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II: Case study comparisons with a multimoment scheme. *J. Atmos. Sci.*, **70**, 365–376.
- Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Park, S.-Y., and K.-S. S. Lim, 2023: Modified WDM6 with prognostic cloud ice number concentration. *J. Geophys. Res. Atmos.*

[Figure captions not reproduced — see original paper for Figs. 1–12, Tables 1–4, and Appendix]
