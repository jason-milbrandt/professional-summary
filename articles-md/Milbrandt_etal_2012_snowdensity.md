# Predicting the Snow-to-Liquid Ratio of Surface Precipitation Using a Bulk Microphysics Scheme

**Authors:** J. A. Milbrandt and A. Glazer (Numerical Weather Prediction Research Section, Environment Canada, Dorval, Quebec, Canada); D. Jacob (National High Impact Weather Laboratory, Environment Canada, Dorval, Quebec, Canada)

**Journal:** *Monthly Weather Review*, **140**, 2461–2476 (August 2012)

**Manuscript:** received 18 October 2011, in final form 18 January 2012

**DOI:** 10.1175/MWR-D-11-00286.1

---

## Abstract

Bulk microphysics parameterizations play an increasingly important role for quantitative precipitation forecasting (QPF) in operational numerical weather prediction (NWP). For wintertime, numerical prediction of snowfall amounts is done by applying an estimated snow-to-liquid ratio to the liquid-equivalent QPF from the NWP model. A method has been developed to use prognostic fields from a detailed bulk scheme to predict the instantaneous snow-to-liquid ratio of precipitating snow. By exploiting aspects of the parameterization of the large crystal/aggregate (snow) category, which allow for a prediction of the mean particle size and a corresponding realistic bulk density, combined with pristine ice and graupel fields, the total volume flux of ice-phase precipitation (excluding hail) is computed, independently from the computation of the total solid mass flux. Ultimately, the accumulated unmelted solid precipitation quantity is thus predicted without having to estimate the average snow-to-liquid ratio for a given event, as is typically done for wintertime QPF.

The new technique has been implemented into the two-moment version of the Milbrandt–Yau microphysics scheme, which was used in a high-resolution (2.5 and 1 km) NWP modeling system over the Vancouver–Whistler region of Canada in support of forecasting for the Vancouver 2010 Olympic and Paralympic Games. Experimental fields were produced including the instantaneous snow-to-liquid ratio and the snowfall accumulation predicted directly from the scheme using the new approach. Subjective evaluation indicates that the model can discriminate between low-density and high-density snow for instantaneous precipitation. Comparison of the predicted snow-to-liquid ratio to observed climatologies indicates that the scheme produces a realistic probability distribution.

---

## 1. Introduction

The snow-to-liquid ratio (SLR) is the ratio of the volume of unmelted snow to its liquid-equivalent (melted) volume, equivalent to the ratio of the density of liquid water to the average density of the snow. From a climatology of 1650 snow events (Roebber et al. 2003), SLR ranged from 1.9 to 46.8, with mean/median/mode of 15.6/14.1/10.0. Many forecast offices still apply the "10-to-1" rule (snow density of 100 kg m⁻³; Potter 1965), though this ignores considerable case-to-case variability.

Three factors affect snow density (Roebber et al. 2003): in-cloud processes (crystal habit, riming, aggregation, breakup); sub-cloud processes (melting, sublimation); and post-precipitation surface processes (fragmentation, compaction, metamorphism). Previous approaches to estimating SLR include empirical rules, neural network ensembles (Roebber et al. 2003), and decision-tree algorithms based on NWP soundings (Dubé 2003). All are based on model configurations without sufficient detail to directly predict snow density.

This study describes the **first attempt to predict the instantaneous SLR explicitly, directly from a bulk microphysics scheme**, using information already present in the BMS with no additional prognostic variables and hence no additional computational cost. The method can be readily applied to any existing BMS.

## 2. Microphysics scheme

The BMS is the two-moment, fixed-dispersion version of the Milbrandt and Yau (2005a,b) scheme (**MY2**), with prognostic $q_x$ and $N_x$ for six categories: cloud, rain, ice, snow, graupel, hail ($x = c, r, i, s, g, h$). Since the original publications, several changes have been made to the snow category that directly impact SLR prediction:

**New $m$–$D$ relation:** $c_s = 0.1597$, $d_s = 2.078$ (MKS units), based on ground-based disdrometer observations of precipitating snow (Brandes et al. 2007). The exponent $d_s \approx 2$ implies a realistic inverse relation between maximum particle dimension $D$ and bulk snow particle density (Fig. 1).

**Constraints on snow PSD parameters:** After sedimentation, $N_s$ is recomputed such that: the intercept parameter $N_{0s}$ does not exceed $N_{0s,max} = 10^8$ m⁻⁴; and the slope $\lambda_s$ is not less than $\lambda_{s,min} = 600$ m⁻¹ (following Heymsfield et al. 2008). The latter effectively imposes a maximum mean snow particle diameter.

