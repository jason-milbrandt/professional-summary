# McTaggart-Cowan et al. (2019)

**Full citation:** McTaggart-Cowan, R., Vaillancourt, P. A., Zadra, A., Chamberland, S., Charron, M., Corvec, S., Milbrandt, J. A., Paquin-Ricard, D., Patoine, A., Roch, M., Separovic, L., and Yang, J., 2019: Modernization of atmospheric physics parameterization in Canadian NWP. *J. Adv. Model. Earth Syst.*, **11**, 3593–3635. DOI: 10.1029/2019MS001781

---

## Abstract

Atmospheric physics is represented in numerical models by parameterizations that use resolved-scale information to estimate the effects of physical processes on the atmospheric state. Over time, our understanding of these processes improves, new techniques are introduced, and increased resolution changes the relative importance of different parameterizations within the system. A major update to the package of physical parameterizations used in Canadian operational NWP is introduced. The primary goals of this effort were to improve the global energy budget and to facilitate an increase in the vertical resolution of operational configurations. Both objectives were achieved, along with a significant improvement in guidance quality for global and regional prediction systems.

---

## 1. Introduction

The Canadian Meteorological Centre (CMC) runs several NWP systems based on different configurations of the Global Environmental Multiscale (GEM) model (Table 1):

| System | Domain | Grid spacing |
|--------|--------|-------------|
| GEPS | Global | 39 km |
| GDPS | Global | 15 km |
| REPS | North America | 10 km |
| RDPS | North America | 10 km |
| HRDPS | Canada | 2.5 km |

A multiyear modernization project initiated in 2014 had two primary goals:
1. Reduction of unphysical sensitivity to vertical resolution
2. Improvement of representation of the global hydrological cycle

---

## 2. Background

### 2.1 NWP Systems at the CMC

The updated physics configuration was adopted by GDPS, RDPS, and REPS in mid-2019. The HRDPS had already adopted the P3 microphysics scheme (replacing MY2) in late 2018.

### 2.2 Development and Evaluation Methods

A hierarchy of modeling and evaluation systems was used:
- 1-year "model climate" integrations (4 × 13-month runs as a lagged ensemble for climatological assessment)
- Data assimilation cycles (winter: Jan–Feb 2017; summer: Jul–Aug 2016)
- Forecast sequences (44 cases, sampled at 36-hr intervals)
- Case studies for specific problems

### 2.3 Increasing Vertical Resolution

The operational vertical grid (L80) was updated to L84. Key changes:
- Bottom momentum level lowered from 40 to 20 m (thermodynamic level at 10 m)
- Number of levels below 850 hPa increased from 9 to 12
- Smooth function for layer depth expansion

Sources of unphysical vertical resolution sensitivity required numerical fixes:
- Layer depth calculations in orographic blocking scheme reformulated to use physical heights
- Higher-order interpolants (piecewise cubic Hermite polynomials) for vertical integrals throughout parameterizations

### 2.4 A Conservative Approach

The existing model showed excessive latent heat fluxes over tropical/subtropical oceans, leading to an overactive hydrological cycle. Conservation of liquid water static energy ($E$) and total water mixing ratio ($q_t$) was assessed and enforced across parameterizations:
- Shallow convection scheme replaced due to poor conservation properties
- Conservation corrections applied to large-scale condensation scheme — yielded significant midtropospheric warming (Figure 4)
- Water vapor conservation in dynamics: total precipitation drops ~5% with Sørensen et al. (2013) correction adopted
- Dissipative heating ($\partial T/\partial t = -(1/c_{pd})\ \partial K/\partial t$) included in blocking and boundary layer schemes

---

## 3. Physical Processes in NWP at the CMC

### 3.1 Radiative Transfer

Updated version of the Li and Barker (2005) correlated-$k$ distribution scheme:
- Improved water vapor continuum treatment
- Methane solar absorption introduced
- Ozone cross sections with weak temperature dependence (causes stratospheric warming)
- New ozone climatology (blend of Fortuin & Kelder 1998 and ERA5)
- Solar constant updated from 1367 to 1361 W/m² (Kopp & Lean, 2011)
- 3D climatologies for CH₄, N₂O, CFC-11, CFC-12 replacing uniform values above tropopause

