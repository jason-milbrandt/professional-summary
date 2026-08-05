# A Multimoment Bulk Microphysics Parameterization. Part IV: Sensitivity Experiments

**Authors:** J. A. Milbrandt (Dept. of Atmospheric and Oceanic Sciences, McGill University, Montreal, and Recherche en Prévision Numérique, Meteorological Service of Canada, Dorval, Quebec, Canada); M. K. Yau (Dept. of Atmospheric and Oceanic Sciences, McGill University, Montreal, Quebec, Canada)

**Journal:** *Journal of the Atmospheric Sciences*, **63**, 3137–3159 (December 2006)

**Manuscript:** JAS3817 (received 1 April 2005, in final form 10 March 2006)

**DOI:** 10.1175/JAS3817.1

---

## Abstract

This is the fourth in a series of papers exploring the effects of the number of predicted moments in bulk microphysics schemes. In Part III, the three-moment version of a new multimoment scheme was used to simulate a severe hailstorm. The model successfully reproduced many of the observed gross characteristics, including the reflectivity structure and the maximum hail sizes at the ground. In this paper, the authors compare a series of sensitivity experiments using various one- and two-moment versions of the scheme with the three-moment version to explore the effects of predicting additional moments on the simulated hydrometeor fields, precipitation, and storm dynamics.

Six sensitivity runs were performed. They varied in their ability to reproduce the precipitation pattern, storm structure, and peak values of microphysical fields of the control simulation. The two-moment simulations, which used diagnostic relations to prescribe the relative dispersion parameter, $\alpha$, closely reproduced the spatial pattern, quantity, and phase of the precipitation at the surface as well as the overall storm structure, propagation speed, and peak values of several hydrometeor fields. The two-moment simulations, which used fixed values of $\alpha$, on the other hand, differed more from the control. The runs using one-moment versions of the scheme were considerably different from each other and were poor at reproducing the control simulation.

The results suggest that there is a dramatic improvement in the simulation moving from one- to two-moment schemes. For the case studied, it was found that if maximum particle size is not of concern, a two-moment scheme with a diagnostic dispersion parameter can reproduce most of the important aspects in a hailstorm simulation with a three-moment scheme.

---

## 1. Introduction

With continuous increase in computational power, operational NWP models are moving toward convective-scale resolutions, where bulk microphysics schemes play an increasingly important role. In general, simulation skill increases as the complexity of the microphysics scheme increases, particularly with inclusion of the ice phase (Cotton and Anthes 1989). Studies have shown improvement with increasing number of frozen categories (McCumber et al. 1991; Ferrier et al. 1995) and with increasing number of predicted moments (Meyers et al. 1997; Reisner et al. 1998). Predicting extra moments adds computational expense, so the topic merits further examination.

Two-moment schemes generally hold the relative dispersion of the hydrometeor spectra constant. Milbrandt and Yau (2005a, Part I) showed the spectral shape parameter $\alpha$ in the gamma distribution

$$N(D) = N_0 D^\alpha e^{-\lambda D} \tag{1}$$

is important for computing sedimentation and microphysical growth rates, and proposed two alternatives to the fixed-dispersion approach: (i) a two-moment method in which $\alpha$ is diagnosed as a monotonically increasing function of the mean-mass diameter, and (ii) a three-moment approach adding a predictive equation for a third moment, allowing $\alpha$ to vary independently. Part II (2005b) introduced the resulting six-category multimoment scheme. In Part III (2006), the three-moment version simulated a severe hailstorm with realistic microphysical fields.

The purpose of this study is to investigate the abilities of one- and two-moment versions of the new scheme to reproduce the full three-moment simulation of Part III. A key feature is that **all sensitivity runs use different versions of the same microphysics scheme**, so differences can be confidently attributed to the treatment of the predicted/diagnosed parameters rather than other scheme differences. Since lower-moment schemes are known a priori to be intrinsically more limited, the **three-moment control run (CNTR) is treated as the "truth,"** and differences are interpreted as errors resulting from the imposed simplifications. (This does not mean a lower-moment field is necessarily further from observations than the control.)

