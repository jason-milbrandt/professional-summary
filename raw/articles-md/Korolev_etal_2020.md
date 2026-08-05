# A New Look at the Environmental Conditions Favorable to Secondary Ice Production

**Full citation:** Korolev, A., I. Heckman, M. Wolde, A. S. Ackerman, A. M. Fridlind, L. A. Ladino, R. P. Lawson, J. Milbrandt, and E. Williams, 2020: A new look at the environmental conditions favorable to secondary ice production. *Atmos. Chem. Phys.*, **20**, 1391–1429. DOI: 10.5194/acp-20-1391-2020

---

## Abstract

This study attempts a new identification of mechanisms of secondary ice production (SIP) based on the observation of small faceted ice crystals (hexagonal plates or columns) with typical sizes smaller than 100 µm. Due to their young age, such small ice crystals can be used as tracers for identifying the conditions for SIP. Observations were conducted in oceanic tropical mesoscale convective systems (MCSs) and midlatitude frontal clouds in the temperature range from 0 to −15°C, in heavily seeded regions of aged ice particles. In both MCSs and frontal clouds, SIP was observed right above the melting layer and extended to higher altitudes with colder temperatures.

The roles of six possible mechanisms to generate SIP particles are assessed using additional observations. In most observed SIP cases, small secondary ice particles spatially correlated with liquid-phase, vertical updrafts, and aged rimed ice particles. However, in many cases, neither graupel nor liquid drops were observed in the SIP regions, and therefore the conditions for an active Hallett–Mossop process were not met. In many cases, large concentrations of small pristine ice particles were observed right above the melting layer, starting at temperatures as warm as −0.5°C. It is proposed that the initiation of SIP above the melting layer is stimulated by the recirculation of large liquid drops through the melting layer with convective turbulent updrafts. After re-entering a supercooled environment above the melting layer, they impact with aged ice, freeze, and shatter. The size of the splinters generated during SIP was estimated as 10 µm or less. A principal conclusion of this work is that only the freezing-drop shattering mechanism could be clearly supported by the airborne in situ observations.

---

## 1. Introduction

Secondary ice production (SIP) is a fundamental cloud microphysical process. Along with primary ice formation via ice nucleating particles (INPs), vapor growth, aggregation, riming, and sedimentation, SIP commonly plays a critical role in the formation of ice particle size distributions and habits. Through the modulation of ice particle concentration, SIP can impact precipitation formation, glaciation rate of mixed-phase clouds, cloud longevity, cloud electrification, and radiative properties.

A persistently observed discrepancy of up to 5 orders of magnitude between INP concentrations and measured ice concentrations has motivated the search for secondary ice production mechanisms since the 1960s. Proposed mechanisms include:
1. **Droplet fragmentation during freezing** (drop shattering) — Langham and Mason (1958)
2. **Hallett–Mossop (HM) rime splintering** — active when riming of graupel occurs between −3 and −8°C
3. **Collisional fragmentation** of ice particles
4. **Thermal shock fragmentation**
5. **INP activation around freezing drops**
6. **Activation of INPs in the wake of ice particles**

In microphysics schemes that predict ice number concentration — including spectral (bin) and multi-moment bulk schemes (e.g., Milbrandt and Yau 2005) — SIP is most commonly modeled exclusively with a simple Hallett–Mossop parameterization.

---

## 2. Method: Small Faceted Ice Crystals as SIP Tracers

Small faceted hexagonal ice crystals (columns, short columns, plates) with $L_{max} < 100$ µm are used as tracers to identify SIP cloud regions. Key rationale:

- The typical vapor deposition growth time for small ice columns to grow to 40–50 µm at water saturation is $\tau_{corr} \sim 60$–120 s
- Therefore, such small crystals are still spatially associated with the environment in which they were produced
- This allows the conditions at the time of SIP to be inferred from the observed co-located cloud environment

A convolutional neural network (fine-tuned from Krizhevsky et al. 2017) was used to identify small hexagonal faceted ice crystals in Cloud Particle Imager (CPI) images, with 96% classification accuracy on validation images.

---

## 3. Observational Datasets

### Tropical MCSs
- 10 tropical MCSs sampled during 13 flights in tropical oceanic conditions, temperature range $-15°C < T_a < 0°C$
- ECCC's Convair 580 research aircraft instrumented with CPI, UHSAS, and other probes
- Concentration of small faceted ice crystals peaked at 500–1000 L$^{-1}$

