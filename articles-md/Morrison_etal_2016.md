# Advection of Coupled Hydrometeor Quantities in Bulk Cloud Microphysics Schemes

**Full citation:** Morrison, H., A. A. Jensen, J. Y. Harrington, and J. A. Milbrandt, 2016: Advection of coupled hydrometeor quantities in bulk cloud microphysics schemes. *Mon. Wea. Rev.*, **144**, 2809–2829. DOI: 10.1175/MWR-D-15-0368.1

**Authors:** Hugh Morrison, Anders A. Jensen, Jerry Y. Harrington, Jason A. Milbrandt  
**Journal:** Monthly Weather Review  
**Year:** 2016  
**Volume/Pages:** 144, 2809–2829

---

## Abstract

This paper discusses the advection of coupled hydrometeor quantities by air motion in atmospheric models. It is shown that any bulk property derived from a set of advected microphysical variables must meet certain conditions in order to be preserved during transport using linear or semilinear advection schemes when the property is initially uniform, with implications for physical consistency of the property. A new, efficient flux-based method for calculating hydrometeor advection, similar to vector transport applied previously in aerosol modeling, is also presented. In this method, called scaled flux vector transport (SFVT), lead scalars (the mass mixing ratios) are advected using the host model's unmodified advection scheme and secondary scalars (e.g., number mixing ratios) are advected by appropriately scaling the lead scalar fluxes. By design, SFVT retains linear relationships between the advected scalars. Analytic tests reveal that mean errors using SFVT are similar to those incurred using the traditional approach of separately advecting each variable. SFVT is applied to the multimoment predicted particle properties bulk microphysics scheme in idealized two-dimensional squall-line simulations using the Weather Research and Forecasting Model. The computational cost in total wall clock runtime is reduced by 10%–15% while producing solutions similar to the traditional approach. Thus, SFVT can reduce the overall cost of using multimoment bulk microphysics schemes, making them competitive with simpler schemes having fewer prognostic variables.

---

## 1. Introduction

The parameterization of cloud and precipitation microphysics is a key component of atmospheric modeling. It directly impacts distributions of latent heating and cooling and condensate loading, affecting buoyancy and dynamics. It is also critical for cloudy radiative transfer, cloud chemistry, and cloud–aerosol interaction.

Multimoment bulk microphysics schemes predict multiple moments of the particle size distribution (PSD), including two-moment schemes (e.g., Milbrandt and Yau 2005; Morrison et al. 2005), three-moment schemes, and schemes with prognostic variables for ice particle properties (e.g., Morrison and Milbrandt 2015; Milbrandt and Morrison 2016).

With the trend of including two or more prognostic variables for each hydrometeor category, an important question arises: how do numerical errors incurred during the physical transport of these coupled quantities affect schemes whose process rates depend on certain relationships between the advected variables?

Two basic constraints for advected variables in cloud microphysics schemes are previously established:
1. Advected microphysical variables must be extensive quantities (not intensive). Directly advecting intensive quantities can generate large errors from numerical diffusion and dispersion.
2. Consistency between prognostic variables and the advection algorithm when there are changes in fluid density.

Beyond these basic constraints, errors in microphysical quantities derived from two or more prognostic advected variables in multimoment schemes can still occur.

---

## 2. Criteria for the Preservation of Derived Microphysical Quantities

Nearly all schemes used in Eulerian atmospheric models to advect scalars apply techniques to ensure positive definiteness.

**Linear and semilinear advection schemes** preserve initial linear relationships between advected scalars. This linear property means that for linear cloud advection (LCA)—where the advected variables are all linearly related within a finite hydrometeor region and zero elsewhere—derived intensive quantities are preserved.

An intensive quantity $F(G_x)$ is expressed as a function of some set $G_x(S_y)$, where $S_y = \{S_1, S_2, S_3, ...\}$ is the set of advected variables. Writing each $G \in G_x$ as the ratio of two generalized power series:

$$G = \frac{\sum_{j=1}^{J} (a_j S_1^{b_{1,j}} S_2^{b_{2,j}} S_3^{b_{3,j}} \cdots)}{\sum_{k=1}^{K} (g_k S_1^{f_{1,k}} S_2^{f_{2,k}} S_3^{f_{3,k}} \cdots)}$$

For intensive microphysical quantities meeting the criteria derived in the paper, the diffusion and/or dispersion errors exactly cancel so that the quantities are preserved. A key result is that the PSD shape parameter $\mu$ from the three-moment bulk scheme of Milbrandt and Yau (2005), despite its complicated functional dependence on three prognostic advected moment variables ($Q$, $N$, $Z$), meets these criteria and hence is preserved for LCA. However, an initially uniform $\mu$ is not preserved if at least two of the advected variables are not linearly related.

---

## 3. Alternative Approaches for Advection of Coupled Scalar Quantities

### 3a. Discussion of previous methods

