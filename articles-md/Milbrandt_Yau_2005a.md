# A Multimoment Bulk Microphysics Parameterization. Part I: Analysis of the Role of the Spectral Shape Parameter

**Full citation:** Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part I: Analysis of the role of the spectral shape parameter. *J. Atmos. Sci.*, **62**, 3051–3064. DOI: 10.1175/JAS3534.1

**Authors:** J. A. Milbrandt (Department of Atmospheric and Oceanic Sciences, McGill University, Montreal, and Recherche en Prévision Numérique, Meteorological Service of Canada, Dorval, Quebec, Canada); M. K. Yau (Department of Atmospheric and Oceanic Sciences, McGill University, Montreal, Quebec, Canada)

**Received:** 19 December 2003; **In final form:** 14 February 2005

**Journal:** *Journal of the Atmospheric Sciences*, Vol. 62, September 2005, pp. 3051–3064

---

## Abstract

With increasing computer power, explicit microphysics schemes are becoming increasingly important in atmospheric models. Many schemes have followed the approach of Kessler in which one moment of the hydrometeor size distribution, proportional to the mass content, is predicted. More recently, the two-moment method has been introduced in which both the mass and the total number concentration of the hydrometeor categories are independently predicted.

In bulk schemes, the size spectrum of each hydrometeor category is often described by a three-parameter gamma distribution function, $N(D) = N_0 D^\alpha e^{-\lambda D}$. Two-moment schemes generally treat $N_0$ and $\lambda$ as prognostic parameters while holding $\alpha$ constant. In this paper, the role of the spectral shape parameter, $\alpha$, is investigated by examining its effects on sedimentation and microphysical growth rates. An approach is introduced for a two-moment scheme where $\alpha$ is allowed to vary diagnostically as a function of the mean-mass diameter. Comparisons are made between calculations using various bulk approaches—a one-moment, a two-moment, and a three-moment method—and an analytic bin model. It is found that the size-sorting mechanism, which exists in a bulk scheme when different fall velocities are applied to advect the different predicted moments, is significantly different amongst the schemes. The shape parameter plays an important role in determining the rate of size sorting. Likewise, instantaneous growth rates related to the moments are shown to be significantly affected by this parameter.

---

## 1. Introduction

In operational numerical weather prediction, computer power and model resolution continue to increase. As the horizontal grid size decreases, grid-scale saturation becomes more likely and explicit microphysics schemes should be used for the prediction of clouds and precipitation.[^1] Because bin-resolving (spectral) methods are expensive and impractical in an operational context, bulk methods continue to be the standard approach in representing cloud processes in 3D models.

In addition to predicting precipitation, explicit microphysics schemes serve other functions. The release of latent heat during phase change invigorates storm dynamics while hydrometeor mass loading reduces the buoyancy. Radiative transfer calculations in cloudy air are sensitive to microphysical properties and, depending on the time scale and the extent to which the modeled microphysics and radiation schemes are coupled, may affect significantly the evolution of a modeled storm system (e.g., Yu et al. 1997). Explicit schemes also serve as an excellent tool for conducting detailed process studies.

Many bulk schemes represent the size spectra of each precipitating hydrometeor category by a three-parameter gamma distribution function of the form $N(D) = N_0 D^\alpha e^{-\lambda D}$. For $\alpha = 0$, the equation reduces to an inverse-exponential distribution. Hence the parameters $N_0$ and $\lambda$ are often referred to as the intercept and the slope, respectively. The parameter $\alpha$ gives a measure of the spectral width, or relative dispersion, and is often called the shape parameter. Changes to the distributions are modeled by predicting changes to these parameters. This in turn is accomplished by formulating prognostic equations for one or more of the moments of the distribution function. Since each predicted moment is associated with one prognostic parameter, three predictive moment equations are required to determine the three parameters uniquely. However, many bulk schemes have followed the approach of Kessler (1969) in which only one moment of the hydrometeor size distribution function is predicted (e.g., Lin et al. 1983; Cotton et al. 1986; Kong and Yau 1997) and the other two parameters are prescribed or diagnosed. Generally, in one-moment schemes the mass content, which is proportional to the third moment of $N(D)$, is predicted and $\lambda$ is the prognostic parameter, while $N_0$ and $\alpha$ are held constant. A number of two-moment schemes [e.g., Ziegler (1985, hereafter Z85); Murakami (1990, hereafter M90); Ferrier (1994, hereafter F94); Meyers et al. (1997, hereafter M97); Cohard and Pinty (2000, hereafter CP00); and Reisner et al. (1998, hereafter RRB)] formulate predictive equations for both the mass content and the total number concentration such that $\lambda$ and $N_0$ become independent prognostic variables while $\alpha$ is held constant.

The role of the spectral shape parameter, $\alpha$, for distributions of precipitation particles in bulk schemes has not been thoroughly investigated in the literature. A constant value of $\alpha$ is often used. However, Uijlenhoet et al. (2003) show that in raindrop spectra of a squall line described by gamma distributions the value of the shape parameter for rain ($\alpha_r$) changes from 2.11 during the stratiform phase to 5.66 during the convective phase. Furthermore, for an inverse exponential distribution, where the mean particle diameter equals $1/\lambda$, a large mean diameter implies small values for the slope and unrealistically large particles can be generated near the tail of the distribution. These artificial large particles may impact the bulk fall velocities and the bulk growth rates of microphysical processes. M97 conducted idealized simulations of convection and compared the cases where the shape parameter for all hydrometeor categories changes from 0 to 2.[^2] They found that the peak accumulated surface precipitation more than tripled when $\alpha$ increases from 0 to 2.

In view of the importance of the shape parameter, it is the objective of this paper to analyze the role of $\alpha$ for precipitating hydrometeor categories and to investigate alternatives to holding $\alpha$ constant. The approach is to examine separately the two major roles of a microphysics scheme, the computation of sedimentation and the calculation of microphysical source/sink terms. In a 3D atmospheric model, all of these processes interact very nonlinearly, with each other as well as with the model dynamics, making it difficult to isolate specific effects when $\alpha$ changes. We therefore consider separately sedimentation and microphysical sources under simple, idealized conditions by comparing various bulk schemes to an analytic model. A method to improve the two-moment scheme by diagnosing $\alpha$ as a function of the predicted moments is introduced, together with a formulation of a three-moment parameterization. Based on these results, a new multimoment bulk scheme, with a balance between complexity and efficiency, potentially useful in operational NWP models, has been developed and is described in detail in Milbrandt and Yau (2005, hereafter referred to as Part II).

The following section gives a general overview of the bulk method and discusses the advantages of the two-moment over the one-moment approach. Section 3 introduces a method to diagnose the shape parameter in a two-moment scheme. An analysis of the computation of sedimentation and microphysical growth rates for various bulk methods, with particular attention given to the role of $\alpha$, is presented in section 4. Concluding remarks are given in section 5.

[^1]: In this paper, "explicit" microphysics schemes refer to schemes that are activated upon resolved grid-scale saturation. (Explicit is not used here to refer to the way the hydrometeor size spectrum is modeled, as it is sometimes used.)

