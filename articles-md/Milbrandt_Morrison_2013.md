# Prediction of Graupel Density in a Bulk Microphysics Scheme

**Authors:** Jason A. Milbrandt (Atmospheric Numerical Prediction Research, Environment Canada, Montreal, Quebec, Canada); Hugh Morrison (National Center for Atmospheric Research, Boulder, Colorado)

**Journal:** *Journal of the Atmospheric Sciences*, **70**, 410–429 (February 2013)

**Manuscript:** received 17 July 2012, in final form 4 September 2012

**DOI:** 10.1175/JAS-D-12-0204.1

---

## Abstract

A method to predict the bulk density of graupel $\rho_g$ has been added to the two-moment Milbrandt–Yau bulk microphysics scheme. The simulation of graupel using the modified scheme is illustrated through idealized simulations of a mesoscale convective system using a 2D kinematic model with a prescribed flow field and different peak updraft speeds. To examine the relative impact of the various approaches to represent rimed ice, simulations were run for various graupel-only and graupel-plus-hail configurations.

Because of the direct feedback of $\rho_g$ to terminal fall speeds, the modified scheme produces a much different spatial distribution of graupel, with more mass concentrated in the convective region resulting in changes to the surface precipitation at all locations. With a strong updraft, the model can now produce solid precipitation at the surface in the convective region without a separate hail category. It is shown that a single rimed-ice category is capable of representing a realistically wide range of graupel characteristics in various atmospheric conditions without the need for a priori parameter settings.

Sensitivity tests were conducted to examine various aspects of the scheme that affect the simulated $\rho_g$. Specific parameterizations pertaining to other hydrometeor categories now have a direct impact on the simulation of graupel, including the assumed aerosol distribution for droplet nucleation, which affects the drop sizes of both cloud and rain, and the mass–size relation for snow, which affects its density and hence the embryo density of graupel converted from snow due to riming.

---

## 1. Introduction

Graupel — heavily rimed crystals that have not undergone wet growth — is commonly parameterized as "medium-density graupel" with a fixed bulk density $\rho_g = 400$ kg m⁻³ and corresponding fixed fall speed parameters (e.g., Rutledge and Hobbs 1983; MY2005a). In nature, graupel has a large range of densities and fall speeds (Locatelli and Hobbs 1974; Pruppacher and Klett 1997), from ~50 to ~900 kg m⁻³ (Macklin 1962; Heymsfield and Pflaum 1985). Most schemes use either a single graupel or hail category with fixed parameters, though some use two separate categories (Ferrier 1994; Meyers et al. 1997; MY2005b).

There is considerable sensitivity of simulations to fixed density and fall speed parameters (Gilmore et al. 2004; van Weverberg et al. 2010; van den Heever and Cotton 2004; Adams-Selin et al. 2013; Morrison and Milbrandt 2011; Bryan and Morrison 2012). Fall speeds should depend explicitly on $\rho_g$ — increasing $\rho_g$ should result in greater fall speeds — but unless fall speed parameters are modified simultaneously with $\rho_g$, models give an incorrect sensitivity because increasing $\rho_g$ reduces mean particle size and hence mass-weighted fall speed.

Prior work on prognostic graupel density includes Farley (1987, spectral scheme), Connolly et al. (2006, bulk volume mixing ratio), and Mansell et al. (2010, M2010, who parameterized rime density from laboratory experiments with density-dependent fall speeds). This study adds a prognostic $\rho_g$ approach to MY2, using a rime density parameterization based on Cober and List (1993, CL1993) and a physically based $\rho_g$-dependent fall speed formulation following Khvorostyanov and Curry (2002) and Mitchell and Heymsfield (2005). The impacts of various approaches to representing rimed ice are examined in a 2D kinematic model framework.

The paper explicitly frames this work as "part of a paradigm shift for microphysics models... toward adding physical degrees of freedom for a given hydrometeor type rather than including more categories with different prescribed physical characteristics" (Hashino and Tripoli 2007; Morrison and Grabowski 2008, 2010; M2010; Harrington et al. 2013).

## 2. Description of method

### a. The new prognostic variable

Since $\rho_g$ is not conserved during advection, it cannot be predicted directly. Following Connolly et al. (2006) and M2010, the **bulk graupel volume mixing ratio**:
$$B_g = q_g / \rho_g \quad (\text{m}^3\text{ kg}^{-1})$$
is introduced as a new prognostic variable. Since $\rho B_g$ is advected and diffused (where $\rho$ is air density), $\rho_g$ evolves correctly during advection because errors in advection of $q_g$ and $B_g$ tend to cancel:
$$\rho_g = q_g / B_g. \tag{1}$$

This is analogous to accurate evolution of mean-mass diameter $D_x = (\rho q_x / c_x N_x)^{1/d_x}$ in two-moment schemes. The conservation equation for $B_g$ is:

