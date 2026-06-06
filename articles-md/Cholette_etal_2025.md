# Cholette et al. (2025)

**Full citation:** Cholette, M., J. A. Milbrandt, H. Morrison, J. M. Thériault, K.-S. Lim, W.-Y. Chang, K. Kim, and G. Lee, 2025: Simulation of wet snow during winter orographic precipitation using the Predicted Particle Properties (P3) microphysics scheme. *Mon. Wea. Rev.*, **153**, 2491–2512. DOI: 10.1175/MWR-D-25-0017.1

---

## 1. Introduction

Winter storms bring diverse precipitation types — rain, snow, ice pellets, freezing rain, and wet snow — whose phase depends sensitively on near-surface temperature. Wet snow (defined by the AMS as deposited snow containing a great deal of liquid water) can accumulate quickly on structures, causing power line damage, vegetation loss, and transportation disruptions. A 1°C temperature change can shift precipitation from wet snow to rain or from ice pellets to freezing rain, making accurate forecasting difficult.

Wet snow properties that govern damage potential include particle density and liquid mass fraction $F_{i,liq}$; both increase as particles become wetter. Most NWP bulk microphysics schemes do not explicitly predict wet snow — they use fixed or predefined ice categories without mixed-phase representation. The Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015) is one of the few that prognoses the bulk liquid mass fraction of ice hydrometeors.

Prior P3 liquid-fraction (LF) studies evaluated hail, ice pellets, and freezing rain (Cholette et al. 2019, 2020, 2023, 2024; Milbrandt et al. 2025) and idealized 1D wet-snow simulations (Cholette et al. 2019), but 3D NWP evaluation for wet snow had not been done.

**Objective:** Evaluate 3D kilometer-scale GEM+P3 simulations of wet snow during winter orographic precipitation using data from the ICE-POP 2018 field campaign in South Korea, comparing simulations with and without predicted liquid fraction.

---

## 2. ICE-POP 2018 Cases and Data

### 2a. Cases

Ten cases from the 2017–18 Winter Olympics field campaign in the Gangwon region of South Korea are analyzed (Table 1). Cases are classified as "cold" (4 cases) or "warm" (6 cases) low-pressure synoptic systems (Kim et al. 2021). Warm cases feature more precipitation, precipitation-type transitions, and riming.

| Case | Initial date | End date | Period (h) | Synoptic type |
|------|-------------|---------|-----------|--------------|
| 1 | 1500 UTC 9 Dec 2017 | 1600 UTC 10 Dec 2017 | 25 | Cold |
| 2 | 2100 UTC 23 Dec 2017 | 1600 UTC 24 Dec 2017 | 19 | Warm |
| 3 | 1500 UTC 7 Jan 2018 | 2000 UTC 8 Jan 2018 | 29 | Cold |
| 4 | 0300 UTC 16 Jan 2018 | 0100 UTC 17 Jan 2018 | 22 | Warm |
| 5 | 0000 UTC 22 Jan 2018 | 2300 UTC 22 Jan 2018 | 23 | Cold |
| 6 | 0000 UTC 30 Jan 2018 | 0000 UTC 31 Jan 2018 | 24 | Cold |
| 7 | 1800 UTC 27 Feb 2018 | 0100 UTC 1 Mar 2018 | 31 | Warm |
| 8 | 0900 UTC 4 Mar 2018 | 0900 UTC 5 Mar 2018 | 24 | Warm |
| 9 | 0000 UTC 7 Mar 2018 | 0000 UTC 9 Mar 2018 | 48 | Warm |
| 10 | 1200 UTC 20 Mar 2018 | 2100 UTC 21 Mar 2018 | 33 | Warm |

### 2b. Observational Data