[^2]: M97 use the symbol $\nu$ (and refer to it as the breadth parameter), which is equivalent to our $\alpha + 1$.

---

## 2. Overview of the Bulk Method

### a. Equations related to the size distribution

To facilitate the discussion on the role of the shape parameter in bulk microphysics schemes, a general overview of the bulk method is presented here. The particle size distribution for each hydrometeor category in a bulk scheme is described by an analytic function. Most bulk schemes use some form of the generalized gamma distribution function, which can be expressed as

$$N_x(D) = \frac{N_{Tx} \nu_x}{\Gamma(1 + \alpha_x)} \lambda_x^{\nu_x(1+\alpha_x)} D^{\nu_x(1+\alpha_x)-1} \exp\left[-(\lambda_x D)^{\nu_x}\right], \quad (1)$$

where $N_x(D)$ is the total number concentration per unit volume of particles of diameter $D$ for category $x$, $N_{Tx}$ is the total number concentration, $\lambda_x$ is the slope parameter, $\nu_x$ and $\alpha_x$ are dispersion parameters, and $\Gamma$ is the gamma function. CP00 indicated that (1) best describes the observed distribution of cloud droplets. However, for raindrops (e.g., Ulbrich 1983) and ice crystals (e.g., Ivanova et al. 2001), a simplified form of (1) with $\nu_x = 1$ has been found adequate. For snow and hail, the inverse exponential function with $\nu_x = 1$ and $\alpha_x = 0$ in (1) is often used (e.g., Z85 and M90).

Equation (1) can be integrated analytically over all sizes. This property is especially useful in obtaining the moments of the distribution required in the derivation of the source terms and the bulk fall velocities. Specifically, the $p$th moment of the distribution, $M_x(p)$, is given by

$$M_x(p) \equiv \int_0^\infty D^p N_x(D)\, dD = \frac{N_{Tx}}{\lambda_x^p} \frac{\Gamma(1 + \alpha_x + p/\nu_x)}{\Gamma(1 + \alpha_x)}. \quad (2)$$

By setting $\nu_x = 1$, (1) reduces to a three-parameter function involving $N_{Tx}$, $\alpha_x$, and $\lambda_x$ as

$$N_x(D) = N_{0x} D^{\alpha_x} e^{-\lambda_x D}, \quad (3)$$

where

$$N_{0x} = N_{Tx} \frac{1}{\Gamma(1 + \alpha_x)} \lambda_x^{1+\alpha_x}. \quad (4)$$

For the remainder of the paper, we consider only the gamma distribution function of the form of (3), though the generalized form of (1) with $\nu_x = 1$ is implicitly assumed. Now $\lambda_x$ can be related to $N_{Tx}$ and the mixing ratio $q_x$ as follows. It is assumed that the mass $m_x$ of a particle in a hydrometeor category is related to its diameter $D_x$ by $m_x(D_x) = c_x D_x^{d_x}$, where $c_x$ and $d_x$ are constants. The mixing ratio is then given by the $d_x$th moment through the relationship $Q_x = \rho q_x = c_x M_x(d_x)$, with $\rho$ being the density of air. By substituting $p = d_x$ in (2), it is readily shown that

$$\lambda_x = \left[\frac{\Gamma(1 + d_x + \alpha_x)}{\Gamma(1 + \alpha_x)} \frac{c_x N_{Tx}}{\rho q_x}\right]^{1/d_x}. \quad (5)$$

Many one-moment schemes predict $q_x$ while fixing $N_{0x}$ and $\alpha_x$, and use (4) and (5) to solve for $N_{Tx}$ and $\lambda_x$. Most two-moment schemes predict $q_x$ and $N_{Tx}$ and hold $\alpha_x$ constant. To also prognose $\alpha_x$, it is necessary to add a third predictive equation for an added moment to form a three-moment scheme. In principle, any other moment can be used. However, there is the advantage in using the sixth moment of the distribution $M_x(6)$, which is the radar reflectivity factor $Z_x$, obtained routinely from radar measurements. Here $Z_x$ can be derived from (2) and (5) and is of the form

$$Z_x = M_x(6) = \frac{G(\alpha_x)}{c_x^2} \frac{(\rho q_x)^2}{N_{Tx}}, \quad (6)$$

where

$$G(\alpha_x) = \frac{(6+\alpha_x)(5+\alpha_x)(4+\alpha_x)}{(3+\alpha_x)(2+\alpha_x)(1+\alpha_x)}.$$

Using Rayleigh theory, $Z_x$ can also be converted to the equivalent radar reflectivity $Z_{ex}$ using

$$Z_{ex} = \frac{|K|_i^2}{|K|_w^2} \left(\frac{c_x}{c_r}\right)^2 Z_x, \quad (7)$$

with the ratio of the dielectric constants for ice and liquid water $|K|_i^2/|K|_w^2 = 0.224$ (F94), and $c_r = (\pi/6)\rho_w$, where $\rho_w$ is the density of water. Equations (4)–(6), along with the microphysical source/sink terms to predict changes in $N_{Tx}$, $q_x$, and $Z_x$, constitute a three-moment bulk scheme to predict the size spectra for hydrometeor category $x$.

### b. Advantages of the two-moment over the one-moment approach

Before proceeding to analyze the role of the shape parameter, it is useful to understand the advantages in predicting two moments instead of a single moment. In a one-moment scheme, regardless of the choice of the predictive variable, (4) and (5) indicate that the mass mixing ratio $q_x$ and the total number concentration $N_{Tx}$ (or $N_{0x}$) are always monotonically related. However, this assumption is not always valid because in nature each quantity can vary independent of the other. For example, if particles were growing by accretion or diffusion, the total mass of the particles changes but the total number does not. Conversely, for aggregation or breakup, the total number of particles changes while the total mass remains constant. The independent change of $q_x$ and $N_{Tx}$ is also borne out by numerical experiments. In two squall line simulations using a two-moment scheme for the ice phase, Ferrier et al. (1995) found that $\lambda_x$ varied by a factor of 3 while $N_{0x}$ varied by several orders of magnitude for snow, graupel, and hail particles.

Many one-moment schemes use a Kessler-type (1969) approach to model the warm rain process. The size distribution of raindrops is assumed to follow a Marshall–Palmer (1948) distribution with a fixed $N_{0r}$. Although this assumption may be valid for certain stratiform conditions, $N_{0r}$ can vary by 2 orders of magnitude in time and space for convective cases (Waldvogel 1974). Furthermore, in convective situations with rainwater contents larger than 1 g m$^{-3}$, $\lambda_r$ tends toward a constant while $N_{0r}$ varies with the rainwater content (Srivastava 1978; Ferrier et al. 1995; RRB). Many storm systems consist of regions that are distinctly stratiform and others that are distinctly convective. Since the different regions have different microphysical structures and histories, a two-moment scheme would be more appropriate than a one-moment approach.