### 3.2 Stratospheric Chemistry

Methane oxidation parameterization (CH₄ + OH → CH₃ + H₂O chain). No changes in this update.

### 3.3 Unresolved Orography and Gravity Wave Drag

**Blocking and orographic GWD:** Lott and Miller (1997) / McFarlane (1987) combined scheme. Key updates:
- Orographic smoothing filter sharpened from 20 Δx to 3 Δx (GDPS) / 5 Δx (RDPS, REPS)
- Beljaars et al. (2004) reference orography spectrum for consistent subgrid separation
- Net effect: reduced drag, shifted precipitation upslope along coastal mountains (Figure 8)

**Nonorographic GWD:** Hines (1997a,b) Doppler spread parameterization. No changes.

### 3.4 The Earth's Surface

**Land surface:** No significant changes; focus on next-generation scheme (Husain et al., 2016). Key interactions updated:
- Minimum wind speed replaced by minimum Obukhov length (L > 20 m) under stable conditions
- Supercooled rain water treated as solid precipitation in land surface scheme (improves freezing rain forecasts; Figure 10)

**Water surface:** 
- Zeng and Beljaars (2005) one-dimensional thermodynamic mixed layer model introduced (warm layer + cool skin effects on SST for turbulent flux calculations)
- Salt water correction: 2% subsaturation at air-sea interface
- Deacu et al. (2012) thermal roughness length applied globally (previously only RDPS)
- These changes reduce excessive oceanic latent heat fluxes

### 3.4.1 Surface Layer

Updated stability functions: Beljaars and Holtslag (1991) replaces Delage (1997) for stably stratified conditions. Minimum Obukhov length condition (L > 20 m) enforced.

### 3.5 Turbulence in the Planetary Boundary Layer

1.5-order TKE closure (Bélair et al., 1999; McTaggart-Cowan & Zadra, 2015):

$w'\theta'_l = -K_T \frac{\partial\theta_l}{\partial z}$, where $K_T = c_n \lambda \sqrt{\text{TKE}}$

Updates:
- Global systems adopt same scheme as regional (unified boundary layer across all systems)
- Buoyancy enhancements over ocean reduced by 20%; cloud formation restricted to coupled boundary layers below 1.5×PBL height
- New regime-dependent mixing length: Bougeault–Lacarrère (1989) in turbulent flows, Blackadar (1962) in laminar
- Reduces winter cold bias; enables use of Blackadar length in global systems
- Relaxation time scale for λ: 7,200 s → 900 s; dissipation length limit: <50 m

### 3.6 Moist Convection

Three separate mass-flux-based schemes: deep, shallow, and midlevel.

**3.6.1 Deep Convection** (Kain & Fritsch / Bélair et al. framework, revised):
- Environmental mass flux calculation error corrected (nonconservation fix)
- Convective adjustment time scale related to cloud object depth (Lagrangian view)
- Downdraft detrainment depth increased to moisten lower levels over oceans
- Convective momentum transport implemented using Romps (2012) framework

**3.6.2 Shallow Convection:**
- Original shallow convection scheme replaced entirely with a conservative scheme
- Eliminates leading-order moisture nonconservation that was affecting hydrological cycle diagnostics

**3.6.3 Midlevel Convection:**
- New midlevel convection scheme introduced
- Represents elevated moist convection not captured by deep/shallow schemes
- Reduces grid-point storms and improves precipitation scores

### 3.7 Large-Scale Clouds and Precipitation

Two cloud schemes in GEM:

**3.7.1 Legacy grid-scale condensation scheme** (Sundqvist et al., 1989): Used by GEPS, GDPS, REPS, RDPS. Simple fractional cloud cover based on relative humidity:
$f_c = 1 - \sqrt{(1-H)/(1-H_0)}$

