# Summary: Thériault et al. (2012)

**Full citation:** Thériault, J. M., R. Rasmussen, T. Smith, R. Mo, J. A. Milbrandt, M. M. Brugman, P. Joe, G. A. Isaac, J. Mailhot, and B. Denis, 2012: A Case Study of Processes Impacting Precipitation Phase and Intensity during the Vancouver 2010 Winter Olympics. *Wea. Forecasting*, **27**, 1301–1325.
**Journal:** Weather and Forecasting
**Year:** 2012
**Authors:** Julie M. Thériault, Roy Rasmussen, Trevor Smith, Ruping Mo, Jason A. Milbrandt, Melinda M. Brugman, Paul Joe, George A. Isaac, Jocelyn Mailhot, Bertrand Denis
**DOI:** 10.1175/WAF-D-11-00114.1
**Author's role:** Tier 3 — Provided the Milbrandt–Yau (2005) double-moment bulk microphysics scheme used in all GEM-LAM configurations for the Vancouver 2010 Olympics NWP system; contributed NWP expertise from the Atmospheric Numerical Prediction Research group at Environment Canada (Montreal)

---

## Overview

During the 2010 Vancouver Winter Olympics, a winter storm with near-0°C temperatures on 13–14 February 2010 created a critical forecasting challenge: would precipitation at the Whistler alpine venues be rain or snow? This paper analyzes the storm using dense observations from the SNOW-V10 field project, high-resolution GEM-LAM model runs (15-km, 2.5-km, 1-km), and 1D microphysics sensitivity experiments, demonstrating that diabatic cooling of melting snow — not synoptic-scale warm advection — dominated precipitation evolution during the first 6 hours of the event.

## Context and Motivation

The Vancouver 2010 Winter Olympics required precipitation forecasts at unprecedented accuracy for venues where rain vs. snow could determine whether competitions could proceed safely. Synoptic models predicted warm temperatures and rain at Whistler, but the observed rain–snow transition was near competition elevation, creating high uncertainty. This study is one of several SNOW-V10 papers (Isaac et al. 2012, Joe et al. 2010/2012, Mo et al. 2012, Mailhot et al. 2010/2012) that collectively document the science behind the Olympic weather forecasting effort.

## Key Scientific Contributions

- Demonstrated that diabatic cooling due to snow melting created a sustained 0°C isothermal layer for ~6 h, keeping precipitation as snow rather than rain at lower elevations despite synoptic-scale warm advection
- Showed that evaporation of rain dominated initial cooling (~first 60 min) while melting snow cooling dominated thereafter — two competing diabatic processes acting in sequence
- Quantified the role of precipitation rate in deepening the 0°C isothermal layer using 1D sensitivity experiments (higher rates → deeper isothermal layer → more snow at the surface)
- Demonstrated that the cool, dense air produced by diabatic cooling likely triggered the observed switch from up-valley to down-valley flow in the Whistler area
- Evaluated the GEM-LAM 1-km model's ability to capture diabatic processes and precipitation phase over complex terrain, finding reasonable skill but with temperature and wind speed biases at valley locations

## Methods Summary

The analysis combined: (1) observations from the SNOW-V10 network (dense surface stations, soundings, FD12P optical sensors, disdrometers, vertically pointing radar, C-band Doppler radar at VVO); (2) GEM model runs at 15-km, 2.5-km, and 1-km resolution, all using the double-moment Milbrandt–Yau (2005) bulk microphysics scheme; and (3) 1D kinematic cloud model sensitivity experiments initialized from the 0000 UTC 14 February 2010 sounding, varying precipitation rate from 1 to 5 mm h$^{-1}$ to isolate the diabatic cooling effect.

## Key Results

- Observations showed temperatures dropped to 0°C at lower elevations ~2 h after precipitation onset, coinciding with an isothermal layer that persisted for ~6 h
- Down-valley flow was observed and captured by radar, consistent with cold-air pooling from diabatic cooling
- 1D simulations with observed precipitation rates (2–3 mm h$^{-1}$) reproduced the observed temperature decrease; rates ≥3 mm h$^{-1}$ produced an isothermal layer reaching the surface
- GEM-LAM 1-km captured the general structure of the storm, especially at higher elevations, but underestimated the temperature drop at valley stations and misrepresented the depth of down-valley flow
- Final conclusion: diabatic cooling from melting snow is the primary cause of the rain-to-snow transition and should be accurately parameterized in NWP models for near-0°C winter storms in mountainous terrain

## Limitations and Caveats

- 1D model cannot account for horizontal warm-air advection, flow blocking, or adiabatic cooling/warming from vertical motion
- Model warm bias at lower valley elevations (e.g., VOD) partly attributed to wind speed biases and terrain representation limitations
- The relative contributions of flow blocking, adiabatic effects, and diabatic cooling to the valley-flow reversal could not be fully quantified
- Study is a single-case analysis; the generality of findings to other near-0°C events requires further work

## Relation to Author's Research Program

Milbrandt's connection to this paper is through the MY bulk microphysics scheme: the entire GEM-LAM NWP system used for the Vancouver Olympics used the double-moment Milbrandt–Yau (2005a,b) scheme in all three grid configurations (15, 2.5, and 1 km), and radar reflectivity computations also relied on the Milbrandt et al. (2008) parameterization. This is a SNOW-V10 paper (related to Joe_etal_2020, Isaac_etal_2012, Mo_etal_2012, and Mailhot_etal_2012 in Milbrandt's paper set) in which the MY scheme was a critical model component. The paper illustrates the operational deployment of the MY scheme in a high-profile real-time forecasting application.

## Impact and Citations

**Citation count:** ~22 (Semantic Scholar, retrieved 2026-06-06)

The paper has been cited primarily in winter precipitation and mountain meteorology literature, particularly studies of diabatic cooling effects on rain–snow transitions over complex terrain. Its context as part of the widely-cited SNOW-V10 publication cluster (many papers in that set have higher individual citation counts) makes it an important component of a well-known collective contribution to winter Olympics forecasting science.

---