Another drawback of one-moment schemes lies in the treatment of sedimentation. Sedimentation is an important process because surface precipitation and the feedback of microphysics to storm dynamics through mass loading and diabatic heating are highly dependent on the distribution of hydrometeor mass, which is affected by sedimentation. In an NWP or mesoscale model, the distribution of hydrometeor mass is governed by the equation

$$\frac{\partial q_x}{\partial t} = -\frac{1}{\rho} \nabla \cdot (\rho q_x \mathbf{U}) + \text{TURB}(q_x) + \frac{1}{\rho} \frac{\partial}{\partial z}(\rho q_x V_{Qx}) + \left.\frac{dq_x}{dt}\right|_S, \quad (8)$$

where $\mathbf{U}$ is the 3D velocity vector, and $V_{Qx}$ is the mass-weighted fall speed [see (A3) in the appendix]. The terms on the right of (8) represent, respectively, advection/divergence, turbulent mixing, sedimentation, and microphysical sources. In nature, a major effect of sedimentation is size sorting, where large particles, by virtue of their large terminal fall speed, appear preferentially at lower levels than at upper levels. As a result, the mean size of the particles would decrease with height if sedimentation were to act alone. This effect, however, cannot be duplicated in a one-moment scheme because there is a single mean fall speed for particles of different sizes in a hydrometeor category.

Size sorting can be modeled by a two-moment scheme that includes a second predictive equation for a quantity like the total number concentration

$$\frac{\partial N_{Tx}}{\partial t} = -\nabla \cdot (N_{Tx} \mathbf{U}) + \text{TURB}(N_{Tx}) + \frac{\partial}{\partial z}(N_{Tx} V_{Nx}) + \left.\frac{dN_{Tx}}{dt}\right|_S, \quad (9)$$

where $V_{Nx}$ is the number concentration-weighted fall velocity [see (A5)]. Since $q_x$ and $N_{Tx}$ sediment at different bulk fall velocities, and since $V_{Qx}$ is always larger than $V_{Nx}$ [see (A3) and (A5)], sedimentation would result in larger values for the ratio $q_x/N_{Tx}$ at lower levels than at upper levels. Hence the mean-mass diameter $D_{mx}$, given by

$$D_{mx} = \left(\frac{\rho q_x}{c_x N_{Tx}}\right)^{1/d_x}, \quad (10)$$

increases toward the ground. Differential sedimentation in a bulk scheme (i.e., $N_{Tx}$ sediments at a different bulk fall velocity than $q_x$), therefore effectively represents a realistic gravitational size-sorting mechanism whereby the mean sizes are redistributed in the vertical with larger (smaller) mean sizes appearing at relatively lower (higher) levels. This effect does not occur in a one-moment scheme or in a multimoment scheme in which $q_x$ and $N_{Tx}$ sediment at the same fall velocity. A more accurate method of incorporating the effects of size sorting is to treat sedimentation using a spectral approach, such as in Feingold et al. (1998). This approach is more costly, however, since it involves the use of look-up tables. Furthermore multimoment bulk schemes can closely reproduce the effects of sedimentation from a bin model, as is shown below in section 4, provided that each of the predicted moments of the size distribution sediments at the appropriate fall velocity.

During sedimentation, the rate of change of $(\rho q_x)/N_{Tx}$ (and thus $D_{mx}$) is proportional to the fall speed ratio

$$\frac{V_{Qx}}{V_{Nx}} = \frac{\Gamma(1 + d_x + \alpha_x + b_x)\Gamma(1 + \alpha_x)}{\Gamma(1 + d_x + \alpha_x)\Gamma(1 + \alpha_x + b_x)}, \quad (11)$$

where $b_x$ is the fall speed parameter defined in (A1). For the five precipitating hydrometeor categories (rain, ice, snow, graupel, and hail, denoted by the subscripts r, i, s, g, and h, respectively) considered in the scheme described in Part II, the values for $b_x$ are tabulated in Table 2 of that paper. Figure 1 depicts the fall speed ratio, a measure of the rate of size sorting or the rate at which $D_{mx}$ is redistributed in the vertical, against the shape parameter $\alpha_x$. Evidently, the size-sorting rate decreases as $\alpha_x$ increases and approaches 1 for large values of $\alpha_x$. For a given value of the shape parameter, size sorting occurs faster for categories with larger values of $b_x$.

[Figure 1: Ratio of the mass-weighted fall velocity ($V_{Qx}$) to the number-weighted fall velocity ($V_{Nx}$) vs $\alpha_x$ for rain (long dashed), hail (solid), ice (dashed), snow (dot–dashed), and graupel (dotted). — image not reproducible in markdown]

Since the fall speed ratio exceeds 1, size sorting always occurs and, given enough time, can eventually lead to unrealistically large mean sizes. CP00 discussed this problem for rain and proposed a solution by setting an upper limit on $D_{mr}$ to account for spontaneous breakup of water drops. Wherever $D_{mr}$ exceeds the maximum allowable size $D_{mr}^{\text{MAX}}$ of 5 mm immediately after sedimentation, $N_{Tr}$ is adjusted so that $D_{mr} = D_{mr}^{\text{MAX}}$. For frozen categories, breakup does not occur and the setting of a maximum size cannot be justified on physical grounds but may still be necessary for numerical reasons.

---

## 3. Diagnostic Relation for $\alpha$ — An Alternative Two-Moment Approach

Ideally, for a hydrometeor category described by a three-parameter size distribution function, three moments of the distribution should be independently predicted such that the shape parameter is a prognostic variable. However, three-moment schemes are costly and hence two-moment schemes are still attractive in terms of efficiency. In most two-moment schemes, $\alpha_x$ is held constant. This assumption is not intrinsic of the method, which only requires that $\alpha_x$ cannot vary independently. Similarly, a one-moment scheme with an inverse-exponential distribution need not fix one of the distribution parameters ($N_{0x}$ or $\lambda_x$) as a constant. It is possible to obtain a diagnostic relation between the two parameters provided that there is a good physical justification (e.g., Sekhon and Srivastava 1970; Cheng and English 1983).

An alternative solution to the problem of excessively large mean sizes in a two-moment scheme can be obtained from an inspection of (11). If $\alpha_x$ were allowed to increase as size sorting occurs, the ratio $V_{Qx}/V_{Nx}$ would decrease and excessive size sorting can be controlled. An increase in $\alpha_x$ due to size sorting also makes physical sense because in nature size-sorting results in a narrowing of the spectrum characterized by larger values of $\alpha_x$.

A method to develop an empirical relation of this type is to use results from a detailed model as a guide. Gravitational size sorting is the most important physical mechanism in producing a narrowing of the hydrometeor size spectra. It is demonstrated in the next section that a three-moment approach reproduces remarkably well the profiles of various moments resulting from pure sedimentation in a one-dimensional model. Specifically, an initial population of hail particles was defined by specifying $Q_h$, $N_{Th}$, and $Z_h$ at all levels between 8 and 10 km above the ground. By solving the equations governing pure sedimentation in a three-moment scheme (see the appendix), the evolution of the vertical profile of the moments of the hail spectrum were obtained. The corresponding profiles of $\alpha_h$ and $D_{mh}$ were then computed using (6) and (10). Figure 2 shows plots of $\alpha_h$ versus $D_{mh}$ at various times from the three-moment sedimentation profiles. Each thin curve represents all of the $(\alpha_h, D_{mh})$ points in the vertical at a fixed time. Although there is no monotonic relation between $\alpha_h$ and $D_{mh}$, it is apparent that $\alpha_h$ almost always increases with $D_{mh}$. This suggests that for a two-moment scheme, a monotonically increasing function relating $D_{mx}$ and $\alpha_x$ may be an improvement over the assumption of a constant $\alpha_x$.

