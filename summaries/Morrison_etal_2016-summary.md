# Summary: Morrison et al. (2016)

**Full citation:** Morrison, H., A. A. Jensen, J. Y. Harrington, and J. A. Milbrandt, 2016: Advection of coupled hydrometeor quantities in bulk cloud microphysics schemes. *Mon. Wea. Rev.*, **144**, 2809–2829. DOI: 10.1175/MWR-D-15-0368.1
**Journal:** Monthly Weather Review
**Year:** 2016
**Authors:** Hugh Morrison, Anders A. Jensen, Jerry Y. Harrington, Jason A. Milbrandt
**DOI:** 10.1175/MWR-D-15-0368.1
**Author's role:** Tier 3 — Contributing co-author; provided the P3 and MY microphysics scheme implementations and microphysics expertise; the SFVT method was tested against the P3 scheme in WRF squall-line simulations

---

## Overview

This paper addresses a fundamental numerical issue in multimoment bulk microphysics schemes: how to advect multiple coupled hydrometeor quantities (e.g., mass and number mixing ratios) in a physically consistent and computationally efficient way. The authors derive conditions for which derived intensive microphysical properties (such as the PSD shape parameter) are preserved during advection, then propose a new method — Scaled Flux Vector Transport (SFVT) — that reduces computational cost by 10–15% while matching the accuracy of the conventional independent-advection approach.

## Context and Motivation

Multimoment bulk microphysics schemes predict two or more prognostic variables per hydrometeor category (e.g., mass mixing ratio $Q$ and number mixing ratio $N$). The PSD and process rates depend on derived intensive properties (e.g., mean particle size $\propto (Q/N)^{1/3}$, or the three-moment shape parameter $\mu$) that are functions of the advected variables. During numerical advection, errors arise from separately transporting each scalar with nonlinear limiters. This leads to the question: when are derived intensive properties physically consistent (i.e., preserved when they should be uniform)? This had not been addressed systematically for multimoment bulk schemes. The paper fills this gap and proposes an efficient solution.

## Key Scientific Contributions

- Derived general analytic criteria for functional forms of intensive microphysical quantities (ratios of generalized power series of advected variables) that are preserved under Linear Cloud Advection (LCA) using linear or semilinear advection schemes
- Showed that the Milbrandt–Yau (2005) three-moment shape parameter $\mu = a_2 G^2 + a_1 G + a_0$ (where $G = NZ/Q^2$) meets these criteria and is preserved during LCA, despite its complicated form
- Proposed the SFVT method: mass mixing ratios ($Q$) are advected using the model's full nonlinear scheme; secondary scalars ($N$, $Q_\text{rim}$, $B_\text{rim}$) are advected by scaling the $Q$ fluxes with linear weighting functions
- Demonstrated that SFVT reduces wall clock time by 10.7–14.4% relative to traditional independent advection, while producing nearly identical solutions

## Methods Summary

Two types of tests: (1) 1D analytic advection tests with three initial profile shapes (TRI1, TRI2, STAIR) at multiple Courant numbers, comparing SFVT against traditional independent advection (TRAD) and analytic solutions; (2) idealized 2D squall-line simulations in WRF using the P3 microphysics scheme at 1 km horizontal resolution, comparing SFVT configurations (WRF-PD-5-SFVT, WENO-5-SFVT, and others) against traditional advection and reference schemes (WSM6, Thompson). Computational cost measured as mean wall clock time per time step from three runs each.

## Key Results

- SFVT mean errors are similar to TRAD in 1D analytic tests across all Courant numbers and profile shapes
- 2D squall-line solutions with SFVT are virtually identical to TRAD: histograms of Z, precipitation rate, ice mass, and rime mass fraction show no systematic biases
- Computational cost reduction: 10.7% (WRF-PD-5-SFVT), 11.7% (WENO-5-SFVT), 14.4% (WENO-3-SFVT)
- P3 with SFVT is 22–24% faster than WSM6 or Thompson (one- and partially two-moment schemes using traditional advection), despite P3 having equal or more prognostic variables
- Preserving monotonicity of derived intensive quantities (WRF-PD-5M-SFVT) has little impact, suggesting this constraint is not important in practice

## Limitations and Caveats

- SFVT does not guarantee monotonicity of intensive derived properties; this is argued to be unimportant in practice based on tests
- Tests are limited to idealized 1D and 2D cases; real-case 3D performance was not evaluated in this paper
- Efficiency gains depend on the cost of the nonlinear advection scheme; benefits are reduced for cheaper advection methods (e.g., hole-filling vs. flux limiters)
- Efficiency gains also reduced if grid-tile communication is a significant cost factor

## Relation to Author's Research Program

Milbrandt is the fourth (and last) author on this paper. His primary contribution was providing the P3 scheme (which he co-developed with Morrison) and the MY three-moment scheme as the test cases for SFVT. The SFVT method was specifically motivated by and demonstrated with the P3 scheme in WRF. The paper explicitly builds on the Milbrandt–Morrison P3 framework (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016), making it directly relevant to Milbrandt's research program even though the SFVT method itself was developed by Morrison and colleagues. SFVT's greatest potential is for multi-category P3 and bin schemes — areas Milbrandt subsequently worked on.

## Impact and Citations

**Citation count:** ~17 (Semantic Scholar, retrieved 2026-06-06)

The paper is a niche technical contribution addressing a specific numerical issue in multimoment microphysics advection. The relatively modest citation count reflects its specialized scope. Its impact is indirect: SFVT was incorporated into the P3 scheme development pathway and is directly relevant to any multimoment scheme seeking to improve computational efficiency. The paper is cited in subsequent P3 and multi-moment scheme development work.