**New V–D parameters:** Changed to those of Locatelli and Hobbs (1974) for "aggregates of unrimed radiating assemblages of plates, side planes, bullets, and columns": $a_s = 11.720$, $b_s = 0.4100$. These produce faster-falling snow than the previous Ferrier (1994) parameters (e.g., $V_t = 1.2$ vs 0.9 m s⁻¹ for $q_s = 1.0$ g kg⁻¹ and $N_{0s} = 3 \times 10^{-6}$ m⁻⁴). The previous slow fall speeds contributed to excessive snow mass (Milbrandt et al. 2010); the new parameters fit observed velocities from Brandes et al. (2007).

**New collection efficiencies:** $E_{c\_s}$ (cloud collecting by snow) changed from unity to the Wang and Ji (2000) parameterization based on ice-crystal Reynolds numbers:
$$E_{c\_s} = \left[\frac{\min(D_{m\_c},\ 30\ \mu\text{m})}{30\ \mu\text{m}}\right]\left[\frac{\min(D_{m\_s},\ 1000\ \mu\text{m})}{1000\ \mu\text{m}}\right]^2. \tag{A4}$$
Values now range from ~0.30–1.0, increasing with cloud and snow mean sizes. Analogously, $E_{c\_g}$ and $E_{r\_g}$ (graupel collecting cloud and rain) changed from unity to the Cober and List (1993) Stokes parameter parameterization; values range 0.35–0.80.

**Reduced capacitance:** Based on Field et al. (2008) and Westbrook et al. (2008), the capacitance for diffusional growth of ice and snow changed from $C = D/2$ to $C = D/4$ (half the traditional value), correcting for the irregular shapes of real crystals.

## 3. Description of method

### a. Mass and volume fluxes

The mass flux per unit area for sedimenting category $x$:
$$F_{m\_x} = \int_0^\infty m_x(D)\, V_x(D)\, N_x(D)\, dD. \tag{1}$$

The unmelted volume flux:
$$F_{v\_x} = \int_0^\infty \frac{m_x(D)}{\rho_x(D)}\, V_x(D)\, N_x(D)\, dD. \tag{2}$$

The liquid-equivalent volume flux:
$$F_{v\_liq\_x} = \frac{1}{\rho_L} F_{m\_x}. \tag{3}$$

For ice and graupel (constant bulk density $\rho_x$):
$$F_{v\_x} = \frac{1}{\rho_x} F_{m\_x}. \tag{4}$$

For **snow**, since $d_s \approx 2$ implies a variable density, the volume flux is computed explicitly assuming a sphere with diameter $D$:
$$F_{v\_s} = \int_0^\infty \frac{\pi}{6} D^3\, V_s(D)\, N_s(D)\, dD. \tag{5}$$

The **total unmelted snow volume flux** is then:
$$F'_{v\_snow} = \frac{F_{m\_i}}{\rho_i} + \frac{F_{m\_g}}{\rho_g} + F_{v\_s}. \tag{6}$$

### b. Estimation of liquid fraction

In the current scheme, snow melts directly to rain; there is no representation of partially melted snow (snowflakes do not shed drops but gradually become liquid). To prevent unrealistically large $\text{SLR}_{inst}$ in the melting layer, the liquid fraction is estimated as:
$$f_{liq} = \frac{q_r}{q_r + (q_i + q_g + q_s)} \quad [\text{where } T > 0°\text{C}]. \tag{7}$$

The corrected unmelted volume flux:
$$F_{v\_snow} = (1 - f_{liq}) F'_{v\_snow} + f_{liq} F_{v\_liq} \quad [\text{if } T > 0°\text{C}]. \tag{8}$$

The instantaneous SLR:
$$\text{SLR}_{inst} = F_{v\_snow} / F_{v\_liq\_snow}.$$

The accumulated snow depth $A$ and SLR over an accumulation period:
$$\text{SLR} = A / A_{liq}. \tag{9}$$

### c. Other processes

Post-precipitation processes (fragmentation, compaction) are not considered; analogous to liquid-equivalent QPF not accounting for drainage. These should be handled by the land surface scheme.

## 4. Model configuration

In support of the Vancouver 2010 Winter Olympics and Paralympics (12 February – 28 March 2010; 12–21 March for Paralympics), Environment Canada developed a high-resolution (2.5 and 1-km) configuration of the GEM NWP model (Côté et al. 1998). The system was run in real time by the CMC: a variable-resolution global forecast (15-km over Canada) was cascaded to 15-, 2.5-, and 1-km LAM grids centered over Vancouver–Whistler (Fig. 3). The MY2 scheme with SLR modifications provided SLR, unmelted snowfall, and snowfall accumulation fields.

## 5. Results

### a. Application for the Vancouver 2010 Winter Games