[Figure 2: Plots of $\alpha_h$ vs mean-mass diameter ($D_{mh}$) at the indicated times from the sedimentation profiles of hail in a three-moment scheme and from the diagnostic Eq. (12) for $\alpha_h = f(D_{mh})$. — image not reproducible in markdown]

The $(\alpha_h, D_{mh})$ data points from the three-moment sedimentation profiles were used as guidance to explore functional relations between $\alpha_x$ and $D_{mx}$ as possible diagnostic equations for $\alpha_x$ in a two-moment scheme. By trial and error, it was found that the application of the following expression in a two-moment scheme gave the best overall improvement for pure sedimentation of hail compared to using a fixed value of the shape parameter:

$$\alpha_h = \begin{cases} c_{1h} \tanh\left[c_{2h}(D_{mh} - c_{3h})\right] + c_{4h} & \text{for } D_{mh} \leq 8 \text{ mm} \\ c_{5h} D_{mh} - c_{6h} & \text{for } D_{mh} > 8 \text{ mm}. \end{cases} \quad (12)$$

Similarly, for the other sedimenting hydrometeor categories described in Part II, the relation between the mean diameter and the shape parameter is chosen to be

$$\alpha_x = c_{1x} \tanh\left[c_{2x}(D_{mx} - c_{3x})\right] + c_{4x}, \quad (13)$$

where the values of the constants for each category $x$ are listed in Table 1.

**Table 1.** Constants in diagnostic relations for $\alpha_x$ [(12) and (13)] for each hydrometeor category $x$ of the proposed scheme described in Part II.

| Category, $x$ | $c_{1x}$ | $c_{2x}$ (mm$^{-1}$) | $c_{3x}$ (mm) | $c_{4x}$ | $c_{5x}$ (mm$^{-1}$) | $c_{6x}$ |
|---|---|---|---|---|---|---|
| Rain    | 19.0 | 0.6 | 1.8 | 17.0 | n/a | n/a |
| Ice     | 12.0 | 0.7 | 1.7 | 11.0 | n/a | n/a |
| Snow    |  4.5 | 0.5 | 5.0 |  5.5 | n/a | n/a |
| Graupel |  5.5 | 0.7 | 4.5 |  8.5 | n/a | n/a |
| Hail    |  3.7 | 0.3 | 9.0 |  6.5 | 1.0 | 6.5 |

---

## 4. Assessing the Importance of the Shape Parameter

The role of the shape parameter was described qualitatively in the previous sections. Here, we examine in some detail the quantitative effects of the different approaches in the treatment of $\alpha_x$ on the prediction of hydrometeor mass given by (8). Our focus is on how $\alpha_x$ affects the sedimentation terms and the source terms separately.

### a. Sedimentation

A 1D model is used to investigate pure sedimentation of the various moments of the size distribution of hail using the appropriate moment-weighted bulk fall velocities [see (A3), (A5), and (A7)]. The fall velocity parameters for hail are $a_h = 206.89$ m$^{1-b_h}$ s$^{-1}$, $b_h = 0.6384$, and $f_h = 0$ m$^{-1}$ (F94). All processes except for sedimentation are switched off. The hail category is chosen to avoid confusion regarding the neglected effects of particle coalescence and breakup. An initial population of hail particles is defined by specifying $Q_h$ to vary sinusoidally between heights ($z$) of 8 and 10 km above ground with a maximum value of 1 g m$^{-3}$ at $z = 9$ km. Values of $N_{0h} = 4 \times 10^4$ m$^{-4}$ and $\alpha_h = 0$ are used to compute the initial values of $N_{Th}$ and $Z_h$ at each level. Each frame in Fig. 3 displays the vertical profiles every 5 min caused by pure sedimentation. The rows depict the quantities $Q_h$, $N_{Th}$, $Z_{eh}$, and $D_{mh}$, respectively. The different columns contain the results of the different bulk methods tested. The symbols SM, FIX0, FIX3, DIAG, TM, and ANA denote one-moment, two-moment with $\alpha_h = 0$, two-moment with $\alpha_h = 3$, two-moment with $\alpha_h$ diagnosed by (12), three-moment, and the Lagrangian analytic model, respectively. For SM, changes to the $Q_h$ profiles were computed using (A2) and $\lambda_h$ is calculated using (5) with $N_{0h}$ and $\alpha_h$ held constant. For FIX0, changes in $Q_h$ and $N_{Th}$ were computed using (A2) and (A4), respectively. Also $N_{0h}$, as well as $\lambda_h$, becomes a prognosed parameter and $Z_{eh}$ is computed from $Q_h$, $N_{Th}$, and $\alpha_h$ using (6) and (7). FIX3 is the same as FIX0 except $\alpha_h = 3$. In DIAG, $\alpha_h$ is diagnosed from (12). In TM, changes to $Q_h$ and $N_{Th}$ are calculated using (A2) and (A4) and changes to $Z_h$ are computed using (A6) and converted to $Z_{eh}$ using (7). With $Q_h$, $N_{Th}$, and $Z_h$ known, $\alpha_h$ can be obtained through the solution of (6). In ANA, the profiles are computed using an analytic model, in which the size spectra at each level are partitioned into 5000 size bins. The levels to which the particles in each bin fall after a given time are calculated using the fall velocity (A1) for a given bin. For simplicity, the air density factor $\gamma$ in (A1) is set to 1.

A number of aspects can be noted from Fig. 3. In SM, $N_{Th}$, $Z_{eh}$, and $D_{mh}$ are diagnosed directly from $Q_h$ and their profiles are therefore similar. This result is known a priori, but it is important to recognize that the same profiles would be obtained for a two-moment scheme without differential sedimentation where the fall velocities for $N_{Th}$ and $Q_h$ are identical. It may appear from Fig. 3s that size sorting occurs in SM since larger (smaller) values of $D_{mh}$ are found at lower (higher) levels. However, this interpretation is misleading since in SM, the maximum value of $D_{mh}$ at all times simply corresponds to the maximum value of $Q_h$ and is never larger than 4 mm. In all other schemes, size sorting is apparent by the redistribution of larger sizes to lower levels and the large increase in the mean sizes with time but without a large mass content.

