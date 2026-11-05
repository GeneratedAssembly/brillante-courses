---
title: Maxwell's Equations and Light
description: The full derivation at last — Maxwell's equations, the electromagnetic wave they force into existence, dielectric index, Poynting's energy bookkeeping, and the boundary-condition argument behind the Fresnel coefficients.
order: 25
section: wave-optics-foundations
---

[The Fresnel equations](17-fresnel-equations.md) were used without being
derived; their price list for reflection waited on this lesson. Maxwell's
equations are the derivation — of the wave equation, of light's speed,
of its transversality, of its energy, and of every coefficient at every
interface. Four vector equations compress all of classical
electromagnetism; light is their most famous consequence.

## The four equations in vacuum

<Widget type="math" id="com.github.richbai90.optics.maxwell-em-waves.math-maxwell" />

Read them physically: charges source divergence of $\mathbf{E}$; no
magnetic charge exists; a changing $\mathbf{B}$ curls $\mathbf{E}$
(Faraday); and a current *or* a changing $\mathbf{E}$ curls $\mathbf{B}$
(Ampère–Maxwell). In vacuum the source terms vanish, and the equations
feed each other: a changing $\mathbf{E}$ makes a $\mathbf{B}$, whose
change remakes the $\mathbf{E}$. The fields chase each other out into
empty space — that chase *is* the wave.

## The wave equation, and what falls out for free

Take the curl of Faraday's law, substitute the Ampère–Maxwell law, and
the fields decouple:

<Widget type="math" id="com.github.richbai90.optics.maxwell-em-waves.math-c" />

Each component obeys the [wave
equation](24-wave-equation-phasors.md#the-wave-equation) with speed
$c = 1/\sqrt{\mu_0\varepsilon_0}$ — which evaluates to
$299{,}792{,}458$ m/s, the measured speed of light, to the precision of
the constants. Light is an electromagnetic wave; the 19th century's two
threads — optics and electricity — joined here.

Two more facts come free. **Transversality**: $\nabla\cdot\mathbf{E} = 0$
(in the source-free wave) forces $\mathbf{k}\cdot\mathbf{E} = 0$, so the
field oscillates perpendicular to its travel, and
$\mathbf{B} = \hat{\mathbf{k}}\times\mathbf{E}/c$ with
$|\mathbf{E}| = c|\mathbf{B}|$. And **independence of polarizations**:
the wave equation does not care which transverse direction $\mathbf{E}$
takes — the s/p split of [the Fresnel
lesson](17-fresnel-equations.md#two-polarizations) is built into
Maxwell's own structure.

<Widget type="quiz" id="com.github.richbai90.optics.maxwell-em-waves.quiz1" />

## Light in matter: the index from ε

In a linear dielectric, $\mathbf{D} = \varepsilon\mathbf{E} =
\varepsilon_r\varepsilon_0\mathbf{E}$ and the wave slows to $c/n$ with

<Widget type="math" id="com.github.richbai90.optics.maxwell-em-waves.math-index" />

For water, $n = 1.33$ means $\varepsilon_r = n^2 \approx 1.77$ — while
the *static* permittivity of water is about 80. The discrepancy is
physical, not an error: dipoles need time to reorient. At optical
frequencies ($10^{15}$ Hz) only the fast electronic polarizations
respond; the sluggish molecular rotation that makes water's static
$\varepsilon_r$ enormous sits this oscillation out. The frequency
dependence of $\varepsilon_r$ **is** dispersion — the same mechanism
behind [prisms](06-prisms-and-dispersion.md) and
[chromatic aberration](20-chromatic-spherical-coma.md#chromatic-aberration):
near an atomic resonance $\varepsilon_r$ turns over, and $n$ falls with
frequency (normal dispersion) or rises (anomalous, near absorption).

<Widget type="quiz" id="com.github.richbai90.optics.maxwell-em-waves.quiz2" />

## Energy: the Poynting vector

Electromagnetic fields carry energy with flux density

<Widget type="math" id="com.github.richbai90.optics.maxwell-em-waves.math-poynting" />

Optics measures the time average — the **irradiance**. For a harmonic
plane wave, $\langle S \rangle = \tfrac{1}{2}c\varepsilon_0 E_0^2$.
Sunlight on the ground, about $1000\ \mathrm{W/m^2}$, corresponds to
$E_0 \approx 870\ \mathrm{V/m}$ and a magnetic amplitude
$B_0 \approx 2.9\ \mu\mathrm{T}$. A wave's electric field of a few
hundred volts per meter is ordinary; it is also, in a precise sense, the
only reason a solar panel works.

<Widget type="quiz" id="com.github.richbai90.optics.maxwell-em-waves.quiz3" />

## The Fresnel coefficients, derived

Boundary conditions close the loop. At an interface (no surface charge
or current): tangential $\mathbf{E}$ continuous, tangential
$\mathbf{H}$ continuous, and the normal components of $\mathbf{D}$ and
$\mathbf{B}$ continuous. Matching the phase along the interface forces
$k_{1\parallel} = k_{2\parallel}$ — Snell again — and matching the field
amplitudes prices the reflection:

<Widget type="stepper" id="com.github.richbai90.optics.maxwell-em-waves.stepper-fresnel" />

At oblique incidence the same two continuity equations, applied to the
s and p geometries separately, produce the four amplitude coefficients
[the Fresnel lesson](17-fresnel-equations.md#the-amplitude-coefficients)
tabulated — and with them Brewster's angle and the TIR phases that
[Fresnel zones](18-fresnel-zones.md) and
[polarization](26-polarization-poynting.md) exploit. Nothing in optics
is arbitrated by convention; the interface obeys Maxwell.

<Widget type="flashcard" id="com.github.richbai90.optics.maxwell-em-waves.card-maxwell" />

<Widget type="flashcard" id="com.github.richbai90.optics.maxwell-em-waves.card-poynting" />

## Recommended reading and viewing

Lecture 13 introduces the electromagnetic program; lecture 14 executes
it — Maxwell's equations, polarization, and Poynting's vector together.

<Widget type="resource-link" id="com.github.richbai90.optics.maxwell-em-waves.link-lecture-13" />

<Widget type="resource-link" id="com.github.richbai90.optics.maxwell-em-waves.link-lecture-14" />

<Widget type="resource-link" id="com.github.richbai90.optics.maxwell-em-waves.link-notes" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 13 — 3D wave phenomena;
  introduction to
  electromagnetics](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-13-3d-wave-phenomena-introduction-to-electromagnetics/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 — Maxwell's equations;
  polarization; Poynting's
  vector](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-14-maxwells-equations-polarization-poyntings-vector/)
  (CC BY-NC-SA 4.0) — the Fresnel derivation from boundary conditions
- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec14/)
  (CC BY-NC-SA 4.0)
- Constants: $c = 1/\sqrt{\mu_0\varepsilon_0} = 299{,}792{,}458$ m/s;
  $\tfrac12 c\varepsilon_0 = 1.327\times10^{-3}$ W/m² per (V/m)², so
  $1000\ \mathrm{W/m^2} \leftrightarrow E_0 = 868$ V/m,
  $B_0 = 2.9\ \mu\mathrm{T}$
- Water permittivity: static $\varepsilon_r \approx 80$ (rotational
  polarization) versus optical $n^2 \approx 1.77$ — standard dielectric
  relaxation physics
