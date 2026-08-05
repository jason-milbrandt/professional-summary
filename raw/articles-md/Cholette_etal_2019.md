# Parameterization of the Bulk Liquid Fraction on Mixed-Phase Particles in the Predicted Particle Properties (P3) Scheme: Description and Idealized Simulations

**Citation:** Cholette, M., H. Morrison, J. A. Milbrandt, and J. M. Thériault, 2019: Parameterization of the bulk liquid fraction on mixed-phase particles in the predicted particle properties (P3) scheme: Description and idealized simulations. *J. Atmos. Sci.*, **76**, 561–582. DOI: 10.1175/JAS-D-18-0278.1

---

## Abstract

Bulk microphysics parameterizations that are used to represent clouds and precipitation usually allow only solid and liquid hydrometeors. Predicting the bulk liquid fraction on ice allows an explicit representation of mixed-phase particles and various precipitation types, such as wet snow and ice pellets. In this paper, an approach for the representation of the bulk liquid fraction into the predicted particle properties (P3) microphysics scheme is proposed and described. Solid-phase microphysical processes, such as melting and sublimation, have been modified to account for the liquid component. New processes, such as refreezing and condensation of the liquid portion of mixed-phase particles, have been added to the parameterization. Idealized simulations using a one-dimensional framework illustrate the overall behavior of the modified scheme. The proposed approach compares well to a Lagrangian benchmark model. Temperatures required for populations of ice crystals to melt completely also agree well with previous studies. The new processes of refreezing and condensation impact both the surface precipitation type and feedback between the temperature and the phase changes. Overall, prediction of the bulk liquid fraction allows an explicit description of new precipitation types, such as wet snow and ice pellets, and improves the representation of hydrometeor properties when the temperature is near 0°C.

---

## 1. Introduction

Most bulk microphysics schemes allow only solid-phase (snow, graupel, hail) and liquid-phase (rain, cloud) hydrometeors; mixed-phase particles such as wet snow are not represented. For example, instead of forming wet snow from partial melting, most schemes immediately transfer the melted water directly into the rain category.

Several types of winter precipitation — including wet snow, ice pellets, and freezing rain — require tracking the liquid fraction:
- **Wet snow**: formed from partial melting of snowflakes in layers where T > 0°C; liquid water accumulates on the ice core
- **Ice pellets**: formed by refreezing of partially melted ice particles in a cold layer below the warm layer
- **Freezing rain**: supercooled rain reaching cold surface; the supply of freezing rain can be inhibited by collisional freezing between supercooled raindrops and ice pellets/graupel (Barszcz et al. 2018)

Prior work on explicit liquid fraction: Szyrmer and Zawadzki (1999), Thériault and Stewart (2010), Frick et al. (2013; COSMO model, no refreezing), bin microphysics models (Reeves et al. 2016; Geresdi et al. 2014). These have not been implemented in the P3 scheme.

The P3 scheme (Morrison and Milbrandt 2015 = MM15; Milbrandt and Morrison 2016 = MM16) uses "free" ice categories with four prognostic variables per category: total ice mass $q_{i,\mathrm{tot}}$, total ice number $N_{i,\mathrm{tot}}$, rime mass $q_{i,\mathrm{rim}}$, and rime volume $B_{i,\mathrm{rim}}$. This paper extends P3 by adding a fifth prognostic variable: the bulk liquid mass mixing ratio accumulated on ice, $q_{i,\mathrm{liq}}$.

---

## 2. Overview of the Original P3 Microphysics Scheme

The original P3 scheme (P3_ORIG) uses a gamma particle size distribution (PSD) with parameters $N_0$, $\lambda$, and $\mu$. The mass–diameter relationship $m_d(D)$ follows size-dependent power laws covering four regimes:
- Small spherical ice ($D \leq D_\mathrm{th}$): $m_d = \frac{\pi}{6}\rho_i D^3$
- Unrimed nonspherical ice ($D_\mathrm{th} < D \leq D_\mathrm{gr}$): $m_d = a_{va} D^{b_{va}}$
- Graupel/hail ($D_\mathrm{gr} < D \leq D_\mathrm{cr}$): $m_d = \frac{\pi}{6}\rho_g D^3$
- Partially rimed nonspherical ($D > D_\mathrm{cr}$): $m_d = \frac{a_{va}(1+F_{i,\mathrm{rim}})}{1-F_{i,\mathrm{rim}}} D^{b_{va}}$

