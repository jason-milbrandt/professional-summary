# Simulation of an Orographic Precipitation Event during IMPROVE-2. Part II: Sensitivity to the Number of Moments in the Bulk Microphysics Scheme

**Authors:** J. A. Milbrandt (Meteorological Research Division, Environment Canada, Dorval, Quebec, Canada); M. K. Yau (McGill University, Montreal, Quebec, Canada); J. Mailhot, S. Bélair, and R. McTaggart-Cowan (Meteorological Research Division, Environment Canada, Dorval, Quebec, Canada)

**Journal:** *Monthly Weather Review*, **138**, 625–642 (February 2010)

**Manuscript:** received 30 June 2009, in final form 17 August 2009

**DOI:** 10.1175/2009MWR3121.1

---

## Abstract

This is the second in a series of papers examining the behavior of the Milbrandt–Yau multimoment bulk microphysics scheme for the simulation of the 13–14 December 2001 case of orographically enhanced precipitation observed during the IMPROVE-2 experiment. The sensitivity to the number of predicted moments of the hydrometeor size spectra in the bulk scheme was investigated. The triple-moment control simulations presented in Part I were rerun using double- and single-moment configurations of the multimoment scheme as well as the single-moment Kong–Yau scheme. Comparisons of total precipitation and in-cloud hydrometeor mass contents were made between the simulations and observations, with the focus on a 2-h quasi-steady period of heavy stratiform precipitation. The double- and triple-moment simulations were similar; both had realistic precipitation fields, though generally overpredicted in quantity, and had overprediction of snow mass and an underprediction of cloud water aloft. Switching from the triple- to single-moment configuration resulted in a simulation with a precipitation pattern shifted upwind and with a larger positive bias, but with hydrometeor mass fields that corresponded more closely to the observations. Changing the particular single-moment scheme used had a greater impact than changing the number of moments predicted in the same scheme, with the Kong–Yau simulations greatly overpredicting the total precipitation in the lee side of the mountain crest and producing too much snow aloft. Further sensitivity tests indicated that the leeside overprediction in the Kong–Yau runs was most likely due to the combination of the absence of the latent heat effect term in the diffusional growth rate for snow combined with the assumption of instantaneous snow melting in the scheme.

---

## 1. Introduction

Bulk microphysics schemes (BMSs) play an important role in high-resolution 3D models and are becoming more common in operational NWP. While numerous sensitivity studies have examined the effects of varying hydrometeor categories, size distribution parameters, and mass–diameter/fall velocity relations, comparatively less research has addressed the sensitivity to the number of predicted moments — despite its importance. Milbrandt and Yau (2005a, MY05a) showed that growth rates and sedimentation were greatly improved with more prognostic moments; deep convection simulations (MY06a,b) showed dramatic improvement from single- to double-moment, with marginal additional gain to triple-moment.

The multimoment MY05a,b scheme is ideally suited for this study because it offers the same scheme in one-, two-, or three-moment variants. The goal is to understand how the moment-sensitivity from MY06b transfers to an orographic heavy-precipitation event with large-scale forcing. The 13–14 December 2001 IMPROVE-2 case (described fully in Part I, Milbrandt et al. 2008) is used, with the triple-moment control (MY-3) rerun as double-moment (MY-2) and single-moment (MY-1). For comparison, the single-moment Kong–Yau (KY97) scheme is also run.

## 2. Overview of sensitivity tests

**Table 1. Schemes used in the sensitivity runs:**

| Simulation | Microphysics scheme | Treatment of size distribution parameters |
|---|---|---|
| MY-3 | MY05a,b, triple-moment | Fully prognostic |
| MY-2 | MY05a,b, double-moment | Diagnostic $\alpha_x$; prognostic $N_{Ti}$, $N_{Tc}$, $N_{0,r}$, $N_{0,s}$, $N_{0,g}$, $N_{0,h}$ |
| MY-1 | MY05a,b, single-moment | Fixed $\alpha_x$; diagnostic $N_{Ti}$; fixed $N_{Tc}$, $N_{0,r}$, $N_{0,s}$, $N_{0,g}$, $N_{0,h}$ |
| KY | KY97 (single moment) | Fixed $\alpha_x$; diagnostic $N_{Ti}$; fixed $N_{0,r}$, $N_{0,i-s}$, $N_{0,g}$ |

All model conditions were identical to the Part I control simulation (GEM model, same initial/boundary conditions, same nested 36/12/4/1 km grids). The MY05 scheme has six categories (cloud, rain, ice, snow, graupel, hail). The KY97 scheme has four categories: cloud, rain, a hybrid pristine ice–snow category (referred to here as *snow*), and a graupel–hail category.

