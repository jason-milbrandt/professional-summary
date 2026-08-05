# Summary: Milbrandt and Yau (2006a) — Part III

**Full citation:** Milbrandt, J. A., and M. K. Yau, 2006: A multimoment bulk microphysics parameterization. Part III: Control simulation of a hailstorm. *J. Atmos. Sci.*, **63**, 3114–3136.
**Journal:** *Journal of the Atmospheric Sciences*
**Year:** 2006
**Authors:** J. A. Milbrandt, M. K. Yau
**DOI:** 10.1175/JAS3816.1
**Author's role:** Tier 1 — Lead author; designed and ran the first 3D three-moment cloud-resolving supercell simulation (Pine Lake hailstorm)

---

## Overview

This paper is the third in the four-part series that introduced the Milbrandt–Yau (MY) multimoment bulk microphysics scheme. It presents the first 3D cloud-resolving simulation using the full three-moment version of the scheme, applied to a real severe hailstorm — the 14 July 2000 "Pine Lake" supercell in Alberta, Canada. The simulated storm reproduced many observed gross features (propagation, bounded weak echo region, hook echo, mesocyclone, reflectivity magnitudes, surface precipitation), and the paper introduces a novel method for diagnosing physically observable maximum hail sizes from the three predicted moments of the gamma size distribution.

## Context and Motivation

Parts I and II (Milbrandt and Yau 2005a,b) established the theoretical case for multimoment schemes and described the complete six-category scheme with one-, two-, and three-moment options, but validation had been confined to idealized 1D kinematic frameworks. The key open question was whether the three-moment method — which lets the spectral shape parameter $\alpha$ evolve independently via a predicted radar reflectivity — would produce realistic results in a full 3D, full-physics simulation coupled to model dynamics. This is, to the authors' knowledge, the first cloud-resolving simulation ever performed with a three-moment bulk scheme. Hail was chosen as the focus because hail size matters both scientifically (it affects storm dynamics) and practically (it is observable at the ground, providing a rare validation target).

## Key Scientific Contributions

- Demonstrated the first 3D cloud-resolving simulation using a fully three-moment bulk microphysics scheme, coupled to the Canadian MC2 mesoscale model and nested from synoptic scale (12 km) down to 1 km.
- Showed that the three-moment MY scheme produces a realistic supercell, reproducing observed storm-scale features (BWER, hook echo, mesocyclone, suspended overhang, HP-supercell classification) and quantitatively matching radar reflectivity (model core 50–60 dBZ vs observed 51–54 dBZ) and accumulated precipitation.
- **Introduced two new diagnostic parameters for inferring physically observable maximum hail size from a bulk scheme:** $N_h^*\{D^*\}$, the number concentration of hail larger than threshold $D^*$ (Eq. 3), and $R_h^*\{D^*\}$, the corresponding surface flux (Eq. 4), with proposed critical thresholds ($N^*_{CRIT} = 10^{-4}$ m⁻³; $R^*_{CRIT} = 10^{-3}$ m⁻² s⁻¹).
- Established that the mean-mass diameter $D_{mh}$ is a poor indicator of large hail (because the hail category spans small frozen drops to large stones), and that the higher moments captured by the three-moment scheme are required to identify large hail meaningfully.
- Provided a physical, mechanistic explanation (threefold: advection, microphysical source/sink terms, sedimentation) of how $\alpha$ can locally *decrease* in a three-moment scheme, despite sedimentation tending to increase it — an effect impossible to represent in fixed- or diagnosed-$\alpha$ schemes.
- Confirmed via simulated rain spectra that the predicted shape parameter range ($\alpha_r \sim 2.5$–4.3) matches the observed range of gamma-fit shape parameters from disdrometer measurements in other systems (Uijlenhoet et al. 2003: 2.11–5.00).

## Methods Summary

