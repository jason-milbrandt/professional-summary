# Boudala, F.S., I. Gultepe, and J.A. Milbrandt, 2021: The Performance of Commonly Used Surface-Based Instruments for Measuring Visibility, Cloud Ceiling, and Humidity at Cold Lake, Alberta. *Remote Sensing*, **13**, 5058. DOI: 10.3390/rs13245058

---

## Abstract

Data from automated meteorological instruments are used for model validation and aviation applications, but their measurement accuracy has not been adequately tested. In this study, a number of ground-based in-situ, remote-sensing instruments that measure visibility (VIS), cloud base height (CBH), and relative humidity (RH) were tested against data obtained using standard reference instruments and human observations at Cold Lake Airport, Alberta, Canada. The instruments included the Vaisala FS11P and PWD22 (FSPW), a profiling microwave radiometer (MWR), the Jenoptik ceilometer, Rotronic, Vaisala WXT520, AES-Dewcell RH, and temperature sensors. Results showed that VIS measured using the FSPWs were well correlated (R = 0.84 under precipitation, R = 0.96 during non-precipitating conditions). The FS11P on average measured higher VIS. The Jenoptik ceilometer generally measured lower CBH than human observation, while the MWR overestimated CBH for values < 2 km and underestimated for higher CBHs. Two extinction parameterizations as functions of snowfall rate were developed.

---

## 1. Introduction

Ceiling and visibility are among the most important weather elements for aviation safety. Low ceiling and visibility conditions are responsible for over 27% of weather-related aviation accidents and 70% of fatalities (2009–2013 FAA data). Accurate measurement of VIS, CBH, RH, and temperature is essential for nowcasting, forecasting, and validation of NWP/climate models.

---

## 2. Materials and Methods

### 2.1 Study Area

Cold Lake Regional Airport (CYOD), northeastern Alberta, Canada (54°N, 110°W; 541 m MSL). Two years of data: 2015–2016, as part of the 4Wing Cold Lake Research project. The region has humid continental climate; nearby lakes and the Beaver River valley contribute to weather variability including fog and low ceilings.

### 2.2 Instruments

- **Vaisala FS11P and PWD22** (FSPW): forward-scattering present weather sensors; measure VIS, precipitation intensity/type. FS11P scatters at 42°; PWD22 at 45°. VIS computed from extinction: VIS = 3/Ext.
- **Jenoptik CHM15k ceilometer**: 1064 nm laser; measures up to 15 km with 15 m range resolution. Reports up to 3 CBHs.
- **Microwave radiometer (MWR) MP-3000A**: retrieves CBH from infrared brightness temperatures; incorporates Rotronic RH/T into profiling algorithms.
- **Rotronic HygroMet MP102**: capacitive sensor; accuracy ±0.8% RH, ±0.1°C at 23°C.
- **Vaisala WXT520**: capacitive HUMICAP180 sensor; accuracy ±3% RH (0–90%), ±5% (90–100%).
- **AES-Dewcell** (DND site, ~948 m away): standard Canadian operational RH/T sensor; accuracy ±0.5°C for Td.

### 2.3 Human Observation

Human VIS observations use designated markers around the airdrome; reported at increments of 1/8 SM, 1/4 SM, 1 SM, and 5 SM.

---

## 3. Results

### 3.1 Visibility: FS11P vs. PWD22

- Well correlated: R = 0.84 (precipitation), R = 0.96 (non-precipitation).
- Under precipitation: MD = 280 m (VIS < 5 km), 490 m (VIS < 15 km); FS11P measured higher.
- Under fog/clear: MD = 410 m (VIS < 5 km), 2180 m (VIS < 15 km); FS11P still higher.

### 3.2 Visibility vs. Human Observation

- Significant quantization in human data, less during daytime.
- R ≈ 0.6 for both instruments vs. human.
- For VIS < 5 km: MD(PWD22) ≈ 0.98 km; MD(FS11P) ≈ 1.37 km — PWD22 slightly closer to human.
- For VIS < 2 km: human observer reported lower by 640 m (vs. FS11P) and 370 m (vs. PWD22).

### 3.3 Extinction/Snowfall Parameterizations

Two extinction parameterizations as functions of snowfall rate were developed from FSPW data; results similar to each other but new coefficients underestimated the prior Ontario-based parameterization.

### 3.4 Cloud Base Height

- Ceilometer vs. human: MD = 390 m (CBH < 10 km), 100 m (CBH < 4 km); R ≈ 0.80.
- MWR overestimated CBH for CBH < 2 km; underestimated for higher CBH; MD ≈ 1 km vs. both ceilometer and human; R ≈ 0.65.
- MWR CBH deemed unreliable, particularly at lower cloud base heights.

### 3.5 Relative Humidity and Temperature

- All RH sensors correlated well with AES-Dewcell (R = 0.97) but underestimated: MD = 2% (Rotronic), 6% (WXT520).
- Bias increases near saturation: at RH = 100%, WXT520 measured ~90.3% (≈10% error).
- Temperature: all sensors R > 0.99, MD < 0.1°C — excellent agreement.

---

## 4. Summary and Conclusions

Stand-alone automated meteorological instruments require corrections before being used for model validation or aviation applications. Two similar instruments (FS11P, PWD22) do not measure identical visibilities. MWR CBH is unreliable at low values. RH sensors systematically underestimate near saturation. Temperature measurements are reliable. Data from these instruments should not be treated as equivalent to human observations without adjustment.

---

## Author Contributions

Boudala: project administration, funding acquisition, conceptualization, methodology, validation, formal analysis, data curation, writing (original draft). Gultepe and Milbrandt: writing (review and editing).
