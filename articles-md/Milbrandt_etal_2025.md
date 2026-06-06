# Milbrandt et al. (2025): Impacts of Predicted Liquid Fraction and Multiple Ice-Phase Categories on the Simulation of Hail in the Predicted Particle Properties (P3) Microphysics Scheme

**Full citation:** Milbrandt, J. A., H. Morrison, and M. Cholette, 2025: Impacts of predicted liquid fraction and multiple ice-phase categories on the simulation of hail in the Predicted Particle Properties (P3) microphysics scheme. *J. Adv. Model. Earth Syst.*, **17**, e2024MS004404. DOI: 10.1029/2024MS004404

**Authors:** Jason A. Milbrandt (ECCC), Hugh Morrison (NSF NCAR), Mélissa Cholette (ECCC)

**Journal:** Journal of Advances in Modeling Earth Systems (JAMES)

**Volume/Article:** 17, e2024MS004404

**Published:** 2025 (accepted 27 Jan 2025; received 18 Apr 2024)

**DOI:** 10.1029/2024MS004404

**Open Access:** Yes (Creative Commons Attribution License)

---

## Abstract

Since its inception in 2015, the Predicted Particle Properties (P3) bulk microphysics scheme has undergone several major developments. Ice is now represented by a user-specified number of freely-evolving (non-prescribed) categories; the liquid fraction of particles is predicted, thereby allowing for mixed-phase particles and improved process rates; and the scheme is triple-moment, which allows the size spectral width to vary independently. As such, P3 is now capable of representing key properties and microphysical processes that are important for hail. In this study, the impacts of some new capabilities of P3 on the simulation of hail amounts and sizes are examined in the context of idealized, high-resolution (200-m isotropic grid spacing) hailstorm simulations using a cloud-resolving model. Sensitivity tests are conducted to examine the impacts of (a) the predicted liquid fraction, and (b) the number of generic ice-phase categories (varied between one and four). Predicted liquid fraction leads to a more realistic treatment of melting and shedding, which decreases the mean ice (hail) sizes during melting compared to the original P3 scheme. In contrast, with an increasing number of ice-phase categories, the problem of property dilution is mitigated, ultimately resulting in greater quantities of hail and larger sizes reaching the surface. It is argued that the latest version of the P3 scheme is now capable of realistically representing the major microphysical processes involved in the initiation, growth, and decay of hail.

---

## 1. Introduction

Bulk microphysics schemes (BMSs) remain central to operational NWP and climate modeling. Ice-phase parameterization has grown increasingly sophisticated over decades.

**P3 scheme background:** The P3 scheme (Morrison and Milbrandt 2015 [MM15]; Milbrandt and Morrison 2016) uses freely-evolving generic ice categories with no prescribed particle type. Since its inception, P3 has undergone several major developments:
- Generalization to multiple ice categories (Milbrandt and Morrison 2016)
- Prognostic liquid fraction for mixed-phase particles (Cholette et al. 2019)
- Triple-moment ice (Milbrandt et al. 2021)
- Diagnostic subgrid-scale cloud fraction (Jouan et al. 2020)
- Triple-moment rain (Paukert et al. 2019; not incorporated into main code stream)

**Motivation:** Johnson et al. (2019) showed that original two-moment P3 performed poorly for dual-polarization hail signatures. Triple-moment ice (Milbrandt et al. 2021) alleviated these deficiencies. Two additional innovations — predicted liquid fraction and multiple ice categories — have not yet been examined for hail impacts.

**Study goal:** Examine the impacts on hail simulation from (a) predicted liquid fraction and (b) multiple generic ice categories, using idealized high-resolution (200-m) CM1 supercell simulations.

---

## 2. Experimental Design

### 2.1. Overview of the P3 Scheme (v5)

