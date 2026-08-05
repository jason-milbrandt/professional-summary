# Milbrandt, J. A., and M. K. Yau, 2005: A Multimoment Bulk Microphysics Parameterization. Part II: A Proposed Three-Moment Closure and Scheme Description. *Journal of the Atmospheric Sciences*, **62**, 3065–3081.

---

## Abstract

Many two-moment bulk schemes use a three-parameter gamma distribution of the form $N(D) = N_0 D^\alpha e^{-\lambda D}$ to describe the size spectrum of a given hydrometeor category. These schemes predict changes to the mass content and the total number concentration thereby allowing $N_0$ and $\lambda$ to vary as prognostic parameters while fixing the shape parameter, $\alpha$. As was shown in Part I of this study, the shape parameter, which represents the relative dispersion of the hydrometeor size spectrum, plays an important role in the computation of sedimentation and instantaneous growth rates in bulk microphysics schemes. Significant improvement was shown by allowing $\alpha$ to vary as a diagnostic function of the predicted moments rather than using a fixed-value approach. Ideally, however, $\alpha$ should be an independent prognostic parameter.

In this paper, a closure formulation is developed for calculating the source and sink terms of a third moment of the size distribution—the radar reflectivity. With predictive equations for the mass content, total number concentration, and radar reflectivity, $\alpha$ becomes a fully prognostic variable and a three-moment parameterization becomes feasible. A new bulk microphysics scheme is presented and described. The full version of the scheme predicts three moments for all precipitating hydrometeor categories.

Simulations of an idealized hailstorm in the context of a 1D kinematic cloud model employing the one-moment, two-moment, and three-moment versions of the scheme are compared. The vertical distribution of the hydrometeor mass contents using the two-moment version with diagnostic-$\alpha$ relations are much closer to the three-moment than the one-moment simulation. However, the evolution of the surface precipitation rate is notably different between the three-moment and two-moment schemes.

---

## 1. Introduction

Given the increasing importance of bulk microphysics parameterization schemes in atmospheric models, it is important to develop detailed yet computationally efficient schemes and to understand the strength and limitation of various approaches. Many two-moment bulk schemes use a three-parameter gamma size distribution of the form $N(D) = N_0 D^\alpha e^{-\lambda D}$. The schemes predict changes to the mass content and total number concentration thereby allowing $N_0$ and $\lambda$ to vary as prognostic parameters while fixing the spectral shape parameter, $\alpha$.

In Milbrandt and Yau (2005a, hereafter Part I), the impact of changes to the relative dispersion of the hydrometeor size spectrum, as represented by the shape parameter, was examined. It was shown that $\alpha$ plays an important role in the computation of sedimentation and instantaneous growth rates in bulk microphysics schemes. A method that diagnoses $\alpha$ as a monotonically increasing function of the mean-mass diameter was introduced and shown to yield notable improvement over the standard fixed-value approach. It was also demonstrated, however, that $\alpha$ should be a fully prognosed parameter by predicting three moments of the size distribution.

In this paper, a closure formulation is developed for calculating the source and sink terms of a third moment of the size distribution, the radar reflectivity. With predictive equations for the mass content, total number concentration, and radar reflectivity, $\alpha$ becomes a fully prognostic variable and a three-moment parameterization becomes feasible. In view of the analysis in Part I, a new multimoment bulk scheme, with options to diagnose or prognose the shape parameter, has been developed and is presented here.

---

## 2. Prognostic Relation for $\alpha$ — A Proposed Closure for the Three-Moment Approach

From the results presented in Part I, it is clear that there are advantages to extend the bulk approach to allow the spectral shape parameter $\alpha$, as well as the intercept parameter $N_{0x}$ and the slope parameter $\lambda_x$, of the size distribution for hydrometeor species $x$ to be independent. To predict the evolution of $\alpha$, a prognostic equation for another moment such as the radar reflectivity $Z_x$ with the form:

$$\frac{\partial Z_x}{\partial t} = -\nabla \cdot (Z_x \mathbf{U}) + \text{TURB}(Z_x) + \left(\frac{\partial Z_x}{\partial t}\right)_V + \sum_d \left(\frac{\partial Z_x}{\partial t}\right)_S \tag{1}$$

must be added to the continuity equations for the mass and total number concentration (Eqs. (8) and (9) in Part I), along with the closure equation (Eq. (6) in Part I).

The source term for $Z_x$ in (1) is computed as the sum of the individual tendencies of $Z_x$ for each microphysical process listed in appendix A. The source terms for $Z_x$ are classified into three types.

**Type 1**: For processes in which the change in $\alpha_x$ is negligible due to a particular process A. By differentiating the closure Eq. (6) in Part I, the tendency of $Z_x$ can be related to the tendencies of $q_x$ and $N_{Tx}$:

$$\left(\frac{dZ_x}{dt}\right)_A = \frac{G(\alpha_x)}{c_x^2} \left[4 \cdot \frac{2q_x}{N_{Tx}} \left(\frac{dq_x}{dt}\right)_A - \frac{q_x^2}{N_{Tx}^2} \left(\frac{dN_{Tx}}{dt}\right)_A\right] \tag{2}$$

Equation (2) is applied to collection, diffusional growth, and melting. The assumption that $\alpha_x$ does not change because of a particular process is analogous to holding $\lambda_x$ constant for a process in order to relate the fractional change in $N_{Tx}$ to the fractional change in $q_x$.

**Type 2**: Terms related to processes in which hydrometeors are being initiated in a category, such as during nucleation. For these, with $Z_x^{init} = q_x^{init} = N_{Tx}^{init} = 0$ at the beginning of the time step:

$$Z_x^{fin} = \frac{G(\alpha_{xA})}{c_x^2} \frac{(q_x^{fin})^2}{N_{Tx}^{fin}} \tag{3}$$

Taking the limit as $\Delta t \to 0$:

$$\left(\frac{dZ_x}{dt}\right)_A = G(\alpha_{xA}) \frac{4}{c_x} \left(\frac{dq_x}{dt}\right)_A^2 \left(\frac{dN_{Tx}}{dt}\right)_A^{-1} \tag{4}$$

**Type 3**: When one category $x$ is converted into another category $y$:

$$\left(\frac{dZ_x}{dt}\right)_A = -\frac{c_y}{c_x} \left(\frac{dZ_y}{dt}\right)_A \tag{5}$$

An example is the probabilistic freezing of rain to hail. The total radar reflectivity due to such a process is thus conserved.

---

## 3. Overview of the New Scheme

A new multimoment bulk scheme has been developed. The scheme consists of six hydrometeor categories. As is standard in bulk parameterizations, the liquid water spectrum is partitioned into cloud (small nonsedimenting droplets) and rain (sedimenting drops). Following McCumber et al. (1991), the proposed scheme includes ice, snow, graupel, and hail for the ice phase.

- **Cloud**: Small nonsedimenting droplets; $\alpha_c = 3$ (fixed), following Cohard and Pinty 2000a.
- **Rain**: Sedimenting drops; minimum size $82\,\mu\text{m}$ ("hump" diameter separating cloud and rain spectra).
- **Ice**: Pristine ice crystals, assumed to be bullet rosettes; $c_i = 440\,\text{kg m}^{-3}$; embryo mass $10^{-12}\,\text{kg}$.
- **Snow**: Large crystals (radii $> 100\,\mu\text{m}$) and aggregates; $\rho_s = 100\,\text{kg m}^{-3}$; embryo mass $4.4 \times 10^{-10}\,\text{kg}$.
- **Graupel**: Moderate-density graupel from heavily rimed ice or snow; $\rho_g = 400\,\text{kg m}^{-3}$; embryo mass $1.6 \times 10^{-10}\,\text{kg}$.
- **Hail**: High-density hail and frozen raindrops; $\rho_h = 900\,\text{kg m}^{-3}$; embryo diameter depends on temperature and LWC.

