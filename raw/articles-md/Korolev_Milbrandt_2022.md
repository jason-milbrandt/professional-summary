# Korolev, A., & Milbrandt, J. (2022): How Are Mixed-Phase Clouds Mixed?

**Full citation:** Korolev, A., & Milbrandt, J. (2022): How are mixed-phase clouds mixed? *Geophysical Research Letters*, **49**, e2022GL099578. DOI: 10.1029/2022GL099578

**Journal:** Geophysical Research Letters
**Year:** 2022
**Authors:** Alexei Korolev, Jason Milbrandt
**Affiliation:** Environment and Climate Change Canada, Atmospheric Science and Technology Directorate, Toronto, ON, Canada

---

## Abstract

Mixed-phase clouds are recognized as significant contributors to the modulation of precipitation and radiation transfer on both regional and global scales. This study is focused on the analysis of spatial inhomogeneity of mixed-phase clouds based on an extended data set obtained from airborne in situ observations. The lengths of continuous segments of ice, liquid, and mixed-phase clouds present a cascade of scales varying from $10^2$ km down to a minimum scale of 100 m determined by the spatial resolution of measurements. It was found that the phase composition of mixed-phase clouds is highly intermittent, and the frequency of occurrence of ice, liquid, and mixed-phase regions increases with the decrease of their spatial scales. The distributions of spatial scales have well-distinguished power-law dependencies. The results obtained yield insight into the morphology of mixed-phase clouds and have important implications for improvement in representing subgrid inhomogeneity of mixed-phase clouds in weather and climate models.

---

## Key Points

- In mixed-phase clouds, droplets and ice particles may be uniformly distributed (genuinely mixed) or spatially separated (conditionally mixed)
- Horizontal lengths of genuine mixed-phase and single-phase ice and liquid clouds present a cascade of scales from 100 km down to 100 m or less
- At small scales, mixed-phase clouds have high spatial intermittency, which is currently unconstrained in weather and climate models

## Author Contributions

- **Conceptualization:** Alexei Korolev, Jason Milbrandt
- **Data curation:** Alexei Korolev
- **Formal analysis:** Alexei Korolev
- **Methodology:** Alexei Korolev, Jason Milbrandt
- **Project Administration:** Alexei Korolev, Jason Milbrandt
- **Writing – original draft:** Alexei Korolev
- **Writing – review & editing:** Alexei Korolev, Jason Milbrandt

---

## 1. Introduction

Mixed-phase clouds represent a three-phase colloidal system consisting of water vapor, ice particles, and supercooled liquid droplets. They are ubiquitous in the troposphere, occurring at all latitudes from the polar regions to the tropics, and play important roles in precipitation formation and the radiative energy balance on both regional and global scales.

There are two possible extremes of mixing:

1. **Genuine mixed-phase:** ice particles and liquid droplets are uniformly distributed in a cloud volume.
2. **Conditional mixed-phase:** ice particles and liquid droplets are clustered in single-phase regions with complex morphology; ice and liquid are spatially separated.

In genuine mixed-phase clouds, the Wegener–Bergeron–Findeisen (WBF) process can operate — ice grows at the expense of evaporating droplets — eventually glaciating the cloud. Glaciation time varies from a few minutes to tens of minutes depending on temperature, ice concentration, and liquid water content.

In conditional mixed-phase clouds, the WBF process is suppressed because ice and liquid are spatially separated. Such clouds are colloidally more stable, and their endurance is controlled by processes other than the WBF mechanism. Precipitation formation in conditional clouds is slower (for the same total ice and liquid amounts), and radiative properties differ because liquid is concentrated in droplet clusters rather than uniformly distributed.

Understanding spatial phase intermittency is critical for numerical modeling: many climate and NWP models use cloud fraction representations for liquid and ice contents, but the degree of overlap of in-cloud liquid and ice within a grid cell (the mixed-phase cloud fraction) is currently unconstrained. Grid spacings range from ~3–15 km in NWP systems to 60–300 km in global climate models, and the assumption of homogeneous mixing can bias precipitation production and radiation transfer.

---

## 2. Methodology and Data Set

### Airborne Platform and Instrumentation

Measurements were collected by the NRC Convair-580 research aircraft equipped by Environment and Climate Change Canada (ECCC) in collaboration with the National Research Council (NRC). The instrument suite included:

- **Nevzorov probe** — liquid water content (LWC) and ice water content (IWC) measurements; primary phase discrimination tool
- **Rosemount Icing Detector** — identification of liquid phase presence; used to exclude false liquid signals in ice clouds
- **FSSP (Forward Scattering Spectrometer Probe)** — identifies liquid droplets < 45 μm diameter
- **OAP-2DC and OAP-2DP (Optical Array Probes)** — ice particle identification by non-circular binary image shapes

### Phase Discrimination

Cloud phase composition was determined using the ice water fraction:

$$\mu = \frac{IWC}{LWC + IWC}$$

- Ice cloud: $\mu > 0.9$
- Liquid cloud: $\mu < 0.1$
- Mixed-phase: $0.1 \leq \mu \leq 0.9$