Default values: $a_{va} = 0.0121$ kg m$^{-b_{va}}$, $b_{va} = 1.9$ (Brown and Francis 1995). Microphysical process rates are pre-integrated offline and stored in lookup tables as a function of $q_{i,\mathrm{tot}}/N_{i,\mathrm{tot}}$, $\rho_{i,\mathrm{rim}}$, and $F_{i,\mathrm{rim}}$.

---

## 3. Parameterization Description of the Bulk Liquid Fraction

### a. New prognostic variable

The modified scheme (P3_MOD) adds $q_{i,\mathrm{liq}}$ (bulk liquid mass mixing ratio accumulated on ice). The total ice/mixed-phase mass becomes:

$$q_{i,\mathrm{tot}} = q_{i,\mathrm{ice}} + q_{i,\mathrm{liq}} = q_{i,\mathrm{rim}} + q_{i,\mathrm{dep}} + q_{i,\mathrm{liq}}$$

The bulk liquid mass fraction:

$$F_{i,\mathrm{liq}} = \frac{q_{i,\mathrm{liq}}}{q_{i,\mathrm{tot}}}$$

Conservation equation for $q_{i,\mathrm{liq}}$ includes source/sink terms: melting ($Q_{i,\mathrm{mlt}}$), wet growth ($Q_{l,\mathrm{wgrth}}$), collection of rain ($Q_{l,\mathrm{coll},r}$), collection of cloud ($Q_{l,\mathrm{coll},c}$), vapor transfer ($Q_{l,\mathrm{dep}}$), refreezing ($-Q_{l,\mathrm{frz}}$), shedding ($-Q_{l,\mathrm{shd}}$).

### b. Main assumptions

- Mass–diameter relationship for whole mixed-phase particle: linear interpolation in $F_{i,\mathrm{liq}}$ between dry-ice and liquid-drop limits: $m_t(D_p, F_{i,\mathrm{liq}}) = (1-F_{i,\mathrm{liq}})m_d(D_p) + F_{i,\mathrm{liq}} m_\mathrm{liq}(D_p)$
- Similarly for projected area $A_t(D_p, F_{i,\mathrm{liq}})$ and terminal velocity $V_t(D_p, F_{i,\mathrm{liq}})$
- Melting depends on ice-core properties (integrated over ice-core PSD with diameter $D_d$); refreezing and condensation/evaporation depend on whole-particle properties (integrated over full-particle PSD with diameter $D_p$)
- Small spherical ice ($D \leq D_\mathrm{th} \approx 66$ μm) melts completely and transfers directly to rain within one time step
- Sublimation/deposition allowed only when $F_{i,\mathrm{liq}} = 0$; when $F_{i,\mathrm{liq}} > 0$, condensation/evaporation of the liquid component is used instead

### c. New and modified processes

**Melting:** Rate depends on ice-core capacitance $C(D_d, F_{i,\mathrm{liq}})$ and ventilation coefficient $F(D_d, F_{i,\mathrm{liq}})$, both interpolated linearly in $F_{i,\mathrm{liq}}$ between dry-ice and liquid-drop limits. Shedding during melting occurs for rimed particles ($F_{i,\mathrm{rim}} > 0$) and large particles ($D_p > 9$ mm).

**Refreezing:** Occurs when mixed-phase particles enter cold air ($T < 0°C$). Rate balances latent heat of freezing against heat conduction through the ice shell and exchange with the environment.

**Vapor transfer of $q_{i,\mathrm{liq}}$:** Condensation/evaporation of liquid portion using quasi-analytic supersaturation formulation with liquid-phase thermodynamic parameters.

**Collection:** Collected rain and cloud when $T \geq 0°C$ is added to $q_{i,\mathrm{liq}}$; when $T < 0°C$ (dry growth), added to $q_{i,\mathrm{rim}}$.

**Lookup tables:** All integrations done offline; values stored as a function of $q_{i,\mathrm{tot}}/N_{i,\mathrm{tot}}$, $\rho_{i,\mathrm{rim}}$, $F_{i,\mathrm{rim}}$, and $F_{i,\mathrm{liq}}$ (50 × 5 × 4 × 4 table).

---

## 4. Comparison with a Benchmark Melting Model

P3_MOD is validated against a Lagrangian model using the Mitra et al. (1990) (M90) parameterization for two initial PSDs of unrimed nonspherical ice particles. Results:
- $F_{i,\mathrm{liq}}$ from P3_MOD and the Lagrangian model agree within 0.15 at all depths below 0°C; total melting distance is nearly identical
- Small differences arise from differences in capacitance and ventilation coefficient parameterizations (P3_MOD uses linear interpolation in $F_{i,\mathrm{liq}}$; M90 uses experimental relationships)
- PSD evolution during melting (shift toward smaller sizes) is consistent between P3_MOD and the Lagrangian model