All hydrometeor categories $x$ (with $x \in [c, r, i, s, g, h]$) have the mass–diameter relationship $m_x(D_x) = c_x D_x^{d_x}$ (with $d_x = 3$). Particles are spherical except ice crystals.

**TABLE 1.** Bulk densities and minimum particle sizes of hydrometeor categories.

| Category | Bulk density (kg m$^{-3}$) | Minimum sizes |
|----------|---------------------------|---------------|
| Cloud | 1000 | n/a |
| Rain | 1000 | $82\,\mu$m |
| Ice | 500 | $10^{-12}$ kg |
| Snow | 100 | $4.4 \times 10^{-10}$ kg |
| Graupel | 400 | $1.6 \times 10^{-10}$ kg |
| Hail | 900 | ** (depends on T and LWC) |

There are three main versions of the proposed scheme:
- **Single-moment (SM)**: Predicts $q_x$; fixed values for $N_{Tc}$ and $N_{0x}$ for precipitating categories; fixed $\alpha_x$.
- **Two-moment (DIAG)**: Predicts $q_x$ and $N_{Tx}$; $\alpha_x$ either fixed or diagnosed from the mean-mass diameter relations of Part I.
- **Three-moment (TM)**: Also predicts $Z_x$ for all categories except cloud water; $\alpha_x$ obtained by solving the closure equation (I.6).

Sedimentation is computed following the equations described in the appendix of Part I.

**TABLE 2.** Terminal fall velocity parameters for hydrometeor category $x$.

| Category | $a_x$ (m$^{1-b_x}$ s$^{-1}$) | $b_x$ | $f_x$ (m$^{-1}$) |
|----------|-------------------------------|--------|------------------|
| Rain | 4854.00 | 1.0 | 195 |
| Ice | 71.34 | 0.6635 | 0 |
| Snow | 8.996 | 0.42 | 0 |
| Graupel | 19.30 | 0.37 | 0 |
| Hail | 206.89 | 0.6384 | 0 |

The microphysical source/sink terms were taken and adapted from various existing schemes. Warm-rain processes follow Cohard et al. (1998, CPB98) and Cohard and Pinty (2000a, CP00a). Ice phase processes are mainly adapted from Cotton et al. (1986, C86), Ferrier (1994, F94), Kong and Yau (1997, KY97), Lin et al. (1983, LFO), Meyers et al. (1997, M97), and Murakami (1990, M90).

---

## 4. Description of Source/Sink Terms

Source/sink term notation: $V^{AB}_{y,x}$, where $V$ is the prognostic variable ($Q$ for mixing ratio, $N$ for total concentration, $Z$ for radar reflectivity), $AB$ represents the microphysical process (CL: collection, CN: conversion, FZ: freezing, IM: ice multiplication, ML: melting, NU: nucleation, SH: shedding, VD: diffusional growth), and subscript $y,x$ indicates mass transfer from category $y$ to $x$.

### a. Cloud nucleation ($N^{NU}_{\nu c}$)

The cloud nucleation rate is parameterized following CPB98 and CP00a:

$$N^{NU}_{\nu c} = \frac{\max\left[N_{CCN}(w, T, p) - N_{Tc}, 0\right]}{\Delta t} \tag{6}$$

A least-square fit to $N_{CCN}(w,T,p)$ of CPB98 is used to reduce computational cost.

### b. Condensation and evaporation of cloud and rain ($Q^{VD}_{\nu c}$, $Q^{VD}_{\nu r}$, $N^{VD}_{\nu c}$, $N^{VD}_{\nu r}$, $Z^{VD}_{\nu r}$)

The rate of change in cloud mixing ratio due to nucleation and subsequent growth by condensation, $Q^{VD}_{\nu c}$, is parameterized following the saturation adjustment technique of KY97. For the rate of evaporation of rain in subsaturated air:

$$Q^{VD}_{\nu r} = \frac{2\pi(S_w - 1) N_{0r} \text{VENT}_r}{AB_w} \tag{7}$$

where

$$\text{VENT}_r = A_r \frac{\Gamma(2+\alpha_r)}{\lambda_r^{2+\alpha_r}} + B_r S_c^{1/3} \frac{\sqrt{\pi a_r}}{\nu_{\text{kin}}^{1/2}} \frac{\Gamma\left(\frac{9+2\alpha_r+2b_r}{2}\right)}{\lambda_r^{(9+2\alpha_r+2b_r)/2}} \tag{8}$$

is the bulk ventilation coefficient for rain and

$$AB_w = \frac{L_\nu^2}{K_a R_\nu T^2} + \frac{1}{\Delta q_s} \tag{9}$$

is the thermodynamic function. During evaporation, $N_{Tc}$ and $N_{Tr}$ decrease at the rates of $N^{VD}_{\nu x}$, given by an equation of the form of (B1) in appendix B for $x \in [c, r]$, and $Z_r$ decreases at the rate of $Z^{VD}_{\nu r}$, given by an equation of the form of (B3).

### c. Warm-rain collection ($Q^{CN}_{cr}$, $Q^{CL}_{cr}$, $N^{CN}_{c,cr}$, $N^{CN}_{r,cr}$, $N^{CL}_{cr}$, $Z^{CN}_{cr}$, $Z^{CL}_{cr}$, $Z^{CL}_{rr}$)

The source terms for the mixing ratios and number concentrations of cloud and rain due to warm-rain collection come from CP00a, based on analytic solutions to the stochastic collection equation (SCE) using Long's (1974) polynomial approximation for the collection kernel.

The $q_x$ tendency for autoconversion, $Q^{CN}_{cr}$, is adopted from CP00a. For the change in rain particle concentration due to autoconversion, a threshold mean diameter is first computed using Berry and Reinhardt (1974):

$$D_{mr\_aut} = \frac{1.26 \times 10^{-3}}{(0.5 \times 10^6) \cdot \sigma_c - 3.5} \tag{10}$$

where $\sigma_c$ is the standard deviation of the cloud droplet size. Spontaneous breakup of rain is parameterized by including a mean-drop-size limiter in the bulk collection efficiency in $N^{CL}_{rr}$.

### d. Collection involving ice particles

#### (i) Collection amongst rain and frozen categories

For collection amongst sedimenting categories, M90's approximation is used:

$$\delta V \approx |V_{Qx} - V_{Qy}| \approx \sqrt{(V_{Qx} - V_{Qy})^2 + 0.04 V_{Qx} V_{Qy}} \tag{16}$$

Bulk collection efficiencies $E_{xy}$ are used. For the collection of cloud droplets by graupel and hail, an empirical formula from Macklin and Bailey (1966) is used:

$$E_{xc}(D_{mx}, D_{mc}) = \exp\left(-8.68 \times 10^{-7} D_{mc}^{-1.6} D_{mx}\right) \tag{13}$$

where $x \in [g, h]$. For dry collection among ice particles (following Ferrier et al. 1995):

$$E_{is} = \min\left[0.05 \exp(0.1 T_c), 1\right] \tag{14}$$

$$E_{ig} = E_{sg} = E_{ih} = E_{sh} = \min\left[0.01 \exp(0.1 T_c), 1\right] \tag{15}$$

During wet growth of hail: $E_{ih} = E_{sh} = 1$.

The analytically integrated collection equations are:

$$Q^{CL}_{yx} = \frac{c_y}{\pi/4} E_{xy} \delta V \frac{N_{Tx} N_{Ty}}{\lambda_x^{\alpha_x+1} \lambda_y^{\alpha_y+1}} \left[\frac{\Gamma(\alpha_x+3)\Gamma(\alpha_y+1)}{\lambda_x^2 \lambda_y} - \frac{2\Gamma(\alpha_x+2)\Gamma(\alpha_y+5)}{\lambda_x \lambda_y^4 \lambda_x} + \cdots \right] \tag{17}$$

