---
title: Fresnel Diffraction and the Zone Plate
description: The near field of edges and apertures — soft shadow boundaries, the Cornu spiral that computes them, and the ring-plate that focuses like a lens with its chromatism reversed.
order: 19
section: fresnel-optics
---

With [Fresnel zones](18-fresnel-zones.md) you can now answer the question
ray optics refuses: what does a shadow actually look like? In the near
field ($N_F \gtrsim 1$) every obstacle and opening reorganizes the zones
that reach each point, and the answer is a pattern of fringes both *inside*
and *outside* the geometric shadow. This lesson is the general method plus
its most useful invention: a lens with no glass in it.

## The edge of shadow is not sharp

Take a straight edge — half of an opaque screen — and look at the intensity
across the geometric shadow boundary. Far inside, zones are blocked and the
field vanishes; far outside, the wavefront is essentially complete and the
intensity is the free value. But *near the edge* the open wavefront is a
partial, lopsided sum: the intensity oscillates — overshooting to about
1.4× the free value just outside the boundary, and ringing faintly inside.
Exactly **at** the geometric edge the two halves of the wavefront cancel to
one-sided symmetry, and the intensity is half the free value. A ray diagram
draws a step function; Fresnel diffraction draws a fringe pattern.

## The Cornu spiral

For straight edges and slits the zone sum can be evaluated in closed shape.
Write the wavefront coordinate $u$ so that the phase at $P$ across it grows
like $u^2$; the contribution of the segment from $-t$ to $+t$ is the pair of
**Fresnel integrals**

$$C(t) = \int_0^t \cos\!\Big(\tfrac{\pi u^2}{2}\Big)\,du, \qquad
S(t) = \int_0^t \sin\!\Big(\tfrac{\pi u^2}{2}\Big)\,du,$$

and the curve $(C(t), S(t))$ is the **Cornu spiral**:

<Widget type="plot" id="com.github.richbai90.optics.fresnel-diffraction.plot-cornu" />

Read it as a phasor odometer. The curve spirals into $(\tfrac12,
\tfrac12)$ as $t \to +\infty$ and into $(-\tfrac12, -\tfrac12)$ as
$t \to -\infty$; the contribution of *any* open stretch of the wavefront is
the chord between the two corresponding points of the spiral, and intensity
is the squared chord length. For the straight edge, one end of the chord is
pinned at the far limit $(\tfrac12, \tfrac12)$ and the other slides around
the spiral — which is exactly why the intensity overshoots and rings: the
chord length oscillates before settling. Every straight-edge number quoted
above is one chord measurement on this curve.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-diffraction.quiz1" />

## One aperture, many focal lengths

Return to the circular aperture, now letting the *distance* vary instead of
the radius. The on-axis intensity of [Lesson 18](18-fresnel-zones.md) was
$4\sin^2(\pi N_F/2)$ in units of the free value, with $N_F = a^2/(\lambda
z)$. Define $f \equiv a^2/\lambda$ — the distance at which exactly one
Fresnel zone fits — and sweep $z$:

<Widget type="interactive" id="com.github.richbai90.optics.fresnel-diffraction.int-aperture" />

The axis lights up not at one distance but at $z = f, f/3, f/5, \dots$ —
every distance at which an odd number of zones fits. A bare aperture is a
mediocre lens with several focal lengths. Make it a good one:

<Widget type="stepper" id="com.github.richbai90.optics.fresnel-diffraction.stepper-zoneplate" />

<Widget type="math" id="com.github.richbai90.optics.fresnel-diffraction.math-zoneplate" />

The **zone plate** is a mask of concentric rings, open where the odd zones
are, opaque where the even ones are. At $f$ every open zone arrives in
phase, the alternating sum becomes a plain sum, and the on-axis intensity —
proportional to the square of the number of zones — is genuinely bright.
Fresnel presented these plates in the same 1818 memoir that cost Poisson
his argument: a lens that works by interference alone.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-diffraction.quiz2" />

## Diffractive power versus refractive power

A zone plate has optical *power*, and it behaves like a lens in every
imaging sense — with two reversals that matter to designers:

- **Chromatism runs backwards.** A glass lens's power grows with
  $n(\lambda)$, and [Cauchy dispersion](04-light-in-matter.md) makes blue
  refract harder: blue focuses *short*. A zone plate's focal length is
  $f = \rho_1^2/\lambda$: longer wavelengths diffract harder, so **red
  focuses short and blue long** — the exact opposite of glass, and far
  stronger (the "Abbe number" of a diffractive element is about $-3.4$,
  where common crown glasses sit near $+60$). Pairing one weak diffractive
  ring plate with strong glass cancels both colors' error: that hybrid is
  inside your phone camera, where it also saves millimeters of thickness
  and weight.
- **Power is shared among orders.** The plate focuses at $f, f/3, f/5, \dots$
  and defocuses at $f/2, f/4, \dots$; a binary amplitude plate sends only
  about $1/\pi^2 \approx 10\%$ of the light into the first focus. Blazed
  *phase* zone plates — rings that shift phase instead of blocking — push
  most light into one order and are the standard tool when refraction is
  impossible: **X-ray microscopes** focus with zone plates because at
  X-ray wavelengths every material has $n \approx 1$ and no lens can be
  ground.

Zone plates are also the one-dimensional cousin of the diffraction grating
([gratings: amplitude and phase](33-gratings.md)) — the same interference
lattice, rolled into rings.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-diffraction.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-diffraction.card-cornu" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-diffraction.card-zoneplate" />

## Recommended reading and viewing

Lecture 15 covers the straight-edge problem and the zone construction; the
notes PDF has the worked geometry.

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-notes" />

## Assignments

Two MIT problem sets carry the wave mathematics this section leans on:
Homework 4's complex-arithmetic, phasor, and superposition problems (its
Hamiltonian GRIN opening is the aberrations-and-design material), and
Homework 5's interference patterns between plane, spherical, and
counter-propagating waves — the physics behind the alternating zone sum.

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-hw4" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-hw4-sol" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-hw5" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-diffraction.link-hw5-sol" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle,
  interferometers, Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec15/)
  (CC BY-NC-SA 4.0)
- Fresnel diffraction itself is outside OpenStax UP III ch 1–4; the zone
  plate and Cornu-spiral treatment follows the standard wave-optics
  literature (Hecht, *Optics*; Goodman, *Introduction to Fourier Optics*),
  linked from [references](01-references.md).