The MY-2 configuration uses a diagnostic $\alpha_x = f(D_{mx})$ following MY05a Eqs. (12–13), equivalent to the DIAG_B configuration in MY06b. The MY-1 configuration uses fixed $\alpha_x = 0$ for all frozen categories ($\alpha_r = 2$ for rain) with constant intercept parameters ($N_{0,r} = 10^6$, $N_{0,s} = 10^7$, $N_{0,g} = 4 \times 10^5$, $N_{0,h} = 10^5$ m⁻⁴; $N_{Tc} = 10^8$ m⁻³) and ice number concentration from the Cooper (1986) parameterization:

$$N_{Ti}(T) = 5 \exp\{0.304[T_0 - \max(233.15, T)]\}\ \text{m}^{-3}. \tag{A2}$$

## 3. Results

### a. Vertical motion

Vertical velocity fields upwind of the Cascade crest were very similar for all runs — the quasi-stationary mountain-wave pattern was essentially unchanged by the scheme. The region of upward motion on the lee side was notably larger for MY-1 and KY than for MY-2 and MY-3, but these differences did not affect forcing upwind of the crest.

[Figure 1: Vertical motion at 0000 UTC from 1-km simulations along a vertical cross section and along P-3 leg 2 for MY-3, MY-2, MY-1, and KY — image not reproducible in markdown]

### b. Precipitation

18-h (1400–0800 UTC) accumulated precipitation was compared to 145 rain gauges (4-km) and 65 gauges (1-km).

- **MY-3 and MY-2** (Figs. 2a,b, 3a,b): Very similar precipitation patterns. Systematic overprediction of quantities but realistic spatial distributions (reduced Willamette Valley, higher windward Cascades, low leeside).
- **MY-1** (Figs. 2c, 3c): Similar overall spatial pattern but larger overprediction along the coast and windward slope (>20 mm more than MY-3 in those areas), slight upwind shift.
- **KY** (Figs. 2d, 3d): Notably different — a **distinct pronounced overprediction on the immediate lee side of the Cascade crest** (>80 mm more than MY-3 in that region), similar to G05a,b's Reisner-2 runs.

Bias scores (Fig. 5) for lower thresholds (<30 mm): all runs have slight positive bias, MY-1 slightly better. For higher thresholds (>40 mm): MY-3 has least bias, KY the greatest.

[Figures 2–6: Accumulated precipitation fields and difference fields for 4-km and 1-km runs, scatterplots, and bias scores — images not reproducible in markdown]

### c. Hydrometeor mass fields

Time-averaged (2300–0100 UTC) vertical cross sections of $Q_x$ from the 1-km runs:

**MY-2 vs MY-3:** Fields are very similar across all categories. Average and peak cloud water and snow along the flight legs vary only slightly between MY-2 and MY-3. Total number concentrations and mean-mass diameters (not shown) also very similar.

**MY-1 vs MY-3:** Several notable differences:
- *Cloud*: Greater vertical extent in MY-1, with $Q_c > 0.60$ g m⁻³ at 700 hPa upwind (vs ~0.40 g m⁻³ for MY-3).
- *Ice*: Much greater $Q_i$ in MY-1 (peak >0.1 g m⁻³ at 300 hPa vs an order of magnitude less in MY-3), attributed to the Cooper (1986) ice nucleation yielding larger $N_{Ti}$ than the Meyers et al. (1992) parameterization used in MY-2/MY-3 for this temperature range.
- *Snow*: **Much less snow in MY-1** (peak $Q_s$ only 0.20–0.40 g m⁻³ vs >1.5 g m⁻³ for MY-3). Along flight legs, MY-1 snow mass was **closer to observations** than MY-3 and MY-2 (though all overpredicted).
- *Graupel*: Similar peak mass contents, but larger vertical extent in MY-1.

**KY vs MY-x:**
- *Cloud*: Much deeper than MY-2/MY-3, similar to MY-1, extending above 400 hPa with large $Q_c > 0.40$ g m⁻³ over the windward Cascades. KY and MY-1 better predict cloud water at the P-3 flight levels (though still overpredicted).
- *Rain*: Greater $Q_r$ than MY-1 throughout, plus a region of large $Q_r$ on the immediate lee side corresponding to the leeside overprediction.
- *Snow*: Pattern closer to MY-2/MY-3 than MY-1; similar overprediction at Convair-580 levels.
- *Graupel*: Only trace amounts in KY (vs appreciable in MY-x), due to strict conditions for snow-to-graupel conversion in KY97.

**Table 2. Cloud liquid water along P-3 flight legs** (mean [peak] g m⁻³):