(full form given in the paper). Similarly for $N^{CL}_{yx}$ (Eq. 18) and $Z^{CL}_{yx}$ (form of B3).

#### (ii) Collection of cloud water by frozen categories

Since cloud droplets have negligible terminal fall velocity:

$$Q^{CL}_{cx} = \pi a_x w E_{xc} \frac{N_{Tx} N_{Tc}}{\lambda_x^{\alpha_x+1} \lambda_c^{\alpha_c+1}} \left[\frac{\Gamma(\alpha_x+3+b_x)\Gamma(\alpha_c+1)}{\lambda_x^{2+b_x} \lambda_c} + \frac{2\Gamma(\alpha_x+2+b_x)\Gamma(\alpha_c+1+\kappa_c)}{\lambda_x^{1+b_x} \lambda_c^{1+\kappa_c}} + \cdots \right] \tag{19}$$

(full form given in paper).

#### (ii) Aggregation for snow ($N^{CL}_{ss}$, $Z^{CL}_{ss}$)

The rate of decrease in $N_{Ts}$ (snow aggregation) follows F94. The corresponding rate of change in radar reflectivity $Z^{CL}_{ss}$ is of the form of (B3) with $Q^{CL}_{ss} = 0$.

#### (iii) Wet growth of hail ($N^{SH}_{hr}$, $Z^{SH}_{hr}$, $Q^{CL}_{rh}$)

When the hailstone enters the wet growth mode (beyond the Shumann–Ludlam limit, SLL), it sheds accreted water. The approach of LFO is followed to determine criteria for wet growth and the mass increase rate $Q^{WET}_h$ based on the heat balance equation (Musil 1970). The shedding tendency for $N_{Tr}$ is:

$$N^{SH}_{hr} = \frac{\Delta t}{D_{shed}^3} \left[Q^{CL}_{rh} - Q^{CL^\dagger}_{rh}\right] \tag{22}$$

The $Z_r$ tendency due to shedding:

$$Z^{SH}_{hr} = G(\alpha_{rSH}) \frac{c_r}{r} \left[Q^{CL}_{rh} - Q^{CL^\dagger}_{rh}\right]^2 \left(N^{SH}_{hr}\right)^{-1} \tag{23}$$

where $\alpha_{rSH} = 2$.

### e. Ice nucleation

Ice crystals are initiated via three modes: primary nucleation, rime splintering, and homogeneous freezing of cloud droplets.

#### (i) Primary nucleation ($Q^{NU}_{\nu i}$, $N^{NU}_{\nu i}$, $Z^{NU}_{\nu i}$)

Primary nucleation includes contact nucleation (following Young 1974 as described in C86 and W95) and deposition/condensation-freezing nucleation parameterized by Meyers et al. (1992):

$$N_{Ti}(S_i) = 1000 \exp\left[12.96(S_i - 1) - 0.639\right] \tag{24}$$

The deposition/condensation-freezing nucleation $N_{Ti}$ tendency:

$$N_u^{DEPSOR} = \frac{N_{Ti}(S_i)}{2\Delta t} \tag{25}$$

A maximum depositional growth rate is imposed (following KY97):

$$N^{NU}_{max} = \frac{(q_\nu - q_{si})}{5806.485 L_s q_{si}^2 \Delta t \cdot C_p(T - 7.66)^{-2}} \tag{26}$$

The combined primary nucleation tendency is:

$$N^{NU}_{\nu i} = \min\left(N^{NU}_{max}, \max\left(N_u^{DEPSOR} + N_u^{CONT} - \frac{N_{Ti}}{2\Delta t}, 0\right)\right) \tag{27}$$

The mixing ratio and reflectivity tendencies use an assumed nucleated ice crystal mass $m_{i0} = 10^{-12}$ kg (KY97; RRB):

$$Q^{NU}_{\nu i} = \frac{m_{i0} N^{NU}_{\nu i}}{\Delta t} \tag{28}$$

#### (ii) Ice multiplication ($Q^{IM}_{si}$, $Q^{IM}_{gi}$, $N^{IM}_{ii}$, $N^{IM}_{si}$, $N^{IM}_{gi}$, $Z^{IM}_{ii}$, $Z^{IM}_{si}$, $Z^{IM}_{gi}$)

Ice multiplication (rime splintering) for riming of ice, snow, and graupel at temperatures between $-3°$C and $-8°$C is based on Hallett and Mossop (1974) and parameterized following the equations of RRB.

#### (iii) Homogeneous freezing of cloud droplets ($Q^{FZ}_{ci}$, $N^{FZ}_{ci}$, $Z^{FZ}_{ci}$)

The number of droplets that freeze in time $\Delta t$ at a given temperature (DeMott et al. 1994):

$$\Delta N_{freeze} = \int_0^\infty \left[1 - \exp(-JV\Delta t)\right] N_{Tc}(D)\, dD \tag{29}$$

where

$$\log_{10}(J) = -606.3952 - 52.6611 T_c - 1.7439 T_c^2 - 2.65 \times 10^{-2} T_c^3 - 1.536 \times 10^{-4} T_c^4 \tag{30}$$

Substituting the mean droplet volume $V = (\pi/6)D_{mc}^3$:

$$f_{fr} = \frac{\Delta N_{freeze}}{N_{Tc}} = 1 - \exp\left(-J \frac{\pi}{6} D_{mc}^3 \Delta t\right) \tag{31}$$

Thus:

$$N^{FZ}_{ci} = \frac{f_{fr} N_{Tc}}{\Delta t} \tag{32}$$

$$Q^{FZ}_{ci} = \frac{f_{fr} q_c}{\Delta t} \tag{33}$$

For $T_c \geq -30°$C, $f_{fr} = 0$; for $T_c \leq -50°$C, $f_{fr} = 1$.

### f. Deposition/sublimation ($Q^{VD}_{\nu i}$, $Q^{VD}_{\nu s}$, $Q^{VD}_{\nu g}$, $Q^{VD}_{\nu h}$, $N^{VD}_{\nu i}$, $N^{VD}_{\nu s}$, $N^{VD}_{\nu g}$, $N^{VD}_{\nu h}$, $Z^{VD}_{\nu i}$, $Z^{VD}_{\nu s}$, $Z^{VD}_{\nu g}$, $Z^{VD}_{\nu h}$)

All frozen categories undergo deposition (sublimation) in an environment supersaturated (subsaturated) with respect to ice. The diffusional growth rate for frozen category $x \in [i, s, g, h]$:

$$Q^{VD}_{\nu x} = \frac{2\pi(S_i - 1) N_{0x} \text{VENT}_x}{AB_i} - s_f \frac{L_f}{K_a R_\nu T^2}(Q^{CL}_{cx} + Q^{CL}_{rx}) \tag{34}$$

where

$$AB_i = \frac{L_s^2}{K_a R_\nu T^2} + \frac{1}{\Delta q_{si}} \tag{35}$$

is the thermodynamic function and

$$\text{VENT}_x = A_x \frac{\Gamma(2+\alpha_x)}{\lambda_x^{2+\alpha_x}} + B_x S_c^{1/3} \sqrt{\frac{\pi a_x}{\nu_{\text{kin}}}} \frac{\Gamma\left(\frac{5+2\alpha_x+b_x}{2}\right)}{\lambda_x^{(5+2\alpha_x+b_x)/2}} \tag{36}$$

is the mass-weighted ventilation factor. A maximum diffusional growth rate $VD_{max}$ is also computed to prevent excessive supersaturation or subsaturation from large time steps.

### g. Freezing of rain

