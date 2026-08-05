# Summary: Korolev et al. (2020)

**Full citation:** Korolev, A., I. Heckman, M. Wolde, A. S. Ackerman, A. M. Fridlind, L. A. Ladino, R. P. Lawson, J. Milbrandt, and E. Williams, 2020: A new look at the environmental conditions favorable to secondary ice production. *Atmos. Chem. Phys.*, **20**, 1391–1429.
**Journal:** Atmospheric Chemistry and Physics (ACP)
**Year:** 2020
**Authors:** Alexei Korolev, Ivan Heckman, Mengistu Wolde, Andrew S. Ackerman, Ann M. Fridlind, Luis A. Ladino, R. Paul Lawson, Jason Milbrandt, Earle Williams
**DOI:** 10.5194/acp-20-1391-2020
**Author's role:** Tier 3 — Contributing co-author (7th of 8 authors); Milbrandt contributed as an ECCC team member, likely providing cloud microphysics parameterization expertise and contributing to the observational campaigns using ECCC's Convair 580 aircraft ⚠ verify

---

## Overview

This 39-page study uses airborne in situ observations in tropical mesoscale convective systems and midlatitude frontal clouds to identify, for the first time with robust observational evidence, the environmental conditions favorable to secondary ice production (SIP). By tracking small faceted hexagonal ice crystals ($L_{max} < 100$ µm) as near-real-time tracers of recent SIP, the study assesses the relative roles of six candidate SIP mechanisms and concludes that the freezing-drop shattering mechanism — not the commonly modeled Hallett–Mossop rime splintering — is the most likely dominant mechanism in the observed cloud systems. The findings have direct implications for improving SIP parameterizations in cloud microphysics schemes used in NWP models.

## Context and Motivation

Secondary ice production has been recognized since the 1960s as a fundamental cloud microphysical process needed to explain the ubiquitous discrepancy of up to 5 orders of magnitude between ice nucleating particle (INP) concentrations and observed ice crystal concentrations. Despite decades of work, the dominant physical mechanisms responsible for SIP remained poorly established. The Hallett–Mossop (HM) rime splintering process — which operates only at temperatures between −3 and −8°C during graupel riming — is the only mechanism routinely parameterized in cloud microphysics schemes (including multi-moment bulk schemes such as MY2 and P3), yet observations consistently show ice concentrations exceeding HM predictions. A new approach to observationally constrain the conditions for SIP was needed.

## Key Scientific Contributions

- Establishes a methodology for using small faceted hexagonal ice crystals ($L_{max} < 100$ µm) as tracers of recent SIP, based on a rigorous timescale analysis showing such crystals cannot have migrated far from their generation environment ($\tau_{corr} \sim 60$–120 s)
- Uses a convolutional neural network to identify small faceted ice crystals in Cloud Particle Imager (CPI) imagery with 96% accuracy, enabling systematic quantitative analysis across many flight hours
- Demonstrates that SIP occurs right above the melting layer starting at temperatures as warm as $-0.5°C$ — far warmer than the HM temperature range
- Identifies the freezing-drop shattering mechanism (large drops recirculated above the melting layer by convective updrafts, colliding with and shattering on aged ice) as the most likely dominant SIP mechanism by process of elimination
- Finds that HM rime splintering conditions (graupel + liquid water at $-3$ to $-8°C$) were frequently not met in observed SIP regions
- Presents a conceptual chain-reaction model of SIP near the melting layer involving drop recirculation by convective updrafts

## Methods Summary

Airborne in situ observations with ECCC's Convair 580 research aircraft in two settings: (1) tropical oceanic mesoscale convective systems during 13 flights at temperatures $-15°C < T_a < 0°C$; (2) midlatitude frontal clouds during the BAIRS2/WERVEX project (24 March 2017). Instruments include the Cloud Particle Imager (CPI), UHSAS (ultra-high sensitivity aerosol spectrometer), and standard cloud microphysics probes. A convolutional neural network identifies small hexagonal faceted ice crystals in CPI images. SIP regions are identified by elevated concentrations of small faceted crystals ($N_{pr100}$ up to 500–1000 L$^{-1}$). Correlation analysis (30 and 60 s averaging intervals) links small crystal concentrations to ambient droplet size distributions, updraft strength, and aged rimed ice presence.

## Key Results

- SIP was observed in all tropical MCS cases and in midlatitude frontal clouds; concentration of small faceted ice crystals peaked at 500–1000 L$^{-1}$
- Best correlation between small faceted crystal concentration and liquid droplet concentration was for $D > 60$ µm drops in tropical MCSs and $D > 40$ µm in frontal clouds
- SIP consistently initiated immediately above the melting layer at $T_a$ as warm as $-0.5°C$ — well outside the HM temperature range
- In many cases, neither graupel nor liquid water were observed in SIP regions, ruling out HM rime splintering as the active mechanism
- Concentrations of frozen drops exceeded expected INP concentrations by many orders of magnitude ($10^{-6}$–$10^{-3}$ L$^{-1}$), confirming that SIP rather than primary ice initiation is responsible
- The minimum splinter size during SIP was estimated at $\leq 10$ µm based on CPI video and crystallographic arguments
- In tropical MCSs, SIP regions vertically correlate with coldest cloud tops, suggesting coupling with deep convective dynamics

## Limitations and Caveats

- Aircraft observations are 1D penetrations of 3D cloud systems; the initial and boundary conditions of the studied cloud systems are poorly known, and parcel trajectories are not identifiable
- Conclusions are largely qualitative; concentrations of small faceted crystals provide a lower bound on SIP (some SIP particles may be irregular and not identified by the algorithm)
- The study cannot fully quantify the relative efficiencies of the competing SIP mechanisms — only identify which are most consistent with the observations
- Airborne techniques face fundamental limitations in identifying the major mechanisms of SIP; laboratory data providing clear and repeatable evidence of specific mechanism strengths are still lacking

## Relation to Author's Research Program

Milbrandt is the 7th of 8 authors. As a microphysics scheme developer at ECCC (MY2, P3), his involvement in this study is directly relevant to his core research: the paper explicitly cites multi-moment bulk schemes including "Milbrandt and Yau (2005)" as examples of schemes in which SIP is parameterized only as the Hallett–Mossop process, and frames improved SIP parameterization as a necessary next step. The ECCC Convair 580 aircraft was central to the observational data collection, and Milbrandt likely contributed both to campaign support and to the interpretation of results in the context of parameterization needs. The findings have direct implications for future development of the MY2 and P3 schemes, as drop shattering should eventually be added as a SIP mechanism beyond the HM process.

## Impact and Citations

**Citation count:** ~122 (Semantic Scholar, retrieved 2026-06-06)

This is a highly cited paper within the cloud microphysics community, reflecting the significance of establishing a new observational methodology for identifying SIP conditions and providing the first robust evidence that drop shattering — rather than Hallett–Mossop — may be the dominant SIP mechanism in many cloud types. The 122 citations reflect uptake in laboratory studies of drop freezing and shattering, modeling studies evaluating SIP parameterizations, and field campaign analyses seeking to validate or extend the findings to other cloud regimes. It has established the use of small faceted ice crystals as SIP tracers as a standard analysis approach.