| Leg | Obs | MY-3 | MY-2 | MY-1 | KY |
|-----|-----|------|------|------|----|
| Leg 1 (2000 m, 775 hPa) | 0.14 [0.40] | 0.09 [0.40] | 0.11 [0.55] | 0.11 [0.32] | 0.31 [0.47] |
| Leg 2 (2500 m, 725 hPa) | 0.26 [0.50] | 0.06 [0.19] | 0.06 [0.17] | 0.09 [0.34] | 0.40 [0.71] |
| Leg 3 (3450 m, 650 hPa) | 0.20 [0.25] | 0.00 [0.00] | 0.00 [0.00] | 0.02 [0.17] | 0.30 [0.55] |
| Leg 4 (4000 m, 600 hPa) | 0.12 [0.15] | 0.00 [0.00] | 0.00 [0.00] | 0.01 [0.10] | 0.03 [0.30] |
| Leg 5 (3100 m, 675 hPa) | 0.04 [0.10] | 0.01 [0.14] | 0.01 [0.07] | 0.00 [0.00] | 0.00 [0.03] |

**Table 3. Snow mass along Convair-580 legs** (mean g m⁻³):

| Leg | Obs | MY-3 | MY-2 | MY-1 | KY |
|-----|-----|------|------|------|----|
| a–b (6000 m, 450 hPa) | 0.12 | 0.37 | 0.31 | 0.26 | 0.35 |
| c–d (5300 m, 500 hPa) | 0.17 | 0.58 | 0.50 | 0.28 | 0.66 |
| e–f (4900 m, 525 hPa) | 0.25 | 0.65 | 0.54 | 0.37 | 0.69 |
| g–h (4300 m, 625 hPa) | 0.27 | 0.85 | 0.79 | 0.48 | 1.02 |

## 4. Discussion

### a. Reduction to double-moment (MY-3 versus MY-2)

The near-identical results of MY-2 and MY-3 confirm that the **diagnostic-$\alpha$ approach allows MY-2 to reproduce most of the effects of the full triple-moment scheme** for this case. MY-3 had slightly larger $Z_e$ in some regions (e.g., Willamette Valley), attributable to larger rain $Z_e$ — because the diagnosed $\alpha_r$ in MY-2 was larger than the prognostic value in MY-3, yielding a narrower rain spectrum and lower reflectivity.

### b. Reduction to single-moment (MY-3 versus MY-1)

Greater sensitivity was found when reducing to single moment: larger precipitation bias, upwind shift, but a snow–cloud mass balance closer to observations. **This contrasts with MY06b** (deep convection), where single-moment runs produced very different, unrealistic storm structures and propagation. The difference in sensitivity between the two cases is attributed to: (1) rain and hail size-sorting being more important in deep convection; (2) stronger microphysics–dynamics feedback in deep convection vs. strong large-scale orographic forcing.

The much greater ice mass in MY-1 is explained by the Cooper (1986) ice nucleation (used in MY-1) yielding larger $N_{Ti}$ than the Meyers et al. (1992) parameterization (dominant in MY-2/MY-3 for deposition-condensation freezing at −30 to −45°C). This also reduces ice-to-snow conversion in MY-1 (no aggregation pathway since $N_{Ti}$ is not prognosed; smaller ice diameter for given mass → slower conversion by deposition/riming).

The lower snow mass in MY-1 is less obvious. It is not simply faster sedimentation (snow in MY-1 sediments more slowly in most regions). Rather, the diagnostic $N_{0,s}$ in MY-1 is such that the snow spectrum is broader (smaller $\alpha_s$), reducing the depositional growth rate compared to MY-2/MY-3 which have narrower spectra (larger $\alpha_s$). This is discussed in detail via direct comparison of snow size distributions.

### c. Sensitivity to scheme choice (MY-1 versus KY)

The KY simulations produced pronounced leeside overprediction, similar to G05a,b's Reisner-2 runs. Since the same GEM model was used for KY and MY-3 (with the same large-scale forcing), this confirms that the leeside difference is attributable to the microphysics scheme. Importantly, **MY-1 did not produce leeside overprediction**, showing that the MY-3 vs. Reisner-2/KY difference cannot simply be attributed to the number of moments — other formulation differences matter.

### d. Depositional growth of snow

Differences in snow mass among the runs were examined via:

**1) Residence time.** Snow fall velocities in MY-1 were generally slower than in MY-3/MY-2 (not faster), so shorter residence time in the growth zone cannot fully explain lower snow mass. Similarly, KY has the highest fall velocities but similar or greater snow mass than MY-3/MY-2.

**2) Instantaneous growth rates.** With the same prognostic moment values prescribed for comparison:

- MY-1 has a larger $N_{0,s}$ (inverse-exponential) and lower deposition rate than MY-2 (fixed, inverse-exponential), consistent physically with fewer, larger particles for the same mass.
- MY-2 and MY-3 have **narrower spectra** (larger $\alpha_s$) and **larger depositional growth rates** — the narrowing being driven by diagnosed/prognostic $\alpha_s$.
- For KY, the snow $N_{Ts}$ depends exponentially on the saturation ratio $S_i$ via the Meyers et al. (1992) parameterization [Eq. (5)]:
  $$N_{Ts} = 1000 \exp[12.96(S_i - 1) - 0.639]\ \text{m}^{-3}$$
  leading to $N_{0,s}$ and deposition rates that increase sharply with supersaturation (by ~1 order of magnitude per 10% increase in $S_i$). This makes the KY depositional growth rate very sensitive to small changes in temperature/supersaturation.

### e. Leeside precipitation: two contributing factors

Two sensitivity tests using MY-2 identified the mechanisms causing leeside overprediction in KY (and G05a,b's Reisner-2):

**1) Latent heat effect on the diffusional growth rate.** The depositional growth rate in MY-x includes a term reducing deposition when accretion of cloud/rain water occurs (second term in the brackets of the growth rate equation), because freezing of accreted water releases latent heat, raising the local saturation mixing ratio. A sensitivity run **MY-2_S1** with this term shut off produced a distinct increase in leeside precipitation that coincided closely with the KY leeside overprediction (Fig. 15a). The KY scheme (as coded in GEM) does not include this term.

**2) Instantaneous snow melting.** In KY, snow melts instantly when ambient air temperature exceeds 0°C, concentrating the precipitation on the immediate lee side (rain has much faster fall velocities than snow, so the precipitation reaches the surface near the melting level rather than being advected further downstream). A sensitivity run **MY-2_S2** with instantaneous melting also produced increased leeside precipitation (Fig. 15b), though with less pronounced effect than the latent heat term.

Together, these two factors explain most of the leeside overprediction in KY and, likely, in G05a,b's Reisner-2 runs.

## 5. Conclusions

1. **MY-2 ≈ MY-3**: The double-moment configuration (with diagnostic $\alpha$) closely reproduced the triple-moment results for this orographic case — consistent with MY06b.
2. **MY-1 differs more**: Reduction to single-moment increased precipitation bias and caused an upwind shift, but the snow–cloud mass balance was closer to observations. This is opposite to MY06b (deep convection), where single-moment simulations were far less realistic in storm structure and propagation.
3. **Scheme identity > number of moments**: The choice of single-moment scheme had a greater impact than the number of predicted moments within the MY framework. KY produced pronounced leeside precipitation overprediction (>80 mm over MY-3), unlike MY-1.
4. **Mechanism for leeside overprediction**: The KY/Reisner-2 leeside problem is attributable to two factors: (a) absence of the latent heat effect term in the snow depositional growth rate, and (b) instantaneous rather than explicit snow melting.
5. **Snow mass can be improved**: Unconstrained multimoment configurations overpredicted snow mass, but sensitivity tests showed that imposing upper limits on $N_{0,s}$ produces snow–cloud balance much closer to observations — multimoment configurations are easily calibrated.
6. **Other error sources**: Overestimated capacitances in the electrostatic analogy for depositional growth (by a factor of 2–8 per Bailey and Hallett 2004, 2006; Westbrook et al. 2008) and the use of spherical snow particles (rather than the better-supported mass–diameter exponent of ~2; Mitchell 1996) may contribute to systematic biases across all schemes. Modernization of the MY05 snow category is underway and will be reported in a forthcoming paper.

---

## Appendix: Description of Scheme Configurations

Each hydrometeor category in all MY05 versions uses a three-parameter gamma distribution:
$$N_x(D_x) = N_{0,x} D^{\alpha_x} e^{-\lambda_x D_x}. \tag{A1}$$

**MY-2:** Mass mixing ratios and total number concentrations prognosed; $N_{0,x}$ and $\lambda_x$ computed from MY05a; $\alpha_x$ diagnosed from $D_{mx}$ following MY05a Eqs. (12–13) with constants from MY06b Table 3 (equivalent to DIAG_B in MY06b).

**MY-1:** Mass mixing ratios prognosed; $\lambda_x$ is the independent variable. Constant intercepts: $N_{0,r} = 10^6$ m⁻⁴, $N_{0,s} = 10^7$ m⁻⁴, $N_{0,g} = 4 \times 10^5$ m⁻⁴, $N_{0,h} = 10^5$ m⁻⁴; $N_{Tc} = 10^8$ m⁻³; $\alpha_x = 0$ for all frozen (except $\alpha_r = 2$); ice concentration from Cooper (1986) [Eq. A2].

---

*Acknowledgments: Research funded by the Modelling of Clouds and Climate (MOC2) project through CFCAS and NSERC.*
