# Summary: Gultepe and Milbrandt (2007)

**Full citation:** Gultepe, I., and J. A. Milbrandt, 2007: Microphysical Observations and Mesoscale Model Simulation of a Warm Fog Case during FRAM Project. *Pure Appl. Geophys.*, **164**, 1–18.
**Journal:** Pure and Applied Geophysics
**Year:** 2007
**Authors:** I. Gultepe, J. A. Milbrandt (2 authors; Milbrandt is 2nd)
**DOI:** 10.1007/s00024-007-0212-9
**Author's role:** Tier 3 — ran the MC2 mesoscale model simulation using the Milbrandt–Yau triple-moment microphysics scheme to demonstrate the new fog visibility parameterization in an NWP context

---

## Overview

This paper develops and evaluates a new fog visibility parameterization that depends on both liquid water content (LWC) and cloud droplet number concentration ($N_d$), improving over existing NWP visibility schemes that rely on LWC alone. Observations from the FRAM (Fog Remote Sensing And Modeling) project in Ontario (winter 2005–2006) are used to derive the parameterization, and MC2 mesoscale model simulations using the Milbrandt–Yau multi-moment bulk microphysics scheme are used to demonstrate its application, with simulated visibility corrections of up to 20–50% over single-variable approaches.

## Context and Motivation

Existing NWP fog visibility parameterizations (e.g., Kunkel 1986; Stoelinga and Warner 1999) use LWC as the sole independent variable. However, observations show that $N_d$ can vary by two orders of magnitude for a fixed LWC, and neglecting $N_d$ can introduce visibility errors exceeding 50%. Demonstrating the new parameterization in an NWP model required a microphysics scheme that predicts $N_d$ and LWC independently — specifically a double- or multi-moment scheme. The MY scheme fulfilled this requirement.

## Key Scientific Contributions

- Derived a new fog visibility parameterization: $\text{Vis} \propto (\text{LWC} \cdot N_d)^{-0.65}$, validated against FRAM in-situ observations, with visibility corrections of 20–50% over LWC-only parameterizations.
- Developed new parameterizations for fog droplet settling rate and LWC-weighted terminal velocity as functions of LWC and $N_d$.
- Demonstrated that the new parameterization can be applied in an NWP model using the MC2 with the Milbrandt–Yau triple-moment scheme, producing simulated fog visibility values consistent with FRAM surface observations.
- Showed that if $N_d$ is not independently predicted by the cloud scheme, a diagnostic $N_d$ from environmental variables (T, moisture) can still enable use of the new parameterization in single-moment models.

## Methods Summary

FRAM observations at the CARE site (Toronto, ON; Dec 2005–Apr 2006) provide in-situ LWC, $N_d$, and visibility data. The 4 January 2006 warm fog case is simulated with MC2 (nested: 10-km outer, 2-km inner domain, 41 vertical levels) using the Milbrandt–Yau triple-moment scheme for resolved-scale microphysics. Fog visibility is diagnosed from model-predicted cloud mass and number concentration using the new parameterization.

## Key Results

- Observed $N_d$ during fog: a few cm⁻³ to ~100 cm⁻³; corresponding LWC: ~0.1 g m⁻³; visibility: 30–500 m.
- Bimodal droplet size spectra were observed, with drizzle-size drops (>15 μm) forming a second mode; neglecting these leads to ~50% overestimate of visibility.
- Simulated $N_d$ (50–200 cm⁻³) and LWC (0.02–0.30 g m⁻³) over the CARE site were broadly consistent with observations.
- Simulated fog visibility (50–500 m) broadly agreed with observed range (30–500 m).

## Limitations and Caveats

- Single case study (one fog event); generalizability to other fog types (marine, advection, ice fog) remains to be demonstrated.
- The parameterization was derived primarily from warm-temperature stratiform cloud data; applicability to cold-season or mixed-phase fog needs further validation.
- Model $N_d$ overestimated at 21 UTC (~200 cm⁻³ vs. observed ~100 cm⁻³ at the CARE site).
- MWR LWC values were elevated by coincident rain, complicating direct comparison with model cloud LWC.

## Relation to Author's Research Program

Milbrandt is the 2nd author of this 2-author paper. His role was to run the MC2 mesoscale model simulation using the triple-moment version of the Milbrandt–Yau (MY) bulk microphysics scheme and to provide the scheme for the NWP demonstration. The paper is outside Milbrandt's primary research focus (bulk microphysics for precipitation and deep convection), but it is directly relevant in demonstrating the practical utility of the MY scheme's multi-moment capability in a fog context — a use case not originally envisioned when the scheme was developed. The paper shows that the ability to independently prognose $N_d$ and LWC, a design feature of MY, enables downstream applications beyond storm-scale microphysics.

## Impact and Citations

**Citation count:** ~108 (Semantic Scholar, retrieved 2026-06-06)

This is a well-cited paper in the fog forecasting and cloud microphysics literature, reflecting widespread interest in improved visibility parameterizations for NWP applications. It is regularly cited in fog modelling and observational studies, particularly those evaluating the role of $N_d$ in visibility predictions. The ~108 citations indicate the paper became an important reference for the community working on fog and low-visibility forecasting. ⚠ verify specific citing papers