- **AWS network** (Korea Meteorological Administration): hourly 2-m air temperature and total accumulated precipitation from 604 sites.
- **Five ICE-POP supersites** aligned coast-to-mountains: GWU (47 m elevation), BKC (229 m), CPO (855 m), MHS (789 m), YPO (772 m).
- **Retrieved bulk liquid fraction and bulk density of snow** from collocated Micro Rain Radar (MRR) and Parsivel disdrometer (Chang et al. 2024) at 1-min intervals, averaged to 10 min. T-matrix method used to match Parsivel-simulated reflectivity to MRR-measured reflectivity.

Bulk density of snow: $\rho_{i,bulk} = y_i \cdot 0.92 + y_w \cdot 1$ g cm$^{-3}$.

---

## 3. Simulations and Analysis

### 3a. Model and Nesting

Three-nested domain simulations using the GEM model (Côté et al. 1998; Girard et al. 2014):

| Simulation | Grid spacing | Initial/LBC source | LBC update |
|-----------|-------------|-------------------|------------|
| LF_10km | ~10 km (0.09°) | ECCC GDPS | 3 h |
| LF_2.5km | ~2.5 km (0.0225°) | LF_10km | 1 h |
| 1-km (LF and noLF) | ~1 km (0.009°) | LF_2.5km | 30 min |

All simulations: 84 staggered vertical levels, 10 m near surface to 220 m aloft. The 1-km configuration matches ECCC's operational HRDPS (Milbrandt et al. 2016). Temporal spinups of 3–6 h used.

The 1-km simulations are performed in two versions: **LF** (with predicted bulk liquid fraction) and **noLF** (without). Both use the 3-moment (3MOM) ice PSD and two ice categories.

### 3b. The P3 Microphysics Scheme

P3 prognoses six mixing ratio variables per ice category:
- Total ice number $N_{i,tot}$ (kg$^{-1}$)
- Total ice mass $q_{i,tot}$ (kg kg$^{-1}$)
- Rime mass $q_{i,rim}$ (kg kg$^{-1}$)
- Rime volume $B_{i,rim}$ (m$^3$ kg$^{-1}$)
- Liquid on ice $q_{i,liq}$ (kg kg$^{-1}$) [LF only]
- Sixth moment $Z_{i,tot}$ (m$^6$ kg$^{-1}$) [3MOM]

Total ice mass: $q_{i,tot} = q_{i,dep} + q_{i,rim} + q_{i,liq} = q_{i,ice} + q_{i,liq}$

Bulk liquid fraction: $F_{i,liq} = q_{i,liq}/q_{i,tot}$; rime mass fraction: $F_{i,rim} = q_{i,rim}/q_{i,ice}$.

In noLF: $q_{i,liq} = 0$.

**Key melting difference between LF and noLF:**
- noLF: all melted water is instantaneously transferred to rain each time step (standard approach).
- LF: melting is split — small ice particles fully melt (transfer to rain), while larger particles accumulate melt water in $q_{i,liq}$ (Fujiyoshi 1986 parameterization). When $F_{i,liq} > 0.99$, remaining ice transfers to rain.

**Wet snow definition in P3:** $F_{i,liq} > 0.15$.

### 3c. Analysis

Precipitation types determined diagnostically at every level and time step using a decision tree based on $F_{i,liq}$, $F_{i,rim}$, $\rho_{i,rim}$, $D_{im}$, and $T_{k,bot}$. Mean mass-weighted density:

$$\rho_{im} = \frac{\int_0^\infty m(D) n(D) \, dD}{\int_0^\infty V(D) n(D) \, dD}$$

where $V(D) = \pi D^3/6$ (spherical equivalent volume).

---

## 4. Simulated Cases

### 4a. Temperature

- Cold cases: 2-m air temperature mostly below 0°C except near the coast.
- Warm cases: mostly near or above 0°C over land.
- Systematic cold biases of ~−2°C at supersites, larger for cold cases than warm cases.
- Differences between LF and noLF are negligible in temperature.

### 4b. Total Precipitation and Precipitation Type