#### (i) Probabilistic freezing ($Q^{FZ}_{rh}$, $N^{FZ}_{rh}$, $Z^{FZ}_{r,rh}$, $Z^{FZ}_{h,rh}$)

When the ambient air temperature is below 0°C, rain can undergo spontaneous or probabilistic freezing. The rate of change of number concentration (Bigg 1953):

$$N^{FZ}_{rh} = -B^\prime \left[\exp(A^\prime T_c) - 1\right] \frac{\Delta q_r}{\rho_w} \tag{37}$$

and the rate of change in mass:

$$Q^{FZ}_{rh} = \frac{q_r}{N_{Tr}} N^{FZ}_{rh} \tag{38}$$

where $A^\prime = 0.66\,\text{K}^{-1}$ and $B^\prime = 100\,\text{m}^{-3}\,\text{s}^{-1}$.

#### (ii) Collisional (three-component) freezing ($N^{CL}_{irg}$, $N^{CL}_{irh}$, $N^{CL}_{srs}$, $N^{CL}_{srg}$, $N^{CL}_{srh}$, $Z^{CL}_{irg}$, $Z^{CL}_{irh}$, $Z^{CL}_{srs}$, $Z^{CL}_{srg}$, $Z^{CL}_{srh}$)

When $T < 0°$C, rain drops also freeze upon contact with a frozen category $x$. A simplification of F94's three-component freezing method is used. The density of the new frozen category $z$ is:

$$\frac{\pi}{6}\left(\rho_w D_{mr}^3 + \rho_x D_{mx}^3\right) = \frac{\pi}{6}(\rho_z D_{mz}^3) \tag{39}$$

The destination category $z$ is classified as snow if $\rho_z < 0.5(\rho_s + \rho_g)$, as graupel if $0.5(\rho_s + \rho_g) \leq \rho_z < 0.5(\rho_g + \rho_h)$, and as hail if $\rho_z \geq 0.5(\rho_g + \rho_h)$.

The $N_{Tz}$ tendency for the resulting category:

$$N^{CL}_{xrz} = \frac{\delta_{xrz}(Q^{CL}_{xr} + Q^{CL}_{rx})}{(\pi/6)\rho_z \max(D_{mr}, D_{mx})^3} \tag{40}$$

The $Z_z$ tendency:

$$Z^{CL}_{xrz} = G(\alpha_{zCL}) \frac{c_z}{r} \left(Q^{CL}_{xr} + Q^{CL}_{rx}\right)^2 \left(N^{CL}_{xrz}\right)^{-1} \tag{41}$$

where $\alpha_{zCL} = 0$ is assumed for newly formed particles.

### h. Conversion processes

#### (i) Ice to snow ($Q^{CN}_{is}$, $N^{CN}_{i,is}$, $N^{CN}_{s,is}$, $Z^{CN}_{i,is}$, $Z^{CN}_{s,is}$)

Ice is converted to snow by growth to embryo snow particle size and by aggregation. With $m_{s0} = 4.4 \times 10^{-10}$ kg as the embryo snow particle mass, the total conversion rate:

$$Q^{CN}_{is} = Q^{CN,dep+rim}_{is} + Q^{CN,aggr}_{is} \tag{42}$$

For ice aggregation, the $N_{Ti}$ tendency is:

$$\left(\frac{dN_{Ti}}{dt}\right)_{aggr} = -\frac{1}{2} K_i N_{Ti}^2 \tag{43}$$

where

$$K_i = \frac{\pi}{6} D_{mi}^2 V_i E_{ii} X_{disp} \tag{44}$$

and $X_{disp} = 0.25$ is the dispersion of the fall velocity spectrum of ice crystals.

The total $N_{Ti}$ tendency due to conversion to snow:

$$N^{CN}_{i,is} = \frac{1}{m_{s0}}\left(Q^{CN,dep+rim}_{is} + \frac{1}{2} K_i N_{Ti}^2\right) \tag{45}$$

#### (ii) Ice to graupel ($Q^{CN}_{ig}$, $N^{CN}_{i,ig}$, $N^{CN}_{g,ig}$, $Z^{CN}_{i,ig}$, $Z^{CN}_{g,ig}$)

Ice is converted to graupel when the riming rate of ice crystals exceeds its depositional growth rate:

$$Q^{CN}_{ig} = 2 \cdot \max\left[Q^{CL}_{ci} - \max(Q^{VD}_{\nu i}, 0), 0\right] \tag{46}$$

#### (iii) Snow to graupel ($Q^{CN}_{sg}$, $N^{CN}_{sg}$, $Z^{CN}_{s,sg}$, $Z^{CN}_{g,sg}$)

Snow is converted to graupel by riming. Conversion occurs if the riming rate $Q^{CL}_{cs}$ exceeds the depositional growth rate $Q^{VD}_{\nu s}$:

$$Q^{CN}_{sg} = Q^{CL}_{cs} \frac{\Delta t}{g_s - g_s} \tag{47}$$

(full expression in paper).

#### (iv) Graupel to hail ($Q^{CN}_{gh}$, $N^{CN}_{gh}$, $Z^{CN}_{g,gh}$, $Z^{CN}_{h,gh}$)

The conversion of graupel to hail occurs when graupel first reaches the SLL. The embryo diameter of a hailstone is approximated as a function of environmental temperature and water/ice contents (Ziegler 1985):

$$D_{h0} = 0.01 \exp\left[-T_c\left[1.1 \times 10^4(q_c + q_r) - 1.3 \times 10^3 q_i + 1 \times 10^{-3}\right]^{-1}\right] \tag{48}$$

The conversion rate:

$$Q^{CN}_{gh} = \frac{D_{mg}}{2D_{h0}}(Q^{CL}_{cg} + Q^{CL}_{rg} + Q^{CL}_{ig}) \tag{49}$$

A lower limit of 0.1 is placed on the ratio $D_{mg}/D_{h0}$ below which the conversion rate is set to zero.

### i. Melting of frozen particles ($Q^{ML}_{ir}$, $Q^{ML}_{sr}$, $Q^{ML}_{gr}$, $Q^{ML}_{hr}$, $N^{ML}_{ir}$, $N^{ML}_{sr}$, $N^{ML}_{gr}$, $N^{ML}_{hr}$, $Z^{ML}$ terms)

Ice melts instantaneously to rain upon falling into warm ($T > 0°$C) air:

$$Q^{ML}_{ir} = \frac{q_i}{2\Delta t} \tag{51}$$

$$N^{ML}_{ir} = \frac{N_{Ti}}{2\Delta t} \tag{52}$$

For snow, graupel, and hail, the melting rate is based on a heat balance with cooling by melting offset by heating from conduction and convection at the particle surface, latent heat of condensation/evaporation, and sensible heating from collected cloud and rainwater:

$$Q^{ML}_{xr} = \frac{2\pi}{\Delta t L_f} N_{0x}\left(K_a T_c - L_\nu \Delta q_s\right) \text{VENT}_x + \frac{C_w T_c}{L_f}(Q^{CL}_{cx} + Q^{CL}_{rx}) \tag{53}$$

where $\text{VENT}_x$ is the mass-weighted ventilation factor, and $N^{ML}_{xr}$ is given by (B1).

---

## 5. Results in a 1D Kinematic Model

For testing and demonstration, the three main versions of the scheme—the one-moment version (SM), the two-moment with the diagnosed-$\alpha$ (DIAG), and the three-moment (TM) versions—have been interfaced with a 1D kinematic column model and used to simulate an idealized hailstorm. The model was initialized using a conditionally unstable sounding with a 0°C isotherm at approximately 3.5 km in a 12-km vertical domain. A time-dependent, kinematic updraft is prescribed, growing sinusoidally from an initial peak value of 2 m s$^{-1}$ to a maximum of 20 m s$^{-1}$ over 15 min and then decreasing to zero. The column model uses a two-time-level semi-Lagrangian advection scheme with a vertical grid spacing of 240 m and time step of 20 s.