The 14 July 2000 Pine Lake supercell was simulated with the fully compressible, nonhydrostatic MC2 model using one-way self-nesting through three domains (12, 3, 1 km grid spacing). Initial and boundary conditions came from the CMC regional analysis (GEM-based). The 1-km control run (**CNTR**) used the three-moment version of the Part II scheme and ran from 2:00 P.M. to 8:00 P.M. local time. Validation was primarily by comparison to C-band radar observations (ODA and Carvel radars), including reflectivity structure, VIL (as a large-hail surrogate), storm track, and accumulated precipitation. Because no in situ microphysical measurements were available, simulated hydrometeor fields were compared to published microphysical observations from other storms. The new $N_h^*$ and $R_h^*$ parameters were applied at the time of peak hail precipitation (3:45 h / 5:45 P.M.) to infer maximum observable hail size.

## Key Results

- The simulated storm propagated at 48–52 km h⁻¹ (observed 46–52 km h⁻¹), both moving to the right of the steering flow, with a slight northward bias in the model.
- Updraft intensified rapidly at 4:30 P.M., peaking at 33 m s⁻¹; peak precipitation rates (3:45 h) were 185 (total), 166 (liquid), and 87 mm h⁻¹ (solid).
- Modeled core reflectivity (50–60 dBZ, >60 dBZ at 6:30 P.M.) closely matched observed core values (51–54 dBZ); the storm reproduced a BWER, hook echo, and mesocyclone.
- Simulated hydrometeor magnitudes (mass contents, number concentrations, mean sizes) were consistent with published observations from other storms.
- Using $R_h^*$ at peak hailfall, the model produced a **significant flux of grape- and walnut-sized hail (2–3 cm) at the surface but negligible golf ball–sized hail** — i.e., max simulated hail size 2–3 cm versus observed golf ball–sized hail, a reasonable agreement.
- The maximum mean hail diameter aloft was 18.4 mm; the surface mean diameter was only 3.4 mm at the location of maximum hail, underscoring that $D_{mh}$ alone cannot indicate large hail.

## Limitations and Caveats

- A single case study with no in situ microphysical observations; validation of microphysical fields rests on comparison to observations from *other* storms, which the authors explicitly state does not constitute rigorous validation.
- The observed storm had been cloud-seeded for hail suppression; seeding was not modeled, and its effect on observed hail sizes is unknown (the authors argue this is a second-order uncertainty relative to the lack of in situ data).
- The model failed to capture the observed reintensification of large hail after ~6:45 P.M., though the authors attribute this to dynamics rather than the microphysics.
- The critical thresholds $N^*_{CRIT}$ and $R^*_{CRIT}$ used to delineate "observable" hail are acknowledged as subjective.
- The prestorm shear (~20 m s⁻¹) was only marginally sufficient for supercell maintenance, making the simulated regime sensitive to perturbations (relevant to the Part IV sensitivity runs).

## Relation to Author's Research Program

This paper is the practical proving ground for the MY scheme that Milbrandt developed during his doctoral work with M. K. Yau. Where Parts I and II built the theory and the closure, Part III demonstrates that the three-moment approach works in a realistic 3D NWP setting — a necessary step before the scheme could be adopted operationally or in research models (e.g., WRF, GEM) ⚠ verify. The $N_h^*$ / $R_h^*$ hail-size diagnostics introduced here are a distinctive methodological contribution tied to the unique information content of a three-moment scheme, and the mechanistic analysis of $\alpha$ evolution deepens the physical understanding begun in Part I. The paper directly sets up Part IV (the sensitivity experiments) by defining this simulation as the control run, and the recognition that the hail category awkwardly spans small frozen drops to large stones foreshadows the motivation for the later Predicted Particle Properties (P3) scheme (Morrison and Milbrandt 2015), which replaces rigid ice-phase categories with continuously evolving particle properties.

## Impact and Citations

**Citation count:** ~62 (Semantic Scholar, retrieved 2026-06-06)

As the application/demonstration paper of the four-part MY series, Part III is cited less heavily than the foundational Parts I and II (which together exceed 1,200 citations), but it holds a specific niche as the first 3D cloud-resolving simulation with a three-moment bulk scheme and as the origin of the $N_h^*$/$R_h^*$ hail-size diagnostics. It is cited in the hail-modeling and convective-storm microphysics literature, particularly in studies concerned with simulating and verifying hail size from bulk schemes, and it is a standard reference for the real-world validation pedigree of the MY scheme that was subsequently implemented across multiple community NWP models ⚠ verify.

## Related topics
- [[hail-diagnostics]]
- [[milbrandt-yau-scheme]]
