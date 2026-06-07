# Summary: Thériault et al. (2006)

**Full citation:** Thériault, J. M., R. E. Stewart, J. A. Milbrandt, and M. K. Yau, 2006: On the simulation of winter precipitation types. *J. Geophys. Res.*, **111**, D18202. DOI: 10.1029/2005JD006665
**Journal:** Journal of Geophysical Research – Atmospheres
**Year:** 2006
**Authors:** Julie M. Thériault, Ronald E. Stewart, Jason A. Milbrandt, M. K. Yau
**DOI:** 10.1029/2005JD006665
**Author's role:** Tier 3 — Provided the Milbrandt–Yau (2005) double-moment bulk microphysics scheme as the model foundation; co-author at McGill University supporting lead student Thériault's thesis work

---

## Overview

This paper describes a 1-D cloud model study of winter precipitation type formation, built around a modified version of the Milbrandt–Yau double-moment bulk microphysics scheme. By systematically varying temperature and moisture profiles, it investigates how six precipitation types — freezing rain, ice pellets, snow, slush, wet snow, and refrozen wet snow — form and interact within a column where snow falls through a temperature inversion. A key finding is that semimelted particles (wet snow, slush) fundamentally alter which precipitation types appear at the surface and in what quantities.

## Context and Motivation

Predicting winter precipitation type is critical for hazard assessment, but a physically rigorous simulation framework capturing the full spectrum of types — including partly melted and refrozen particles — did not exist. Prior observational studies (e.g., Zerr 1997) had characterized atmospheric sounding environments associated with different surface types, but without a microphysics scheme capable of representing semimelted particles, model simulations could not reproduce the observed diversity of winter precipitation. This paper directly addresses that gap.

## Key Scientific Contributions

- Extended the Milbrandt–Yau (2005) double-moment bulk scheme to include semimelted hydrometeor categories (wet snow, slush, refrozen wet snow), enabling simulation of the full spectrum of winter precipitation types
- Demonstrated that semimelted particle formation dramatically increases the diversity of precipitation types and is the dominant pathway for ice pellet production in many scenarios (slush freezing, not just rain refreezing)
- Quantified the melting and refreezing parameter regimes associated with five key precipitation-type combinations (ZR, IP, ZR-IP, IP-RWS-S, ZR-IP-SL-RWS-S) and compared to Zerr (1997) observations
- Showed that some precipitation-type combinations (those involving semimelted particles) form only within very narrow atmospheric profile windows, while others (ZR, IP) form across broad conditions
- Identified observational gaps: semimelted particles are not operationally reported, limiting model validation

## Methods Summary

A one-dimensional column model was configured with continuous snow input (5 mm h$^{-1}$) falling from 3 km into a temperature inversion structure. The Milbrandt-Yau (2005) double-moment bulk microphysics scheme was modified to add semimelted categories. Systematic parameter sweeps varied surface temperature, melting layer depth and peak temperature, and subfreezing layer depth and minimum temperature. Melting ($\beta_M$) and refreezing ($\beta_F$) parameters from Zerr (1997) were used to characterize each precipitation-type regime and compared to observational data.

## Key Results

- With semimelted particles: up to eight hydrometeor types form (cloud, rain, freezing rain, graupel, wet snow, refrozen wet snow, slush, ice pellets); without them: only four (cloud, rain, graupel, freezing rain)
- Semimelted particles reduce freezing rain at the surface by providing additional ice pellet production pathways (collisional freezing, slush refreezing)
- ZR associated with warm, deep melting layer and shallow subfreezing layer; IP with cool, shallow melting and deep subfreezing
- IP-RWS-S and ZR-IP-SL-RWS-S only form in a narrow window near 0°C inversion maximum
- Model results broadly consistent with Zerr (1997) sounding-based observational climatology, with expected differences due to simplified profile structure

## Limitations and Caveats

- 1-D framework cannot represent horizontal advection, storm dynamics, or the spatiotemporal variability observed in real winter storms
- Semimelted particle thresholds (0–1°C, diameter-independent) are approximate given very limited observational constraints
- Maximum inversion temperature limited to 6°C; observed freezing rain occurs at inversions up to ~10°C
- No direct comparison to in situ semimelted particle observations (none operationally reported)

## Relation to Author's Research Program

This paper is directly rooted in Milbrandt's microphysics scheme development: the entire study is built on the MY2005 double-moment framework, which is extended here for the winter precipitation context. Milbrandt was a co-author at McGill University at the time, working alongside his PhD supervisor M. K. Yau and collaborator R. E. Stewart. His contribution was the microphysics scheme foundation and co-mentorship of lead student Thériault. The paper represents an early application of the MY scheme to a domain (winter precipitation types) beyond the convective storms it was originally designed for, demonstrating its versatility.

## Impact and Citations

**Citation count:** ~65 (Semantic Scholar, retrieved 2026-06-06)

With 65 citations, this paper has had solid impact in the winter precipitation community. It is frequently cited in studies of freezing rain, ice pellet formation, and winter storm microphysics, and contributed to a line of work by Thériault and collaborators on winter precipitation processes. The semimelted particle framework introduced here ⚠ verify influenced subsequent operational and research approaches to winter precipitation prediction ⚠ verify.

---
