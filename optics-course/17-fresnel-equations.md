---
title: The Fresnel Equations
description: How light divides at every interface — amplitude coefficients for s and p polarization, the 4% rule for bare glass, Brewster's angle, and the phase-shifting total reflection that gave Fresnel his rhomb.
order: 17
section: fresnel-optics
---

[Reflection and refraction](05-reflection-and-refraction.md) told you *where*
the two outgoing rays go. It said nothing about *how much* light takes each
path — and every surface you have ever looked through is a beam splitter.
Snell's law is silent on brightness; the wave theory is not. In the 1820s
Augustin-Jean Fresnel (whose wave theory of diffraction we met in
[history](02-a-brief-history-of-optics.md)) wrote down the division of
amplitude at a dielectric interface, and those formulas — the **Fresnel
equations** — now price every reflection in every lens design, every glare
you polarize away, and every decibel of return loss in a fiber link.

## What Snell's law leaves out

A ray hitting a window pane does not choose one path: part of the light
reflects, part refracts, and both laws from the last ray-optics lesson hold
*simultaneously* — the reflected ray at $\theta_r = \theta_i$, the
transmitted ray at Snell's angle. What the ray model cannot say is how the
beam's power splits between them. The answer depends on three things: the
two indices $n_1$, $n_2$ (see
[light in matter](04-light-in-matter.md)), the angle of incidence, and —
decisively — the direction of the electric field oscillation relative to the
plane of incidence.

To get the split you must treat light as a transverse electromagnetic wave
whose fields satisfy boundary conditions at the interface: tangential $E$
continuous, tangential $H$ continuous. The full derivation is one of the
payoffs of [Maxwell's equations](25-maxwell-em-waves.md); this lesson takes
the results and learns to *read* them — which is what an optical engineer
actually spends their day doing.

## Two polarizations

The **plane of incidence** is the plane containing the incident ray and the
surface normal. Reflection and refraction never push light out of it, so an
arbitrary linear polarization splits cleanly into two independent cases:

- **s-polarization** (from German *senkrecht*, perpendicular): $\vec{E}$
  perpendicular to the plane of incidence.
- **p-polarization**: $\vec{E}$ parallel to the plane of incidence.

Every Fresnel formula comes in an s pair and a p pair, and the two behave
differently at oblique angles. ([Polarization](26-polarization-poynting.md)
gives the full language; circular and elliptical states are built from
exactly this s/p split.)

## The amplitude coefficients

Matching fields across the interface yields the reflected *amplitude* per
unit incident amplitude:

<Widget type="math" id="com.github.richbai90.optics.fresnel-equations.math-amplitudes" />

Two conventions worth flagging. First, sign conventions differ between
texts (this one follows the Born-and-Wolf/MacCorti–Sheppard convention
where $r_s$ changes sign at normal incidence but $r_p$ does not); physics
lives in $|r|^2$ and in *relative* phase shifts, which are convention-free.
Second, $\theta_t$ is never independent — Snell's law ties it to $\theta_i$ —
so each coefficient is really a function of the incidence angle and the
index ratio alone.

## Reflectance and the 4% rule

Power follows amplitude. The **reflectance** is $R = |r|^2$ (the fraction of
incident power sent back), and energy conservation forces the transmitted
fraction to be $T = 1 - R$. At normal incidence both polarizations collapse
into one beautifully simple formula:

<Widget type="math" id="com.github.richbai90.optics.fresnel-equations.math-normal" />

Memorize the consequences for air ($n_1 \approx 1$):

- **Glass, $n_2 = 1.5$:** $R_0 = (0.5/2.5)^2 = 4\%$ per surface.
- **Water, $n_2 = 1.33$:** $R_0 \approx 2\%$.
- **Diamond, $n_2 = 2.42$:** $R_0 \approx 17\%$ — one reason a cut stone
  blazes, and one reason diamond is hard to photograph through.

Four percent per surface does not sound like much until you count surfaces:
a six-element phone camera has twelve air–glass interfaces, and $0.96^{12}
\approx 0.61$ — 39% of your light lost to reflections that carry no image,
only glare. This is why coated lenses look purple, and why
[chromatic aberration and optical design](20-chromatic-spherical-coma.md)
begins with a coating recipe.

How the split evolves with angle is worth seeing once, carefully:

<Widget type="plot" id="com.github.richbai90.optics.fresnel-equations.plot-reflectance" />

<Widget type="interactive" id="com.github.richbai90.optics.fresnel-equations.int-rp" />

$R_s$ climbs monotonically to 100% at grazing incidence. $R_p$ does
something stranger: it dips to *zero* partway up.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-equations.quiz1" />

## Brewster's angle

The dip is no accident. $r_p = 0$ exactly when the reflected and refracted
rays would be perpendicular, which fixes one special angle:

<Widget type="math" id="com.github.richbai90.optics.fresnel-equations.math-brewster" />

For air–glass, $\theta_B = \arctan 1.5 \approx 56.3°$; for air–water,
$\approx 53.1°$. Light reflected off water or a wet road near that angle is
**purely s-polarized** — which is why polarized sunglasses work: their
transmission axis blocks the horizontal interface's favorite polarization
and kills the glare while passing the scene underneath.

<Widget type="stepper" id="com.github.richbai90.optics.fresnel-equations.stepper-brewster" />

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-equations.quiz2" />

## Beyond the critical angle

Past the [critical angle](05-reflection-and-refraction.md#total-internal-reflection)
of a denser-to-rarer interface, $\sin\theta_t$ would exceed 1, $\cos\theta_t$
turns imaginary, and the coefficients become complex numbers of unit
magnitude: $|r_s| = |r_p| = 1$. Total reflection — but not total *absence of
field*: an **evanescent wave** trails a fraction of a wavelength outside the
glass (the basis of TIRF microscopy and fiber sensing), and the reflection
carries a *phase*:

<Widget type="math" id="com.github.richbai90.optics.fresnel-equations.math-tirphase" />

The two phase shifts $\delta_s$ and $\delta_p$ are unequal, so total
reflection can turn linear into circular polarization without any birefringent
crystal. Fresnel's own invention for doing it — a paralleloglass block that
delivers two TIRs at angles chosen so $\delta_p - \delta_s = 90°$ — is the
**Fresnel rhomb**, a quarter-wave plate made of nothing but glass, still
used where coatings and crystals fail.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-equations.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-equations.card-coefficients" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-equations.card-brewster" />

## Recommended reading and viewing

The lecture notes derive the coefficients from the field boundary conditions;
the OpenStax section covers Brewster's angle and polarization-by-reflection
qualitatively.

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-equations.link-lecture-14" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-equations.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-equations.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 — Maxwell's equations,
  polarization, Poynting's
  vector](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-14-maxwells-equations-polarization-poyntings-vector/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec14/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.8 (Polarization) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