Ice is represented by $n_\text{Cat}$ generic free categories. Each category has between four and six prognostic mixing ratio variables:
- $Q_{i,tot}$: total ice mass mixing ratio (kg kg$^{-1}$)
- $Q_{i,rim}$: rime mass mixing ratio (kg kg$^{-1}$)
- $N_{i,tot}$: total ice number mixing ratio (kg$^{-1}$)
- $B_{i,rim}$: rime volume mixing ratio (m$^3$ kg$^{-1}$)
- $Z_{i,tot}$: reflectivity factor (6th moment) mixing ratio — optional (m$^6$ kg$^{-1}$); enables triple-moment
- $Q_{i,liq}$: liquid mass on ice — optional (kg kg$^{-1}$); enables predicted liquid fraction

The gamma PSD is:
$$N(D) = N_0 D^\mu e^{-\lambda D}$$

All simulations in this study use triple-moment ice ($Z_{i,tot}$ is prognostic).

From the prognostic variables, derived bulk properties include: rime fraction $F_{rim}$, liquid fraction $F_{liq}$, bulk density $\rho_i$, mass-weighted mean fall speed $V_m$, and mass-weighted mean diameter $D_m$.

Maximum hail size $D_{h,\text{max}}$ is diagnosed from the PSD tail following Milbrandt et al. (2021), applied to ice with density $> 500$ kg m$^{-3}$ and rime fraction $> 0.8$.

**Ice processes depicted (Figure 1):** Pristine crystal initiation (primary nucleation, homogeneous freezing, secondary ice production [SIP] via rime splintering), deposition/sublimation, aggregation, riming, wet growth, melting (including mixed-phase treatment), shedding, and refreezing.

### 2.2. Idealized Simulations

**Model:** CM1 (Bryan and Fritsch 2002), compressible dynamics, 5th-order WENO advection (Balsara and Shu 2000)

**Grid:** 200-m isotropic spacing; 1000 × 1000 horizontal grid points; 100 vertical levels; 20-km model top; 2-s timestep

**Case:** Hailstorm based on Alberta, Canada, 13 June 2020 (the billion-dollar Calgary hailstorm; Joe et al. 2024). Cold cloud base, lower CAPE, strong mid-to-upper-level vertical shear. Initial sounding from ECCC RDPS 6-hour forecast valid 0000 UTC 14 June 2020 near Calgary, adjusted for initial instabilities. Mean 0–6 km wind subtracted from sounding.

**Convection initiation:** Vertical motion nudging method (Naylor and Gilmore 2012) with ellipsoidal region (horizontal radius 15 km, vertical radius 1500 m, peak w = 7.5 m s$^{-1}$), applied over first 20 min.

**Analysis time:** 80 min (mature, quasi-steady stage). Accumulated precipitation is examined over 45–90 min to reduce sensitivity to intermittent instantaneous rates.

**Additional case (not shown):** Oklahoma 1 June 2008 supercell (warmer cloud base, higher CAPE, weaker mid-level shear; also used in Milbrandt et al. 2021). Impacts of sensitivity tests were similar, lending support to general conclusions.

### Simulation Configurations

| Run name | nCat | Liq-Frac | SIP | Treatment of $(dN/dt)_{i,\text{MELT}}$ |
|----------|------|----------|-----|---------------------------------------|
| BASE | 1 | Off | Off | Proportional to $Q_i/N_i$ |
| LF | 1 | On | Off | See text |
| BASE-MOD | 1 | Off | Off | $(dN/dt)_{i,\text{MELT}} = 0$ (similar to LF) |
| LF-MOD1 | 1 | On | Off | Identical to BASE |
| LF-MOD2 | 1 | On | On | Identical to LF |
| LF-2CAT | 2 | On | On | Identical to LF |
| LF-3CAT | 3 | On | On | Identical to LF |
| LF-4CAT | 4 | On | On | Identical to LF |

All simulations use triple-moment ice.

---

## 3. Results of Baseline Simulation (BASE)