The forecast output was made available to forecasters. A forecast on 23 February 2010 at Cypress Bowl South showed SLRinst varying from ~20 (afternoon: "large, fluffy snowflakes") to ~5 (evening: "fast falling snow pellets"), consistent with a riming period leading the dominant category to switch from *snow* to *graupel* around 0300 UTC. The model correctly predicted the rapid transition in snow type.

### b. Effect of liquid fraction correction

Without the $f_{liq}$ correction, SLRinst values in regions where snow is melting at the surface are unrealistically large (often >30). With the correction, SLRinst approaches 1 as melting increases. The need is more pronounced for two-moment (where aggregation simulates increasing mean size and decreasing density) than for one-moment.

### c. Snowfall event over a broad region

The method produces spatially variable SLRinst correlated with the mean-mass snow diameter $D_{m\_s}$: large $D_{m\_s}$ (low density, high SLR) vs small $D_{m\_s}$ (high density, low SLR). SLRinst for the snow-dominant period ranged ~15–23 at one station, reflecting the variable orography and microphysics in the coastal-maritime region.

### d. Preliminary verification

Comparison of model SLR to a 20-yr (1990–2010) climatology of 941 snowfall events at the VOA (Whistler Mountain) station: model values range 4.6–22.5 (mean 12.2) vs observed 2.3–62.3 (mean 12.6). The model PDF is very similar to the observed distribution, except for underprediction of extreme values (SLR < 6 or > 18). Comparison to the Roebber et al. (2003) and Baxter et al. (2005) climatologies for the continental U.S. also shows a remarkably similar distribution — likely not fortuitous given the sensitivity of SLR to specific aspects of the scheme. No forecast skill was found for individual point-to-gridpoint comparisons (the field is too spatially variable for station-to-gridpoint verification in complex terrain).

## 6. Discussion

**Limitations in the scheme:** (a) Assumption that snow is a sphere with diameter $D$ — valid for fractal-like aggregates, but some packing occurs, so SLRinst is an upper-limit estimate. (b) Rime density is still constant ($\rho_g = 400$ kg m⁻³); variable graupel density is under development. (c) Liquid fraction treatment is approximate; melting processes' effects on fall velocities should be corrected. (d) Ice pellets treated as small hail, currently excluded from the SLR calculation.

**Post-precipitation processes:** The explicit SLR method does not account for compaction, which reduces SLR (and snow depth) for heavy accumulations. Unlike statistical methods (where QPF and SLR errors compensate), in the explicit method errors can combine. A calibration factor based on precipitation rate could be applied to account for this.

**Operational status:** The MY2 scheme with these modifications was incorporated into a high-resolution (2.5-km) deterministic prediction system run by the CMC for various regions of Canada; the prognostic SLR and snowfall quantity fields are now available for operational meteorologists.

## 7. Conclusions

A technique was proposed and evaluated to **predict the instantaneous snow-to-liquid ratio explicitly from a bulk microphysics scheme**, using the volume fluxes of ice, snow, and graupel independently from mass fluxes. The method exploits the variable bulk snow density naturally provided by the $d_s \approx 2$ mass–diameter relation and uses no additional prognostic variables. Combined with a liquid-fraction correction for partial melting, the method was implemented in MY2, run in real-time on 2.5- and 1-km grids during the Vancouver 2010 Winter Games. The method produces realistic distributions of SLR values consistent with observed climatologies.

A key appendix documents several snow-category improvements to MY2, including: new $m$–$D$ relation, new V–D parameters, PSD slope/intercept constraints, reduced capacitance, and new collection efficiencies — the modernizations of the snow category that were announced as forthcoming in Milbrandt et al. (2010).

---

## Appendix: The Bulk Microphysics Scheme

A brief overview of MY2 plus the specific snow-category changes listed above (see Sections 3a–d above for details). Key additional formulas:

PSD: $N_x(D) = N_{0x} D^{m_x} e^{-\lambda_x D}$ with $m_x = 0$ for $x = i, r, s, g, h$ and $m_c = 3$.

The mean-mass diameter for each category:
$$D_{m\_x} = \left(\frac{c_x q_x}{\rho_L N_x}\right)^{1/d_x}. \tag{A2}$$

Snow $m$–$D$ parameters: $c_s = 0.1597$, $d_s = 2.078$ (mks). The resulting bulk snow density varies approximately as $\rho_s \propto 1/D$, consistent with observations (Brandes et al. 2007, Fig. 1 in paper).

---

*Acknowledgments: Thanks to colleagues in RPN and CMC at Environment Canada, to the forecast team for the Winter Games, and to H. Morrison, R. McTaggart-Cowan, and two anonymous reviewers.*
