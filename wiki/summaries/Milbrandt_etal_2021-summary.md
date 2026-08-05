# Summary: Milbrandt et al. (2021)

**Full citation:** Milbrandt, J. A., H. Morrison, D. T. Dawson II, and M. Paukert, 2021: A triple-moment representation of ice in the Predicted Particle Properties (P3) microphysics scheme. *J. Atmos. Sci.*, **78**, 439–458. DOI: 10.1175/JAS-D-20-0084.1
**Journal:** Journal of the Atmospheric Sciences
**Year:** 2021
**Authors:** Jason A. Milbrandt, Hugh Morrison, Daniel T. Dawson II, Marco Paukert
**Author's role:** Tier 1 — Lead author; developed the triple-moment ice (sixth-moment PSD) extension to the P3 scheme

---

## Overview

This paper describes the extension of the P3 bulk microphysics scheme from a two-moment to a three-moment representation of the ice particle size distribution (PSD), through the addition of a fifth prognostic variable per ice category: the sixth moment of the PSD ($Z_{i,tot}$, analogous to the radar reflectivity factor). The key advance is that the PSD shape parameter $\mu$ can now vary independently from mean particle size, allowing physically based control of gravitational size sorting without an arbitrary size limiter. In idealized supercell simulations, the three-moment configuration produces larger, more realistic mean hail sizes and improved reflectivity compared to the original two-moment scheme.

## Context and Motivation

In the original two-moment P3 scheme, the shape parameter $\mu$ was prescribed by a diagnostic relation tied to the slope parameter $\lambda$. This prevented independent evolution of spectral dispersion and required imposing an artificial upper limit on the mass-weighted mean ice diameter ($D_{i,\text{limit}} = 2$ mm) to prevent runaway size sorting during sedimentation. As a result, P3 produced unrealistically small mean ice sizes in convective cores and poor dual-polarization radar signatures for hail (documented by Johnson et al. 2019). A three-moment approach — originally developed in the Milbrandt–Yau (MY05) scheme — was the natural solution: predicting a third independent moment allows $\mu$ to vary freely, physically narrowing the PSD as mean size increases and thereby controlling size sorting without an artificial limiter.

## Key Scientific Contributions

- Adds a fifth prognostic variable ($Z_{i,tot}$, the 6th moment of the PSD) to each P3 ice category, enabling triple-moment ice in a free (non-prescribed) ice-category framework — first such attempt in a property-based scheme
- Develops the mathematical framework to solve for $\mu$ from the three prognostic moments ($N_{i,tot}$, $Q_{i,tot}$, $Z_{i,tot}$) using the bulk density to approximate $M_3$
- Demonstrates that advecting $Z_{advect} = Z_{i,tot}/Q_{i,tot}$ (rather than $Z_{i,tot}$ directly) preserves $\mu$ and other PSD parameters during transport, consistent with Morrison et al. (2016)
- Removes the stringent mean ice size limiter; size sorting is now controlled physically via the freely varying $\mu$
- Shows through 1D and 3D simulations that 3-MOM controls size sorting while producing larger, more realistic mean hail sizes and reflectivity compared to both 2-MOM and a size-limiter-relaxed 2-MOM
- Tests an improved diagnostic-$\mu$ relation for two-moment ice as a lower-cost alternative; concludes it can partially compensate but the three-moment approach is preferable for physical consistency

## Methods Summary

**Model:** Cloud Model 1 (CM1) at 250-m isotropic grid spacing (~large-eddy-resolving for deep convection). Also 1-km grid spacing for comparison.

**Case:** Idealized non-tornadic, hail-producing supercell based on the 1 June 2008 Oklahoma storm. Single-ice-category P3 configuration ($n_\text{Cat} = 1$).

**Configurations compared:** 2-MOM (original), 2-MOM_DLIM (relaxed size limiter), 3-MOM (new), 2-MOM_DIAGMU (improved diagnostic-$\mu$), 3-MOM_ADVZ (advecting $Z_{i,tot}$ rather than $Z_{advect}$).

**Evaluation:** Visual comparison of cross-sectional fields ($Q_{i,tot}$, $\mu_i$, $\rho_i$, $D_m$, $D_{h,\text{max}}$, $Z_e$), surface precipitation and hail, 1D sedimentation tests. Maximum hail size $D_{h,\text{max}}$ diagnosed using the Milbrandt and Yau (2006a) critical-flux method (threshold $1.7 \times 10^{-4}$ m$^{-2}$ s$^{-1}$, applied to ice with $\rho_i > 750$ kg m$^{-3}$ and $F_{rim} > 0.75$).

## Key Results

- **2-MOM**: Artificially small mean ice sizes due to the 2-mm size limiter; simulated hail reflectivity and size are unrealistically suppressed
- **2-MOM_DLIM** (limiter removed, same diagnostic $\mu$): Mean sizes grow unrealistically large with no control on size sorting; excessive and unrealistic reflectivity
- **3-MOM**: $\mu$ increases in the hail growth region as mean size increases, physically narrowing the PSD and preventing runaway size sorting; produces larger, more realistic mean and maximum hail sizes and peak reflectivity than 2-MOM, without the artifacts of 2-MOM_DLIM
- Advecting $Z_{advect}$ rather than $Z_{i,tot}$ directly produces nonnegligible improvements in the anvil ice field and is recommended
- Conclusions are qualitatively similar at 1-km grid spacing, relevant to operational NWP
- The improved diagnostic-$\mu$ (2-MOM_DIAGMU) brings the two-moment configuration closer to 3-MOM for one storm type, but requires further validation

## Limitations and Caveats

- Only the single-ice-category configuration ($n_\text{Cat} = 1$) is examined; property dilution issues at high resolution are noted but not addressed
- Results are for a single idealized case (one supercell type); the improved diagnostic-$\mu$ relation particularly needs testing across diverse storm types
- Triple-moment ice is not yet merged with predicted liquid fraction (Cholette et al. 2019) or three-moment rain (Paukert et al. 2019) at time of publication
- Simulated polarimetric fields are not validated (deferred to future work)

## Relation to Author's Research Program

This paper is a direct continuation of the P3 development line initiated in Morrison and Milbrandt (2015) and Milbrandt and Morrison (2016), applying the triple-moment concept originally developed in the MY05 scheme (Milbrandt and Yau 2005a,b) to the free-category P3 framework. It addresses the most significant known weakness of two-moment P3 for convective applications — the inability to simulate large ice and hail — and is the fourth major publication in the P3 series. The triple-moment framework developed here (and its advection theory) is directly built upon in the 2025 JAMES paper (Milbrandt et al. 2025), which examines the additional impacts of predicted liquid fraction and multiple ice categories on hail simulation.

## Impact and Citations

**Citation count:** ~46 (Semantic Scholar, retrieved 2026-06-06)

This paper represents the primary reference for the triple-moment ice capability in P3. With 46 citations in ~5 years, it has been well-received within the microphysics community. The three-moment ice formulation has been incorporated into the operational ECCC P3 code (v5 ⚠ verify exact version adoption) and is the foundation for subsequent P3 developments including the merged triple-moment ice + predicted liquid fraction version described in Cholette et al. (2023). The paper's treatment of the advected variable for three-moment schemes (following Morrison et al. 2016) has also provided practical guidance for other BMS developers implementing triple-moment approaches.

## Related topics
- [[p3-modern-extensions]]