**Surface precipitation rates**: The peak precipitation rate in SM is much larger than that of DIAG and TM, with values of $340\,\text{mm h}^{-1}$ compared to $23$ and $38\,\text{mm h}^{-1}$, respectively. In SM, the bulk hail fall velocity $V_{Qh}$ is monotonically related to the hail mass content $Q_h$, leading to an unrealistically large accumulation zone. The bulk fall velocity of hail turns out to be approximately 14–18 m s$^{-1}$, closely matching the updraft speed. As the updraft decreases in strength, the large quantity of hail sediments very quickly, resulting in a sudden spike of very large precipitation rates at the surface.

**Hydrometeor mass profiles**: The two-moment (DIAG) and three-moment (TM) versions show qualitatively similar hydrometeor mass distributions, both employing the size-sorting mechanism where hail with higher number concentrations (hence relatively lower bulk fall velocities) is advected aloft and away from the region of high LWC, while hail with lower number concentrations (and higher fall velocities) is able to fall through the updraft. In contrast, results for SM are considerably different.

**Two-moment vs. three-moment**: While the two-moment (diagnosed-$\alpha$) version does a much better job at reproducing the results of the full three-moment version than the one-moment version, there are still notable differences in certain aspects such as the surface precipitation rate. There appears to be a gain in skill for the prognosed-$\alpha$ over the diagnosed-$\alpha$ approach.

**Computational cost**: The diagnostic-$\alpha$ two-moment approach involves additional computational cost compared to the fixed-$\alpha$ approach, because many of the growth equations contain expressions involving the gamma function with $\alpha_x$ as an argument, which must be computed at each time step and grid point if $\alpha$ is variable. However, no additional prognostic variable needs to be advected.

---

## 6. Conclusions

A three-moment closure formulation for bulk microphysics parameterizations has been proposed. By introducing a tendency equation for a third moment, the radar reflectivity, as a function of the tendencies of the other two predicted moments for each microphysical process, the spectral shape parameter $\alpha$ of the gamma size distribution becomes an independent prognostic variable. A new multimoment bulk scheme has been developed.

- The two-moment version predicts the zeroth and third moments of the size spectrum of each hydrometeor category, using the diagnostic equations for the shape parameter based on the mean-particle size introduced in Part I.
- The three-moment version also predicts $\alpha$ by an additional prognostic equation for radar reflectivity.
- 1D kinematic model simulations show that while the two-moment (diagnosed-$\alpha$) version does a much better job at reproducing the results of the full three-moment version than the one-moment version, there are still notable differences in certain aspects such as the surface precipitation rate.
- The scheme has been implemented into the Canadian Mesoscale Compressible Community (MC2) model (Benoit et al. 1997) and applied to successfully simulate a severe hailstorm using a horizontal grid spacing of 1 km.

---

## Appendix A: Source and Sink Terms

The microphysical source/sink terms of the continuity equations are listed below. For the two-moment version, (A14)–(A18) are not used, nor are any equations for tendencies of $Z_x$. For the one-moment version, (A8)–(A18) are not used, nor are any equations for the tendencies of $N_{Tx}$ and $Z_x$.

**Tendencies for the mass mixing ratios:**

$$\frac{dq_\nu}{dt}\bigg|_S = -(Q^{VD}_{\nu c} + Q^{VD}_{\nu r} + Q^{NU}_{\nu i} + Q^{VD}_{\nu i} + Q^{VD}_{\nu s} + Q^{VD}_{\nu g} + Q^{VD}_{\nu h}) \tag{A1}$$

$$\frac{dq_c}{dt}\bigg|_S = Q^{VD}_{\nu c} + Q^{CN}_{cr} + Q^{CL}_{cr} + Q^{FZ}_{ci} + Q^{CL}_{ci} + Q^{CL}_{cs} + Q^{CL}_{cg} + Q^{CL}_{ch} \tag{A2}$$

$$\frac{dq_r}{dt}\bigg|_S = Q^{CN}_{cr} + Q^{CL}_{cr} + Q^{VD}_{\nu r} + Q^{ML}_{ir} + Q^{ML}_{sr} + Q^{ML}_{gr} + Q^{ML}_{hr} - Q^{CL}_{ri} - Q^{CL}_{rs} - Q^{CL}_{rg} - Q^{CL}_{rh} - Q^{FZ}_{rh} \tag{A3}$$

$$\frac{dq_i}{dt}\bigg|_S = Q^{NU}_{\nu i} + Q^{FZ}_{ci} + Q^{VD}_{\nu i} + Q^{IM}_{si} + Q^{IM}_{gi} + Q^{CL}_{ci} - Q^{CL}_{ir} - Q^{CL}_{is} - Q^{CL}_{ig} - Q^{CL}_{ih} - Q^{CN}_{is} - Q^{CN}_{ig} + Q^{ML}_{ir} \tag{A4}$$

$$\frac{dq_s}{dt}\bigg|_S = \delta_{srs}(Q^{CL}_{rs} + Q^{CL}_{sr}) + Q^{CN}_{is} + Q^{VD}_{\nu s} + Q^{CL}_{cs} + Q^{CL}_{is} - Q^{CN}_{sg} - Q^{CL}_{sr} - Q^{CL}_{sh} - Q^{IM}_{si} - Q^{ML}_{sr} \tag{A5}$$

$$\frac{dq_g}{dt}\bigg|_S = \delta_{irg}(Q^{CL}_{ir} + Q^{CL}_{ri}) + \delta_{srg}(Q^{CL}_{sr} + Q^{CL}_{rs}) + \delta_{grg}(Q^{CL}_{gr} + Q^{CL}_{rg}) + Q^{CN}_{ig} + Q^{CN}_{sg} + Q^{CL}_{cg} + Q^{CL}_{ig} - Q^{CL}_{gr} + Q^{VD}_{\nu g} - Q^{CN}_{gh} - Q^{ML}_{gr} - Q^{IM}_{gi} \tag{A6}$$

$$\frac{dq_h}{dt}\bigg|_S = \delta_{irh}(Q^{CL}_{ir} + Q^{CL}_{ri}) + \delta_{srh}(Q^{CL}_{sr} + Q^{CL}_{rs}) + \delta_{grh}(Q^{CL}_{gr} + Q^{CL}_{rg}) + Q^{FZ}_{rh} + Q^{CN}_{gh} + Q^{CL}_{ch} + Q^{CL}_{rh} + Q^{CL}_{ih} + Q^{CL}_{sh} + Q^{VD}_{\nu h} - Q^{ML}_{hr} \tag{A7}$$

**Tendencies for the total number concentrations:**

$$\frac{dN_{Tc}}{dt}\bigg|_S = N^{NU}_{\nu c} + N^{CN}_{c,cr} + N^{CL}_{cr} + N^{VD}_{\nu c} + N^{CL}_{ci} + N^{CL}_{cs} + N^{CL}_{cg} + N^{CL}_{ch} + N^{FZ}_{ci} \tag{A8}$$

$$\frac{dN_{Tr}}{dt}\bigg|_S = N^{CN}_{r,cr} + N^{CL}_{rr} + N^{VD}_{\nu r} + N^{CL}_{ri} + N^{CL}_{rs} + N^{CL}_{rg} + N^{CL}_{rh} + N^{FZ}_{rh} - N^{ML}_{ir} - N^{ML}_{sr} - N^{ML}_{gr} - N^{ML}_{hr} - N^{SH}_{hr} \tag{A9}$$

