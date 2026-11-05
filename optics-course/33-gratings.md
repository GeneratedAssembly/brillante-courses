---
title: Diffraction Gratings
description: Many slits, sharp orders — the grating equation, resolving power, and the amplitude-versus-phase design choice that decides where the light goes. The workhorse of spectroscopy.
order: 33
section: diffraction-fourier-optics
---

[Two slits](28-two-slit-interference.md) made fringes; make it ten
thousand slits and the fringes become instruments. A **diffraction
grating** replaces the cosine blur with needle-sharp orders at angles
that encode wavelength — the dispersion engine inside every
spectrometer, and the flat glass or metal surface doing the work of a
prism.

## The grating equation

N slits of spacing $d$ reinforce the [two-slit](28-two-slit-interference.md#path-difference-makes-phase)
condition: bright orders survive where every pair of neighbors differs
by a whole wavelength:

<Widget type="math" id="com.github.richbai90.optics.gratings.math-grating" />

Between orders, the $N$ contributions cancel pairwise — near-totally —
so the peaks sharpen as $1/N$ in angle and tower as $N^2$ in intensity
([the N-slit arithmetic](28-two-slit-interference.md#from-two-slits-to-n)).
A 600 lines/mm grating at 550 nm sends order $m = 1$ to
$\sin\theta = 0.33$ (19.3°), order 2 to 41.3°, and supports only
$m \le 3$ orders at all ($m_{max} = d/\lambda \approx 3$): orders run
out when $\sin\theta$ would exceed 1.

<Widget type="interactive" id="com.github.richbai90.optics.gratings.int-orders" />

<Widget type="plot" id="com.github.richbai90.optics.gratings.plot-orders" />

<Widget type="quiz" id="com.github.richbai90.optics.gratings.quiz1" />

## Resolving power

How close two wavelengths can sit and still separate into distinct
orders is set by the number of illuminated grooves:

<Widget type="math" id="com.github.richbai90.optics.gratings.math-resolving" />

The derivation is one Rayleigh argument: two wavelengths are resolved
when one's maximum falls on the other's first zero, and the $m$-th
order peak's angular width is $\lambda/(Nd\cos\theta)$. A 10 mm beam on
a 600 lines/mm grating illuminates $N = 6000$ grooves: first-order
resolving power $R = 6000$, separating 550.000 nm from 550.092 nm —
ruler-grade spectroscopy from a piece of glass. Resolution scales with
$N$ and with order: a high-order (echelle) grating trades away free
orders to buy resolution.

<Widget type="quiz" id="com.github.richbai90.optics.gratings.quiz2" />

## Amplitude, phase, sinusoidal, binary

Where the light *goes* among the orders is a design choice, made in the
aperture function. The [Fourier-transform
view](32-fraunhofer-fourier.md#apertures-are-fourier-transforms) prices
each profile: for a 50%-duty binary grating,

- **amplitude grating** (opaque/transparent): 25% of the power sits
  unused in the zero order, and each first order carries 10.1%;
- **binary phase grating** (0/π depth): the zero order cancels exactly,
  and each first order carries 40.5% — 81% of the light working;
- **blazed phase grating**: shape each groove's phase ramp so the
  orders' phases add in *one chosen direction* — commercial gratings
  routinely send 80%+ of the light into a single order.

That last step — engineering the phase profile to route light — is the
founding idea of diffractive optics proper; the companion
diffractive-optics course (its binary-grating-efficiency lesson) treats
it with full electromagnetic rigor.

<Widget type="quiz" id="com.github.richbai90.optics.gratings.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.gratings.card-equation" />

<Widget type="flashcard" id="com.github.richbai90.optics.gratings.card-resolving" />

## Recommended reading and viewing

Lecture 16 covers gratings in all four flavors — amplitude and phase,
sinusoidal and binary.

<Widget type="resource-link" id="com.github.richbai90.optics.gratings.link-lecture-16" />

<Widget type="resource-link" id="com.github.richbai90.optics.gratings.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.gratings.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 16 — gratings: amplitude
  and phase, sinusoidal and
  binary](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-16-gratings-amplitude-and-phase-sinusoidal-and-binary/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 16 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec16/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §4.5 (Diffraction Gratings) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: 600 lines/mm grating (d = 1.667 µm), λ = 550 nm:
  order 1 at 19.27°, order 2 at 41.30°, $m_{max} = 3$; R = mN = 6000 →
  Δλ = 0.092 nm; binary 50% duty efficiencies: amplitude 25% (zero) /
  10.1% (each first order), phase 0% (zero) / 40.5% (each first order)