Because of the relatively large $V_{Qh}/V_{Nh}$ ratio for $\alpha_h = 0$ depicted in Fig. 1, the effect of differential sedimentation occurs more rapidly in FIX0 than in ANA. The early production of large mean sizes leads to large values in $V_{Qh}$, earlier arrival of mass at the surface, and too large $D_{mh}$. The values of $Z_{eh}$ are excessively large (e.g., ~80 dBZ at $z = 2$ km after 5 min in FIX0, and ~25 dBZ at 2 km for ANA). In comparison, the profiles in FIX3 are much better than those in FIX0 because of the smaller $V_{Qh}/V_{Nh}$ ratio with $\alpha_h = 3$. Size sorting is still excessive in FIX3. For instance, $Z_{eh}$ at lower levels are still too large at 5 min, though not as large as in FIX0. At 15 and 20 min, the $D_{mh}$ profiles for both FIX0 and FIX3 are reasonable.

In DIAG, both the $Q_h$ and $N_{Th}$ profiles are very similar to those of FIX3. There is some improvement in the $Z_{eh}$ profiles at 5 and 10 min. Excessive size sorting appears to be under control in DIAG, but perhaps too much so as mean sizes at levels below ~4 km at 5 min are now too small. At later times, however, they compare well to ANA for the entire column. The same comments apply to the $Q_h$, $Z_{eh}$, and $D_{mh}$ profiles of TM. Note the improvement in the $N_{Th}$ profiles in TM over those of FIX3 and DIAG.

Experiments FIX3, DIAG, and TM are much better than SM or FIX0 at predicting the vertical distributions of $Q_h$, $N_{Th}$, $Z_{eh}$, and $D_{mh}$. Even though the $D_m$ profile at 5 min in FIX3 below 4 km appears better than those of DIAG and TM, the mass content at the low levels is however negligible. At 10 min when there is appreciable mass content throughout most of the column, DIAG and TM give slightly better $D_m$ profiles than FIX3. In general, the effect of sedimentation is similar in FIX3, DIAG, and TM, with the latter yielding particularly good agreement in radar reflectivity to the analytic solution.

[Figure 3: Vertical profiles of (first row) $Q_h$, (second row) $N_{Th}$, (third row) $Z_{eh}$, and (fourth row) $D_{mh}$ resulting from the sedimentation of hail from (first column) a one-moment scheme, (second column) a two-moment scheme with $\alpha_h = 0$, (third column) a two-moment scheme with $\alpha_h = 3$, (fourth column) a two-moment scheme with a diagnosed $\alpha_h$, (fifth column) a three-moment scheme, and (sixth column) an analytic bin model. Profiles in each panel are every 5 min between 0 and 20 min. — image not reproducible in markdown]

Figure 4 plots the surface precipitation rates from the various schemes. For ANA, precipitation reaches the surface after approximately 8 min with a maximum rate of ~6 mm h$^{-1}$ at 16 min. The arrival of surface precipitation is delayed in SM, and the peak rate is overpredicted (~17 mm h$^{-1}$). In agreement with the finding of Wacker and Seifert (2001), precipitation arrives too early and the rate is too high in FIX0. However, as the value of $\alpha_h$ increases, the first arrival of precipitation becomes increasingly delayed and the peak rate is also reduced. For a two-moment scheme with constant $\alpha_x$, it is clear that $\alpha_x = 3$ yields the best results in terms of surface precipitation and the vertical distribution of mass. On the other hand, TM best predicts the timing of the arrival but slightly underpredicts the peak rate. DIAG best predicts the peak rate though the time of the first arrival is slightly delayed. Except for some minor differences, FIX3, DIAG, and TM are more similar to each other than the other schemes.

[Figure 4: Surface precipitation rates (ordinate) vs time (abscissa) from the sedimentation of hail computed using the indicated bulk schemes. FIX(x) refers to the two-moment scheme with a constant $\alpha_h = x$; SM refers to the one-moment scheme; DIAG refers to the two-moment scheme with $\alpha_h$ diagnosed from Eq. (12); TM refers to the three-moment scheme; and ANA refers to the analytic bin model. — image not reproducible in markdown]

So far, our 1D results are representative of precipitation falling through an environment with no vertical motion. If an updraft were present, a population of hydrometeors would take longer to sediment to the ground and the differences between the various bulk schemes may be amplified. To test this, a similar set of computations was made but with a constant updraft of 10 m s$^{-1}$. The initial peak $Q_h$ at $z = 9$ km is increased to 5 g m$^{-3}$. Only FIX3, DIAG, TM, and ANA are compared since they yield the best results.

Figure 5 shows the profiles for the four schemes at 10 and 40 min. They can be interpreted as the results of pure sedimentation of particles starting near the top of a deep convective system. We consider the top and the base of the cloud to be at 12 and 0 km, respectively. Particles with small bulk fall velocities are advected upward and can be transported out of the column after reaching the cloud top. At 10 min, the $Q_h$ distribution predicted by TM is much closer to ANA than FIX3 or DIAG. By 40 min, the mass distribution for DIAG and TM are very good, with TM being slightly better, whereas the mass throughout the column is significantly underpredicted in FIX3. The $N_{Th}$ profiles for TM are very close to ANA throughout the entire column at both times. On the other hand, both FIX3 and DIAG overpredict $N_{Th}$ aloft, with DIAG performing much better than FIX3. At 10 min, $Z_{eh}$ is well predicted for TM, underpredicted for DIAG, and overpredicted for FIX3. At 40 min, $Z_{eh}$ is nearly exact for TM but has a constant bias of ~5 dBZ throughout the column for both FIX3 and DIAG. Excessive size sorting in FIX3 results in overprediction of $D_{mh}$ throughout the column. The situation is better controlled in DIAG. The $D_{mh}$ profiles for TM are very close to ANA at both 10 and 40 min.

[Figure 5: Vertical profiles of (a),(b) $Q_h$, (c),(d) $N_{Th}$, (g),(h) $Z_{eh}$ at (left) 10 min and (right) 40 min from the sedimentation profiles of hail through a constant updraft of 10 m s$^{-1}$. — image not reproducible in markdown]

Based on the results of our experiments, we conclude that the shape parameter indeed plays an important role in affecting sedimentation. Although differential sedimentation of $Q_x$ and $N_{Tx}$ produces significant improvement over a one-moment scheme, setting $\alpha_x$ constant can still result in large errors. We found that for pure sedimentation, setting $\alpha_x = 3$ in a two-moment scheme results in an apparently optimal fixed $V_{Qx}/V_{Nx}$ ratio. However, there is obvious improvement if $\alpha_x$ is diagnosed as an increasing function of the $D_{mx}$ in a two-moment scheme. Other initial distributions have been tested by varying $\alpha_x$ and $N_{0x}$ and the conclusions remain the same. The profiles due to pure sedimentation were invariably better for the two-moment scheme with diagnosed $\alpha_x$ than with fixed $\alpha_x$. The three-moment scheme clearly outperforms all the rest.

### b. Source/sink terms