Thresholds: LWC > 0.01 g m$^{-3}$, IWC > 0.01 g m$^{-3}$.

The smallest resolved spatial scale was 100 m, determined by the Nevzorov probe temporal resolution (~1 s) and aircraft sampling speed (~100 m s$^{-1}$). Mixed-phase clouds at the 100 m scale were assumed to be genuinely mixed.

### Data Set

Seven flight campaigns led by ECCC over a 10-year period, covering midlatitude and Arctic clouds in the temperature range $-35 < T < 0°C$. Campaign names mentioned: BASE, CFDE, FIRE-ACE, AIRS.

### Analysis

Time series of LWC and IWC were converted to three discrete phase categories (ice, liquid, mixed-phase). The algorithm counted continuous cloud lengths, resetting when phase changed or water contents fell below thresholds. Isolated single-phase clouds (not adjacent to clouds of another phase) were excluded. The ensemble consisted of continuous conditional and genuine mixed-phase cloud segments.

---

## 3. Results

### Spatial Scale Distributions

The lengths of continuous segments of ice, liquid, and mixed-phase clouds span a wide range:

- Scales from $10^1$–$10^2$ km down to a minimum of ~100 m (instrument resolution limit)
- Distributions follow well-defined **power-law** dependencies: $f(L) \propto L^{-\alpha}$
- The frequency of occurrence of ice, liquid, and mixed-phase regions **increases with decreasing spatial scale** — spatial intermittency is high at small scales

### Temperature Dependence

Average lengths of ice, liquid, and mixed-phase cloud segments vary with temperature. The analysis covers $-35 < T < 0°C$.

### Physical Interpretation (Section 4)

The spatial scale of genuine mixed-phase clouds is governed by a balance between the WBF glaciation timescale and turbulent mixing:

$$L_{ph} \approx u' \cdot \tau_{WBF}$$

Substituting typical atmospheric values ($\varepsilon = 10^{-3}$–$10^{-4}$ m$^2$ s$^{-3}$, LWC = 0.01–1.0 g m$^{-3}$, $N_i = 10^1$–$10^2$ L$^{-1}$) yields spatial phase scales $L_{ph} \sim 10^1$–$10^4$ m, consistent with observations.

The LWC frequency distribution $f(W)$ increases with decreasing LWC, which explains the increasing occurrence of small-scale mixed-phase clouds (following from the $L_{ph}$–LWC relationship in Equation 4).

### Minimum Cluster Scale Estimates

The smallest single-phase cluster scale is estimated as:

$$L_{min} \sim (n_{tot}/N)^{1/3}$$

For typical ice concentrations $N_i \sim 0.01$–$10$ L$^{-1}$: $L_{min}$ for ice clusters $\approx 0.1$–$1$ m.  
For ice multiplication ($N_i \sim 10^3$ L$^{-1}$): $L_{min}$ for ice may reach centimeter scales.  
For droplets ($N_{dr} \sim 10$–$1000$ cm$^{-3}$): $L_{min} \approx 2$–$10$ mm.

These theoretical minima are far smaller than the 100 m instrumental resolution of this study. The true minimum scale remains an open question.

---

## 4. Conclusions

- Mixed-phase clouds exhibit spatial phase intermittency from $\sim 100$ km down to the ~100 m measurement resolution, with the true minimum scale possibly reaching 1–10 m or smaller.
- Distributions of ice, liquid, and mixed-phase segment lengths follow power-law dependencies.
- Even cloud-resolving and high-resolution mesoscale models (grid spacings of a few km or less) are unlikely to represent subgrid-scale phase heterogeneity well — they are biased toward genuinely mixed.
- Improving the representation of mixed-phase cloud type in models of all types would improve:
  - Cloud optical properties and radiative transfer
  - WBF process rates and glaciation time
  - Precipitation production and cloud brightness

In situ observations can potentially be used to validate and calibrate atmospheric models for their ability to represent subgrid-scale phase heterogeneity.

---

## Data Availability

Data available at: https://doi.org/10.5281/zenodo.6558498

---

## References (abbreviated)

- Korolev et al. (2017): Mixed-phase clouds: Progress and challenges. *Meteorological Monographs*, 58.
- Korolev & Mazin (2003): Supersaturation of water vapor in clouds. *JAS*, 60.
- Field et al. (2004): Simultaneous radar and aircraft observations of mixed-phase cloud at the 100 m scale. *QJRMS*, 130.
- McTaggart-Cowan et al. (2019): Modernization of atmospheric physics parameterization in Canadian NWP. *JAMES*, 11.
- Wood & Field (2011): The distribution of cloud horizontal sizes. *J. Climate*, 24.

[Figure 1: Conceptual diagrams of (a) genuine and (b) conditional mixed-phase clouds — image not reproducible in markdown]
[Figure 2: Frequency distributions of spatial scales of ice, liquid, and mixed-phase cloud segments — image not reproducible in markdown]
[Figure 3: Average lengths of ice, liquid, and mixed-phase cloud segments versus temperature — image not reproducible in markdown]
[Figure 4: Normalized frequency of occurrences of liquid water content in liquid and mixed-phase clouds — image not reproducible in markdown]