## 2. Description of sensitivity runs

In addition to the three-moment control simulation (**CNTR**), six sensitivity simulations were performed (Table 1). Each used a different version of the scheme on the 1-km grid, with all other model conditions identical to CNTR. Four runs used two-moment versions and two used one-moment versions.

**Table 1. Summary of 1-km sensitivity experiments.** (Note $x \in \{r, i, s, g, h\}$. In SM_A and SM_B, $\alpha_y = 0$ and $\alpha_r = 2$. For all runs, $\alpha_c = 1$.)

| Run | Description of scheme version |
|-----|-------------------------------|
| CNTR | Three moment; full version of scheme |
| DIAG_A | Two moment; diagnostic relation (A) for $\alpha_x = f_A(D_{mx})$ [$\alpha_x \geq 3$] |
| DIAG_B | Two moment; diagnostic relation (B) for $\alpha_x = f_B(D_{mx})$ [$\alpha_x \geq 0$] |
| FIX_0 | Two moment; fixed $\alpha_x$ [$\alpha_y = 0$; $\alpha_r = 2$] |
| FIX_3 | Two moment; fixed $\alpha_x$ [$\alpha_y = 3$; $\alpha_r = 2$] |
| SM_A | One moment; fixed $N_{0h}$ |
| SM_B | One moment; diagnostic $N_{0h} = f(\lambda_h)$ |

The two-moment runs differ in treatment of $\alpha_x$. FIX_0 and FIX_3 use constant $\alpha_x = 0$ and $3$ for all precipitating categories. In DIAG_A, $\alpha_x$ is diagnosed from the mean-mass diameter $D_{mx}$ via (for hail):

$$\alpha_h = \begin{cases} c_{1h}\tanh[c_{2h}(D_{mh} - c_{3h})] + c_{4h} & \text{for } D_{mh} < 8\text{ mm} \\ c_{5h}D_{mh} - c_{6h} & \text{for } D_{mh} \geq 8\text{ mm} \end{cases} \tag{2}$$

and (for rain, ice, snow, graupel):

$$\alpha_x = c_{1x}\tanh[c_{2x}(D_{mx} - c_{3x})] + c_{4x}. \tag{3}$$

These diagnostic relations (introduced in Part I) were empirically derived from vertical profiles of $\alpha_x$ and $D_{mx}$ resulting from pure sedimentation. However, Part III showed that in a full-physics 3D simulation, other processes can locally reduce $\alpha_x$. Because the original relation yields too-large $\alpha_h$ for $D_{mh} < 2$ mm, a second set of constants (DIAG_B) was determined that allows $\alpha_x \to 0$ for small $D_{mx}$.

The two one-moment runs (SM_A, SM_B) both had fixed $\alpha_x = 0$ for frozen categories, $\alpha_r = 2$, and fixed intercept parameters $N_{0r} = 8\times10^6$, $N_{0s} = 1\times10^7$, $N_{0g} = 1\times10^4$ m⁻⁴. The only difference was the hail intercept: SM_A used a constant $N_{0h} = 1\times10^4$ m⁻⁴ (characteristic of graupel), while SM_B diagnosed it as

$$N_{0h} = 1.48\times10^{-6} \times \lambda_h^{3.63} \tag{4}$$

(similar to Cheng and English 1983; more representative of high-density hail). These represent extreme values for the category; the study is not intended to provide guidance on the most appropriate value (see Gilmore et al. 2004; van den Heever and Cotton 2004).

[Table 2 / Table 3: constants $c_{1x}$–$c_{6x}$ in the diagnostic $\alpha_x$ relations for DIAG_A and DIAG_B — tabular constants, see original]

[Figure 1: $D_{mh}$ vs $\alpha_h$ for the diagnostic relations used in DIAG_A (thick solid) and DIAG_B (dot dashed) — image not reproducible in markdown]

## 3. Results

### a. Precipitation