$$\frac{\partial B_g}{\partial t} = \left.\frac{\partial B_g}{\partial t}\right|_{\rm adv} + \left.\frac{\partial B_g}{\partial t}\right|_{\rm diff} + \left.\frac{\partial \rho_g q_g}{\partial t}\right|_{\rm micro}\bigg/\rho_g^2 + \left.\frac{\partial B_g}{\partial t}\right|_{\rm sed}. \tag{3}$$

**Prognostic variables for graupel in the modified scheme (Table 1):** $q_g$ (mass mixing ratio), $B_g$ (bulk volume mixing ratio), $N_g$ (total number mixing ratio). **Diagnostic:** $a_g$, $b_g$ (V–D parameters), $\rho_g$, $c_g$ (m–D coefficient), $N_{0g}$, $\lambda_g$, $m_g$ (shape parameter).

The mass–diameter coefficient $c_g = (\pi/6)\rho_g$ is now diagnostic, no longer constant.

### b. Fall speed parameters

The terminal fall speed:
$$v_g = \left(\frac{\rho_0}{\rho}\right)^{0.5} a_g D^{b_g}, \tag{6}$$

uses density-dependent $a_g(\rho_g)$ and $b_g(\rho_g)$ derived from the Reynolds number–best number approach of Khvorostyanov and Curry (2002) and Mitchell and Heymsfield (2005):
$$X = \frac{4\rho_g g \rho D^3}{3\eta^2}, \tag{7}$$

where $g$ is gravitational acceleration and $\eta$ is dynamic viscosity. The resulting $a_g$ and $b_g$ are fitted by least squares in log–log space over $0.3 < D < 20$ mm and stored in a lookup table as a function of $\rho_g$ from 50 to 850 kg m⁻³ at 100 kg m⁻³ intervals (Table 2):

| $\rho_g$ (kg m⁻³) | $a_g$ (m$^{1-b}$ s⁻¹) | $b_g$ |
|---|---|---|
| 50 | 62.923 | 0.678 |
| 150 | 94.122 | 0.638 |
| 250 | 114.74 | 0.622 |
| 350 | 131.21 | 0.612 |
| 450 | 145.26 | 0.606 |
| 550 | 157.71 | 0.601 |
| 650 | 168.98 | 0.597 |
| 750 | 179.36 | 0.593 |
| 850 | 189.02 | 0.590 |

This approach covers the full range of empirical fall speeds from low-density "graupel-like snow" to high-density lump graupel (Locatelli and Hobbs 1974) and encompasses the original MY2 relations for both medium-density graupel and hail.

**Key point:** The density-dependent fall speeds are *crucial* — a simulation with prognostic $\rho_g$ but fixed fall speed parameters (PF-40) is nearly identical to the fixed-$\rho_g$ simulation (FF-40). The variable density only improves the scheme when correctly linked to variable fall speeds.

### c. Microphysical processes

The updated $\rho_g^*$ at the intermediate time level is a mass-weighted combination of the initial $\rho_g^0$ and the densities of graupel mass added by three processes: (1) conversion from snow (embryo density = snow density $\rho_s = f(D_s)$, via the now-variable snow $m$–$D$ parameters); (2) three-component freezing (mass-weighted density of interacting species; interactions between ice/rain giving graupel assume $\rho_h = 900$ kg m⁻³ as embryo density); (3) riming (rime density $\rho_{\rm rime}$ from Cober and List 1993 parameterization):

$$\rho_g^* = \frac{q_g^0 \rho_g^0 + \Delta q|_{CNsg}\rho_s + \delta_{irg}(\ldots)\rho_h + \delta_{srg}(\ldots)\rho_{s\rho g} + \delta_{rgg}(\ldots)\rho_{rgg} + (\Delta q|_{CLcg} + \Delta q|_{CLrg})\rho_{\rm rime}}{q_g^0 + \Delta q|_{CN} + \ldots}. \tag{12}$$

The rime density from CL1993:
$$\rho_{\rm rime} = 0.078 + 0.184 R_i - 0.015 R_i^2, \tag{B1}$$
where $R_i = 0.5 D_{\rm drop} V_{\rm impact} / T_{sfc}$ (Macklin 1962). This parameterization is applied using the mean-mass drop diameter and mass-weighted graupel fall speed to compute the impact velocity. Lower and upper bounds: 50 and 900 kg m⁻³.

### d. Sedimentation and size sorting

With the large range of possible fall speeds in the prognostic-$\rho_g$ scheme, uncontrolled size sorting becomes a new problem. An effective solution is a diagnostic shape parameter:
$$m_g = (1000 D_g)^{0.075}. \tag{14}$$

