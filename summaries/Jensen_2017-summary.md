# Summary: Jensen et al. (2017)

**Full citation:** Jensen, A. A., Harrington, J. Y., Morrison, H., and Milbrandt, J. A. (2017): Predicting Ice Shape Evolution in a Bulk Microphysics Model. *Journal of the Atmospheric Sciences*, **74**, 2081–2104. DOI: 10.1175/JAS-D-16-0350.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2017
**Authors:** Anders A. Jensen, Jerry Y. Harrington, Hugh Morrison, Jason A. Milbrandt
**DOI:** 10.1175/JAS-D-16-0350.1
**Author's role:** Tier 3 — Contributing co-author; Milbrandt's P3 scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016) and the Milbrandt–Morrison (2013) graupel density paper are key intellectual precursors that ISHMAEL builds upon; Milbrandt contributed scientific guidance and was included as an author likely for his domain expertise in predicted-particle-property bulk schemes

---

## Overview

This paper describes and tests ISHMAEL (Ice-Spheroids Habit Model with Aspect-Ratio Evolution), a novel bulk microphysics scheme that predicts the evolution of ice particle shape (aspect ratio) in addition to mass, number, and density. By modeling ice as spheroids whose aspect ratios evolve during vapor growth and riming, ISHMAEL captures transitional rimed states of ice — from unrimed through lightly rimed to densely rimed — without ad hoc conversion thresholds between predefined categories (e.g., snow → graupel). Tests against wind tunnel data and a 2D kinematic model show that habit-dependent riming produces a natural aspect ratio sorting of ice in physical space, leading to different spatial precipitation distributions than traditional bulk schemes.

## Context and Motivation

A fundamental limitation of traditional bulk microphysics schemes is the need to convert between predefined ice categories (snow, graupel) using ad hoc thresholds that cannot be directly measured and introduce artificial sensitivities. The P3 scheme (Morrison and Milbrandt, 2015) removed snow–graupel conversion by predicting rime mass fraction and rime density (Milbrandt and Morrison, 2013), but still constrained ice shape via fixed m–D relationships. ISHMAEL takes the next step by also predicting ice aspect ratio, enabling habit-dependent vapor growth and riming — processes that fundamentally depend on ice shape and are absent from both traditional and P3 schemes.

## Key Scientific Contributions

- Introduces ISHMAEL, the first bulk microphysics scheme to explicitly predict ice particle aspect ratio (shape) evolution during both vapor growth and riming
- Demonstrates that habit-dependent riming produces natural "aspect ratio sorting" of ice in physical space — an effect missing from all traditional models — which controls the spatial distribution of surface precipitation
- Shows that predicting transitional partially rimed states leads to reduced vapor growth rates and increased riming rates near the updraft, compared with traditional category-based conversion approaches
- Demonstrates that at low liquid water contents, isometric (nearly spherical) ice particles can rime while dendrites cannot — a physically important regime that traditional models cannot capture
- Shows that ISHMAEL's continuous ice evolution produces a more natural precipitation rate response when updraft dynamics change over time

## Methods Summary

ISHMAEL is based on the Adaptive Habit (AHAB) theory of Harrington et al. (2013a,b) and Chen and Lamb (1994) for vapor growth, extended to riming using the single-particle model of Jensen and Harrington (2015). Ice is modeled as spheroids with two primary ice species (nucleated by temperature) plus an aggregate species. Tests include: (1) vapor growth tests vs. wind tunnel data; (2) riming tests vs. wind tunnel data; (3) Lagrangian parcel comparison vs. a bin model; (4) 2D kinematic simulations with a simple updraft in high- and low-shear environments with five updraft strengths, compared against MY2 (Milbrandt–Yau two-moment scheme).

## Key Results

- ISHMAEL captures observed temperature-dependent ice habits during vapor growth and observed riming behavior from wind tunnel data
- In 2D kinematic simulations, MY2 produces precipitation over a larger spatial range than ISHMAEL; ISHMAEL produces a more monotonically decreasing precipitation distribution with distance from the updraft
- Aspect ratio sorting produces fast-falling rimed ice near the updraft and slow-falling pristine ice advected away — physically natural but impossible in traditional schemes
- Sensitivity experiments show that ISHMAEL's behavior approaches MY2 when snow–graupel conversion is added (CONV-AGG), confirming that the continuous ice evolution is responsible for the differences
- Predicting transitional rimed ice reduces total ice mass above 3 km and shifts energy from vapor growth to riming in the updraft

## Limitations and Caveats

- The 2D kinematic framework does not include full model dynamics; tests in a 3D NWP context are needed
- Comparison is primarily against MY2; broader evaluation against observations or other schemes is not included
- Riming of the aggregate species is not treated in detail in this paper
- Parameterization of secondary ice production and melting of spheroids is noted as future work

## Relation to Author's Research Program

Milbrandt's contributions to this paper are as a scientific advisor and domain expert in predicted-particle-property bulk schemes. The paper explicitly builds on Milbrandt's body of work: the P3 scheme (Morrison and Milbrandt, 2015; Milbrandt and Morrison, 2016 Part III) is the closest precursor, and the Milbrandt–Morrison (2013) graupel density scheme introduced the concept of predicting rime density. ISHMAEL extends the P3 philosophy — predicting ice properties rather than assuming predefined categories — to also include shape. The 2D kinematic simulations explicitly compare ISHMAEL against MY2 (Milbrandt–Yau), making Milbrandt's schemes both the scientific motivation and the baseline comparison. This paper represents the natural continuation of the P3 research program into shape-evolving ice, a direction that Milbrandt's work enables and directly informs.

## Impact and Citations

**Citation count:** ~88 (Semantic Scholar, retrieved 2026-06-06)

ISHMAEL has been adopted and further developed, and this paper is well-cited within the bulk microphysics development literature. It represents one of the most physically-based bulk ice schemes published to date, bridging the gap between single-particle theory (Jensen and Harrington, 2015) and full NWP application. Its emphasis on habit-dependent processes and natural ice sorting has influenced subsequent discussions of ice microphysics parameterization. The paper is a key reference for researchers working on next-generation bulk schemes that go beyond the P3/traditional framework.