**1) Instantaneous precipitation rates.** The trend of gradual then rapid intensification of the total precipitation rate (TR), followed by oscillation about ~150 mm h⁻¹, appeared in the two-moment runs with notable differences. DIAG_B's TR evolution was closest to CNTR. For DIAG_A, TR was 20–75 mm h⁻¹ less than CNTR; FIX_3 was similar to DIAG_A; FIX_0 was 30–70 mm h⁻¹ less. The one-moment runs differed most: SM_A roughly doubled CNTR's TR by 4:15 h (~300 mm h⁻¹), and SM_B was distinctly higher at all times. Most liquid precipitation in all runs originated from melting hail. The one-moment runs were heavily biased toward frozen precipitation (solid rates ~4× CNTR; liquid ~25% less).

[Figure 2: Maximum instantaneous (a) total, (b) liquid, and (c) solid precipitation rates of the main storm from CNTR and all sensitivity simulations — image not reproducible in markdown]

**2) Accumulated precipitation.** The total, liquid, and solid accumulated precipitation patterns from DIAG_A, FIX_0, and FIX_3 were similar to CNTR (though DIAG_A and FIX_3 underpredicted total precipitation late). The one-moment runs had much greater magnitudes (SM_A ~⅓ more, SM_B ~double) and too-high areal coverage. **DIAG_B best reproduced CNTR.** For the hail swath, DIAG_B was best (slightly underpredicting peak ~10%); DIAG_A and FIX_3 underpredicted (~50% and 20%); FIX_0 overpredicted (~40%); the one-moment runs greatly overpredicted (~350% SM_A, ~490% SM_B).

[Figures 3–5: Accumulated 6-h total, liquid, and solid precipitation for CNTR and all sensitivity runs — images not reproducible in markdown]

### b. Storm dynamics

All six sensitivity runs produced qualitatively similar results to CNTR (two main storm tracks).

**1) Updraft and downdraft.** Most runs had similar updraft intensities to CNTR. Updraft initiation was delayed ~45 min in DIAG_B and FIX_3, ~30 min in FIX_0. SM_A had a conspicuously different updraft evolution (did not intensify rapidly until after 3:00 h, then weakened to 17 m s⁻¹ by 4:30 h before re-strengthening). Differences in intensification timing relate to differences in vertical redistribution of condensate due to sedimentation. The maximum low-level downdraft in CNTR peaked at 7 m s⁻¹ at 5:30 h; it was roughly doubled in SM_A but weaker in SM_B. DIAG_B was closest to CNTR.

**2) Mesocyclone intensity.** Two-moment schemes were generally close to CNTR (exception: FIX_0 after 4:30 h).

**3) Storm propagation.** All two-moment runs propagated very similarly to CNTR. The one-moment runs differed: SM_A moved faster (less coherent updraft core), SM_B moved slower — directly related to cold-pool strength differences.

**4) Cold pool strength.** The cold pool (identified by $\theta'' = \theta - \theta_0$, $\theta_0 = 303$ K) showed only small differences between two-moment runs and CNTR (DIAG_B closest). The one-moment cold pools differed greatly: SM_A much stronger, SM_B much weaker. These differences are reflected in storm propagation speed. The strong cold pool / small mean hail in SM_A and weak cold pool / large hail in SM_B are consistent with van den Heever and Cotton (2004). Because the prestorm environment was only marginally favorable for supercells (~20 m s⁻¹ shear), even a modest cold-pool increase can switch the regime from supercellular to multicellular — likely why SM_A was more multicellular.

[Figures 6–10: updraft/downdraft velocity, vertical vorticity, storm propagation tracks, and potential temperature anomaly cross sections for CNTR and all sensitivity runs — images not reproducible in markdown]

### c. Simulated hail fields

The 700-hPa $Z_{eh}$ fields and vertical cross sections of $Z_{eh}$, $Q_h$, $N_{Th}$, $D_{mh}$, and $N_h^*\{1\text{cm}\}$ at 4:30 h were examined (maximum values summarized below, Table 4).

