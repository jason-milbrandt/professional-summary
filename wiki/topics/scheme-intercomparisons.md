# Microphysics Scheme Intercomparisons and Process Studies (Tier 3)

**Summary:** Nine papers where MY2 and/or P3 served as reference schemes in multi-scheme intercomparisons or as the enabling framework for process studies led by other groups. This is the largest Tier 3 cluster and the clearest evidence of the schemes' role as community tools — including the paper (Johnson et al. 2019) that first identified the P3 hail weakness later resolved in [[p3-modern-extensions]].

**Sources:** [[Fan_etal_2017-summary]], [[Han_etal_2019-summary]], [[Johnson_etal_2019-summary]], [[Dawson_etal_2016-summary]], [[Jensen_2017-summary]], [[Morrison_etal_2016-summary]], [[Paukert_etal_2019-summary]], [[Stanford_etal_2019-summary]], [[Morrison_etal_2020-summary]]

**Last updated:** 2026-08-05

---

## The MC3E squall-line intercomparison (Fan et al. 2017; Han et al. 2019)

A two-part, eight-scheme WRF intercomparison of a 20 May 2011 MC3E squall line, holding the dynamical core fixed so differences are attributable to microphysics alone. **Part I** (convective updrafts) found ice-related processes dominate the spread in updraft speed and cold-pool intensity; MY2 was in the "stronger convection" group but underpredicted surface precipitation despite having the largest condensate mass — traced to a low graupel bulk density (400 kg m⁻³) giving small terminal fall speeds, a finding directly related to the density-prediction work in [[ice-phase-modernization]]. **Part II** (stratiform precipitation) found MY2 and P3 produced the largest stratiform rain rates and the most rimed particle content among the eight schemes, with P3 showing a notably realistic transition from unrimed to rimed ice near the melting level — evidence for the property-based design philosophy at the heart of [[p3-scheme]].

## The P3 hail-signature weakness (Johnson et al. 2019)

Using idealized supercell simulations and a polarimetric radar forward operator, this paper compared MY2, NSSL, and two-category P3 on their ability to reproduce the $Z_{DR}$ arc and hail signature — two diagnostic radar features tied to rimed-ice size sorting. It found P3's default rain-slope-parameter bound suppresses the $Z_{DR}$ arc entirely, and its ice-size limiter (the same 2-mm cap discussed in [[p3-modern-extensions]]) prevents large rimed ice from reaching the surface. This is the paper that first identified the hail weakness in P3 — the direct motivation for the triple-moment ice extension (Milbrandt et al. 2021) and the combined liquid-fraction/multi-category hail study (Milbrandt et al. 2025), both covered in [[p3-modern-extensions]].

## Tornado dynamics (Dawson et al. 2016)

A real-data ARPS simulation of the 3 May 1999 Oklahoma City tornadic supercell using single- vs. triple-moment [[milbrandt-yau-scheme]] configurations. Triple-moment microphysics produced larger raindrops, less evaporative cooling, a weaker cold pool, and a substantially stronger, longer-lived tornado-like vortex — with a novel finding that pressure buoyancy inside the vortex itself, not just thermal buoyancy, is a critical contributor to intensification. Milbrandt's contribution was providing the scheme; the tornado-dynamics analysis was led by the Oklahoma group.

## Beyond bulk categories: ISHMAEL and advection theory

**Jensen et al. (2017)** built ISHMAEL, a bulk scheme predicting ice particle *shape* (aspect ratio) evolution — explicitly framed as the natural next step after P3's rime-fraction/density prediction ([[ice-phase-modernization]], [[p3-scheme]]), extending the "predict, don't fix" philosophy to particle habit. **Morrison et al. (2016)** solved a numerical problem underlying every multimoment scheme — how to advect coupled hydrometeor quantities without corrupting derived properties like the shape parameter — and demonstrated the resulting SFVT method using both the [[milbrandt-yau-scheme]] three-moment closure and P3, showing a 10–15% computational speedup with no loss of accuracy. That method is directly used in [[p3-modern-extensions]] (Milbrandt et al. 2021) for advecting the triple-moment ice variable.

## Extending P3: three-moment rain and stochastic microphysics

**Paukert et al. (2019)** developed a three-moment rain representation within P3, adding a predicted DSD shape parameter and a spectral-bin-derived collisional-breakup parameterization; the combination raised agreement with a bin-model benchmark from 4% to over 95%. **Stanford et al. (2019)** implemented a stochastic ice mass-diameter framework within P3, showing that natural variability in ice particle properties — variability P3's continuously evolving particle-property design is uniquely suited to represent — produces cloud radiative forcing variability independent of ice water path, a result relevant to climate-model cloud uncertainty.

## The field-defining review (Morrison et al. 2020)

A 68-page, 16-author commissioned review of the entire microphysics parameterization field (~378 citations), framing two central challenges — representing hydrometeor populations and closing process-level knowledge gaps — and proposing Lagrangian particle methods and Bayesian statistical-physical scheme development as the path forward. The paper cites [[p3-scheme]] and [[milbrandt-yau-scheme]] as examples of schemes that address the population-representation problem through predicted particle properties rather than fixed categories, situating Milbrandt's research program within the field's broader trajectory.

## Position in the arc

This cluster is the community's independent verification and extension of [[milbrandt-yau-scheme]] and [[p3-scheme]] — where the schemes are stress-tested against radar polarimetry, real tornadic storms, alternative representations (shape, three-moment rain, stochastic physics), and held up as exemplars in the field's own self-assessment.

## Related pages

- [[milbrandt-yau-scheme]] — MY2, the community reference scheme in most of these intercomparisons
- [[p3-scheme]] — P3, whose hail weakness this cluster identifies
- [[p3-modern-extensions]] — the direct scheme-development response to Johnson et al. (2019)
- [[ice-phase-modernization]] — the graupel-density work relevant to the MY2 stratiform bias
- [[sip-hiwc-mixed-phase]] — related community evaluation in tropical/HIWC contexts