Only change: rain evaporation coefficient increased (2×10⁻⁴ → 4×10⁻⁴); conservation correction applied (significant midtropospheric warming, Figure 4).

**3.7.2 Advanced microphysics scheme (P3):** Used by HRDPS (replaced MY2 in late 2018). The Predicted Particle Properties (P3) scheme (Morrison & Milbrandt, 2015; Milbrandt & Morrison, 2016):
- Single ice category (4 prognostic variables: total mass, rime mass, total number, rime volume)
- Ice particle properties (density, effective size, fall speed) vary continuously without ad hoc category conversion
- Improved spatial distribution of precipitation in mountainous areas due to gradual riming increases in fall speeds
- A fractional cloud component for P3 is under development (preliminary GDPS tests promising)

### 3.8 Cloud-Radiation Interface

Two-step interface combining all cloud sources for radiative transfer:
- Legacy scheme: random overlap of cloud fractions; diagnostic phase partitioning (Boudala et al., 2004); fixed effective radii
- P3 scheme: explicit liquid/ice path lengths from P3 outputs; effective radii computed directly from P3 size distribution; minimum overlap between implicit and explicit clouds

---

## 4. Performance of Updated Physics

### 4.1 Global Energy Budget

Improved representation of global energy budget (Figure 20):
- **A:** Solar constant reduction (1367 → 1361 W/m²) reduces top-of-atmosphere input
- **B:** Water conservation (dynamics and physics corrections) reduces excessive precipitation
- **C:** Turbulent latent heat flux reductions over tropical/subtropical oceans

Net result: global energy and hydrological budgets more consistent with observational estimates (Stephens et al., 2012).

### 4.2 NWP Guidance Quality

**Upper-air and surface scores:**
- Significant improvements in upper-air temperature, geopotential, and wind for GDPS winter and summer forecast sequences
- Surface temperature, dew-point, and wind speed RMSE improved at most forecast lead times
- Stratospheric warm bias introduced (ozone cross-section temperature dependence) is one of few degradations

**Precipitation:**
- Summer precipitation equitable threat scores improved; frequency bias reduced dramatically for large thresholds (~30% reduction in frequency bias at higher thresholds — Figure 27)
- Midlevel convection scheme principally responsible for reducing summertime overprecipitation bias

**Other metrics:**
- Tropical cyclone track and intensity: improved
- Madden-Julian Oscillation prediction: improved
- Quasi-biennial oscillation: no significant change

### 4.3 Computational Cost

| System | Total cost increase |
|--------|-------------------|
| GDPS | +25% |
| RDPS | +30% |
| REPS | +35% |

---

## 5. Discussion/Conclusions

Both primary goals were achieved:
1. Vertical resolution sensitivity reduced to physical levels (L84 grid yields similar upper-air scores to L80)
2. Improved global energy budget and hydrological cycle

The modernization provides a stronger foundation for future development: scale-aware parameterizations spanning ~50 to <1 km, continued unification of physics across all GEM configurations, and improved consistency between physically linked processes. The updated physics was implemented operationally in GDPS, RDPS, and REPS in mid-2019.

---

## Key References

- Morrison, H. and Milbrandt, J. A., 2015: Part I of P3. *J. Atmos. Sci.*, 72, 287–311.
- Milbrandt, J. A. and Morrison, H., 2016: Part III of P3. *J. Atmos. Sci.*, 73, 975–995.
- Milbrandt, J. A. and Yau, M. K., 2005: MY multimoment scheme. *J. Atmos. Sci.*, 62, 3065–3081.
- Chosson, F., Vaillancourt, P. A., Milbrandt, J. A., Yau, M. K., and Zadra, A., 2014: Adapting two-moment microphysics across resolutions. *J. Atmos. Sci.*, 71, 2635–2653.
- Mo, R., Burgman, M., Milbrandt, J. et al., 2019: Impacts of hydrometeor drift on orographic precipitation. *Weather Forecast.*