**1) Equivalent reflectivity $Z_{eh}$.** The four two-moment runs and CNTR exhibited similar BWER structures with a high-$Z_{eh}$ core upshear. FIX_0 was anomalous: maximum $Z_{eh}$ at the surface (83.9 dBZ at 900 hPa) rather than aloft. DIAG_B had the closest peak to CNTR (59.1 vs 59.7 dBZ). The one-moment runs had high-$Z_{eh}$ cores under the updraft with surface maxima of 68.2 (SM_A) and 87.3 dBZ (SM_B), and no suspended $Z_{eh}$ in the anvil.

**2) Mass content $Q_h$.** Similar between two-moment runs and CNTR (mass concentrated aloft). CNTR peak $Q_h = 5.51$ g m⁻³ at 500 hPa, most closely reproduced by DIAG_B (5.58 g m⁻³). One-moment runs differed considerably: SM_A concentrated mass near the surface; SM_B much smaller magnitudes (peak 1.03 g m⁻³).

**3) Total number concentration $N_{Th}$.** Two-moment runs qualitatively similar to CNTR. FIX_0 had the closest peak ($10^{5.22}$ vs CNTR $10^{5.18}$ m⁻³). One-moment $N_{Th}$ fields did not resemble CNTR at all (by definition $N_{Th}$ is a monotonic function of $Q_h$). In SM_A, peak $Q_h$ and peak $N_{Th}$ are collocated; in SM_B (where $N_{0h}$ decreases with $Q_h$), $N_{Th}$ varies inversely with $Q_h$ and has no meaningful maximum.

**4) Mean-mass diameter $D_{mh}$.** DIAG_A, DIAG_B, and FIX_3 similar to CNTR. CNTR peak $D_{mh} = 14.9$ mm at 650 hPa, best reproduced by DIAG_B (11.2 mm). FIX_0 had very large sizes (max 67.2 mm at 900 hPa). In one-moment schemes $D_{mh}$ increased monotonically with $Q_h$ (SM_A max 6.2 mm; SM_B max 41.1 mm).

**5) Number concentration of grape-sized hail $N_h^*\{1\text{cm}\}$.** CNTR maximum 1.03 m⁻³ at 650 hPa, best reproduced by DIAG_B (0.79 m⁻³). Near the surface, CNTR max 0.235 m⁻³ was underpredicted by DIAG_B (0.085), overpredicted by FIX_0 (0.381), greatly underpredicted by DIAG_A and FIX_3, overpredicted ~7× by SM_A. SM_B's near-surface value (0.247 m⁻³) was fortuitously close (it is the maximum possible value by virtue of the diagnostic $N_{0h}$ relation).

**6) Maximum hail sizes at surface.** None of the sensitivity runs reproduced CNTR's maximum hail size range (2–3 cm, walnut-sized). DIAG_A, DIAG_B, and FIX_3 all underpredicted (1–2 cm); FIX_0 overpredicted considerably (8–9 cm). The one-moment runs were extreme: SM_A 4–5 cm, SM_B 22–23 cm.

**Table 4. Maximum values of $Z_e$ and hail variables in the main storm at 4:30 h** (pressure level in hPa parenthetically; rightmost column = max observable hail diameter near surface at 3:45 h):

| Run | $Z_e$ (dBZ) | $Z_{eh}$ (dBZ) | $Q_h$ (g m⁻³) | log $N_{Th}$ (m⁻³) | $D_{mh}$ (mm) | $N_h^*\{1\text{cm}\}$ (m⁻³) | $N_h^*\{1\text{cm}\}$ @900 hPa | Max $D_h$ (cm) @900 hPa |
|-----|------|------|------|------|------|------|------|------|
| CNTR | 63.6 (775) | 59.7 (750) | 5.51 (500) | 5.18 (600) | 14.9 (650) | 1.03 (750) | 0.235 | 2–3 |
| DIAG_A | 62.7 (825) | 56.6 (725) | 4.55 (450) | 4.67 (350) | 8.78 (850) | 0.458 (750) | 0.011 | 1–2 |
| DIAG_B | 63.6 (800) | 59.1 (700) | 5.58 (675) | 4.07 (350) | 11.2 (775) | 0.788 (700) | 0.085 | 1–2 |
| FIX_0 | 83.9 (900) | 83.9 (900) | 4.91 (525) | 5.22 (575) | 67.2 (900) | 0.680 (725) | 0.381 | 8–9 |
| FIX_3 | 59.6 (800) | 56.8 (725) | 4.97 (475) | 4.89 (650) | 9.33 (800) | 0.409 (725) | 0.014 | 1–2 |
| SM_A | 68.3 (800) | 68.2 (800) | 3.70 (800) | 1.53 (800) | 6.15 (800) | 1.76 (800) | 1.600 | 4–5 |
| SM_B | 87.3 (900) | 87.3 (900) | 1.03 (900) | n/a | 41.4 (900) | 0.247 (900) | 0.247 | 22–23 |