$$\frac{dN_{Ti}}{dt}\bigg|_S = N^{NU}_{\nu i} + N^{FZ}_{ci} + N^{IM}_{ii} + N^{IM}_{si} + N^{IM}_{gi} + N^{CL}_{ir} + N^{CL}_{is} + N^{CL}_{ig} + N^{CL}_{ih} + N^{CN}_{i,is} + N^{CN}_{i,ig} + N^{VD}_{\nu i} + N^{ML}_{i,ir} \tag{A10}$$

$$\frac{dN_{Ts}}{dt}\bigg|_S = N^{CN}_{s,is} + N^{VD}_{\nu s} + N^{CN}_{sg} + N^{ML}_{sr} + N^{CL}_{sr} + N^{CL}_{ss} + N^{CL}_{sr} - N^{CL}_{sh} - N^{CL}_{srs} \tag{A11}$$

$$\frac{dN_{Tg}}{dt}\bigg|_S = N^{CN}_{g,ig} + N^{CN}_{sg} + N^{CL}_{irg} + N^{CL}_{srg} + N^{CL}_{grg} - N^{CL}_{gr} - N^{CL}_{gh} + N^{CN}_{gh} + N^{VD}_{\nu g} + N^{ML}_{gr} \tag{A12}$$

$$\frac{dN_{Th}}{dt}\bigg|_S = N^{FZ}_{rh} + N^{CN}_{gh} + N^{CL}_{irh} + N^{CL}_{srh} + N^{CL}_{grh} + N^{VD}_{\nu h} + N^{ML}_{hr} \tag{A13}$$

**Tendencies for the radar reflectivity factors:**

$$\frac{dZ_r}{dt}\bigg|_S = Z^{CN}_{cr} + Z^{CL}_{cr} + Z^{CL}_{rr} + Z^{VD}_{\nu r} + Z^{ML}_{r,ir} + Z^{ML}_{r,sr} + Z^{ML}_{r,gr} + Z^{ML}_{hr} - Z^{CL}_{ri} - Z^{CL}_{rs} - Z^{CL}_{rg} - Z^{CL}_{r,rh} - Z^{FZ}_{rh} \tag{A14}$$

$$\frac{dZ_i}{dt}\bigg|_S = Z^{NU}_{\nu i} + Z^{FZ}_{ci} + Z^{IM}_{ii} + Z^{IM}_{si} + Z^{IM}_{gi} + Z^{CL}_{ci} + Z^{VD}_{\nu i} + Z^{CN}_{i,is} + Z^{CN}_{i,ig} + Z^{ML}_{i,ir} - Z^{CL}_{ir} - Z^{CL}_{is} - Z^{CL}_{ig} - Z^{CL}_{ih} \tag{A15}$$

$$\frac{dZ_s}{dt}\bigg|_S = Z^{CL}_{cs} + Z^{CL}_{is} + Z^{VD}_{\nu s} + Z^{IM}_{si} + Z^{ML}_{s,sr} - Z^{CN}_{s,is} + Z^{CN}_{s,sg} + Z^{CL}_{sr} - Z^{CL}_{sh} - Z^{CL}_{ss} - Z^{CL}_{s,srs} \tag{A16}$$

$$\frac{dZ_g}{dt}\bigg|_S = Z^{CL}_{cg} + Z^{CL}_{ig} + Z^{VD}_{\nu g} + Z^{IM}_{gi} + Z^{ML}_{g,gr} + Z^{CN}_{g,gh} - Z^{CN}_{g,ig} - Z^{CN}_{g,sg} - Z^{CL}_{gr} - Z^{CL}_{irg} - Z^{CL}_{srg} - Z^{CL}_{grg} \tag{A17}$$

$$\frac{dZ_h}{dt}\bigg|_S = Z^{CL}_{ch} + Z^{CL}_{rh} + Z^{CL}_{ih} + Z^{CL}_{sh} + Z^{VD}_{\nu h} + Z^{ML}_{h,hr} - Z^{CN}_{h,gh} - Z^{FZ}_{h,rh} - Z^{CL}_{grh} - Z^{CL}_{irh} - Z^{CL}_{srh} \tag{A18}$$

**Temperature change equation:**

$$\frac{dT}{dt}\bigg|_S = \frac{L_f}{C_p}\left(Q^{CL}_{ci} + Q^{CL}_{cs} + Q^{CL}_{cg} + Q^{CL}_{ch} + Q^{CL}_{ri} + Q^{CL}_{rs} + Q^{CL}_{rg} + Q^{CL}_{rh} + Q^{FZ}_{ci} + Q^{FZ}_{rh} - Q^{ML}_{ir} - Q^{ML}_{sr} - Q^{ML}_{gr} - Q^{ML}_{hr}\right) - L_s(Q^{NU}_{\nu i} + Q^{VD}_{\nu i} + Q^{VD}_{\nu s} + Q^{VD}_{\nu g} + Q^{VD}_{\nu h}) - L_\nu(Q^{VD}_{\nu c} + Q^{VD}_{\nu r}) \tag{A19}$$

---

## Appendix B: General Forms of the Tendency Equations for $N_{Tx}$ and $Z_x$

Many of the tendency equations for $N_{Tx}$ can be described by one of two general equations. The first type, based on the assumption that the mean particle mass does not change due to process AB:

$$N^{AB}_{yx} = \frac{N_{Tx}}{q_x} Q^{AB}_{yx} \tag{B1}$$

The second type, assuming particles of mass $m_{x0}$ are being initiated:

$$N^{AB}_{yx} = \frac{\Delta t}{m_{x0}} Q^{AB}_{yx} \tag{B2}$$

The three types of tendency equations for $Z_x$ are:

$$Z^{AB}_{yx} = \frac{G(\alpha_x)}{c_x^2} \left[\alpha \cdot \frac{2q_x}{N_{Tx}} Q^{AB}_{yx} - \frac{q_x^2}{N_{Tx}^2} N^{AB}_{yx}\right] \tag{B3}$$

$$Z^{AB}_{yx} = G(\alpha_{xAB}) \frac{4}{c_x} \frac{(Q^{AB}_{yx})^2}{N^{AB}_{yx}} \tag{B4}$$

$$Z^{AB}_{xy} = -\frac{c_y}{c_x} Z^{AB}_{yx} \tag{B5}$$

Note that the negative sign that appears in (5) has been dropped in (B5); signs are applied appropriately in (A14)–(A18).

---

## Appendix C: List of Symbols

