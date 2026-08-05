# Summary: Thériault et al. (2015)

**Full citation:** Thériault, J. M., J. A. Milbrandt, J. Doyle, J. R. Minder, G. Thompson, N. Sarkadi, and I. Geresdi, 2015: Impact of melting snow on the valley flow field and precipitation phase transition. *Atmos. Res.*, **156**, 111–124. DOI: 10.1016/j.atmosres.2014.12.006
**Journal:** Atmospheric Research
**Year:** 2015
**Authors:** J. M. Thériault, J. A. Milbrandt, J. Doyle, J. R. Minder, G. Thompson, N. Sarkadi, I. Geresdi
**DOI:** 10.1016/j.atmosres.2014.12.006
**Author's role:** Tier 2 — Co-author providing the MY2 scheme (the primary microphysics scheme used in the study); provided domain expertise on microphysics parameterization of snow melting and contributed to the sensitivity analysis design; co-developed the 1D companion work (Milbrandt et al. 2014) on which this study builds

---

## Overview

This paper investigates how the temperature feedback from melting snow affects valley airflow and precipitation phase transitions in complex terrain, using semi-idealized 2D WRF simulations of the 13–14 February 2010 Whistler, BC event (during the Vancouver 2010 Winter Olympics). Simulations with multiple microphysics schemes — including MY2, Thompson, and a bin-resolving scheme — show that melting-induced cooling is both necessary and sufficient to produce valley flow reversal, without which the flow direction remains constant. Sensitivity experiments varying precipitation rates show that even light snowfall (~1 mm h⁻¹) will eventually reverse the valley flow if synoptic conditions remain calm, but the timing varies substantially.

## Context and Motivation

Near-0°C surface conditions in mountainous terrain create a challenging forecast problem: melting snow can cool the local air column to 0°C, creating an isothermal layer and dense cold air that flows downslope, potentially reversing or stagnating the valley flow and shifting precipitation from rain to snow. This mechanism was hypothesized to explain the well-known Callaghan Valley case during the 2010 Winter Olympics, where a rapid temperature drop and flow reversal occurred while forecast models struggled. A companion 1D study (Milbrandt et al. 2014) showed that the timing of phase transition is highly sensitive to the microphysical parameterization of snow, including fall speed, number of moments, and melting process assumptions. This 2D study extends that work to examine the dynamical mechanism and test its robustness across different microphysics schemes.

## Key Scientific Contributions

- Demonstrated via controlled simulation experiments that the temperature feedback from melting snow is both necessary and sufficient to produce valley flow reversal; suppressing melting cooling eliminates the reversal in all three microphysics schemes tested.
- Quantified the dynamical mechanism: melting increases the moist non-dimensional mountain height $H_m = N_m h / U$ from 1.9 to 3.3 (above the flow stagnation threshold), primarily by stratifying the low-level air, producing a low-level high-pressure anomaly that decelerates and eventually reverses the inflow.
- Showed that the flow reversal timing and precipitation phase transition are robustly reproduced across 1-moment bulk (Thompson), 2-moment bulk (MY2), and bin-resolving (GERBIN) schemes, though with differing timescales.
- Established precipitation rate thresholds: all tested rates (1.25–10 mm h⁻¹) eventually produce reversal, with onset time varying by ~40 min across rates and complete reversal requiring 180–360 min depending on rate.
- Found that MY2 produces faster cooling than Thompson due to higher snow fall speeds and different melting parameterization, demonstrating continued sensitivity to microphysical assumptions even in a dynamical context.

## Methods Summary

Semi-idealized 2D WRF (v3.3.1) simulations of the Whistler Callaghan Valley case (13–14 February 2010). A near-bell-shaped mountain (~1.2 km) was placed in a 200-km domain at 250-m horizontal grid spacing. The model was initialized with the VOC radiosonde profile, and snow was prescribed continuously from 2.3 km altitude at a range of mixing ratios corresponding to surface precipitation rates of 1.25–10 mm h⁻¹. Coriolis force and surface fluxes were neglected to isolate the melting-induced dynamics. Experiments were repeated: (1) with and without the temperature feedback from melting snow (for MY2, Thompson, and GERBIN schemes), and (2) varying the initial snow field at five precipitation rates using MY2 only. The MY2 scheme is the primary (control) microphysics; its MY2005a,b formulation with the modifications of Milbrandt et al. (2014) constraints on snow size distribution is used.

## Key Results

- With full melting: valley flow reversal at ~120 min (onset) and ~210 min (complete) for 5 mm h⁻¹ case — timing consistent with observed Doppler radar winds.
- Without melting cooling: no reversal in any scheme; flow remains up-valley throughout.
- $H_m$ increased from 1.9 to 3.3 by melting — moves the flow into a dynamical regime where flow stagnation is strongly favored.
- MY2: wind speed reaches 0 m/s at 180 min; Thompson: 210 min; GERBIN: 200 min.
- All precipitation rates (1.25–10 mm h⁻¹) produce reversal, with onset taking 4 h (1.25 mm h⁻¹) to less than 2 h (10 mm h⁻¹).
- Rain–snow boundary reaches the mountain base before the valley flow completely reverses at higher precipitation rates; at low rates the boundary and reversal arrive simultaneously.

## Limitations and Caveats

- The 2D geometry neglects valley sidewall volume effects, three-dimensional valley geometry, and Coriolis force — likely underestimating the cooling rate.
- Results are from a single semi-idealized case; applicability to other events and terrain types is inferred but not demonstrated.
- No synoptic forcing was included; the study isolates the melting-induced mechanism without ambient large-scale evolution.
- Radiation and surface energy fluxes were neglected; their effects on the thermodynamics could modify timing.

## Relation to Author's Research Program

This paper sits at the intersection of two of Milbrandt's research threads: the sensitivity of precipitation phase transitions to microphysics parameterization (directly following Milbrandt et al. 2014), and the use of MY2 as the leading tool for process-level microphysics research. The study directly builds on the 1D companion paper (Milbrandt, Thériault, and Mo 2014) in which Milbrandt was first author. Here, Milbrandt contributes the MY2 scheme — which is the control microphysics and the one whose behavior is most carefully analyzed — and brings his expertise in bulk microphysics parameterization of snow melting. The collaboration with Thériault (UQAM) and Minder (Albany) reflects the cross-disciplinary nature of the precipitation dynamics/microphysics boundary, an area where Milbrandt's scheme expertise is widely sought. This work also connects to the SNOW-V10 observational program (Isaac et al. 2014) which Milbrandt contributed to.

## Impact and Citations

**Citation count:** ~12 (Semantic Scholar, retrieved 2026-06-06)

The paper has been cited primarily in the precipitation phase transitions and complex terrain meteorology literature. It is cited in follow-on studies of valley flow dynamics in mountainous regions and in work on forecasting rain–snow boundaries. The connection to the Vancouver 2010 Winter Olympics case gives it applied relevance to winter weather forecasting in complex terrain.