---

## 5. Idealized Simulations

A 1D kinematic model (50 levels, 60-m spacing, 2-h simulation, 1-s time step) is used to compare P3_MOD and P3_ORIG. Boundary conditions at domain top: $q_{i,\mathrm{tot}} = 0.265$ g kg$^{-1}$, $N_{i,\mathrm{tot}} = 5000$ kg$^{-1}$ (snowfall rate ~1 mm h$^{-1}$ for $F_{i,\mathrm{rim}} = 0$). Sensitivity to $F_{i,\mathrm{rim}}$ at domain top is examined.

### Case 1: Melting layer near the surface (SNOW-V10 profile, Whistler Mountain, 7 March 2010)

500-m deep melting layer; near-surface temperature ~2°C; subsaturated above melting layer top.

- P3_ORIG: surface precipitation is pure rain
- P3_MOD: mixture of rain and near-completely melted ice ($F_{i,\mathrm{liq}} \approx 0.98$; i.e., wet snow) at the surface
- P3_MOD produces faster-falling, denser particles in the melting layer; additional evaporative cooling at top of melting layer
- For $F_{i,\mathrm{rim}} \leq 0.2$: P3_ORIG gives pure rain; P3_MOD gives mixture with wet ice ($F_{i,\mathrm{liq}} > 0.95$)
- For $F_{i,\mathrm{rim}} > 0.5$: both P3_MOD and P3_ORIG give mixed surface types
- Main added value of P3_MOD for this case: explicit wet snow at the surface

### Case 2: Melting layer aloft + refreezing layer (St. John's, Newfoundland, 1 February 1992)

Melting layer aloft with refreezing layer below; near-saturation in refreezing layer (supersaturated w.r.t. ice).

- For $F_{i,\mathrm{rim}} \leq 0.6$: both P3_MOD and P3_ORIG produce only freezing rain
- For $F_{i,\mathrm{rim}} > 0.65$: P3_MOD produces ice pellets as the dominant surface type; P3_ORIG produces mostly freezing rain
- Refreezing in P3_MOD warms the cold layer (latent heat of fusion); melting layer becomes slightly colder due to faster particle fall speeds
- P3_MOD ice pellets collect supercooled raindrops in the cold layer, reducing freezing rain supply — consistent with Barszcz et al. (2018)

---

## 6. Summary and Conclusions

P3_MOD adds $q_{i,\mathrm{liq}}$ as a fifth prognostic variable per ice category. Key improvements over P3_ORIG:
1. Explicit prediction of wet snow (near-completely melted ice reaching surface before full melt)
2. Explicit ice pellet formation via refreezing of partially melted ice in cold layers
3. More realistic latent heating/cooling profiles: extra cooling at melting layer top (evaporation of liquid component); extra warming in refreezing layer
4. Faster fall speeds and higher densities during partial melting
5. Applicable to both winter precipitation physics and hail (wet growth, shedding)
6. Minimal computational overhead (one additional prognostic variable per category)

Limitations: Observational validation not included; to be done in future work using a 3D model.

---

## References

- Austin and Bemis (1950); Barszcz et al. (2018); Beard (1976); Braun and Houze (1995)
- Brown and Francis (1995); Carmichael et al. (2011); Dietlicher et al. (2018)
- Doms and Schättler (2002); Fabry and Zawadzki (1995); Frick et al. (2013)
- Fujiyoshi (1986); Geresdi et al. (2014); Gibson and Stewart (2007)
- Gunn and Kinzer (1949); Gyakum and Roebber (2001); Hanesiak and Stewart (1995)
- Heymsfield (2003); Hogan et al. (2012); Isaac et al. (2014)
- Lackmann et al. (2002); Leinonen and von Lerber (2018); Lin and Stewart (1986)
- Mason (1956); Matsuo and Sayso (1981); Milbrandt and Morrison (2016); Milbrandt and Yau (2005)
- Mitchell and Heymsfield (2005); Mitra et al. (1990 = M90); Morrison and Grabowski (2008)
- Morrison and Milbrandt (2015 = MM15); Morrison et al. (2009); Musil (1970)
- Phillips et al. (2007, 2014); Pruppacher and Klett (1997)
- Rasmussen and Pruppacher (1982); Rasmussen et al. (1984a,b)
- Reeves et al. (2016); Simmel et al. (2002); Stewart (1985); Szyrmer and Zawadzki (1999)
- Thériault and Stewart (2010); Thériault et al. (2006, 2010, 2014)
- Thompson et al. (2008); Thorpe and Mason (1966); Walko et al. (2000); Yokoyama and Tanaka (1984)
