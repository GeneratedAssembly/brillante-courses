---
title: Two-Slit Interference
description: Young's experiment — path difference, the cosine fringe pattern, and fringe spacing you can measure with a ruler. From two slits to N — why more openings sharpen the pattern.
order: 28
section: interference-coherence
---

In 1801 Thomas Young passed light through two narrow slits and saw
stripes. The dark stripes were unexplainable by rays — two openings
should make *more* light, not bands of none — and the wave theory's
victory began there (see [a brief history of
optics](02-a-brief-history-of-optics.md)). The analysis takes one page
and pays for a century of interferometry.

## Path difference makes phase

Two slits a distance $d$ apart illuminate a screen at distance $L$. At
angle $\theta$ from the axis, light from the two slits travels paths
differing by

<Widget type="math" id="com.github.richbai90.optics.two-slit-interference.math-pathdifference" />

Each wavelength of extra path is $2\pi$ of phase ([the phasor
rule](24-wave-equation-phasors.md#harmonic-waves-and-phasors)), so the
interference term of [superposition](27-huygens-superposition.md#fields-add-intensities-do-not)
evaluates to:

<Widget type="math" id="com.github.richbai90.optics.two-slit-interference.math-intensity" />

Maxima where $d\sin\theta = m\lambda$ (paths differ by whole
wavelengths), minima where $d\sin\theta = (m + \tfrac{1}{2})\lambda$.

<Widget type="interactive" id="com.github.richbai90.optics.two-slit-interference.int-fringes" />

<Widget type="quiz" id="com.github.richbai90.optics.two-slit-interference.quiz1" />

## Fringe spacing you can measure with a ruler

On a distant screen ($L \gg d$), adjacent bright fringes sit
$\Delta y = \lambda L/d$ apart. The numbers are laboratory-friendly:
$\lambda = 550$ nm, $d = 0.2$ mm, $L = 2$ m gives fringes
$5.5$ mm apart — visible, measurable, and *linear in wavelength*. Count
fringes to measure $\lambda$; measure $\lambda$ to calibrate a ruler;
the interferometer lessons make the counting precise
([interferometers](30-interferometers.md)).

<Widget type="quiz" id="com.github.richbai90.optics.two-slit-interference.quiz2" />

## From two slits to N

Real apertures have structure, and the superposition machinery extends
without new ideas. $N$ identical slits add $N$ phasors per point: the
peaks stay at the same angles but sharpen as the side lobes cancel —
peak intensity $N^2 I_1$, width shrinking as $1/N$. Push $N$ large with
fine spacing and you have a **diffraction grating**, whose resolving
power is [the grating lesson's](33-gratings.md) subject. Push one slit's
*width* instead and its own diffraction (the single-slit envelope of
[Fraunhofer diffraction](32-fraunhofer-fourier.md)) multiplies the fringe
pattern, deciding how many fringes survive.

<Widget type="quiz" id="com.github.richbai90.optics.two-slit-interference.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.two-slit-interference.card-conditions" />

<Widget type="flashcard" id="com.github.richbai90.optics.two-slit-interference.card-spacing" />

## Recommended reading and viewing

Lecture 15 builds two-beam interference on the way to interferometers;
OpenStax treats Young's experiment and its mathematics in chapter 3.

<Widget type="resource-link" id="com.github.richbai90.optics.two-slit-interference.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.two-slit-interference.link-openstax-young" />

<Widget type="resource-link" id="com.github.richbai90.optics.two-slit-interference.link-openstax-math" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle;
  interferometers; Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §3.2 (Young's Double-Slit
  Interference) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- OpenStax University Physics III, §3.3 (Mathematics of Interference) —
  same book (CC BY 4.0)
- Example verified numerically: $\lambda = 550$ nm, $d = 0.2$ mm,
  $L = 2$ m → $\Delta y = 5.50$ mm; dark fringes at $y = 2.75$ mm,
  $8.25$ mm, …; bright at $m\lambda$ multiples of $5.5$ mm
