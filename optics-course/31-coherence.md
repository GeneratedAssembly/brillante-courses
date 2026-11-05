---
title: Coherence
description: Why fringes fade — the finite memory of light. Temporal coherence as bandwidth, spatial coherence as source size, and coherence length as the budget every interferometer must live within.
order: 31
section: interference-coherence
---

Every interference argument so far assumed light with a *memory*: two
beams whose phase relationship holds while they wander and recombine.
Real light forgets. A lamp's atoms radiate in short, uncorrelated
bursts; even a laser's phase wanders on long timescales. **Coherence**
names the memory a beam actually has, and it is the budget within which
every interferometer, holography setup, and coherent-imaging system must
live.

## Temporal coherence: bandwidth is forgetfulness

No source is perfectly monochromatic. A spectral spread $\Delta\lambda$
shortens the wave trains to a coherence time $\tau_c$, and the two are
locked together:

<Widget type="math" id="com.github.richbai90.optics.coherence.math-temporal" />

The numbers span fourteen orders of magnitude. White light
($\Delta\lambda \approx 300$ nm): coherence length $L_c \approx 1\
\mu$m, forgotten in 3 femtoseconds. A filtered LED
($\Delta\lambda = 30$ nm): $L_c \approx 10\ \mu$m. A good single-mode
laser ($\Delta\lambda \sim 0.001$ nm at 550 nm):
$L_c \approx 0.3$ m, and specialized designs reach kilometers. Michelson
arms longer than $L_c$ see fringes wash out, because the recombining
waves no longer remember being siblings:

<Widget type="plot" id="com.github.richbai90.optics.coherence.plot-visibility" />

<Widget type="quiz" id="com.github.richbai90.optics.coherence.quiz1" />

## Spatial coherence: a source has width

Two separate laser pointers aimed at a wall produce two bright spots and
no fringes: nothing enforces a phase relation *between* independent
sources. Interference requires the two beams to descend from *one*
wavefront — which is why Young used a single source feeding both slits.
Spatial coherence quantifies how far apart two points on a wavefront can
sit and still behave like one source: widen the emitting region, and the
tolerance shrinks. The rule of thumb behind the Michelson *stellar*
interferometer: fringes from two points of a source of angular size
$\theta_s$ survive only out to transverse separations of order
$\lambda/\theta_s$ — so measuring how far the fringes survive measures
the star's diameter.

<Widget type="quiz" id="com.github.richbai90.optics.coherence.quiz2" />

## Coherence as a design parameter

Treat $L_c$ as a budget. A Michelson test of a 30 cm optic needs laser
light; a soap-film color needs only femtoseconds of memory and gets it
from sunlight. Holography demands path differences under $L_c$ for the
whole scene — the reason holography and the laser grew up together.
Coherence has costs, too: the speckle that fuzzes laser-lit surfaces and
the interference artifacts of coherent imaging
([coherent versus incoherent imaging](37-coherent-incoherent-imaging.md))
are coherence you did not want. Choosing the bandwidth is choosing which
phenomena you own.

<Widget type="quiz" id="com.github.richbai90.optics.coherence.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.coherence.card-temporal" />

<Widget type="flashcard" id="com.github.richbai90.optics.coherence.card-spatial" />

## Recommended reading and viewing

Lecture 15 ties coherence to the interferometers that need it; OpenStax
§3.6 provides the Michelson context.

<Widget type="resource-link" id="com.github.richbai90.optics.coherence.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.coherence.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.coherence.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle;
  interferometers; Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0) — coherence of real sources in the interferometric
  context
- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec15/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §3.6 (The Michelson Interferometer) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: $L_c = \lambda^2/\Delta\lambda$ at
  $\lambda = 550$ nm: 1.0 µm (white, Δλ = 300 nm), 10.1 µm (LED,
  Δλ = 30 nm), 0.30 m (Δλ = 0.001 nm); τ_c = L_c/c
- The stellar-interferometer scale λ/θ_s follows the van Cittert–Zernike
  theorem (standard coherence theory)