[Figures 11–16: 700-hPa $Z_{eh}$ and vertical cross sections of $Z_{eh}$, $Q_h$, $N_{Th}$, $D_{mh}$, and $N_h^*\{1\text{cm}\}$ for CNTR and all sensitivity runs — images not reproducible in markdown]

## 4. Discussion

### a. Overall evaluation of the sensitivity runs

Characteristics of CNTR were subjectively judged "reproduced" if curves were within thresholds (updraft within 5 m s⁻¹, downdraft within 1 m s⁻¹, vorticity within 0.002 s⁻¹; peak $Z_e$, $Q_h$, $D_{mh}$ within 4 dBZ, 25%, 25%; max hail sizes in the same diameter range). Conclusions:

1. DIAG_B reproduced CNTR most closely.
2. DIAG_A was closer to CNTR than either fixed-$\alpha$ run.
3. FIX_3 was closer to CNTR than FIX_0.
4. The two-moment runs were all much closer to CNTR than the one-moment runs.
5. SM_B was marginally closer to CNTR than SM_A.

**Overall ranking (best to worst): DIAG_B, DIAG_A, FIX_3, FIX_0, SM_B, SM_A.**

Two important conclusions for this case: (i) the two-moment runs were very close to the three-moment run overall; (ii) there is considerable degradation for the one-moment runs. Thus there is considerable gain in predicting two moments over one — particularly if the dispersion parameter is diagnosed rather than fixed — and lesser gain moving from two to three moments. (Caution: based on a single case study, though consistent with Part I.)

**Table 5. Characteristics of CNTR reproduced reasonably closely by each sensitivity run:**

| Reproduced characteristic | DIAG_A | DIAG_B | FIX_0 | FIX_3 | SM_A | SM_B |
|---------------------------|:------:|:------:|:-----:|:-----:|:----:|:----:|
| Total precipitation pattern | ✓ | ✓ | ✓ | ✓ | | ✓ |
| Total precipitation amounts | ✓ | ✓ | ✓ | ✓ | | |
| Liquid/solid precipitation distribution | ✓ | ✓ | | ✓ | | |
| Updraft/downdraft | | ✓ | | ✓ | | |
| Mesocyclone intensity | ✓ | ✓ | | ✓ | | |
| Storm propagation | ✓ | ✓ | ✓ | ✓ | | |
| Cold pool strength | ✓ | ✓ | | ✓ | | |
| Overall storm structure | ✓ | ✓ | ✓ | ✓ | | |
| Maximum total reflectivity ($Z_e$) | ✓ | ✓ | | ✓ | ✓ | |
| Peak hail mass contents ($Q_h$) | ✓ | ✓ | ✓ | ✓ | | |
| Mean-mass hail diameter ($D_{mh}$) | | ✓ | | | | |
| Maximum hail sizes at surface | | | | | | |

### b. Evaluation of the diagnostic-$\alpha$ relations

Comparing $\alpha_h$ profiles from CNTR with values diagnosed from $D_{mh}$ shows that for $D_{mh} < 5$ mm (most columns), $\alpha_h \sim 3$ in DIAG_A — so FIX_3 and DIAG_A are similar, and DIAG_A only showed improved skill over fixed $\alpha_h = 3$ in shallow layers where $D_{mh} > 5$ mm. The DIAG_B relation (no limiting value of 3) yields $\alpha_h$ in much better agreement with CNTR. Nevertheless, there is generally **not** a monotonic relation between $\alpha_h$ and $D_{mh}$ in CNTR, so the extra degree of freedom in the three-moment approach still has advantages over a two-moment approach.