| Symbol | Description | Value | Units |
|--------|-------------|-------|-------|
| $a_x$ | Fall speed parameter for category $x$ | | m$^{1-b_x}$ s$^{-1}$ |
| $A_x$ | Ventilation factor for category $x$ | 0.78 | |
| $AB_i$ | Thermodynamic function for deposition | | m$^{-2}$ s |
| $AB_w$ | Thermodynamic function for rain evaporation | | m$^{-2}$ s |
| $A^\prime$ | Parameter in Bigg freezing equation | 0.66 | K$^{-1}$ |
| $b_x$ | Fall speed parameter for category $x$ | | |
| $B^\prime$ | Parameter in Bigg freezing equation | 100 | m$^{-3}$ s$^{-1}$ |
| $B_x$ | Ventilation factor for category $x$ | 0.31 | |
| $c_i$ | Mass parameter for ice | 440 | kg m$^{-3}$ |
| $c_x$ | Mass parameter for $x$ ($= \rho_x(\pi/6)$ for $x \in \{c,r,s,g,h\}$) | | kg m$^{-3}$ |
| $C$ | Cloud nucleation parameter | | m$^{-3}$ |
| $C_p$ | Specific heat of dry air | 1005.46 | J K$^{-1}$ kg$^{-1}$ |
| $C_i$ | Specific heat of ice | 2093 | J kg$^{-1}$ K$^{-1}$ |
| $C_w$ | Specific heat of liquid water | 4218 | J kg$^{-1}$ K$^{-1}$ |
| $d_x$ | Mass parameter for category $x$ | 3 | |
| $D_{h0}$ | Diameter of embryo hailstone | | m |
| $D_{oh1}$ | Parameter in diagnostic relation for $\alpha_h$ | 0.009 | m |
| $D_{oh2}$ | Parameter in diagnostic relation for $\alpha_h$ | 0.001 | m |
| $D_{mx}$ | Mean-mass diameter of category $x$ | | m |
| $D_{mrMAX}$ | Maximum allowable raindrop diameter | 0.005 | m |
| $D_{r\_new}$ | Diameter of drops formed from autoconversion (computed) | | m |
| $D_{r\_aut}$ | Diameter of drops formed from autoconversion [applied; min($D_r$,$D_{r\_new}$)] | | m |
| $D_{shed}$ | Mean diameter of drops during wet growth | 0.001 | m |
| $D_x$ | Diameter of a particle of category $x$ | | m |
| $E_{xy}$ | Bulk collection efficiency amongst categories $x$ and $y$ | | |
| $E(x,y)$ | Collection efficiency amongst particles $x$ and $y$ | | |
| $f_{fr}$ | Fraction of cloud droplets that freeze in $\Delta t$ | | |
| $f_x$ | Fall velocity parameter for category $x$ | | m$^{-1}$ |
| $f(D)$ | Ventilation factor for a particle of diameter $D$ | | |
| $F$ | Hypergeometric function | | |
| $G(T,p)$ | Thermodynamic function for diffusion growth | | m$^2$ s$^{-1}$ |
| $K_a$ | Thermal conductivity of air | | J m$^{-1}$ s$^{-1}$ K$^{-1}$ |
| $K(x,y)$ | Collection kernel for drops of mass $x$ and $y$ | | |
| $L$ | Characteristic water content for autoconversion | | kg m$^{-3}$ |
| $L_f$ | Latent heat of fusion | $334 \times 10^3$ | J kg$^{-1}$ |
| $L_s$ | Latent heat of sublimation | $283.5 \times 10^4$ | J kg$^{-1}$ |
| $L_\nu$ | Latent heat of condensation | $250.1 \times 10^4$ | J kg$^{-1}$ |
| $m_x(D_x)$ | Mass of a particle with diameter $D_x$ | | kg |
| $m_{i0}$ | Mass of an embryo ice crystal | $10^{-12}$ | kg |
| $m_{g0}$ | Mass of an embryo graupel particle | $1.6 \times 10^{-10}$ | kg |
| $m_{s0}$ | Mass of an embryo snow particle | $4.4 \times 10^{-10}$ | kg |
| $M_x^{(p)}$ | $p$th moment of $N_x(D)$ of category $x$ | | |
| $N_a$ | Concentration of active contact nuclei (for ice) | | m$^{-3}$ |
| $N_{CCN}$ | Concentration of activated CCN | | m$^{-3}$ |
| $N_{Tx}$ | Total number concentration of category $x$ | | m$^{-3}$ |
| $N_x(D)$ | Size distribution function of category $x$ | | m$^{-4}$ (TM) m$^{-1}$ |
| $N_{0x}$ | Intercept parameter for category $x$ | | m$^{-(4+\alpha_x)}$ |
| $N_{ti}$ | Ice concentration given by (24) | | m$^{-3}$ |
| $q_\nu$ | Water vapor mixing ratio | | kg kg$^{-1}$ |
| $q_{s0}$ | Saturation mixing ratio w.r.t. water at $T=0°$C | | kg kg$^{-1}$ |
| $q_{si}$ | Saturation vapor mixing ratio w.r.t. ice | | kg kg$^{-1}$ |
| $q_s$ | Saturation mixing ratio at temperature $T$ | | kg kg$^{-1}$ |
| $q_x$ | Mixing ratio of category $x$ | | kg kg$^{-1}$ |
| $Q_x$ | Mass content of category $x$ | | kg m$^{-3}$ |
| $r_i$ | Mean ice crystal radius | | m |
| $r_{s0}$ | Radius of embryo snow particle | $1 \times 10^{-4}$ | m |
| $R_d$ | Gas constant for dry air | $287.05 \times 10^3$ | J K$^{-1}$ kg$^{-1}$ |
| $R_e$ | Reynolds number | | |
| $R_\nu$ | Gas constant for water vapor | $461.51 \times 10^3$ | J K$^{-1}$ kg$^{-1}$ |
| $s$ | Supersaturation w.r.t. water ($q/q_s - 1$) | | |
| $S_c$ | Schmidt number ($S_c = \kappa/\nu$) | | |
| $S_i$ | Saturation ratio w.r.t. ice | | |
| $S_w$ | Saturation ratio w.r.t. water | | |
| $T$ | Temperature of air | | K |
| $T_c$ | Temperature of air in Celsius | | °C |
| $T_{cc}$ | Temperature of the cloud droplet | | K |
| $T_0$ | Triple point of water | 273.15 | K |
| $\mathbf{U}$ | Three-dimensional velocity vector | | m s$^{-1}$ |
| $V$ | Mean-droplet volume | | m$^3$ |
| $V_c$ | Volume of a cloud droplet | | m$^3$ |
| $V_x(D_x)$ | Fall velocity for particle of category $x$ of size $D_x$ | | m s$^{-1}$ |
| $V_{Nx}$ | Concentration-weighted fall velocity of category $x$ | | m s$^{-1}$ |
| $V_{Qx}$ | Mass-weighted fall velocity of category $x$ | | m s$^{-1}$ |
| $V_{Zx}$ | Reflectivity-weighted fall velocity of category $x$ | | m s$^{-1}$ |
| $\text{VENT}_x$ | Mass-weighted ventilation factor for category $x$ | | m s$^{-2+\alpha_x}$ |
| $w$ | Vertical air velocity | | m s$^{-1}$ |
| $X$ | Maximum allowable condensation/evaporation | | kg kg$^{-1}$ |
| $X_{disp}$ | Dispersion of the fall velocity spectrum of ice | 0.25 | |
| $Z_x$ | Radar reflectivity factor of category $x$ | | m$^3$ |
| $Z_{ex}$ | Equivalent radar reflectivity factor of category $x$ | | m$^3$ |
| $\Delta N_{freeze}$ | Number of cloud droplets that freeze in $\Delta t$ | | |
| $\alpha_{iIM}$ | Value of $\alpha_i$ of new ice crystals from ice multiplication | 0 | |
| $\alpha_{iNU}$ | Value of $\alpha_i$ of new ice crystals from nucleation | 0 | |
| $\alpha_{rAUT}$ | Value of $\alpha_r$ of new raindrops from autoconversion | 2 | |
| $\alpha_{rSH}$ | Value of $\alpha_r$ of new raindrops from shedding | 2 | |
| $\alpha_{zCL}$ | Value of $\alpha_z$ for destination category from three-component freezing | 0 | |
| $\alpha_c$ | Shape parameter for cloud | 1 | |
| $\alpha_x$ | Shape parameter for category $x \in \{r,i,s,g,h\}$ | | |
| $\delta_{xyz}$ | Delta function for three-component freezing between $x$ and $y$ to produce $z$ | 0 or 1 | |
| $\Gamma(x)$ | Complete gamma function | | |
| $\lambda_x$ | Slope parameter for frozen category $x$ | | m$^{-1}$ |
| $\eta$ | Density correction factor for fall velocity, $(\rho/\rho_0)^{1/2}$ | | |
| $\rho$ | Density of air | | kg m$^{-3}$ |
| $\rho_0$ | Surface air density | | kg m$^{-3}$ |
| $\rho_w$ | Density of water | 1000 | kg m$^{-3}$ |
| $\rho_x$ | Bulk density of category $x$ | | kg m$^{-3}$ |
| $\sigma_c$ | Standard deviation of the cloud size distribution | | m |
| $\tau$ | Characteristic timescale for autoconversion | | s |
| $\phi_x$ | Slope parameter of category $x$ | | m$^{-1}$ |
| $\mu$ | Dynamic viscosity of air | | kg m$^{-1}$ s$^{-1}$ |
| $\nu_c$ | Shape parameter for cloud | 3 | |
| $\nu_x$ | Shape parameter for category $x \in \{r,i,s,g,h\}$ | 1 | |
| $\nu_{\text{kin}}$ | Kinematic viscosity coefficient | | m$^2$ s$^{-1}$ |
| $\kappa$ | Diffusivity of water vapor in air | | m$^2$ s$^{-1}$ |
| $\Delta t$ | Time step | | s |

