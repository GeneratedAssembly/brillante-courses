---
title: Polarization States and Polarizers
description: The two transverse components and their phase offset build every polarization state — linear, circular, elliptical — and polarizers, Malus's law, and Fresnel's rhomb turn the states into engineering.
order: 26
section: wave-optics-foundations
---

Maxwell forced light's electric field into the plane perpendicular to
travel ([the wave equation](24-wave-equation-phasors.md#plane-waves-in-three-dimensions))
but left its *direction* inside that plane free. That freedom is
**polarization** — a second, invisible channel of information carried by
every beam, the one sunglasses exploit, liquid crystals switch, and
optical fibers scramble.

## Building states from s and p

Fix a propagation direction and call the two transverse axes $x$ and
$y$. A general monochromatic field superposes the two with a relative
phase $\delta$:

<Widget type="math" id="com.github.richbai90.optics.polarization-poynting.math-states" />

The tip of the electric vector traces a curve in the transverse plane,
and $\delta$ alone chooses its shape:

- $\delta = 0$ or $\pi$: a straight line — **linear polarization**
  (the $E_x$, $E_y$ components rise and fall together or in opposition).
- $\delta = \pm\pi/2$ with equal amplitudes: a circle — **circular
  polarization**; the sign of $\delta$ sets the handedness as seen
  looking into the beam.
- anything else: an **ellipse** — the generic state, degenerating to the
  two special cases above.

<Widget type="plot" id="com.github.richbai90.optics.polarization-poynting.plot-ellipses" />

[The Fresnel lesson](17-fresnel-equations.md#two-polarizations)
established that any interface splits an incoming field cleanly into its
s and p parts — which is why these two axes, not any others, are the
alphabet of the subject.

<Widget type="quiz" id="com.github.richbai90.optics.polarization-poynting.quiz1" />

## Polarizers and Malus's law

A **linear polarizer** passes one transverse axis and rejects the other
— by dichroic absorption (sheet polarizers), by geometry (wire-grid),
or by the crystal anisotropy of the next section. Unpolarized light,
its direction randomized every few femtoseconds, loses half its
intensity; polarized light obeys **Malus's law**:

<Widget type="math" id="com.github.richbai90.optics.polarization-poynting.math-malus" />

Two polarizers at 45° pass a quarter of the light; two at 90° pass
nothing. Insert a *third* between crossed polarizers, at 45°, and light
returns — $\tfrac{1}{2}\times\tfrac{1}{2} = 25\%$ — because the middle
polarizer re-projects the rejected component onto the final axis.
Polarization is a two-state system you can rotate, and projections
compose exactly as the law says.

<Widget type="interactive" id="com.github.richbai90.optics.polarization-poynting.int-malus" />

<Widget type="quiz" id="com.github.richbai90.optics.polarization-poynting.quiz2" />

## Making circular light: the Fresnel rhomb

A quarter of a turn of phase between $E_x$ and $E_y$ converts linear to
circular light. Birefringent wave plates do it with crystal anisotropy
([wave plates and polarization
effects](40-polarization-wave-plates.md)); Fresnel did it in 1817 with
nothing but total internal reflection. Recall from
[the Fresnel equations](17-fresnel-equations.md#beyond-the-critical-angle)
that TIR retards p relative to s. In glass of $n = 1.5$, one internal
reflection at $\theta \approx 51.7°$ retards by $\approx 45°$ — the
maximum the geometry allows — so **two** reflections in a glass rhomb
deliver $90°$: linear in, circular out, with no coating and no crystal.

<Widget type="math" id="com.github.richbai90.optics.polarization-poynting.math-rhomb" />

Fresnel's rhomb is broadband (no thickness resonance to drift) and
achromatic (the retardance is geometry, not material dispersion) — still
the quarter-wave device of choice where coatings fail.

<Widget type="quiz" id="com.github.richbai90.optics.polarization-poynting.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.polarization-poynting.card-states" />

<Widget type="flashcard" id="com.github.richbai90.optics.polarization-poynting.card-malus" />

## Recommended reading and viewing

Lecture 14 pairs polarization with Maxwell's equations; OpenStax
§1.8 covers states, polarizers, and polarization by reflection
qualitatively.

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-poynting.link-lecture-14" />

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-poynting.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-poynting.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 — Maxwell's equations;
  polarization; Poynting's
  vector](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-14-maxwells-equations-polarization-poyntings-vector/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 14 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec14/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.8 (Polarization) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Rhomb numbers verified by direct computation of the TIR phases
  ($\tan(\delta_s/2) = -\sqrt{n^2\sin^2\theta-1}/(n\cos\theta)$,
  $\tan(\delta_p/2) = -n\sqrt{n^2\sin^2\theta-1}/\cos\theta$): maximum
  retardance $45.2°$ at $\theta = 51.7°$ for $n = 1.5$; two bounces give
  $90.5°$
- Three-polarizer arithmetic: $I_0 \to I_0/2 \to I_0/4$ for axes at
  $0°/45°/90°$
