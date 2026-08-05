# Sedimentation-Induced Errors in Bulk Microphysics Schemes

**Authors:** J. A. Milbrandt and R. McTaggart-Cowan (Meteorological Research Division, Environment Canada, Dorval, Quebec, Canada)

**Journal:** *Journal of the Atmospheric Sciences*, **67**, 3931–3948 (December 2010)

**Manuscript:** received 28 April 2010, in final form 4 August 2010

**DOI:** 10.1175/2010JAS3541.1

---

## Abstract

The computation of hydrometeor sedimentation in one-moment, two-moment, and three-moment bulk microphysics parameterizations is examined in the context of a 1D model, with no other microphysical processes active. The solution from an analytic bin model is used as a reference against which the bulk model simulations are compared. Errors in the computed (nonprognostic) moments from 0 to 7 from the bulk model runs are examined. In addition to the commonly used predicted variables (number concentration, mass, and reflectivity), bulk scheme configurations with alternative combinations of prognostic moments are considered.

While the extra degree of freedom in a two-moment scheme adds realism to the simulation of sedimentation over a one-moment scheme, the standard practice of imposing a constant relative dispersion in the particle size distribution results in considerable errors in some of the computed moments. The error can be shifted to different moments by selecting different prognostic moments. For three-moment schemes, the error is considerably reduced over a wide range of computed moments and there is much less sensitivity to the choice of prognostic variables.

Two alternative approaches are proposed for modifying the computation of sedimentation in two-moment schemes to reduce problems associated with excess size sorting. The first approach uses a diagnostic relative dispersion (shape) parameter, generalized for any pair of prognostic moments. The second involves progressively reducing the differential fall velocities between the moments and is therefore applicable for schemes that hold the shape parameter constant. Both approaches greatly reduce the errors in the computed moments, including those on which microphysical process rates depend, and are easily applied to existing two-moment schemes.

---

## 1. Introduction

In 3D atmospheric models run at the convective scale, cloud microphysical processes are computed by a bulk microphysics scheme (BMS). In a BMS, the particle size distribution (PSD) of each hydrometeor category is approximated by a continuous function with one or more free parameters, and one or more prognostic moments of the distribution are predicted. Nearly all early schemes predicted only a single moment — the third moment $M_3$, proportional to the mass content — while two-moment schemes have become more widely used (e.g., Milbrandt and Yau 2005b). Milbrandt and Yau (2005a, hereinafter MY05a) and Milbrandt and Yau (2005b) extended the bulk approach to include a prognostic equation for the sixth moment (radar reflectivity) for a three-moment BMS.

Prior sedimentation studies in bulk schemes include Wacker and Seifert (2001, WS01), who compared one- and two-moment bulk solutions for rain sedimentation to a spectral reference, finding that the two-moment scheme suffered from excessively large sedimentation rates. MY05a further examined sedimentation with a three-parameter gamma distribution

$$N(D) = n_0 D^m e^{-\lambda D}, \tag{1}$$

and showed that by allowing $m$ to vary — either diagnostically or prognostically — the problems of excessive size sorting are controllable. MY05a limited considerations to the "standard" combinations $M_3$, $M_0$-$M_3$, and $M_0$-$M_3$-$M_6$ for one-, two-, and three-moment schemes.

Wacker and Lüpkes (2009, WL09) were the first to examine alternative prognostic moments, showing that changing the prognostic moments affects prediction of NT, LWC, and reflectivity profiles, and that there is considerable nonconservation of moments far from the order of the prognostic moments. Moments between the prognostic ones are underpredicted; moments outside the range are overpredicted (the "overshooting" problem). They recommended that the order of prognostic moments be chosen as close as possible to those with the greatest effect on the simulation, and examined only one- and two-moment schemes with fixed $m$.

The importance of a variable shape parameter (MY05a) and the sensitivity to choice of prognostic moments (WL09) motivate this study. The objective is to quantify sedimentation-induced errors for given selections of prognostic and diagnostic variables and guide cloud modelers in selecting prognostic moments.

## 2. Experimental setup

### a. Bin model

