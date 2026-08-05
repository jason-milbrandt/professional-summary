# Summary: Milbrandt, Thériault, and Mo (2012)

**Full citation:** Milbrandt, J. A., J. Thériault, and R. Mo, 2012: Modeling the phase transition associated with melting snow in a 1D kinematic framework: Sensitivity to the microphysics. *Pure Appl. Geophys.*, **171**, 303–322 (2014 in print; published online 2012).
**Journal:** *Pure and Applied Geophysics*
**Year:** 2012 (online); 2014 (in print)
**Authors:** J. A. Milbrandt, J. Thériault, R. Mo
**DOI:** 10.1007/s00024-012-0552-y
**Author's role:** Tier 1 — Lead author; developed the 1D kinematic snow-melting framework and sensitivity analysis

**Note on PDF files:** Both `Milbrandt_etal2012_PAAG.pdf` and `Milbrandt_etal_2012-1Dsnowmelting.pdf` are the same paper. The latter is the final print version (2014); the former is the online-first version (2012). Only one article-md has been created (`Milbrandt_etal_2012_PAAG.md`).

---

## Overview

This paper uses a simple 1D kinematic cloud model coupled to the two-moment Milbrandt–Yau scheme (MY2) to examine how sensitive the simulated snow-to-rain phase transition is to specific parameterization choices for the snow category. The case is a heavy precipitation event near Whistler Mountain during the 2010 Vancouver Winter Olympics, where diabatic cooling from melting snow is hypothesized to have driven an observed low-level flow reversal. Nine sensitivity experiments test: number of prognostic moments, mass–diameter relation, fall velocity–diameter relation, aggregation treatment, and minimum allowable slope parameter. The main conclusion is that when the melting level is close to the ground, the predicted timing and duration of the phase transition can be highly sensitive to snow parameterization details — and that all tested configurations produce an unrealistically long mixed-phase period due to a fundamental limitation in how BMSs represent snow melting.

## Context and Motivation

Accurate prediction of precipitation phase near the melting level is critically important for high-impact weather in mountainous coastal regions — and particularly so for the Vancouver 2010 Winter Olympics, where Environment Canada was running a special 1-km GEM forecast system in real time. The IMPROVE-2 Part II paper (Milbrandt et al. 2010) had just shown that scheme-identity differences (latent heat effect, instantaneous melting) matter more than number-of-moments differences for orographic precipitation; the closing comment in that paper announced that "modernization of the MY snow category is underway." This paper directly follows up: it uses the same MY2 scheme (with snow-category updates already in progress) in an idealized 1D framework to quantify which snow parameters most affect the phase transition — a targeted process study that complements the full 3D model work and is motivated by operational needs.

## Key Scientific Contributions

- Demonstrated that the **timing and duration of the snow-to-rain phase transition** — a key forecast challenge in coastal mountainous regions — can be quite sensitive to snow parameterization choices that are within realistic physical ranges.
- Showed that **one-moment vs two-moment** snow significantly changes the sedimentation profile and hence the cooling rate and phase transition timing, consistent with prior 1D sedimentation work; but noted that the specific behavior depends strongly on how $N_{0s}$ is prescribed in the one-moment configuration.
- Showed that **fall velocity parameters have the largest single impact** on the transition period: slower V–D parameters (EXP3) greatly extended the phase transition; the choice of snow fall speed is the dominant sensitivity for this case.
- Showed that **aggregation treatment matters**: shutting aggregation off entirely produced a dramatically shorter phase transition (faster cooling), but doubling the aggregation rate had negligible effect — suggesting the baseline aggregation rate may already be too high in phase-transition situations.
- Showed that **the minimum allowable slope parameter $\kappa_{s,min}$** (an upper limit on mean snow size) can significantly affect the transition period, through its effects on fall speed and melting rate.
- Identified and articulated a **fundamental BMS limitation**: all configurations produce an unrealistically long mixed-phase period because the BMS cannot represent partially melted snow (in nature, a snowflake retains liquid on its surface and increases its fall speed as it melts; in the BMS, melted mass immediately becomes separate rain). Announced that a fix (estimating the liquid fraction of partially melted snow and adjusting fall velocities accordingly) is under development, with results to be reported in a future paper.
- Proposed and described a **potential application of the 1D model as a forecaster's tool**: a rapid ensemble of perturbed-parameter simulations or "what-if" experiments (each taking seconds on a desktop) could be used in real-time operational settings where high-resolution NWP models are expected to have large errors in precipitation phase.