**Vector transport (VT):** A lead scalar is chosen; all other prognostic scalars related to the lead scalar are normalized. The lead scalar is advected using the full advection scheme; derived intensive properties are updated as linear combinations of pre-advection values from neighboring grid cells. VT preserves valid sets of derived properties and is computationally efficient, but can produce errors if spatial gradients of the lead and secondary scalars differ markedly, and requires reverse engineering of the host model's advection scheme.

**Nonnegative least squares method (McGraw 2007):** At each time step all extensive scalars are updated using the model's standard advection scheme applied independently. Results are combined, and inconsistencies are resolved using nonnegative least squares. Improves accuracy compared to VT but loses computational efficiency.

### 3b. Scaled Flux Vector Transport (SFVT)

The new method proposed in this paper. Similar to VT, a "lead" scalar is chosen and advected using the model's unmodified advection scheme. The hydrometeor mass mixing ratio $Q$ is recommended as the lead scalar for each hydrometeor category.

The fluxes of secondary scalars at the grid interfaces are calculated from scaling the $Q$ fluxes by $W(S)/W(Q)$, where $W$ is a linear weighting function and $S$ is the secondary scalar. The time tendencies of $S$ from advection are obtained by a standard flux divergence calculation of these scaled fluxes.

Three linear weighting functions $W$ are described: first-order ($W^{\text{First}}$), third-order ($W^{\text{Third}}$), and fifth-order ($W^{\text{Fifth}}$), analogous to respective flux calculation operators in WRF.

By design, SFVT with a linear $W$ preserves initial linear correlations. SFVT does not guarantee monotonicity of intensive quantities if they are initially nonuniform, unlike VT.

---

## 4. Results

### 4a. Description of advection schemes tested

Tested schemes in WRF: WRF-PD (positive-definite), WRF-MONO (monotonic), WENO (fifth-order weighted essentially nonoscillatory). SFVT was applied using fifth-order and third-order weighting functions.

### 4b. 1D Analytic Tests

Three cases: TRI1 (triangular $S_1$, top-hat $S_2$), TRI2 (triangular $S_2$, top-hat $S_1$), STAIR (two-step stairlike profile). Courant numbers ranging from 0.02 to 0.5.

**Key result:** SFVT gives similar mean errors compared to the traditional approach (TRAD) of independently advecting each scalar. Mean errors using SFVT with fifth-order weighting are generally comparable to TRAD for all three cases. Using a lower-order or first-order weighting for $S_2$ (WRF-MONO5, WRF-MONO1) gives considerably larger errors, indicating the benefit of the SFVT flux scaling approach.

### 4c. 2D Squall-Line Tests

Domain: 500 km × 20 km, 1 km horizontal grid spacing, 80 vertical levels (~225–290 m spacing). P3 microphysics scheme in WRF. Lead scalars: $Q_c$, $Q_r$, $Q_i$; secondary scalars: $N_r$, $N_i$, $Q_\text{rim}$, $B_\text{rim}$.

**Key result:** SFVT gives very similar results compared to the corresponding simulations using the traditional approach. Histograms of radar reflectivity $Z$, surface precipitation rate, total ice mass mixing ratio, and rime mass fraction show no systematic errors or biases between SFVT and TRAD tests.

**Computational cost (Table 8):**
- WRF-PD-5-SFVT: 10.7% reduction in wall clock time relative to WRF-PD
- WRF-PD-3-SFVT: 11.2% reduction
- WENO-5-SFVT: 11.7% reduction relative to WENO
- WENO-3-SFVT: 14.4% reduction
- P3 with SFVT is 22%–24% faster than WSM6 or Thompson microphysics using traditional advection

A simple monotonic adjustment operator for secondary scalars (WRF-PD-5M-SFVT) has only a limited impact on results, confirming that preserving monotonicity of derived quantities is not important for these tests.

---

## 5. Summary and Conclusions

- General analytic criteria were derived for functional forms of microphysical quantities that are preserved during LCA using linear or semilinear schemes.
- The PSD shape parameter $\mu$ in the three-moment MY scheme meets these criteria and is preserved for LCA, despite its complicated functional form.
- A new advection method, SFVT, was proposed. In SFVT, mass mixing ratios (lead scalars) are advected using the host model's unmodified scheme; secondary scalars are advected by scaling the lead scalar fluxes using linear weighting functions.
- SFVT reduces computational cost by 10%–15% in total wall clock runtime while producing solutions very similar to the traditional approach.
- SFVT makes multimoment bulk schemes competitive in cost with simpler one-moment schemes.
- SFVT is expected to be especially amenable to the multicategory version of P3 and bin microphysics schemes.

---

## References

[Key references cited in the paper include: Milbrandt and Yau (2005), Morrison and Milbrandt (2015), Milbrandt and Morrison (2016), Mansell et al. (2010), Wright (2007), McGraw (2007), Skamarock (2006), Jiang and Shu (1996), Wicker and Skamarock (2002)]