This follows the MY2005a approach of varying the spectral shape parameter as an increasing function of mean-particle size, thereby narrowing the PSD and reducing the fall speed differential as $D_g$ increases. Equation (14) was selected through minor trial and error and is intended only to illustrate the approach; a properly calibrated $m_g = f(D_g)$ from three-moment (prognostic-$m_g$) simulations is recommended.

## 3. Kinematic model description and setup

The modified MY2 scheme is tested in a 2D kinematic model (Szumowski et al. 1998; Grabowski 1999). The prescribed flow field represents a mature squall line with strong, deep ascent in the convective region and a mesoscale stratiform region. The peak updraft $w_{\rm peak}$ is varied between 1 and 40 m s⁻¹. Grid spacings: 750 m (horizontal), 250 m (vertical); 240×12-km domain; 5-s time step. Positive-definite MPDATA advection. The initial sounding is from the 0000 UTC 1 September 1974 GATE radiosonde.

**All simulations (Table 3):**

| Name | Description |
|---|---|
| PD-($w$) | Prognostic $\rho_g$, diagnostic $a_g$/$b_g$; graupel only (control) |
| FF-($w$) | Fixed $\rho_g$, fixed $a_g$/$b_g$; graupel only |
| PF-($w$) | Prognostic $\rho_g$, fixed $a_g$/$b_g$; graupel only |
| PD-HAIL-($w$) | Prognostic $\rho_g$, diagnostic $a_g$/$b_g$; graupel + hail |
| FF-HAIL-($w$) | Fixed $\rho_g$, fixed $a_g$/$b_g$; graupel + hail |
| PD-MU-($w$) | PD + diagnostic $m_g$ [Eq. 14]; graupel only |
| OldSnow-($w$) | PD + spherical constant-$\rho_s$ snow $m$–$D$ |
| Maritime-($w$) | PD + maritime CCN for droplet nucleation |
| RH_rime-($w$) | PD + Rasmussen–Heymsfield (1985) $\rho_{\rm rime}$ formulation |
| 3comp-($w$) | PD + constant $\rho_g$ for three-component freezing |
| delT2-($w$) | PD + $T_{sfc} = T + 2$°C in $\rho_{\rm rime}$ calculation |

## 4. Results

### a. Demonstration of the prognostic-$\rho_g$ scheme (PD-20)

The prognostic-$\rho_g$ scheme produces a realistic squall line reflectivity structure. Graupel evolution: at 12 min, new graupel near the updraft core originates as frozen rain (embryo density 900 kg m⁻³), then $\rho_g$ decreases as riming leads to low-density graupel lofted aloft. By 15 min, the majority of graupel mass is above the updraft core with $\rho_g < 250$ kg m⁻³, $D_g < 1$–2 mm, and $V_g \sim 1$–3 m s⁻¹. By 20 min, high-density graupel ($\rho_g > 600$ kg m⁻³) with large sizes ($D_g > 15$ mm) and high fall speeds ($V_g > 20$ m s⁻¹) reaches the surface.

At steady state: high-density graupel concentrated in the convective region, with a narrow "shaft" of fast-falling large graupel reaching the surface; lower-density graupel transported far into the stratiform region and melts to rain. Snow density varies inversely with $D_s$ as expected from the $d_s \approx 2$ mass–diameter relation.

[Figures 3–5 in original: model reflectivity evolution; graupel fields at 12, 15, 20 min; steady-state cross sections — images not reproducible in markdown]

### b. Comparison to standard approaches

**Graupel only (PD-40 vs FF-40):**
- PD-40: graupel mass concentrated in the convective region; high-density graupel reaches the surface; surface solid precipitation rate is non-negligible.
- FF-40: graupel mass spread into the stratiform region (slower fixed fall speeds); no graupel reaches the surface without melting completely.
- PF-40 (prognostic $\rho_g$ but fixed $a_g$, $b_g$): nearly identical to FF-40 despite wide range of $\rho_g$ values. **The variable density only helps when correctly linked to variable fall speeds.**

**Graupel plus hail:** PD-HAIL-40 has similar graupel structure to PD-40, but with a distinct narrow hail shaft near the convective core (hail $D_h > 20$ mm, $V_h > 30$ m s⁻¹). FF-HAIL-40 similarly has a hail shaft but with more graupel spread into the stratiform region. The graupel-only PD scheme can simulate solid precipitation at the surface without a separate hail category, though it cannot simultaneously represent both high-density and lower-density rimed ice at the same point.

### c. Weak-updraft cases (PD-3 vs FF-3)

PD-3 exhibits the size-sorting problem: despite the weak 3 m s⁻¹ updraft, size sorting creates unrealistically large $D_g$ and $V_g$ in the lower column, causing graupel to reach the surface. FF-3 correctly keeps all graupel suspended and melting before reaching the surface.