---

## References

Benoit, R., J. M. Desgagné, P. Pellerin, S. Pellerin, Y. Chartier, and S. Desjardins, 1997: The Canadian MC2: A semi-Lagrangian, semi-implicit wideband atmospheric model suited for finescale process studies and simulation. *Mon. Wea. Rev.*, **125**, 2382–2415.

Berry, E., and R. Reinhardt, 1974: An analysis of cloud drop growth by collection. Part II: Single initial distributions. *J. Atmos. Sci.*, **31**, 1825–1831.

Bigg, E. K., 1953: The supercooling of water. *Proc. Phys. Soc. London*, **B66**, 668–694.

Byers, H. R., 1965: *Elements of Cloud Physics*. The University of Chicago Press, 191 pp.

Cohard, J.-M., and J.-P. Pinty, 2000a: A comprehensive two-moment warm microphysical bulk scheme. I: Description and tests. *Quart. J. Roy. Meteor. Soc.*, **126**, 1815–1842.

——, and ——, 2000b: A comprehensive two-moment warm microphysical bulk scheme. II: 2D experiments with a nonhydrostatic model. *Quart. J. Roy. Meteor. Soc.*, **126**, 1843–1859.

——, ——, and C. Bedos, 1998: Extending Twomey's analytical estimate of nucleated cloud droplet concentrations from CCN spectra. *J. Atmos. Sci.*, **55**, 3348–3357.

Cotton, W. R., G. J. Tripoli, R. M. Rauber, and E. A. Mulvihill, 1986: Numerical simulations of the effects of varying ice crystal nucleation rates and aggregation processes on orographic snowfall. *J. Climate Appl. Meteor.*, **25**, 1658–1680.

DeMott, P. J., M. P. Meyers, and W. R. Cotton, 1994: Parameterization and impact of ice initiation processes relevant to numerical model simulations of cirrus clouds. *J. Atmos. Sci.*, **51**, 77–90.

Ferrier, B. S., 1994: A two-moment multiple-phase four-class bulk ice scheme. Part I: Description. *J. Atmos. Sci.*, **51**, 249–280.

——, W.-K. Tau, and J. Simpson, 1995: A two-moment multiple-phase four-class bulk ice scheme. Part II: Simulations of convective storms in different large-scale environments and comparisons with other bulk parameterizations. *J. Atmos. Sci.*, **52**, 1001–1033.

Hallet, J., and S. C. Mossop, 1974: Production of secondary ice particles during the riming process. *Nature*, **249**, 26–28.

Harrington, J. Y., M. P. Meyers, R. L. Walko, and W. R. Cotton, 1995: Parameterization of ice crystal conversion processes due to vapor deposition for mesoscale models using double-moment basis functions. Part I: Basic formulation and parcel model results. *J. Atmos. Sci.*, **52**, 4344–4366.

Kong, F., and M. K. Yau, 1997: An explicit approach to microphysics in MC2. *Atmos. Ocean*, **33**, 257–291.

Lesins, G., R. List, and P. Joe, 1980: Ice accretions. Part I: Testing of new atmospheric icing concepts. *J. Rech. Atmos.*, **14**, 347–356.

Lin, Y.-L., R. D. Farley, and H. D. Orville, 1983: Bulk parameterization of the snow field in a cloud model. *J. Climate Appl. Meteor.*, **22**, 1065–1092.

Long, A. B., 1974: Solutions to the droplet collection equation for polynomial kernels. *J. Atmos. Sci.*, **31**, 1040–1052.

Macklin, W. C., and I. H. Bailey, 1966: On the critical liquid water concentrations of large hailstones. *Quart. J. Roy. Meteor. Soc.*, **92**, 297–300.

McCumber, M., W.-K. Tao, and J. Simpson, 1991: Comparison of ice-phase microphysical parameterization schemes using numerical simulations of tropical convection. *J. Appl. Meteor.*, **30**, 985–1004.

Meyers, M. P., P. J. DeMott, and W. R. Cotton, 1992: New primary ice-nucleation parameterizations in an explicit cloud model. *J. Climate Appl. Meteor.*, **31**, 708–721.

——, R. L. Walko, J. Y. Harrington, and W. R. Cotton, 1997: New RAMS cloud microphysics. Part II: The two-moment scheme. *Atmos. Res.*, **45**, 3–39.

Milbrandt, J. A., and M. K. Yau, 2005a: A multimoment bulk microphysics parameterization. Part I: Analysis of the role of the spectral shape parameter. *J. Atmos. Sci.*, **62**, 3051–3064.

Murakami, M., 1990: Numerical modeling of dynamical and microphysical evolution of an isolated convective cloud—The 19 July 1981 CCOPE cloud. *J. Meteor. Soc. Japan*, **68**, 107–128.

Musil, D. J., 1970: Computer modeling of hailstone growth in feeder clouds. *J. Atmos. Sci.*, **27**, 474–482.

Rasmussen, R. M., and A. J. Heymsfield, 1987: Melting and shedding of graupel and hail. Part II: Sensitivity study. *J. Atmos. Sci.*, **44**, 2764–2782.

Reisner, J., R. M. Rasmussen, and T. Bruintjes, 1998: Explicit forecasting of supercooled liquid water in winter storms using the MM5 mesoscale model. *Quart. J. Roy. Meteor. Soc.*, **124**, 1071–1107.

Walko, R. L., W. R. Cotton, M. P. Meyers, and J. Y. Harrington, 1995: New RAMS cloud microphysics. Part I: The one-moment scheme. *Atmos. Res.*, **38**, 29–62.

Wisner, C., R. D. Orville, and C. Myers, 1972: A numerical model of a hail-bearing cloud. *J. Atmos. Sci.*, **29**, 1160–1181.

Young, K. C., 1974: The role of contact nucleation in ice phase initiation in clouds. *J. Atmos. Sci.*, **31**, 1735–1748.

——, 1993: *Microphysical Processes in Clouds*. Oxford University Press, 427 pp.

Ziegler, C. L., 1985: Retrieval of thermal and microphysical variables in observed convective storms. Part 1: Model development and preliminary testing. *J. Atmos. Sci.*, **42**, 1497–1509.

[Figure 1: Total surface precipitation rates vs time for idealized simulations with a 1D kinematic column model using the one-moment (heavy dashed), two-moment (solid), and three-moment (heavy dot–dashed) versions of the microphysics scheme. (The peak precipitation rate for the one-moment simulation is 340 mm h$^{-1}$.) Inset shows the prescribed updraft profiles every 5 min. — image not reproducible in markdown]

[Figure 2: Profiles of the mass contents of cloud (solid), rain (thick gray), ice (dashed), snow (thick dashed), graupel (dot–dashed), and hail (thick solid) for idealized 1D kinematic column model simulations using the (a),(d) one-moment, (b),(e) two-moment (with diagnosed $\alpha_x$), and (c),(f) three-moment versions of the proposed microphysics scheme at (top) 20 and (bottom) 30 min. — image not reproducible in markdown]