The mass source term of (8) for each category $x$ is computed as the sum of the individual microphysical sources and sinks. Collection, melting, and diffusional growth/decay are the processes that have the greatest impact on the prediction of hydrometeor mass content. It can be shown readily that the growth rate in $q_x$ for a frozen hydrometeor category accreting cloud water is strongly dependent on $M_x(2 + b_x)$, $M_x(1 + b_x)$, and $M_x(b_x)$ [see (2) above and (25) of Part II]. Similarly, the growth rate due to diffusion is strongly dependent on $M_x(1)$ and $M_x(1.5 + 0.5b_x)$ [see (43)–(45) of Part II]. The rate of mass change due to melting is governed by all the above moments [see (45) and (79) of Part II]. In addition, the rates of change in $N_{Tx}$ and $Z_x$ due to collection, melting, and diffusional growth are related to the rates of change in $q_x$ [e.g., see (80) and (81) of Part II for melting]. Since the shape parameter affects directly the calculation of the moments, an assessment of the impact of $\alpha_x$ on the source terms is equivalent to assessing the effect of $\alpha_x$ on computing the moments.

Our goal is to determine the errors in the computation of the instantaneous source/sink terms due to an incorrect estimation of the value of $\alpha_x$ for a given total number concentration $N_{Tx}$ and mass content $q_x$. To this end we define the following ratio:

$$r(p, \alpha_\text{est}, \alpha_\text{corr}) \equiv \frac{M(p, \alpha_\text{est})}{M(p, \alpha_\text{corr})} = \frac{\Gamma(1 + \alpha_\text{corr})\Gamma(1 + p + \alpha_\text{est})}{\Gamma(1 + \alpha_\text{est})\Gamma(1 + p + \alpha_\text{corr})} \times \left[\frac{\Gamma(1 + \alpha_\text{est})\Gamma(4 + \alpha_\text{corr})}{\Gamma(4 + \alpha_\text{est})\Gamma(1 + \alpha_\text{corr})}\right]^{(p/3)}, \quad (14)$$

where $M(p, \alpha_\text{est})$ is the $p$th moment of $N(D)$ calculated using an estimated value of $\alpha_\text{est}$ from a bulk scheme [either fixed, diagnosed, or computed from (6)] and $M(p, \alpha_\text{corr})$ is the $p$th moment computed using the correct value $\alpha_\text{corr}$. Since $r(p, \alpha_\text{est}, \alpha_\text{corr}) = 1$ when $\alpha_\text{corr} = \alpha_\text{est}$, the difference between $r(p, \alpha_\text{est}, \alpha_\text{corr})$ and 1 represents the error in $M(p)$ computed using $\alpha_\text{est}$ in a given bulk scheme. Figure 6 displays $r(p, \alpha_\text{est}, \alpha_\text{corr})$ as a function of $\alpha_\text{corr}$ for $p$ ranging from 0.6 to 6. The curves shown are for two values of $\alpha_\text{est}$ because in many two-moment schemes, an inverse-exponential distribution is used for frozen hydrometeor categories with $\alpha_\text{est} = 0$ and we have demonstrated previously that for a fixed value of the shape parameter, $\alpha_\text{est} = 3$ yields the best improvement in terms of sedimentation. Note that the curves always pass through the point $(\alpha_\text{est}, 1)$. In general, for $\alpha_\text{corr} > \alpha_\text{est}$, the values of the moments with $p$ smaller (larger) than 3 are underestimated (overestimated). The reverse is true for $\alpha_\text{corr} < \alpha_\text{est}$. For $0 < p < 3$ the largest error occurs for $p \approx 1.6$, while for $p > 3$ the error is larger the higher the moment. For example, suppose a particular population of hail should have an $\alpha_h$ of 5 ($\alpha_\text{corr}$) but the scheme uses a fixed value of 0 ($\alpha_\text{est}$), then the radar reflectivity $M(6)$ would be overestimated by nearly 700% while the approximate growth rate by collection of cloud [proportional to $M(2.6)$ with $b_h \approx 0.6$] underestimated by ~15%. The same effect occurs if $\alpha_\text{est} = 3$ but $\alpha_\text{corr} = 5$. In this case $M(6)$ is overestimated by ~42% while $M(2.6)$ underestimated by ~3%. However, if $\alpha$ is fixed at 3 and its true value should be 0, $M(2.6)$ would be overestimated by ~15%.

[Figure 6: Ratios of $r(p, \alpha_\text{est}, \alpha_\text{corr})$ (see text) vs $\alpha_\text{corr}$ for (a) $\alpha_\text{est} = 0$ and (b) $\alpha_\text{est} = 3$ for various $p$th moments. Insets are magnifications of the panel. — image not reproducible in markdown]

To further examine the role of $\alpha$ on the source terms, vertical profiles of $M(1.6)$ and $M(2.6)$ [i.e., $M_x(1 + b_x)$ and $M_x(2 + b_x)$ for $b_h \approx 0.6$] after sedimentation of an initial population of hail particles, identical to the setup shown in Fig. 5, were calculated using the various bulk approaches as well as the analytic model. The moments $M(1.6)$ and the $M(2.6)$ are related to the largest and the smallest errors in the instantaneous growth rate of hail, respectively. To separate the effect of sedimentation from the computation of the source terms, the profiles of $Q_h$, $N_{Th}$, and $Z_h$, due to pure sedimentation in the analytic model, were used to calculate $N_{0h}$, $\lambda_h$, and $\alpha_h$ in the various bulk schemes in the same manner described in section 2. The calculated parameters at various times were then used to compute $M(1.6)$ and $M(2.6)$. For the analytic model, the moments were obtained by summing $D_i^p N_{Ti} \Delta D$ over all bins with $N_{Ti}$ being the number of particles in bin $i$ with diameter $D_i$ and $\Delta D$ is the bin width. The ratios of $M_h(p)_\text{bulk}/M_h(p)_\text{ana}$ were then computed.

The profiles of $M_h(p)_\text{bulk}/M_h(p)_\text{ana}$ for $p = 1.6$ and $p = 2.6$ after 2 and 8 min, along with the corresponding profiles for $\alpha_h$ in a given scheme, are shown in Fig. 7. These early times are chosen for the following reason. Size sorting from sedimentation quickly produces narrow particle spectra at all levels after only a few minutes. In a full simulation, other processes may also be occurring which maintain a broad spectrum. Therefore it is important to investigate also situations with relatively broad spectra. For pure sedimentation, these situations occur only at early times at the mid- and upper levels. At 2 min, size sorting is only moderate between $z = 8.0$ and 10.5 km and the size spectra, characterized by the low values of $\alpha$ for TM, are broad. Below $z = 8.0$ km at 2 min and at most levels at or after 8 min, size sorting is well advanced and the size spectra are relatively narrow. The moment ratio $M_h(p)_\text{bulk}/M_h(p)_\text{ana}$ is a measure of the accuracy in calculating the $p$th moment relative to the analytic solution. Values smaller (larger) than 1 for a particular bulk scheme imply under- (over-) prediction of the magnitude of the moment.