At 80 min, the BASE simulation produces a well-developed deep convective supercell with:
- Most ice heavily rimed ($F_{rim} > 0.7$) throughout, including in the anvil (originating from the convective updraft with ample liquid for riming)
- High bulk density, large sizes ($D_m$), and fast fall speeds in the convective core
- Small, dense ice at high altitudes in the anvil with evidence of gravitational size sorting
- $D_{h,\text{max}}$ concentrated in a narrow shaft in the convective core reaching the surface on the right flank
- Smaller hail ejected into the anvil melts before reaching the surface

---

## 4. Microphysics Sensitivity Tests

### 4.1. Impacts of Liquid Fraction

**Key mechanism:** In BASE (liquid fraction off), all melted ice mass is immediately shed to rain. The $N_{i,tot}$ tendency during melting assumes constant $D_{mm}$ (Equation 2), so $N_{i,tot}$ decreases proportionally to $Q_{i,tot}$.

With liquid fraction on (LF), melting is more physically realistic:
- Small ice particles melt directly to rain (with $N_{i,tot}$ decreasing via Equation 3)
- Remaining melted mass transfers from solid to liquid within mixed-phase particles ($Q_{i,rim}$ decreases, $Q_{i,liq}$ increases, $Q_{i,tot}$ unchanged, $N_{i,tot}$ unchanged)
- Shedding of liquid on mixed-phase particles is explicit (depends on rime fraction)

**Effect on hail:** The different treatment of $N_{i,tot}$ during melting/shedding with liquid fraction on results in:
- $N_{i,tot}$ is not reduced during the transfer of solid mass to liquid (unlike BASE where $N_{i,tot} \propto Q_{i,tot}$ during melting)
- Therefore $D_m$ (proportional to $(Q/N)^{1/3}$) decreases more rapidly
- Smaller mean size → slower fall speeds → greater surface area → faster melting rate
- Hail more likely to completely melt before reaching surface

**Sensitivity tests to isolate mechanism:**
- **BASE-MOD** (liquid fraction off, but $(dN/dt)_\text{MELT} = 0$): Produces reduced hail at surface similar to LF — confirms that the change in $N_{i,tot}$ treatment is responsible
- **LF-MOD1** (liquid fraction on, but $N_{i,tot}$ decreases proportionally as in BASE): Produces more hail at surface similar to BASE — confirms that $N_{i,tot}$ closure drives the difference

**Quantitative impact:** LF reduces domain-mean solid precipitation and $D_{h,\text{max}}$ compared to BASE. The specific numbers are visible in the accumulated precipitation figures (not reproduced here).

**Additional process rates (Figure 8):**
- $(dQ/dt)_\text{MELT1}$: frozen mass melting directly to rain
- $(dQ/dt)_\text{MELT2}$: transfer from frozen to liquid within mixed-phase particles
- $(dQ/dt)_\text{SHED}$: mass loss from shedding
- Rate of change of $D_m$ due to combined melting and shedding:

$$\left(\frac{dD}{dt}\right)_\text{MELT+SHED} = \frac{1}{3}\left(\frac{\pi}{6\rho_i}\right)^{1/3} \left[Q^{-2/3}N^{-1/3}\left(\left(\frac{dQ}{dt}\right)_\text{MELT1} + \left(\frac{dQ}{dt}\right)_\text{SHED}\right) - Q^{1/3}N^{-4/3}\left(\frac{dN}{dt}\right)_\text{MELT1}\right]$$

With liquid fraction on, mean hail size decreases much faster in convective cores ($x \approx 25$ km).

**LF-MOD2** (adds SIP to LF): Results similar to LF; SIP does not substantially change the hail simulation for this case.

### 4.2. Impacts of Number of Ice Categories

**Property dilution problem:** In a single-ice-category simulation, large hail falling through the main updraft mixes (via aggregation or numerical blending) with smaller ice being transported upward from below. This dilutes the physical properties (bulk density, size) of the hail, reducing simulated hail reaching the surface.

