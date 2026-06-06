# Summary: Morrison and Milbrandt (2011)

**Full citation:** Morrison, H., and J. A. Milbrandt, 2011: Comparison of two-moment bulk microphysics schemes in idealized supercell thunderstorm simulations. *Mon. Wea. Rev.*, **139**, 1103–1130.
**Journal:** *Monthly Weather Review*
**Year:** 2011
**Authors:** H. Morrison (NCAR), J. A. Milbrandt (Environment Canada)
**DOI:** 10.1175/2010MWR3433.1

---

## Overview

This paper compares the behavior of two widely used two-moment bulk microphysics schemes — the Morrison (MOR) scheme and the Milbrandt–Yau (MY) scheme — in identical idealized 3D supercell simulations using WRF. Despite the overall similarity of the two schemes, the baseline simulations produce strikingly different storms: MOR yields ~3× higher surface precipitation and a much stronger cold pool. A systematic set of sensitivity experiments identifies the primary culprits: the treatment of rimed-ice (graupel vs hail) and raindrop breakup. The paper is a landmark intercomparison that established the community's understanding of the key sources of uncertainty in two-moment bulk microphysics for deep convection.

## Context and Motivation

By 2010, two-moment bulk schemes had become standard for convection-permitting NWP and research, with the Morrison and Milbrandt–Yau schemes among the most widely deployed. The MY scheme had been compared to its own one-moment version (MY06b) and tested against observations (IMPROVE-2), but a head-to-head comparison between two major two-moment schemes in a controlled identical framework had not been published. This gap was significant: if two schemes of comparable sophistication produce very different storms, modelers need to understand why — both to interpret their results correctly and to identify which parameterization choices are most consequential for improving schemes. The paper directly addresses this need, using the MY supercell simulation (MY06a,b) as its benchmark framework.

## Key Scientific Contributions

- Demonstrated that two comparably detailed two-moment schemes produce substantially different supercell simulations even in an identical modeling framework, with MOR generating ~3× more surface precipitation and a ~3–4 K stronger cold pool than MY in their baseline configurations.
- Identified **graupel vs hail as the dominant control**: MOR-BASE uses a single hail category; MY-BASE is dominated by graupel (hail contributes <0.1% of the frozen condensate above the freezing level). Switching either scheme to a single graupel-only or hail-only configuration reveals that the choice of rimed-ice type largely explains the baseline discrepancy: hail-only runs (from either scheme) are similar to each other, as are graupel-only runs.
- Showed that **including hail in the MY baseline had negligible impact** because of uncertainties in hail initiation, highlighting a fundamental limitation: having two rimed-ice categories does not guarantee that both contribute meaningfully.
- Demonstrated that **raindrop breakup parameterization strongly affects cold pool strength** in MOR but less so in MY, because other processes in MY inherently produce smaller rain drops. The aggressive drop-size limiter ($D_{mr,max} = 0.9$ mm) in MOR-BASE compensates for MOR's tendency to otherwise produce large rain drops (from large hail melting to large drops), partially reconciling the two baseline cold pools.
- Showed that fall velocity parameters (V–D relations) rather than bulk density are the first-order driver of the graupel-vs-hail difference in cold pool and precipitation.
- Issued an important community warning: **two-moment schemes do not converge simply due to added complexity**; the uncertainties in rimed-ice and breakup parameterizations mean that scheme-to-scheme spread can rival or exceed moment-count differences.

## Methods Summary

All simulations used WRF 3.1 with identical model configuration: 200×200-km domain, 1-km horizontal and ~500-m vertical grid spacing, model lid at 20 km, 6-s time step. Weisman–Klemp (1982, 1984) sounding; Weisman–Rotunno (2000) quarter-circle supercell hodograph with shear to 7 km (40 m s⁻¹ length); 3-K thermal perturbation to initiate convection; 2-h integration. Seventeen simulations total (Table 1): two baselines (MOR-BASE, MY-BASE), plus sensitivity experiments isolating the effects of: single vs dual rimed-ice category (graupel vs hail), bulk density, V–D parameters, and four raindrop breakup parameterizations at two $D_{mr,max}$ settings.