At 2 min, SM underpredicts the two moments above 9 km and greatly overpredicts them below. The results for FIX0 are generally better with the moment ratio always less than 1.00 but never below 0.50 for $M(1.6)$ or 0.80 for $M(2.6)$. For FIX3, the curves for the moment ratio shifted to the right with an underestimation of ~20% for $M(0.6)$ and ~10% for $M(2.6)$ at lower levels but an overestimation at higher levels. DIAG behaves similarly to FIX3 above 8.5 km but the underestimation is greatly reduced below. The best results occur in TM, particularly for the $p = 2.6$ moment ratio, which is close to 1 throughout the column. The behavior of the curves at 8 min is consistent with those at 2 min; TM performs the best, followed by DIAG, FIX3, FIX0, and SM in descending order of performance.

The accurate prediction of the source terms is closely related to the accurate prediction of the width of the particle size distribution. In Fig. 8, the size spectra at three different levels and at two different times are displayed. For the calculation of the $M(1.6)$ and $M(2.6)$ moments, it is important to predict accurately the size spectra near the peak of the distribution. For example at 2 min and at $z = 9.5$ km, FIX3, DIAG, and TM overpredict the concentration in the diameter range from ~0.002 to 0.006 m, while FIX0 underpredicts. This accounts for the overprediction of the moment $M(1.6)$ in FIX3, DIAG, and TM, but an underprediction in FIX0. At $z = 7.5$ km and 2 min, TM and DIAG predict well the concentration in the diameter range 0.014–0.028 m surrounding the peak, as a result the moment $M(1.6)$ in these two schemes shows excellent agreement with the analytic solution. The underprediction of the concentration in FIX3 and FIX0 in the same diameter range is reflected in the underprediction of the 1.6th moment. In the case of the well sorted and thus narrow distribution at 5 km and 8 min, the spectra of FIX0 and FIX3 are much broader than the analytic distribution resulting in underestimation of the concentration around the modal diameter (~0.019 m) as well as the moments $M(1.6)$ and $M(2.6)$. The distribution is better in DIAG, being narrower and with a higher concentration around the modal diameter, but it is not as good as in TM, which has a high value for $\alpha$. Although still broader than the analytic spectrum, the size distribution of TM yields excellent $M(1.6)$ and $M(2.6)$.

[Figure 7: Vertical profiles of the ratios of $M(2.6)$ computed by various bulk schemes to $M(2.6)$ computed from the analytic model after (top) 2 min and (bottom) 8 min and corresponding profiles of $\alpha$ from (right) the bulk schemes. The bulk schemes shown are the three-moment (dot–dashed), two-moment with $\alpha$ diagnosed from Eq. (12) (thick solid), two-moment with a fixed $\alpha = 3$ (thick dashed), two-moment with a fixed $\alpha = 0$ (thin dashed), and one-moment (dotted) schemes. — image not reproducible in markdown]

[Figure 8: Particle size distributions from ANA (solid), TM (dot–dashed), DIAG (thick solid), FIX3 (thick dashed), and FIX0 (dotted) at (a) $z = 9.5$ km at 2 min, (b) $z = 7.5$ km at 2 min, and (c) $z = 5.0$ km at 8 min. — image not reproducible in markdown]

---

## 5. Conclusions

Given the increasing importance of bulk microphysics parameterizations in operational weather prediction and research mesoscale models, it is important to have an understanding of the strengths and limitations of various approaches in order to most appropriately develop detailed yet computationally efficient schemes. A diagnostic equation for the spectral shape parameter $\alpha$ of the gamma size distribution, based on the mean-particle size, has been introduced. Comparisons were made between a one-moment, two-moment (with prescribed and diagnosed values of $\alpha$), and a three-moment scheme to study the effect of pure sedimentation on the vertical distribution of mass content, total number concentration, equivalent reflectivity, and mean-particle diameter. Each scheme was evaluated by comparing the computed profiles to those from a highly resolved analytic bin model. A comparison was also made on the accuracy of calculating the moments governing the tendencies of the most important microphysical processes.

The two-moment scheme is superior in all aspects to the one-moment approach. For a two-moment scheme with a fixed $\alpha$, it was shown that setting $\alpha = 3$ is much better than setting $\alpha = 0$, regardless of the precipitating hydrometeor category. On the other hand, there is considerable improvement when $\alpha$ is diagnosed from a monotonically increasing function of the mean-mass diameter, $D_m$. While very simple, this relation is successful because $D_m$ essentially acts as a surrogate for the amount of size sorting that has occurred and increasing values of $\alpha$ control excessive size sorting. By far the best results are from the three-moment scheme, in which $\alpha$ is a prognostic parameter.

It is recognized that the results presented regarding the role of the shape parameter are for sedimenting hydrometeor categories only, for which size sorting plays an important role in narrowing the size spectra. The role of the shape parameter in affecting the cloud droplet spectrum was not discussed. It is well known that the width of the cloud droplet spectrum also plays an important role in the overall prediction of precipitation processes by affecting the rate of autoconversion to rain (e.g., Z85; M98; CP00). Methods to predict or diagnose changes to the dispersion of the cloud droplet spectrum in the bulk scheme are outside the scope of this paper.

In Part II, a three-moment closure approach is proposed. In view of the importance of the added benefit of allowing the shape parameter to vary in a bulk parameterization, a new microphysics scheme, with options for $\alpha$ to be either diagnosed or prognosed, is presented and described in detail.

**Acknowledgments.** We thank the three anonymous reviewers for their suggestions for improving the original manuscript. This research was supported by the Canadian Foundation for Climate and Atmospheric Science.

---

## Appendix: Computation of Sedimentation

The computation of sedimentation follows the standard approach, extended to include $Z_x$. Values for the fall speed parameters $a_x$, $b_x$, and $f_x$ for various hydrometeor categories can be found in F94. The vertical flux convergence terms for $q_x$, $N_{Tx}$, and $Z_x$ of each sedimenting category $x$ are computed using moment-weighted fall velocities. The terminal fall velocity, $V_x(D_x)$ for a single particle of size $D_x$ is given by

$$V_x(D_x) = \gamma a_x D_x^{b_x} \exp(-f_x D_x), \quad (A1)$$

where $\gamma = (\rho_0/\rho)^{1/2}$ is the density correction factor, with $\rho_0$ being the surface air density and $\rho$ the air density.

For each category $x$, the change in $q_x$ due to sedimentation is given by the vertical flux convergence for falling particles

$$\left.\frac{\partial q_x}{\partial t}\right|_\text{SEDI} = \frac{1}{\rho} \frac{\partial(q_x V_{Qx})}{\partial z}, \quad (A2)$$

where the mass-weighted fall speed is given by

$$V_{Qx} = \frac{\displaystyle\int_0^\infty V_x(D_x)\, m_x(D_x)\, N_x(D_x)\, dD_x}{\displaystyle\int_0^\infty m_x(D_x)\, N_x(D_x)\, dD_x} = \gamma a_x \frac{\Gamma(1 + d_x + \alpha_x + b_x)}{\Gamma(1 + d_x + \alpha_x)} \frac{\lambda_x^{(1+d_x+\alpha_x)}}{(\lambda_x + f_x)^{(1+d_x+\alpha_x+b_x)}}. \quad (A3)$$

Similarly, the change in $N_{Tx}$ due to sedimentation is

