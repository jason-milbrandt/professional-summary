# Cholette, M., J.M. Thériault, J.A. Milbrandt, and H. Morrison, 2020: Impacts of Predicting the Liquid Fraction of Mixed-Phase Particles on the Simulation of an Extreme Freezing Rain Event: The 1998 North American Ice Storm. *Mon. Wea. Rev.*, **148**, 3799–3821. DOI: 10.1175/MWR-D-20-0026.1

---

## Abstract

A prognostic equation for the liquid fraction of mixed-phase particles has been added to the Predicted Particle Properties (P3) bulk microphysics scheme. Mixed-phase particles are necessary to simulate key microphysical processes leading to various winter precipitation types, such as ice pellets and freezing rain. To illustrate the impacts of predicting the bulk liquid fraction (Fi,liq), the 1998 North American Ice Storm is simulated using the WRF Model with the modified P3 scheme (P3_MOD) versus the original (P3_ORIG). Predicting partial melting produces higher mass and number mixing ratios of rain, smaller rain sizes in the refreezing layer, and decreases freezing rain accumulation at the surface by up to 30% in some locations. Solid surface precipitation rates are generally higher in P3_MOD due to increased fall speed and density during partial melting and improved refreezing representation.

---

## 1. Introduction and Background

Winter precipitation types (snow, wet snow, ice pellets, freezing rain) form in environments with warm layers aloft and cold layers near the surface. Correct prediction requires explicit representation of partial melting and refreezing of mixed-phase particles — processes not captured in most bulk microphysics schemes, which assume binary ice/liquid transitions. The P3 scheme (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016) predicts particle properties (rime fraction, density, dimension) rather than fixed hydrometeor categories. Cholette et al. (2019, hereafter C19) extended P3 by adding a prognostic liquid mass mixing ratio (qi,liq) on ice particles, enabling prediction of the bulk liquid fraction Fi,liq = qi,liq / qi,tot.

---

## 2. Experimental Design

### Model

WRF v3.9.1.1; 352×352 grid, 3-km horizontal spacing, 56 vertical levels. Domain: southern Quebec (Lake Ontario to New Brunswick). Period: 0600 UTC 4–10 January 1998. Initial/boundary conditions from NARR (32 km, 3-hourly). No data assimilation.

### Simulations

| Label | Description |
|-------|-------------|
| P3_ORIG | Original P3 (Morrison and Milbrandt 2015; Milbrandt and Morrison 2016) |
| P3_MOD | P3 extended with predicted Fi,liq (Cholette et al. 2019) |

### Key Differences P3_MOD vs. P3_ORIG

**P3_ORIG**: Melted mass immediately converted to rain (sharp fall speed increase); instantaneous refreezing assumed.

**P3_MOD**:
- Tracks liquid mass on ice (qi,liq) as prognostic variable
- Melting increases Fi,liq gradually; partial melting increases density (ri,rim) and fall speed of ice particles
- Smaller raindrops generated from partial melting, reducing raindrop size entering refreezing layer
- Refreezing process improved: particles with ice fraction present freeze faster; raindrop sizes increase upon refreezing

---

## 3. Results

### Meteorological Overview

Both simulations reproduced observed temperature profiles, winds, and storm structure reasonably well. The 1998 Ice Storm produced nearly 100 mm of freezing rain accumulation in southern Quebec.

### Impact on Precipitation Types

- **Freezing rain**: P3_MOD produces generally lower freezing rain accumulation than P3_ORIG, with reductions up to ~30% in regions where ice pellets and freezing rain coexist. Both show consistent improvement vs. observations.
- **Ice pellets**: P3_MOD produces ice pellets where P3_ORIG does not, via the explicit refreezing of partially melted particles.
- **Solid precipitation**: P3_MOD generally shows higher total solid rates (snow + ice pellets) due to increased particle density and fall speed during melting.

### Physical Mechanisms

1. **Partial melting**: increases particle density → increases fall speed → particles spend less time in warm layer → less total melting.
2. **Raindrop size**: smaller drops from partial melting → more likely to refreeze completely in cold layer → more ice pellets.
3. **Refreezing**: removes the implicit melting scaling factor for Nrain change in P3_ORIG, leading to larger particles growing during refreezing.

### Bias/RMSE

Small but consistent improvement in P3_MOD vs. P3_ORIG relative to surface precipitation type observations.

---

## 5. Conclusions

Predicting Fi,liq in P3 substantially impacts simulated precipitation type distributions in winter storms. P3_MOD reproduces ice pellets and wet snow that P3_ORIG cannot produce, and reduces freezing rain accumulation by up to 30%. Solid precipitation accumulation is generally higher. Limitations: ice pellet underestimation near Montreal; single ice category precludes secondary ice production; high-temporal-resolution observations of precipitation type needed for rigorous validation.
