# Summary: Milbrandt et al. (2014)

**Full citation:** Milbrandt, J. A., J. Thériault, and R. Mo, 2014: Modeling the phase transition associated with melting snow in a 1D kinematic framework: Sensitivity to the microphysics. *Pure Appl. Geophys.*, **171**, 303–322, doi:10.1007/s00024-012-0552-y.
**Journal:** Pure and Applied Geophysics
**Year:** 2014 (published online 2012)
**Authors:** J. A. Milbrandt, J. Thériault, R. Mo
**DOI:** 10.1007/s00024-012-0552-y
**Author's role:** Tier 1 — Lead author; developed the 1D kinematic snow-melting framework and sensitivity analysis

---

## Overview

This paper uses a simple 1D kinematic cloud model coupled to the two-moment Milbrandt–Yau (MY2) microphysics scheme to perform quasi-idealized simulations of snow falling through a near-surface melting layer. Motivated by a specific case from the 2010 Vancouver Winter Olympics, the study examines how sensitive the timing and duration of the precipitation phase transition from snow to rain is to various parameter choices in the microphysics scheme. The key finding is that the modeled transition period can be quite sensitive to parameters specified within physically realistic ranges, with important implications for forecasting phase transitions at high-resolution NWP scales.

## Context and Motivation

Forecasting precipitation phase transitions in mountainous and coastal regions is particularly challenging when the melting level is close to the surface. During the 2010 Vancouver Winter Olympic and Paralympic Games, Environment Canada ran an operational 1-km GEM NWP model for the Vancouver-Whistler region. A heavy precipitation event on 13–14 February 2010 at Whistler Mountain, where diabatic cooling from melting snow is hypothesized to have induced a low-level flow reversal, provided an ideal observed case for examining the sensitivity of modeled phase transitions to microphysics. The SNOW-V10 research project provided detailed observational data including Doppler radar.

## Key Scientific Contributions

- Developed a simple 1D kinematic modeling framework coupled to an operational-grade two-moment microphysics scheme (MY2), capable of simulating the snow-melting process in a near-surface melting layer
- Quantified the sensitivity of the modeled precipitation phase transition to: (1) number of prognostic moments, (2) snow mass–diameter ($m$–$D$) parameters, (3) fall velocity–diameter ($V$–$D$) parameters, (4) treatment of aggregation, and (5) minimum slope parameter $\lambda_{s,\min}$
- Demonstrated that a one-moment scheme cannot simulate gravitational size-sorting, fundamentally changing the snow sedimentation structure and hence the diabatic cooling profile
- Identified a known deficiency in most bulk microphysics schemes: when snow melts, the liquid immediately becomes rain, whereas in nature a snowflake retains liquid until it collapses into a drop — leading to systematic overestimation of the mixed-phase transition period
- Proposed the 1D model as a potential operational forecasting tool: a single run takes only seconds, enabling ensemble-style sensitivity testing in real time

## Methods Summary

The 1D kinematic model is initialized with the 0000 UTC 14 February 2010 sounding at VOC near Whistler Mountain. A snow field is prescribed at 1600 m AGL based on observed radar reflectivity (25 dBZ) and temperature (−5°C), yielding $q_s = 0.45$ g kg$^{-1}$ and $N_s = 3115$ m$^{-3}$. The model has 47 evenly-spaced levels ($\Delta z = 35$ m), time step 10 s, and is integrated for 8 h. Nine sensitivity experiments (EXP1–EXP9) test variations in snow parameterization parameters.

## Key Results

- **CTR (control):** Realistically simulates the nearly isothermal layer near 0°C below the melting level, and surface precipitation rates of 1–2 mm h$^{-1}$ consistent with observations at VOT
- **EXP1 (one-moment):** Delays onset of surface precipitation but then results in faster phase transition; highlights the role of gravitational size-sorting in two-moment schemes
- **EXP3 ($V$–$D$ parameters, slower snow):** Greatly increases the duration of the phase transition — the choice of snow fall speed parameters has the largest sensitivity
- **EXP4 (aggregation off):** Increases cooling and dramatically shortens the transition period
- **EXP7 (high $\lambda_{s,\min}$):** Imposes smaller mean snow sizes, slower fall velocities, faster melting — similar to turning off aggregation
- All simulations exhibit unrealistically long mixed-phase transition periods due to the scheme's treatment of melting snow

## Limitations and Caveats

- The 1D kinematic model has no dynamical feedback: vertical motion does not respond to diabatic forcing, so induced downdrafts cannot be simulated
- Only quasi-qualitative links to NWP model behavior can be made
- All simulations overestimate the mixed-phase transition period due to the inherent limitation of treating melted snow as immediately becoming rain
- Results are specific to one case (Whistler Mountain, February 2010)

## Relation to Author's Research Program

This paper represents Milbrandt's continued work on evaluating and improving the MY2 scheme in a controlled, idealized framework. It follows the sedimentation study (Milbrandt and McTaggart-Cowan 2010) and the IMPROVE-2 sensitivity studies (Milbrandt et al. 2010) in using simplified frameworks to isolate microphysics behavior. The paper also directly motivates subsequent improvements to MY2's treatment of melting snow (later incorporated into the scheme). The 1D modeling approach introduced here would later prove useful for operational applications at Environment Canada.

## Impact and Citations

**Citation count:** ~15 (Semantic Scholar, retrieved 2026-06-06)

This is a smaller, specialized paper focused on a specific application: the 2010 Vancouver Olympics and precipitation phase forecasting in complex terrain. The 15 citations reflect its niche scope — it addresses a practical NWP forecasting challenge (phase transitions in mountain weather) rather than a broadly adopted scheme component. The paper has been cited in the context of precipitation phase transition modeling and cold-season NWP evaluation. The 1D modeling framework described here was subsequently used in operational settings at Environment Canada and motivates a community interest in inexpensive but physically consistent phase-transition test beds.

## Related topics
- [[ice-phase-modernization]]
