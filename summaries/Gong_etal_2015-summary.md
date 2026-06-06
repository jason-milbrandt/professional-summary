# Summary: Gong et al. (2015)

**Full citation:** Gong, W., P.A. Makar, J. Zhang, J. Milbrandt, S. Gravel, K.L. Hayden, A.M. Macdonald, and W.R. Leaitch, 2015: Modelling aerosol–cloud–meteorology interaction: A case study with a fully coupled air quality model (GEM-MACH). *Atmos. Environ.*, **115**, 695–715.
**Journal:** Atmospheric Environment
**Year:** 2015
**Authors:** W. Gong et al. (8 authors; Milbrandt is 4th)
**DOI:** 10.1016/j.atmosenv.2015.05.062
**Author's role:** Tier 3 — provided the Milbrandt–Yau double-moment (MYDM) microphysics scheme used in GEM-MACH and contributed cloud microphysics expertise

---

## Overview

This paper introduces and evaluates an aerosol–cloud microphysics feedback mechanism in Canada's operational on-line air quality forecast model, GEM-MACH. The aerosol indirect effect is activated by coupling the on-line, size-resolved aerosol information from the chemistry module to the Milbrandt–Yau two-moment cloud microphysics scheme for droplet nucleation. Evaluated against aircraft observations from the ICARTT 2004 campaign over Michigan, the feedback substantially improved model predictions of cloud droplet number concentration, liquid water content, and downstream air chemistry.

## Context and Motivation

Regional air quality models have historically run with one-way coupling: meteorology influences chemistry but chemistry cannot feed back into meteorology. As Environment Canada's GEM-MACH moved to full on-line coupling, a key missing link was the aerosol indirect effect — the ability of model-predicted aerosols to influence cloud droplet number concentration ($N_d$) and thus cloud microphysics. This required a double-moment microphysics scheme (one that predicts both mass and number concentration) rather than the single-moment schemes used operationally at that time. The MY scheme filled this role.

## Key Scientific Contributions

- Implemented a two-way aerosol–cloud feedback in GEM-MACH using the Abdul-Razzak–Ghan (AR-G) activation scheme coupled to the Milbrandt–Yau double-moment (MYDM) microphysics scheme, allowing on-line aerosols to influence $N_d$ and hence cloud development.
- Demonstrated that this feedback substantially improves model predictions of cloud amount, LWC, and $N_d$ for a stratocumulus case over the U.S. Midwest (ICARTT 2004), where the non-feedback base case dramatically under-predicted $N_d$ and cloud extent.
- Showed that the feedback has downstream effects on air chemistry: increased cloud coverage decreased surface O₃ via reduced photolysis and increased PM₂.₅ sulphate via enhanced aqueous-phase oxidation.
- Quantified the sensitivity of aerosol activation to the parameterization of cloud-scale updraft velocity, identifying this as a major source of model uncertainty in aerosol indirect effect calculations.
- Found that modelled aerosol size distribution differences have little impact on $N_d$ at relevant activation diameters (~80 nm), but do affect the size distribution of cloud-processed aerosols.

## Methods Summary

The fully coupled GEM-MACH model is run in nested domains (15 km → 2.5 km) for 10 August 2004. The 2.5-km inner domain uses the MYDM microphysics scheme with the AR-G aerosol activation scheme replacing the original Cohard nucleation. Multiple sensitivity experiments vary the updraft velocity used in the activation calculation. Evaluation uses in-situ aerosol (SMPS/APS size distributions, Q-AMS sulphate), cloud (LWC, $N_d$), and gas-phase (CO, NO₂, O₃, SO₂) measurements from two NRC Convair 580 flights through stratocumulus downwind of the Chicago industrial plume.

## Key Results

- Base case $N_d$: average < 10 cm⁻³, maximum ~30 cm⁻³ — far below observed average of ~150 cm⁻³.
- ARG0 feedback $N_d$: average ~200 cm⁻³, median ~120 cm⁻³ — much closer to observations.
- Cloud droplet mass-mean diameter reduced from ~30–40 μm (base) to ~20 μm (feedback), consistent with aerosol indirect effect.
- LWC increased by ~0.6 g kg⁻¹ on average in the feedback run; the base case missed cloud coverage almost entirely at 23 Z during Flight 17.
- LWP increased by 0.5–2 kg m⁻² in the feedback run, reducing surface shortwave flux and lowering surface air temperature by up to 2°C.
- ARG1 run (with observation-based 0.6 m s⁻¹ updraft) gave the best match to observed cloud fraction (29% modelled vs. 31% observed) and $N_d$.
- The feedback enhanced sulphate mass from 2.8 to 3.8 μg m⁻³ in-cloud, due to increased LWC driving more aqueous-phase oxidation.

## Limitations and Caveats

- Single case study (one day, one region); generalizability to other cloud types or aerosol regimes is not established.
- Organic aerosol is severely under-predicted by the model (~10% of observations), affecting the modelled aerosol size distribution below the activation diameter range.
- The choice of cloud-scale updraft velocity for the AR-G activation scheme is a major unresolved uncertainty; parameterizations vary substantially and none is clearly best.
- Results apply only to resolved-scale clouds; sub-grid convection and boundary-layer clouds do not receive the aerosol feedback in this framework.

## Relation to Author's Research Program

Milbrandt is the 4th author. His contribution was providing the MY double-moment scheme (MYDM), which was specifically required for this work: the aerosol–cloud feedback mechanism depends on having a cloud microphysics scheme that predicts $N_d$ as a prognostic variable — something the single-moment schemes in GEM's physics library cannot do. The paper is one of several in the AQMEII-2 suite that used MYDM in GEM-MACH and is relevant to Milbrandt's research program as an example of the MY scheme enabling air quality research beyond its original NWP microphysics context.

## Impact and Citations

**Citation count:** ~77 (Semantic Scholar, retrieved 2026-06-06)

This is a well-cited paper in the on-line (coupled) air quality modelling literature, reflecting the community's interest in aerosol–cloud–meteorology feedbacks in regional forecast models. It is part of a broader AQMEII-2 suite of papers and is frequently cited in the context of online coupled weather-chemistry model development and evaluation. ⚠ verify specific citing papers