The framework is designed to investigate errors associated with pure sedimentation (no other processes). An analytic spectral model provides the reference solution. Initial conditions follow WL09 closely: a 1.5-km-deep square-wave profile of rain, with LWC $= 0.5 \times 10^{-3}$ kg m⁻³ and $N_T = 3 \times 10^3$ m⁻³, with an inverse-exponential PSD ($m = 0$), equivalent to $n_0 = 8 \times 10^6$ m⁻⁴. The rain is placed between 6500 and 8000 m (higher than WL09's 2500–4000 m) so that results apply to any hydrometeor category existing throughout a deep atmospheric layer.

The reference solution is computed analytically: the sedimentation velocity follows the power-law relation

$$V(D) = \gamma a D^b, \quad a = 130\ \text{m}^{0.5}\text{s}^{-1},\ b = 0.5\ \text{(Kessler 1969)}, \tag{A1}$$

with $\gamma = (\rho/\rho_0)^{0.5}$ set to 1 throughout. Profiles of any moment $k$ are computed by direct summation over 5000 bins (diameter 0–10 mm, bin width 0.002 mm):

$$M_k(z, t) = \sum_i D_i^k N_i(D_i, z, t) \Delta D. \tag{A3}$$

Key relationships:

$$\text{LWC} = \frac{6}{\pi \rho_L} M_3, \quad D_m = \left(\frac{6\,\text{LWC}}{\pi \rho_L N_T}\right)^{1/3} = \left(\frac{M_3}{M_0}\right)^{1/3}. \tag{2,3}$$

### b. Bulk model

Bulk model simulations use the same initial profile. The PSDs are constrained by (1) at all times, with any moment computed analytically from

$$M_k = \int_0^\infty D^k N(D)\, dD = n_0 \Gamma(k + m + 1)\,\lambda^{-(k+m+1)}. \tag{4}$$

The prognostic equation for moment $M_k$ is

$$\frac{\partial M_k}{\partial t} - \frac{\partial(M_k V_k)}{\partial z} = 0, \tag{7}$$

where the moment-weighted sedimentation velocity is

$$V_k = \gamma a \frac{\Gamma(1 + k + m + b)}{\Gamma(1 + k + m)} \lambda^b. \tag{8}$$

Equation (7) is solved numerically using the box-Lagrangian advection scheme (Kato 1995) with a vertical grid spacing of 12.5 m and a time step of 0.25 s. For one-moment runs, closure is $n_0 = 8 \times 10^6$ m⁻⁴ and $m = 0$. For two-moment runs in section 3, $m = 0$ is the only constraint. Simulations are integrated for 2000 s.

### c. Evaluation method

Because many moments are of potential interest, errors are presented as 2D error plots showing normalized errors for moments $M_0$–$M_7$ at any given time, with color shading for overprediction (warm) and underprediction (cold). A summary metric — the time-averaged normalized mean absolute error (NMAE) over moments $M_0$–$M_7$, $M_0$–$M_3$, and the prognostic moments — is used to rank bulk scheme configurations.

The ratio of moment-weighted sedimentation velocities for two prognostic moments $j < k$ is

$$\frac{V_k}{V_j} = \frac{\Gamma(k+1+m+b)\Gamma(j+1+m)}{\Gamma(j+1+m+b)\Gamma(k+1+m)}. \tag{9}$$

For a given constant $m \geq 0$, $V_k/V_j > 1$ (constant), so $M_k$ always sediments faster than $M_j$, causing $D_m = (M_3/M_0)^{1/3}$ to constantly increase at the leading edge — uncontrolled size sorting.

## 3. Results and error analysis

### a. Commonly used bulk configurations

**One-moment ($M_3$, $m = 0$):** LWC translates downward at a constant sedimentation velocity; all other moments are monotonically related to $M_3$; no size-sorting possible. All diagnostic moments are overpredicted near the peak, underpredicted at the leading and trailing edges.

**Two-moment ($M_0$-$M_3$, $m = 0$):** Size sorting is produced (increasing $D_m$ with decreasing altitude), but the scheme suffers from excessive size sorting. $M_6$ and higher-order moments are grossly overpredicted; lower-order moments are underpredicted. Error score is very large — worse than all but one other bulk configuration, including the standard one-moment scheme.

**Three-moment ($M_0$-$M_3$-$M_6$):** Size sorting is essentially controlled (maximum $D_m$ somewhat larger at $t = 300$ s than the reference model's prescribed maximum of 0.010 m, but does not grow extremely large). Profiles of all three prognostic moments are very similar to the reference solution. Errors for all moments $M_0$–$M_7$ are greatly reduced compared to both one- and two-moment results.

### b. Alternative combinations of prognostic moments

**One-moment schemes:** For any prognostic moment $M_j$, the profiles are qualitatively similar to the standard $M_3$ run but with translation speed systematically slower (faster) for lower (higher) order prognostic moments. Error plots are all qualitatively similar.

**Two-moment schemes:** For all combinations with constant $m = 0$, diagnostic moments between the two prognostic moments are underpredicted. Severity increases with the distance between the prognostic moments (e.g., $M_0$-$M_2$: moderate underprediction of moments between; $M_0$-$M_8$: severe). All moments outside the range of prognostic moments are greatly overpredicted ("overshooting"), explained by the fact that as $M_k$ sediments faster than $M_j$, a diagnostic $M_l$ can take unrealistically large values per the gamma-function relation $M_l \propto (M_j^{k-1}/M_k^{j-1})^{1/(k-j)}$.

**Three-moment schemes:** No large systematic overshooting for moments outside the range of the prognostic moments, because $m$ is not constant — its variability adjusts the relative sedimentation speeds. Configurations with moment numbers separated by 1 (e.g., $M_0$-$M_1$-$M_2$) show general underprediction of non-prognostic moments. Configurations with moment numbers separated by 2 or more generally have quite low errors.

### c. Discussion of error scores

From Table 1 (ranked configurations):

| Configuration | Error score |
|---|---|
| 3-mom, $M_1$-$M_3$-$M_5$ | 0.2548 (best) |
| 3-mom, $M_0$-$M_2$-$M_4$ | 0.2782 |
| 3-mom, $M_0$-$M_3$-$M_6$ | 0.4137 |
| 2-mom, $M_0$-$M_3$, diagnostic-$V_k/V_j$ (proposed) | 0.6539 |
| 2-mom, $M_0$-$M_3$, diagnostic-$m$ (proposed) | 0.7188 |
| 1-mom, $M_3$, $m = 0$ | 1.0568 |
| 2-mom, $M_0$-$M_3$, $m = 0$ (standard) | **~1000** (worst practical) |

The standard 3-mom $M_0$-$M_3$-$M_6$ configuration (the only combination used in published 3D three-moment simulations to date) ranks more poorly than several alternative three-moment configurations, demonstrating that careful selection of prognostic moments can yield improvements even in three-moment BMSs. The standard two-moment $M_0$-$M_3$, $m = 0$ configuration has a catastrophically large error score, largely due to uncontrolled size sorting and overprediction of higher-order moments.

## 4. Controlling size sorting in a two-moment scheme

### a. Background

From (9), with constant $m \geq 0$, $V_k/V_j$ is fixed and $> 1$, so $D_m$ always grows at the leading edge during sedimentation. Two mitigation approaches are examined.

### b. Diagnostic-$m$ approach

MY05a showed that diagnosing $m = f(D_m)$ suffices to narrow the PSD in a two-moment scheme, controlling size sorting. This paper **generalizes the diagnostic-$m$ approach for any pair of prognostic moments $M_j$, $M_k$** by fitting the reference-model PSD profiles (from which any moment can be computed) to a gamma function. The quantity $(M_k/M_j)^{1/(k-j)}$ is relatively independent of the choice of moments used for the fit, motivating a parameterization of $m$ as a diagnostic function of this ratio. After examining the curves at multiple times, the proposed parameterization is:

$$m = 11.84\left[1000\left(\frac{M_k}{M_j}\right)^{1/(k-j)} - 0.75\right]^2 + 2. \tag{10}$$

This relation is general for a two-moment scheme with any choice of prognostic moments (unlike MY05a's $m = f(D_m)$ which is specific to the $M_0$-$M_3$ pair). Compared to the MY05a diagnostic relation and the Seifert (2008) relation, the proposed parameterization better captures narrow distributions (large $m$) at small values of $(M_k/M_j)^{1/(k-j)}$ and produces less error (Table 1). The two-moment $M_0$-$M_3$, diagnostic-$m$ run using (10) ranks better than several three-moment configurations.

### c. Alternative approach for fixed-$m$ schemes

For BMSs that are hard-coded to hold $m$ constant (e.g., code-optimized or designed around inverse-exponential PSDs), a **diagnostic $V_k/V_j$ ratio approach** is proposed. The method:
1. Compute $V_k$ normally from (8) using the prescribed fixed $m$.
2. Compute a diagnostic $m' = $ (10) using the prognostic moments $M_j$, $M_k$.
3. Use $m'$ (instead of $m$) only in (9) to compute $V_j$ from the computed $V_k$.

This causes the fall velocity of the lower moment to approach that of the higher moment as $D_m$ increases, reducing differential sedimentation and the rate of size sorting — without actually changing $m$ in the rest of the BMS. For example, for a standard $M_0$-$M_3$ scheme with $m = 0$: when $D_m = 1.3$ mm, $m' = 6$, so $V_3/V_0 = 1.2$ (instead of 2.2 under the standard calculation), implying a much slower rate of size sorting.

This approach ranks slightly better than the diagnostic-$m$ approach in Table 1 (error score 0.6539 vs 0.7188), though likely fortuitously. It is simple to implement and very effective at mitigating excess size sorting in existing fixed-$m$ two-moment schemes.

## 5. Conclusions

1. **One-moment schemes** cannot produce size sorting; all computed moments are monotonically related to the single prognostic moment.
2. **Standard two-moment schemes** ($M_0$-$M_3$, $m = 0$) have catastrophically large errors in higher-order moments due to uncontrolled size sorting, scoring worse than the standard one-moment scheme on the broad NMAE metric. The error can be shifted by changing the prognostic moments, but cannot be eliminated within a fixed-$m$ framework.
3. **Three-moment schemes** are dramatically better across a wide range of moments. The standard $M_0$-$M_3$-$M_6$ configuration is outperformed by alternative moment combinations (best: $M_1$-$M_3$-$M_5$, score 0.2548 vs 0.4137). Errors in three-moment schemes are insensitive to the choice of prognostic variables (no catastrophic overshooting), unlike two-moment schemes.
4. **Two proposed fixes for two-moment schemes:**
   - Diagnostic-$m$ [Eq. (10)]: easily added to most existing two-moment BMSs; effectively reduces excessive size sorting; general for any pair of prognostic moments.
   - Diagnostic $V_k/V_j$ ratio: applicable for fixed-$m$ (hard-coded) schemes; very simple to implement; very effective.

Future work: testing of alternative prognostic moments in full-physics 3D simulations with two-moment $M_0$-$M_3$ and three-moment $M_0$-$M_3$-$M_6$ BMSs.

---

## Appendix A: Computation of the Reference Solution

The spectral model uses 5000 bins (diameters 0–10 mm; bin width 0.002 mm) with the fall velocity relation (A1) and constant $\gamma = 1$. For each bin $i$ at initial height $z_{i0}$, the height after time $t$ is $z_i(t) = z_{i0} - V_i(D_i)t$. The moment $M_k$ at height $z$ and time $t$ is given by (A3). The solution is obtained analytically (no time-stepping), since $V_i(D_i)$ is constant.

## Appendix B: Computation of the Size Distribution Function Parameters

For a **one-moment scheme** (prognostic $M_j$, closures $m = 0$ and $n_0 = 8 \times 10^6$ m⁻⁴):

$$\lambda = \left[\frac{n_0 \Gamma(j + m + 1)}{M_j}\right]^{1/(j+m+1)}. \tag{B1}$$

For a **two-moment scheme** (prognostic $M_j$, $M_k$; $m$ prescribed or diagnosed):

$$n_0 = \frac{M_j^{(k+m+1)/(k-j)}}{\Gamma(j+m+1)}\cdot\frac{M_k^{(j+m+1)/(k-j)}}{\Gamma(k+m+1)}, \tag{B2}$$

with $\lambda$ from (B1).

For a **three-moment scheme** (prognostic $M_j$, $M_k$, $M_l$), $m$ is solved by iterating:

$$M_j^{(l-k)/(k-j)}\, M_k^{(j-l)/(k-j)}\, M_l = \Gamma(j+m+1)^{(l-k)/(k-j)} \cdot \Gamma(k+m+1)^{(j-l)/(k-j)} \cdot \Gamma(l+m+1); \tag{B3}$$

then $n_0$ and $\lambda$ are computed from (B2) and (B1).

---

*Acknowledgments: The authors thank Hugh Morrison for helpful comments and gratefully acknowledge the careful reviews of Jerry Straka and Ulrike Wacker.*