- Positive mean precipitation accumulation biases for most cases and both LF/noLF; cases 7 and 8 highest accumulations.
- Biases partly attributable to wind-driven gauge undercatch (~20–50% for wind speeds 2–3.5 m s$^{-1}$).
- **Key result:** Wet snow is simulated in all six warm cases where it was observed in the LF simulations. In noLF, rain is simulated instead.
- Cold cases mostly yield unrimed/lightly rimed snow.

### 4c. Time Series at Supersites (Selected Warm Cases)

**Case 2:** LF simulates wet snow at BKC and GWU (observed); noLF gives rain. Liquid fraction well reproduced at coastal supersites; density of dry ice remains lower than retrievals at mountain supersites.

**Case 4:** Wet snow not observed; well captured by LF (only small peaks at GWU).

**Case 7:** Wet snow accumulates near BKC in LF but liquid fraction at coast not well captured in time series (single grid-point sampling limitation). YPO, MHS, CPO: wet snow simulated at start; retrieved density suggests riming.

**Cases 8, 9, 10:** Wetter, more heavily rimed ice in both simulations. Case 8 is the only case with retrieved liquid fraction > 0 at all five supersites; wet snow not reproduced at YPO/MHS because simulated temperatures are too cold. Case 10: possible "cold wet snow" (supercooled liquid + ice at T < −5°C) not reproduced by LF.

---

## 5. Impacts of Predicted Liquid Fraction

### 5a. Temperature and Precipitation

- Temperature differences between LF and noLF: negligible (melting layer slightly warmer ~0.05°C with LF).
- Total accumulation differences: small; main effect is **phase shift from rain to wet snow** in LF.
- Decrease in rain accumulation proportional to increase in solid (wet snow) accumulation with LF.

### 5b. Wet Snow Liquid Fraction and Ice Density

- Retrieved and simulated bulk liquid fractions are predominantly 0 across all cases; logarithmic scale needed to see variability.
- Cold cases: simulations fail to reproduce non-zero liquid fraction at MHS/CPO (temperature biases).
- Warm cases: LF simulates higher liquid fractions at coastal supersites (GWU, BKC) vs. inland supersites; gradient from coast to mountains well captured.
- Simulated liquid fractions slightly higher than retrievals at coastal supersites during warm cases.
- Bulk density: simulations lower than retrievals for all cases; improved with LF, especially at coastal supersites.
- **Key trend captured:** Factor of 2–3 higher bulk densities at coastal (GWU, BKC) vs. inland elevated (CPO, YPO, MHS) supersites.

### 5c. Melting Process

- noLF: solid precipitation fraction < 5% for T > 0°C (mostly rain) regardless of riming degree — uniform melting behavior.
- LF: higher counts of solid precipitation > 90% for T between 0° and 1.5°C; variability in melting behavior by case (captures differences between unrimed and rimed ice).
- For unrimed ice ($F_{i,rim} < 0.1$) melting aloft: LF gives much higher solid fraction at near-surface T > 0°C than noLF.
- Explanation: in LF, melted water accumulates on ice ($q_{i,liq}$) rather than being transferred to rain; in noLF, collected rain is shed.
- LF better captures the physically observed melting behavior (Fujiyoshi 1986; ICE-POP 2018 data).

---

## 6. Conclusions

Ten ICE-POP 2018 winter cases were simulated with 1-km GEM+P3. Key findings:

1. **Wet snow prediction:** Predicted liquid fraction shifts precipitation phase from rain to wet snow in all 6 cases where wet snow was observed. noLF gives rain instead.
2. **Liquid fraction:** LF simulations capture higher liquid fractions at coastal supersites vs. inland; slightly overestimates observed values during warm cases.
3. **Snow density:** Bulk density lower than retrievals in all simulations; substantially improved with LF at coastal supersites. Factor of 2–3 density gradient from coast to mountains well reproduced with LF.
4. **Melting behavior:** LF captures case-to-case variability in melting tied to riming degree; noLF gives uniform melting behavior. Most melted water in LF accumulates on ice rather than shedding to rain.
5. **Limitation:** LF fails to simulate "cold wet snow" ($T < 0°C$, liquid fraction > 0 as supercooled accretion) — this will be investigated in future work.