$$\left.\frac{\partial N_{Tx}}{\partial t}\right|_\text{SEDI} = \frac{\partial(N_{Tx} V_{Nx})}{\partial z}. \quad (A4)$$

Here, the concentration-weighted fall speed, rather than the mass-weighted fall speed, is used:

$$V_{Nx} = \frac{\displaystyle\int_0^\infty V_x(D_x)\, N_x(D_x)\, dD_x}{\displaystyle\int_0^\infty N_x(D_x)\, dD_x} = \gamma a_x \frac{\Gamma(1 + \alpha_x + b_x)}{\Gamma(1 + \alpha_x)} \frac{\lambda_x^{(1+\alpha_x)}}{(\lambda_x + f_x)^{(1+\alpha_x+b_x)}}. \quad (A5)$$

Likewise, changes to $Z_x$ due to sedimentation are calculated by

$$\left.\frac{\partial Z_x}{\partial t}\right|_\text{SEDI} = \frac{\partial(Z_x V_{Zx})}{\partial z}, \quad (A6)$$

where

$$V_{Zx} = \frac{\displaystyle\int_0^\infty D^6 V_x(D_x)\, N_x(D_x)\, dD_x}{\displaystyle\int_0^\infty D^6 N_x(D_x)\, dD_x} = \gamma a_x \frac{\Gamma(1 + d_x + \alpha_x + b_x)}{\Gamma(1 + d_x + \alpha_x)} \frac{\lambda_x^{(1+d_x+\alpha_x)}}{(\lambda_x + f_x)^{(1+d_x+\alpha_x+b_x)}}. \quad (A7)$$

Generally, $V_{Zx}$ is larger than $V_{Qx}$, which in turn is larger than $V_{Nx}$ (except for rain with small values of $\lambda_r$). The existence of different bulk fall velocities for the different moments creates potential numerical problems in a discretized model since, for instance, $Z_x$ can arrive at a lower level before $q_x$ and likewise $q_x$ can arrive before $N_{Tx}$. This must be treated with some care since a level must never contain a nonzero value for one moment and a value of zero for another. It was found that simply setting all values to zero whenever there is zero value in either one or two variables (and adding the mass $q_x$ back to water vapor, $q_v$, to conserve the total mass) handles this problem quite adequately. A small quantity of hydrometeor mass can be lost at the top of a vertical profile, but this is a negligible amount. Another possible solution to this problem is simply to use the same bulk fall velocity for the sedimentation of all of the prognostic variables. However, the use of different fall velocities for the different moments results in important differences to the vertical distribution of the quantities, which is an important benefit of multimoment schemes (discussed in section 2).

Equations (A2), (A4), and (A6) are solved by using a forward-in-time and upstream-in-space finite difference scheme in the paper. The time step is 2.5 s and the vertical grid size is 153 m.

---

## References

Cheng, L., and M. English, 1983: A relationship between hailstone concentration and size. *J. Atmos. Sci.*, **40**, 204–213.

Cohard, J.-M., and J.-P. Pinty, 2000: A comprehensive two-moment warm microphysical bulk scheme. I: Description and tests. *Quart. J. Roy. Meteor. Soc.*, **126**, 1815–1842.

Cotton, W. R., G. J. Tripoli, R. M. Rauber, and E. A. Mulvihill, 1986: Numerical simulation of the effects of varying ice crystal nucleation rates and aggregation processes on orographic snowfall. *J. Climate Appl. Meteor.*, **25**, 1658–1680.

Feingold, G., R. L. Walko, B. Stevens, and W. R. Cotton, 1998: Simulations of marine stratocumulus using a new microphysical parameterization. *Atmos. Res.*, **47–48**, 505–528.

Ferrier, B. S., 1994: A two-moment multiple-phase four-class bulk ice scheme. Part I: Description. *J. Atmos. Sci.*, **51**, 249–280.

——, W.-K. Tao, and J. Simpson, 1995: A two-moment multiple-phase four-class bulk ice scheme. Part II: Simulations of convective storms in different large-scale environments and comparisons with other bulk parameterizations. *J. Atmos. Sci.*, **52**, 1001–1033.

Ivanova, D., D. L. Mitchell, W. P. Arnott, and M. Poellot, 2001: A GCM parameterization for bimodal size spectra and ice mass removal rates in mid-latitude cirrus clouds. *Atmos. Res.*, **59–60**, 89–113.

Kessler, E., 1969: *On the Distribution and Continuity of Water Substance in Atmospheric Circulation*. Meteor. Monogr., No. 32, Amer. Meteor. Soc., 84 pp.

Kong, F., and M. K. Yau, 1997: An explicit approach to microphysics in MC2. *Atmos. Ocean.*, **33**, 257–291.

Lin, Y.-L., R. D. Farley, and H. D. Orville, 1983: Bulk parameterization of the snow field in a cloud model. *J. Climate Appl. Meteor.*, **22**, 1065–1092.

Marshall, J. S., and W. McK. Palmer, 1948: The distribution of raindrops with size. *J. Atmos. Sci.*, **5**, 165–166.

Meyers, M. P., R. L. Walko, J. Y. Harrington, and W. R. Cotton, 1997: New RAMS cloud microphysics. Part II: The two-moment scheme. *Atmos. Res.*, **45**, 3–39.

Milbrandt, J. A., and M. K. Yau, 2005: A multimoment bulk microphysics parameterization. Part II: A proposed three-moment closure and scheme description. *J. Atmos. Sci.*, **62**, 3065–3081.

Murakami, M., 1990: Numerical modeling of dynamical and microphysical evolution of an isolated convective cloud — The 19 July 1981 CCOPE cloud. *J. Meteor. Soc. Japan*, **68**, 107–128.

Sekhon, R. S., and R. C. Srivastava, 1970: Snow spectra and radar reflectivity. *J. Atmos. Sci.*, **27**, 299–307.

Srivastava, R. C., 1978: Parameterization of raindrop size distributions. *J. Atmos. Sci.*, **35**, 108–117.

Uijlenhoet, R., M. Steiner, and J. A. Smith, 2003: Variability of raindrop size distributions in a squall line and implications for radar rainfall estimation. *J. Hydrometeor.*, **4**, 43–61.

Ulbrich, C. W., 1983: Natural variations in the analytical form of the raindrop size distribution. *J. Climate Appl. Meteor.*, **22**, 1764–1775.

Wacker, U., and A. Seifert, 2001: Evolution of rain water profiles resulting from pure sedimentation: Spectral vs. parameterized description. *Atmos. Res.*, **58**, 19–39.

Waldvogel, A., 1974: The $N_0$ jump of raindrop spectra. *J. Atmos. Sci.*, **31**, 1067–1078.

Yu, W., L. Garand, and A. P. Dastoor, 1997: Evaluation of model clouds and radiation at 100 km scale using GOES data. *Tellus*, **49A**, 246–262.

Ziegler, C. L., 1985: Retrieval of thermal and microphysical variables in observed convective storms. Part 1: Model development and preliminary testing. *J. Atmos. Sci.*, **42**, 1497–1509.