With more categories ($n_\text{Cat}$), this dilution is mitigated because:
- Different dominant ice modes coexist in separate categories
- Large, dense, highly-rimed hail in one category is not mixed with small, lightly-rimed ice in another
- Hail can grow to larger sizes without property dilution

**Results (LF-2CAT, LF-3CAT, LF-4CAT):**
- Each additional ice category generally increases $D_{h,\text{max}}$ and solid precipitation reaching the surface
- LF-2CAT shows a substantial increase in maximum hail size vs. LF (1-CAT)
- Additional categories beyond 2 show diminishing returns
- The increase in hail sizes with multiple categories partly offsets the decrease due to liquid fraction

**Computational note:** LF-2CAT uses 16 hydrometeor tracers (4 for cloud/rain, 12 for 2-category ice). Using SFVT advection, this is equivalent to advecting 4 primary tracers plus marginal cost for 12 secondary scalars. The LF-2CAT configuration is argued to be computationally affordable for km-scale operational NWP with efficient advection algorithms.

---

## 5. Discussion

**Summary of impacts:**
- Predicted liquid fraction: reduces hail at surface through more physical melting/shedding
- Multiple ice categories: increases hail at surface through reduced property dilution
- The two effects are in opposition; their relative magnitudes depend on storm characteristics and environmental conditions

**Recommendation:** The P3 scheme with triple-moment ice, predicted liquid fraction, and two ice categories (LF-2CAT) provides the most physically complete representation of hail processes currently available in P3 while remaining computationally feasible.

**Generality:** Results for the Alberta 2020 case were confirmed to be qualitatively consistent with the Oklahoma 2008 case, supporting the general applicability of the conclusions.

**Operational NWP applicability:** All simulations were repeated at 1-km grid spacing; sensitivities were qualitatively similar, confirming conclusions hold at scales relevant to current high-resolution operational NWP.

**Future improvements:**
- Full triple-moment treatment of all microphysical process rates (improves PSD dispersion for all processes, not just sedimentation)
- Optimization of ice initiation and merging in multi-category configuration
- Improved primary ice nucleation, additional SIP mechanisms (drop fragmentation; see Qu et al. 2022)
- Prognostic aerosols (CCN/IN)

---

## 6. Conclusions

- Predicted liquid fraction in P3 leads to more realistic melting and shedding, primarily through the treatment of $N_{i,tot}$ during melting, resulting in smaller mean hail sizes and reduced solid precipitation at the surface
- Multiple ice categories in P3 mitigate property dilution, leading to larger hail sizes and greater solid precipitation at the surface
- With triple-moment ice, predicted liquid fraction, and two ice categories, the P3 scheme is now capable of realistically representing the major microphysical processes for hail: initiation (graupel or frozen drop embryos), growth (riming, wet growth), and decay (melting, shedding)
- This configuration is computationally feasible for km-scale NWP using efficient advection techniques such as SFVT

---

## Appendix A: List of Symbols