## Methods Summary

The 1D kinematic cloud model was initialized from the 0000 UTC 14 February 2010 sounding at VOC (near Whistler Mountain), with a prescribed snow field at the model top (1600 m AGL) based on the observed 25-dBZ radar reflectivity and −5°C temperature (yielding $q_s = 0.45$ g kg⁻¹, $N_s = 3115$ m⁻³). The two-moment MY2 scheme was used (the same version as in the real-time operational GEM system during the Games). Model settings: 47 levels, 35-m vertical spacing, 10-s time step, 8-h integration. Nine sensitivity tests were compared to a control (CTR) and to observations of the precipitation rate, surface temperature evolution, and sounding structure.

## Key Results

- **CTR**: Realistically simulated the nearly isothermal layer below 500 m AGL (matching the 0600 UTC sounding), and precipitation rates of 1–2 mm h⁻¹ consistent with observations. An unrealistically long mixed-phase transition period (simultaneous rain + snow for ~280 min) was present in all runs.
- **EXP1 (one-moment)**: Delayed onset of snow at surface by ~130 min; stronger diabatic cooling; surface temperature approaches 0°C ~140 min earlier.
- **EXP2 (original spherical-snow m–D)**: Little effect on the melting simulation.
- **EXP3 (slower Ferrier V–D)**: Phase transition period greatly extended; surface temperature drops much more slowly.
- **EXP4 (no aggregation)**: Shorter transition period with faster cooling and surface temperature drop.
- **EXP5 (2× aggregation rate)**: Negligible differences from CTR.
- **EXP6 (no effective $\kappa_{s,min}$)**: Little effect for this case (CTR values already above the 500 m⁻¹ limit).
- **EXP7 ($\kappa_{s,min} = 1000$ m⁻¹)**: Increased cooling rate, delayed snow at surface, shorter transition period — snow restricted to smaller mean sizes → slower fall and faster melting.

## Limitations and Caveats

- Single case study; conclusions about sensitivity may be case-dependent ⚠ verify.
- The 1D model has no dynamical feedback — diabatic cooling cannot induce downdrafts that would modify the flow (the observed low-level flow reversal involves dynamics not captured by a kinematic model).
- Results from the idealized 1D model are not directly translatable to a full 3D NWP model, but are qualitatively indicative of the same sensitivities.
- The BMS's long mixed-phase transition period is acknowledged as a fundamental limitation; results describing transition timing are contaminated by this artifact.

## Relation to Author's Research Program

This paper is part of the snow-category modernization program announced in IMPROVE-2 Part II (Milbrandt et al. 2010), which closed with "changes to the snow category are currently underway and will be reported in a forthcoming paper." It is the process-study companion to the snow-density/SLR paper (Milbrandt et al. 2012, *Mon. Wea. Rev.*), which documents the implemented snow-category updates. The two together — one examining the sensitivity of the phase transition to snow parameters, the other documenting the new parameters and their SLR forecasting application — constitute the core of the snow-category modernization of the MY scheme. The 1D forecaster's tool concept proposed here also connects to the operational NWP context at ECCC (the real-time GEM system for the 2010 Winter Olympics) and anticipates the kind of tool that would be valuable for precipitation-type forecasting in mountainous regions. The collaboration with Thériault ⚠ verify (whose expertise is precipitation-type classification and microphysics of mixed-phase precipitation) reflects growing breadth in Milbrandt's research network.

## Impact and Citations

**Citation count:** ~15 (Semantic Scholar, retrieved 2026-06-06)

As a single-case process study in a specialized journal (*Pure and Applied Geophysics*), this paper has modest citation count, consistent with its narrower scope ⚠ verify. Its significance is primarily within the trajectory of Milbrandt's own research program (as the process-study foundation for the snow-category updates) and for the precipitation-phase forecasting community in mountainous coastal regions ⚠ verify.

## Related topics
- [[ice-phase-modernization]]