**Future work:**
- Investigate relationship between bulk ice density and liquid fraction to improve parameterization.
- Compare 2MOM vs. 3MOM and n1 vs. n2 ice category configurations for precipitation type.
- Microphysical growth process study using ICE-POP 2018 MASC instrument data.

---

## Appendix: Microphysical Processes in P3 and Differences between LF and noLF

Key differences in microphysical process parameterization:

**Melting:**
- LF: split into (1) complete melting of small ice particles → rain, and (2) accumulated melt water on larger ice → $q_{i,liq}$. When $F_{i,liq} > 0.99$, remaining ice converts to rain.
- noLF: all melted water transferred to rain instantaneously.

**Collection of liquid by ice at $T > 0°C$:**
- LF: cloud droplets and rain collected by ice accumulate in $q_{i,liq}$.
- noLF: collected mass is shed (shed drop size = 1 mm, Rasmussen et al. 1984b).

**Wet growth at $T < 0°C$:**
- noLF: not all collected liquid freezes; some fraction is shed.
- LF: collected liquid at $T < 0°C$ becomes a source of $q_{i,liq}$.

**Refreezing (LF only):** $q_{i,liq}$ freezes when $T < 0°C$; transferred to $q_{i,rim}$.

**Deposition/sublimation:** In LF, deposition/sublimation only when $F_{i,liq} = 0$; otherwise condensation/evaporation of $q_{i,liq}$ occurs.

Secondary ice production (Hallett–Mossop, following Cholette et al. 2024) included in all configurations.

---

## References (selected)

- Chang, W.-Y., and Coauthors, 2024: Estimating the snow density using collocated Parsivel and micro-rain radar measurements: A preliminary study from ICE-POP 2017/2018. *Atmos. Chem. Phys.*, **24**, 11955–11979.
- Cholette, M., H. Morrison, J. A. Milbrandt, and J. M. Thériault, 2019: Parameterization of the bulk liquid fraction on mixed-phase particles in P3: Description and idealized simulations. *J. Atmos. Sci.*, **76**, 561–582.
- Cholette, M., J. M. Thériault, J. A. Milbrandt, and H. Morrison, 2020: Impacts of predicting liquid fraction on the 1998 North American Ice Storm. *Mon. Wea. Rev.*, **148**, 3799–3823.
- Cholette, M., J. A. Milbrandt, H. Morrison, D. Paquin-Ricard, and D. Jacques, 2023: Combining triple-moment ice with prognostic liquid fraction in P3. *J. Adv. Model. Earth Syst.*, **15**, e2022MS003328.
- Cholette, M., J. A. Milbrandt, H. Morrison, S. Kirk, and L.-É. Lalonde, 2024: Secondary ice production improves simulations of freezing rain. *Geophys. Res. Lett.*, **51**, e2024GL108490.
- Milbrandt, J. A., and H. Morrison, 2016: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part III: Multiple free categories. *J. Atmos. Sci.*, **73**, 975–995.
- Milbrandt, J. A., H. Morrison, D. T. Dawson II, and M. Paukert, 2021: A triple-moment representation of ice in P3. *J. Atmos. Sci.*, **78**, 439–458.
- Milbrandt, J. A., H. Morrison, and M. Cholette, 2025: Impacts of predicted liquid fraction and multiple ice-phase categories on hail simulation in P3. *J. Adv. Model. Earth Syst.*, **17**, e2024MS004404.
- Morrison, H., and J. A. Milbrandt, 2015: Parameterization of cloud microphysics based on the prediction of bulk ice particle properties. Part I: Scheme description and idealized tests. *J. Atmos. Sci.*, **72**, 287–311.
- Morrison, H., J. A. Milbrandt, and M. Cholette, 2025: A complete three-moment representation of ice in P3. *J. Adv. Model. Earth Syst.*, **17**, e2024MS004644.

[Figure captions not reproduced — see original paper for Figs. 1–15 and supplemental material]