### Midlatitude Frontal Clouds
- BAIRS2/WERVEX project, 24 March 2017, midlatitude frontal cloud system over Ontario/NY region
- Convair 580 performed porpoise and spiral ascents/descents in the melting layer region (2400–4200 m altitude, $-6°C < T_a < +2°C$)

---

## 4. Key Observational Findings

### Correlation with Cloud Environment Variables
- Best correlation between small faceted ice crystal concentration and liquid droplet concentration was for drops with $D > 60$ µm in tropical MCSs (correlation coefficient ~0.5–0.7 at 30–60 s averaging)
- For midlatitude frontal clouds, best correlation at $D > 40$ µm
- In several cases, no liquid was observed in SIP cloud regions

### Vertical Structure of SIP
- SIP was observed immediately above the melting layer starting at temperatures as warm as $T_a = -0.5°C$
- In MCSs, SIP extended to temperatures down to $-15°C$ with concentration decreasing with height
- Vertical correlation of SIP regions with coldest cloud tops in MCSs; no such dependence found in frontal clouds

### Assessment of SIP Mechanisms
For each of six candidate mechanisms:
1. **Drop shattering**: Evidence was found in many cases (frozen drops with deformed shapes, small faceted crystals, enhanced turbulence near melting layer). **Concluded to be the most likely dominant mechanism.**
2. **HM rime splintering**: In many cases, conditions were not met (no graupel or liquid drops in SIP region, or outside $-3$ to $-8°C$ temperature range)
3. **Collisional fragmentation**: Cannot be confirmed or ruled out; quantitative data insufficient
4. **Thermal shock fragmentation**: Possible contribution but cannot be quantified
5. **INP activation near freezing drops**: Concentrations of frozen drops far exceed expected INP concentrations by orders of magnitude; mechanism cannot account for observed concentrations
6. **INP activation in particle wakes**: Insufficient evidence

---

## 5. Conceptual Model of SIP near the Melting Layer

A chain-reaction mechanism is proposed:
1. Ice particles from above fall into the melting layer and partially melt into liquid drops
2. Convective updrafts recirculate these large supercooled drops ($D = 40$–60 µm optimal) above the melting layer
3. Above the melting layer, the drops impact aged rimed ice particles, freeze, and shatter, producing small ice splinters ($L \leq 10$ µm)
4. The splinters grow by vapor deposition in the supersaturated-over-water environment, become faceted ice crystals detectable as $L_{max} < 100$ µm
5. This chain reaction sustains and amplifies SIP

---

## 6. Implications for Microphysics Parameterization

In multi-moment bulk schemes such as MY2 (Milbrandt and Yau 2005) and P3, SIP is currently parameterized exclusively as the Hallett–Mossop process (active only at $-3$ to $-8°C$ during graupel riming). The paper's findings suggest:
- The drop shattering mechanism is active in a wider temperature range and in cloud environments where HM conditions are not met
- Future parameterizations should incorporate drop shattering as a SIP mechanism
- Observations from this paper can be used by cloud modeling studies (e.g., Qu et al. 2018) to evaluate where small ice appears at high concentrations in simulations

---

## 7. Conclusions

1. SIP was observed above the melting layer at $T_a$ as warm as $-0.5°C$ in both tropical MCSs and midlatitude frontal clouds
2. Most SIP cases were associated with liquid droplets ($D = 40$–60 µm), convective updrafts or turbulence, and aged rimed ice
3. The freezing-drop shattering mechanism is the most likely dominant SIP mechanism based on the collected data
4. HM rime splintering conditions were often not met in observed SIP regions
5. The minimum splinter size during SIP was estimated at $\leq 10$ µm
6. In MCSs, SIP regions vertically correlate with the coldest cloud tops
7. Conclusions are based on needle-like aircraft penetrations; the qualitative character of results reflects the challenge of observing 3D cloud evolution from 1D flight tracks

[Figures 1–25: CPI images of small faceted ice crystals and frozen drops; in situ microphysics time series during tropical MCS and frontal cloud cases; correlation statistics; average concentration profiles; conceptual models of SIP near the melting layer.]

---

*Received: 28 June 2019. Published: 5 February 2020.*