### c. Importance of sedimentation in the sensitivity runs

Many differences are explained by how the schemes treat sedimentation. In one-moment schemes, the mass-weighted fall velocity $V_{Qh}$ is a monotonic function of $Q_h$. In SM_A, hail formed low in the updraft sediments to the ground rather than being advected toward the updraft core, so it cannot grow large by accretion; flux convergence at the surface is large, giving large surface hail precipitation. In SM_B, $V_{Qh}$ varies much more rapidly with $Q_h$, so peak $Q_h$ is underpredicted even more. There is no size-sorting in SM_A or SM_B (peak $D_{mh}$ collocated with peak $Q_h$). The two-moment runs had much better spatial distribution of hail mass. FIX_0 overpredicted $Z_{eh}$, $D_{mh}$, and max surface hail size because fixing $\alpha_x = 0$ leaves size-sorting uncontrolled; FIX_3 and the diagnosed-$\alpha_x$ runs did not suffer from excessive size sorting.

### d. Simulation of hail

At least a two-moment scheme is required to approximately reproduce CNTR's surface hail. FIX_3's hail swath was notably better than FIX_0's and almost as good as DIAG_B's — but at the expense of reproducing hail *sizes* ($N_h^*\{1\text{cm}\}$ too small). Conversely, FIX_0's peak accumulated solid precipitation was too high and max surface hail sizes too large, though grape-sized hail number concentration was not unreasonable. This suggests that for a fixed-$\alpha$ two-moment scheme, **accurate quantitative hail simulation can only be done at the expense of accurate hail-size simulation, and vice versa**: fixing $\alpha_h = 3$ controls excessive size-sorting but forces narrow distributions with reduced large-diameter concentrations. The diagnostic-$\alpha$ two-moment approach controls size-sorting while allowing smaller $\alpha_h$ (larger $N_h^*$, $R_h^*$) — making it the best alternative to a three-moment scheme for hail.

## 5. Conclusions

A series of sensitivity experiments investigated the benefits of predicting extra moments. **The most significant improvement comes from replacing a one-moment scheme by a two-moment scheme**, improving QPF as well as predicted number concentrations and mean particle sizes. The most economical two-moment scheme has fixed $\alpha_x$; the $\alpha_x = 3$ simulation is notably better than $\alpha_x = 0$. Diagnosing $\alpha_x$ adds further improvement to both quantity and sizes of hail, particularly for narrow spectra — though the diagnosed-$\alpha_x$ runs still failed to reproduce walnut-sized (2–3 cm) hail at the surface as simulated by the three-moment run.

Thus, for accurate QPF with less concern for maximum hydrometeor sizes, **a two-moment scheme with diagnosed-$\alpha_x$ is nearly as good as a three-moment scheme**. The authors strongly advocate at least a two-moment scheme — with sedimentation computed as in Part I — over a one-moment scheme for research on convective storms using cloud-resolving models. While a one-moment scheme could in principle be calibrated to resemble CNTR more closely than SM_A or SM_B, the authors believe no amount of tuning of a one-moment scheme can match a two- or three-moment scheme for such a deep-convection case.

The three-moment approach has extra costs: each additional moment adds a predictive variable to be advected (the full triple-moment scheme has 17 additional hydrometeor variables) and a set of source/sink terms to compute. A scheme need not be fully three-moment for all categories — e.g., a scheme that is two-moment for rain, ice, snow, graupel and three-moment for hail would be only slightly more expensive than DIAG_B but might improve hail-size reproduction. An important topic for future work is the ideal number of categories and moments per category, given desired skill and available computational resources; optimization experiments should be conducted to design the optimal bulk scheme for high-resolution models.

---

*Acknowledgments: The authors thank the reviewers for constructive comments. Research supported by the Canadian Foundation for Climate and Atmospheric Science.*