## Key Results

- **Baseline:** MOR-BASE accumulated precipitation ~3× MY-BASE at $t = 60$ and 120 min; minimum $\theta'$ (cold pool) 3–4 K colder in MOR-BASE at $t = 60$ min (Table 2).
- **Graupel vs hail:** Graupel-only and hail-only runs are internally consistent across both schemes (MY-GRPL ≈ MOR-GRPL; MY-HAIL ≈ MOR-BASE). The key mechanism: hail falls faster → quicker delivery to the melting layer → more melting → more rain → more evaporation → stronger cold pool.
- **Effect of hail in MY-BASE:** MY-GRPL ≈ MY-BASE (hail has negligible impact in MY-BASE), explaining why MY-BASE resembles MOR-GRPL despite MOR-BASE using hail.
- **Breakup sensitivity:** Very sensitive in MOR (6.4 K difference in $\theta'_{min}$ between MOR-DMR5 and MY-DMR5 when breakup is minimized); less sensitive in MY because other processes (autoconversion, smaller hail → smaller drops after melting) keep $D_{mr}$ small.
- **MY-DMR0.9** (MY-HAIL with $D_{mr,max} = 0.9$ mm): produces the strongest cold pool of any simulation ($\theta'_{min} = −9.11$ K at $t = 60$ min, $−11.40$ K at $t = 120$ min), comparable to MOR-BASE, demonstrating the large effect of the drop size limiter.

## Limitations and Caveats

- Idealized framework: fixed sounding and hodograph, no surface fluxes, no radiation, simplified boundary conditions; results may not generalize to all storm types or environments ⚠ verify.
- Grid spacing (1 km horizontal, ~500 m vertical) may be insufficient to resolve some microphysical processes accurately.
- The specific parameter choices in both schemes (baseline configurations) were the versions released at the time, which have since been updated ⚠ verify (updated scheme configurations may behave differently).
- No specific recommendations for parameter settings are made; only idealized comparisons — real-case validation against observations is required to determine the most realistic settings.
- A single hodograph and sounding; the regime-dependence of these findings was not examined (different hodographs or storm modes may produce different sensitivities).

## Relation to Author's Research Program

This paper represents a new phase in Milbrandt's program: **external benchmarking and community intercomparison**. It is first-authored by H. Morrison (NCAR), with Milbrandt as the second author and expert on the MY scheme. The collaboration reflects the growing adoption of the MY scheme beyond ECCC (WRF implementation) and the need to understand how it compares to the Morrison scheme — arguably the most widely used two-moment scheme in the research community at the time ⚠ verify. The paper's finding that the MY baseline is dominated by graupel (with hail having negligible impact) is essentially a critique of the hail-initiation parameterization in MY, and the follow-on work on variable graupel density ⚠ verify (referenced in Milbrandt et al. 2012) and the P3 scheme's elimination of separate rimed-ice categories (Morrison and Milbrandt 2015) are directly motivated by the graupel/hail uncertainty identified here. The cold-pool and dynamics findings also directly link to Milbrandt's earlier results in MY06b and to the 2010 IMPROVE-2 work.

## Impact and Citations

**Citation count:** ~210 (Semantic Scholar, retrieved 2026-06-06)

With ~210 citations, this is the most-cited single paper in Milbrandt's corpus so far processed, and one of the most influential scheme-comparison papers in the bulk microphysics literature ⚠ verify. It is a standard reference in studies that compare or evaluate two-moment schemes for deep convection ⚠ verify, and the finding that graupel-vs-hail choice dominates inter-scheme differences is widely cited in the microphysics and storm-simulation literature ⚠ verify. The paper's recommendation for further observational study of ice PSDs and particle properties has influenced subsequent measurement campaigns and microphysics development efforts ⚠ verify.
