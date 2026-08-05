# Summary: Morrison et al. (2020)

**Full citation:** Morrison, H., M. van Lier-Walqui, A. M. Fridlind, W. W. Grabowski, J. Y. Harrington, C. Hoose, A. Korolev, M. R. Kumjian, J. A. Milbrandt, H. Pawlowska, D. J. Posselt, O. P. Prat, K. J. Reimel, S.-I. Shima, B. van Diedenhoven, and L. Xue, 2020: Confronting the challenge of modeling cloud and precipitation microphysics. *J. Adv. Model. Earth Syst.*, **12**, e2019MS001689. DOI: 10.1029/2019MS001689
**Journal:** Journal of Advances in Modeling Earth Systems
**Year:** 2020
**Authors:** Hugh Morrison + 15 co-authors (Milbrandt is 9th of 16)
**DOI:** 10.1029/2019MS001689
**Author's role:** Tier 3 — Contributing co-author; contributed domain expertise in bulk microphysics scheme development (particularly P3 and MY schemes), informed the paper's discussion of multimoment and particle-property-predicting approaches to the representation problem

---

## Overview

This commissioned 68-page review paper provides a broad, community-oriented assessment of the fundamental challenges in representing cloud and precipitation microphysics in atmospheric models. It identifies two distinct problem categories — representing hydrometeor populations and closing knowledge gaps in microphysical process rates — and proposes a hierarchical path forward that combines Lagrangian particle-based modeling, sustained laboratory and field observations, and a Bayesian statistical-physical framework for scheme development. With 378 citations it has become a widely-read manifesto for the microphysics modeling community.

## Context and Motivation

Microphysics parameterization has been a persistent source of uncertainty in weather and climate models for decades. As models push toward convection-permitting resolutions (1–4 km, now standard at many operational centers globally) ⚠ verify, microphysics is no longer hidden beneath convective parameterization and its errors become more directly visible. The paper argues that: (a) traditional bulk and bin approaches face fundamental representational limitations; (b) process-level uncertainty (especially for ice) is severe and largely unresolved; and (c) the field needs a more systematic, statistically rigorous approach to scheme development.

## Key Scientific Contributions

- Framed the microphysics parameterization problem as two distinct challenges: particle-population representation and process-level knowledge gaps
- Advocated Lagrangian particle-based ("super-droplet") schemes as the most physically principled path forward for the population problem, with a rigorous convergence argument toward DNS
- Articulated specific knowledge gaps in ice nucleation, secondary ice production, ice particle habit/density evolution, and collision processes
- Proposed a statistical-physical framework using Bayesian inference to constrain microphysics scheme parameters from observations — framing scheme development as an inverse problem
- Provided six specific community recommendations for accelerating microphysics model improvement
- Proposed a hierarchical approach linking laboratory experiments → Lagrangian/bin models → statistical-physical bulk scheme development → observational constraint

## Methods Summary

This is a review and perspective paper, not an original research study. The paper synthesizes the existing literature across bulk schemes, bin schemes, Lagrangian particle-based schemes, cloud physics process understanding, observational methods, and statistical modeling. No new simulations or datasets are presented. Key framework contributions are conceptual: the two-challenge decomposition, the statistical-physical Bayesian framework, and the hierarchical development blueprint. Supporting figures are schematic (process diagrams, model hierarchy diagrams, framework flowcharts).

## Key Results

- Lagrangian particle-based schemes have gained traction over the past decade and are expected to become standard tools in cloud research modeling within the next decade
- Laboratory work in cloud physics has apparently declined over the past several decades — this is argued as a critical gap to address
- The microphysics inverse problem (observations constrain schemes only indirectly) is naturally addressable using Bayesian inference with MCMC sampling, analogous to approaches already used in hydrology and land surface modeling
- Traditional bulk scheme development, based on heuristics and ad hoc tuning, has inherent limitations compared to systematic statistical-physical approaches
- The P3 and MY schemes are cited as examples of schemes that have addressed the particle-population problem in more physically consistent ways (using predicted particle properties rather than fixed ice categories)

## Limitations and Caveats

- The paper is a perspective/manifesto rather than a verification of specific claims — the proposed frameworks are largely not yet demonstrated at scale
- The Bayesian approach, while advocated, requires substantial technical development and computational infrastructure not yet in place for operational microphysics development
- Lagrangian schemes still face unresolved challenges in representing collection processes (super-particle merging/splitting) and turbulence coupling

## Relation to Author's Research Program

Milbrandt is the ninth of sixteen co-authors on this invited review. His contribution was as a domain expert in bulk microphysics scheme development: the P3 scheme and MY scheme — both products of Milbrandt's primary research program — are prominent examples throughout the paper, illustrating the particle-property-prediction approach to the representation problem. The paper explicitly cites Morrison and Milbrandt (2015) and Milbrandt and Morrison (2016) as key developments in addressing representational challenges. Milbrandt also contributed to the ECCC perspective on operational model microphysics (GEM/P3 context). The paper provides a broader intellectual framing that situates Milbrandt's primary research contributions within the field's overall challenges and priorities.

## Impact and Citations

**Citation count:** ~378 (Semantic Scholar, retrieved 2026-06-06)

This is one of the most widely cited recent papers on cloud microphysics parameterization, reflecting its status as a community-consensus review and forward-looking manifesto. Its high citation count (~378 as of mid-2026) reflects both the breadth of the topic and the authority of the authorship team, which spans bulk schemes, bin schemes, Lagrangian methods, observations, and statistical modeling. The paper is widely assigned in graduate courses and cited in proposals and papers across weather, climate, and cloud physics communities ⚠ verify.
