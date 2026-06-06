# Jensen et al. (2017): Predicting Ice Shape Evolution in a Bulk Microphysics Model

**Full citation:** Jensen, A. A., Harrington, J. Y., Morrison, H., and Milbrandt, J. A. (2017): Predicting Ice Shape Evolution in a Bulk Microphysics Model. *Journal of the Atmospheric Sciences*, **74**, 2081–2104. DOI: 10.1175/JAS-D-16-0350.1

---

## 1. Introduction

Ice particles in the atmosphere have complex shapes, varying sizes, and liminal (transitional) nature that make accurate microphysical modeling difficult. Traditional bulk schemes assume ice can be represented by a few predefined categories (cloud ice, snow, graupel) with fixed mass–dimensional (m–D) and fall speed–dimensional (v–D) relationships. A key deficiency is that conversion from rimed snow to graupel involves ad hoc or tunable thresholds; partially rimed states cannot be captured. Furthermore, shape-dependent processes (habit-dependent riming, vapor growth) are absent from traditional approaches.

Previous advances toward more physically-based ice representations include:
- Morrison and Grabowski (2008): evolving rime-mass fraction
- Morrison and Milbrandt (2015) / P3: predicting rime mass, rime volume, and rime density; removes snow–graupel conversion
- Harrington et al. (2013a,b) / AHAB: predicting ice crystal shape during vapor growth
- Jensen and Harrington (2015): single-particle model of mass, shape, maximum dimension, density, and fall speed during riming

This paper extends these ideas into a bulk microphysics scheme — ISHMAEL — that predicts ice shape evolution during both vapor growth and riming.

---

## 2. ISHMAEL Scheme Description

**ISHMAEL** (Ice-Spheroids Habit Model with Aspect-Ratio Evolution) predicts evolution of:
- Mass mixing ratio ($q$)
- Number concentration ($N$)
- Maximum dimension (via shape and mass)
- Aspect ratio ($\phi$, ratio of minor to major axis length)
- Density (via shape and mass)

### Ice Species

Two primary ice species are employed, nucleated based on temperature:
- Ice one ($q_1$): nucleated at temperatures favorable for planar habits (e.g., dendrites, plates)
- Ice two ($q_2$): nucleated at temperatures favorable for columnar habits

A third aggregate species ($q_3$) is also included, diversifying ice properties.

### Shape Evolution During Vapor Growth

Shape evolution uses the Adaptive Habit (AHAB) theory from Harrington et al. (2013a,b) and Chen and Lamb (1994). The crystal is modeled as a spheroid. The axis ratio evolves based on temperature-dependent depositional growth rates along the a and c crystallographic axes. The ice particle shape controls:
- The cross-sectional area for riming
- The fall speed
- The collection efficiency

### Shape Evolution During Riming

Following Jensen and Harrington (2015), riming evolves the aspect ratio, mass, and density of the ice particle. Supercooled droplets freeze preferentially along the minor axis, thickening the particle. This leads to:
- Fall speed increase without significant increase in maximum dimension (contrast to traditional m–D approaches)
- Aspect ratio evolving continuously from unrimed to lightly rimed to densely rimed states

### Advection

All prognostic quantities (mass, number, shape tracers) are advected together using mass-weighted fall speeds, allowing aspect ratio sorting in physical space.

---

## 3. Tests and Evaluation

### 3.1. Vapor Growth Tests

Bulk model simulations of ice habit evolution during vapor growth compared against wind tunnel data. ISHMAEL captures the observed temperature-dependent habit development including plate and columnar growth regimes.

### 3.2. Riming Tests

Bulk model simulations of riming compared against wind tunnel data (Takahashi and Fukuta 1988; Fukuta and Takahashi 1999). ISHMAEL captures:
- Habit-dependent riming (isometric particles rime more readily than dendrites at low liquid water contents)
- The effect of riming on fall speed

### 3.3. Lagrangian Parcel Studies

Bulk model captures ice property evolution during riming and melting compared with a bin model reference.

---

## 4. 2D Kinematic Framework

ISHMAEL is tested in a 2D kinematic model with a simple updraft in High Shear (HS) and Low Shear (LS) environments, with five updraft strengths (1–5 m/s).

### Key Results

**Aspect ratio sorting:**
- As ice particles rime and their aspect ratio evolves, faster-falling, more-rimed ice settles near the updraft while more-pristine ice is advected away
- This natural sorting produces a different spatial precipitation distribution compared to traditional schemes

**Comparison to MY2 (Milbrandt–Yau):**
- MY2 consistently produces precipitation over a larger spatial range than ISHMAEL
- Accumulated precipitation decreases monotonically with distance from the updraft in ISHMAEL, but levels off in MY2
- This reflects MY2's parameterization of snow–graupel conversion vs. ISHMAEL's continuous aspect ratio evolution

**Predicting partially rimed ice:**
- A significant fraction of ice in ISHMAEL exists as partially rimed states (0.5 < rime fraction < 0.8) that are absent in traditional schemes
- This partially rimed ice has a broad range of fall speeds, sorted by aspect ratio in physical space
- Predicting partial riming leads to reduced vapor growth rates and increased riming rates near z = 5 km in the updraft

**Sensitivity studies:**
- DEND (all ice nucleated as dendrites): similar spatial precipitation but different rate evolution
- S-INIT (ice species split by size rather than temperature): faster riming in LS environment, monomodal precipitation distribution
- CONV (mimicking MY2 via snow–graupel conversion): produces MY2-like spatial distribution when aggregation is included (CONV-AGG)

---

## 5. Discussion and Conclusions

1. ISHMAEL advances beyond traditional bulk schemes by predicting ice particle shape (aspect ratio), which enables habit-dependent vapor growth and riming
2. Shape evolution produces natural aspect ratio sorting in physical space, a process missing from traditional models
3. Aspect ratio sorting leads to a different spatial precipitation distribution than traditional models (e.g., MY2)
4. Transitional partially rimed ice has a broad range of fall speeds that impact spatial distribution and cloud phase partitioning
5. Predicting partial riming leads to a reduction in vapor growth rates and increase in riming rates compared to traditional approaches
6. ISHMAEL is expected to improve forecasts of orographic precipitation, snow–rain transition elevation, and avalanche/flooding hazard
7. Habit-dependent riming allows modeling of environments where dendrites grow by vapor while isometric particles rime simultaneously — a regime inaccessible to traditional models

---

## References (selected)

- Morrison, H., and Milbrandt, J. A. (2015): P3 Part I. *J. Atmos. Sci.*, **72**, 287–311.
- Morrison, H., and Milbrandt, J. A. (2016): P3 Part III. *J. Atmos. Sci.*, **73**, 975–995.
- Milbrandt, J. A., and Morrison, H. (2013): Predicting graupel density in a bulk microphysics scheme. *J. Atmos. Sci.*, **70**, 410–429.
- Milbrandt, J. A., and Yau, M. K. (2005a, 2005b): MY2 Parts I & II. *J. Atmos. Sci.*, **62**, 3051–3081.
- Jensen, A. A., and Harrington, J. Y. (2015): Modeling ice crystal aspect ratio evolution during riming. *J. Atmos. Sci.*, **72**, 2569–2590.
- Harrington, J. Y., Sulia, K., and Morrison, H. (2013a, 2013b): AHAB Parts I & II. *J. Atmos. Sci.*, **70**, 349–376.