| Symbol | Description | Units |
|--------|-------------|-------|
| $B_{i,rim}$ | Rime ice volume mixing ratio | m$^3$ kg$^{-1}$ |
| $D$ | Equivalent diameter | m |
| $D_{h,\text{max}}$ | Maximum diagnosed hail diameter | m |
| $D_m$ | Mass-weighted mean ice diameter | m |
| $D_{mm}$ | Mean-mass diameter | m |
| $F_{liq}$ | Liquid fraction | – |
| $F_{rim}$ | Rime ice mass fraction | – |
| $N(D)$ | Number density function (PSD) | m$^{-1}$ kg$^{-1}$ |
| $N_0$ | Intercept parameter | m$^{-(1+\mu)}$ kg$^{-1}$ |
| $n_\text{Cat}$ | Number of ice categories | – |
| $N_i$ | Total ice number concentration | m$^{-3}$ |
| $N_{i,tot}$ | Total ice number mixing ratio | kg$^{-1}$ |
| $Q_c$ | Cloud droplet mass content | kg m$^{-3}$ |
| $Q_{i,liq}$ | Liquid (on ice) mass mixing ratio | kg kg$^{-1}$ |
| $Q_{i,rim}$ | Rime mass mixing ratio | kg kg$^{-1}$ |
| $Q_{i,tot}$ | Total ice mass mixing ratio | kg kg$^{-1}$ |
| $Q_r$ | Rain mass content | kg m$^{-3}$ |
| $V_m$ | Mass-weighted fall speed for ice | m s$^{-1}$ |
| $w_\text{max}$ | Peak updraft speed | m s$^{-1}$ |
| $Z_{DR}$ | Differential reflectivity | dB |
| $Z_e$ | Equivalent reflectivity | dBZ |
| $Z_{e,c}$ | Equivalent reflectivity, column-maximum | dBZ |
| $Z_{i,tot}$ | Reflectivity factor (6th moment) mixing ratio | m$^6$ kg$^{-1}$ |
| $\rho_a$ | Air density | kg m$^{-3}$ |
| $\rho_i$ | Bulk ice density | kg m$^{-3}$ |
| $\lambda$ | Slope parameter (PSD) | m$^{-1}$ |
| $\mu$ | Shape parameter (PSD) | – |

---

## References (selected)

- Cholette, M., H. Morrison, J. A. Milbrandt, and J. M. Thériault, 2019: Parameterization of the bulk liquid fraction on mixed-phase particles in the P3 scheme. *J. Atmos. Sci.*, **76**, 561–582. https://doi.org/10.1175/JAS-D-18-0278.1
- Cholette, M., J. A. Milbrandt, H. Morrison, D. Paquin-Ricard, and D. Jacques, 2023: Combining triple-moment ice with prognostic liquid fraction in P3. *J. Adv. Model. Earth Syst.*, **15**, e2022MS003328. https://doi.org/10.1029/2022MS003328
- Joe, P., R. E. Stewart, and S. Boodoo, 2024: The billion dollar Calgary hailstorm of 13 June 2020. *CMOS Bulletin*.
- Johnson, M., Y. Jung, J. A. Milbrandt, H. Morrison, and M. Xue, 2019: Effects of the representation of rimed ice in bulk microphysics schemes on polarimetric signatures. *Mon. Wea. Rev.*, **147**, 3785–3810.
- Milbrandt, J. A., and H. Morrison, 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III. *J. Atmos. Sci.*, **73**, 975–995.
- Milbrandt, J. A., H. Morrison, D. T. Dawson II, and M. Paukert, 2021: A triple-moment representation of ice in P3. *J. Atmos. Sci.*, **78**, 439–458. https://doi.org/10.1175/JAS-D-20-0084.1
- Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Morrison, H., J. A. Milbrandt, G. Bryan, K. Ikeda, S. A. Tessendorf, and G. Thompson, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part II. *J. Atmos. Sci.*, **72**, 312–339.
- Paukert, M., J. Fan, P. J. Rasch, H. Morrison, J. A. Milbrandt, J. Shpund, and A. Khain, 2019: Three-moment representation of rain in a bulk microphysics model. *J. Adv. Model. Earth Syst.*, **11**, 257–277.
- Qu, Z., A. Korolev, J. A. Milbrandt, et al., 2022: The impacts of secondary ice production on microphysics and dynamics in tropical convection. *Atmos. Chem. Phys.*, **22**, 12287–12310.

[Figure X: Various figures including baseline simulation fields ($Q_i$, $Z_e$, $F_{rim}$, $F_{liq}$, $\rho_i$, $V_m$, $D_m$, $D_{h,\text{max}}$), accumulated precipitation for all runs, process rate diagrams, vertical cross-sections for LF, BASE-MOD, LF-MOD1, and multi-category runs — images not reproducible in markdown]