### d. Controlling size sorting: diagnostic shape parameter (PD-MU)

Applying the diagnostic $m_g$ relation [Eq. 14]:
- PD-MU-3: size-sorting problem largely corrected; graupel no longer reaches the surface; no detrimental effects elsewhere.
- PD-MU-40: nearly identical to PD-40 for all fields; the diagnostic $m_g$ does not overly restrict the strong-updraft case.

The diagnostic $m_g$ approach is a practical interim solution; the authors recommend eventually deriving $m_g = f(D_g)$ from a three-moment (prognostic-$m_g$) simulation.

### e. Sensitivity to $\rho_g$ computation

Key results from sensitivity experiments (Fig. 15):

- **OldSnow** (spherical snow, constant $\rho_s = 100$ kg m⁻³): for weak updraft, much more graupel in convective region and larger precipitation; for strong updraft, graupel mass shifted toward stratiform region. Snow $m$–$D$ parameters affect embryo density and hence initial $\rho_g$ for graupel converted from snow.
- **Maritime CCN** (larger drops, $N_c \sim 0.8 \times 10^8$ m⁻³ vs $2 \times 10^8$ m⁻³ continental): larger drops → larger $\rho_{\rm rime}$ → larger $\rho_g$ → faster fall speeds → more riming → more graupel. More pronounced for weak updraft.
- **RH85 rime density** (Rasmussen and Heymsfield 1985): larger rime densities → more graupel mass and greater precipitation in convective region for strong updraft.
- **Tsfc = T + 2°C**: very little sensitivity; simple $T_{sfc} = T$ assumption is adequate.
- **3comp (constant $\rho_g$ for three-component freezing)**: minimal sensitivity; the three-component freezing term contributes little to overall $\rho_g$ for these cases.

## 6. Conclusions

A method to predict the bulk graupel density $\rho_g$ was described and added to MY2, using a new prognostic bulk volume mixing ratio $B_g = q_g/\rho_g$. The method uses a laboratory-based rime density parameterization (CL1993) and physically based density-dependent fall speed parameters (Mitchell and Heymsfield 2005 Re–$X$ approach).

**Main findings:**
1. **The prognostic $\rho_g$ fundamentally changes the spatial distribution of graupel**, with mass more concentrated in the convective region, less in the stratiform region.
2. **The density-dependent fall speeds are essential** — without them, variable density has almost no impact (PF ≈ FF).
3. **A single rimed-ice category with prognostic $\rho_g$ can represent a wide range of graupel types** and can produce solid precipitation at the surface in strong-updraft cases, potentially reducing the need for a separate hail category for some applications.
4. **Size sorting must be controlled** when fall speeds have a large range; a diagnostic $m_g = f(D_g)$ is effective.
5. **The snow $m$–$D$ relation and cloud droplet assumptions now affect graupel** through embryo density and riming density.

**Broader significance:** This paper is "part of a paradigm shift... toward adding physical degrees of freedom for a given hydrometeor type rather than including more categories with different prescribed physical characteristics." The limiting case of a single ice-phase category whose properties evolve freely is the concept directly realized in the P3 scheme (Morrison and Milbrandt 2015).

The conclusions also note that: a four-variable graupel scheme ($q_g$, $B_g$, $N_g$, plus a third moment/reflectivity) would allow independent evolution of three size distribution parameters plus bulk density — controlling size sorting while retaining full variability; and reexamination of the conversion from graupel to hail for two-category schemes is warranted. These points directly anticipate P3.

---

## Appendix A: Overview of the MY2 Scheme

Six categories; two-moment (prognostic $q_x$ and $N_x$); gamma PSD with $m_x = 0$ for all categories except cloud ($m_c = 3$). Snow uses $c_s = 0.1597$, $d_s = 2.078$ (Milbrandt et al. 2012). Graupel now has diagnostic $c_g = (\pi/6)\rho_g$ rather than constant.

## Appendix B: Parameterization Details

**Graupel initiation:** Embryo density for conversion from snow = $\rho_s = f(D_s)$ (from variable snow density); for three-component freezing from ice-rain interactions (result going to graupel), embryo density = $\rho_h = 900$ kg m⁻³; for snow-rain interactions going to graupel, mass-weighted average of snow and rain densities.

**Rime density:** Cober and List (1993) parameterization [Eq. B1] using the mean-mass drop diameter $D_{\rm drop}$ from the combined cloud + rain distribution [Eq. B3] and impact velocity [Eq. B4]. Bounds: 50–900 kg m⁻³.

---

*Acknowledgments: Thanks to E. Mansell, J. Straka, one anonymous reviewer, W. Grabowski, and J. Slawinska. HM supported by NOAA, U.S. DOE ARM, U.S. DOE ASR, and NSF CMMAP.*
