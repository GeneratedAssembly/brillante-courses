---
title: Superposition and Huygens' Principle
description: Why fields add but intensities do not, how Huygens' wavelet construction rebuilds reflection and refraction from waves, and what Kirchhoff had to add to make it rigorous.
order: 27
section: interference-coherence
---

Two beams of light can cross and walk away unchanged. A sound wave and a
light wave share a room without arguing. That fact — **superposition** —
is a property of linear wave equations, and it is the single engine
behind every interference effect in this course. Huygens' principle tells
you what to superpose: every point of a wavefront, launching the next
wavefront.

## Fields add; intensities do not

The wave equation of [the phasor lesson](24-wave-equation-phasors.md#the-wave-equation)
is linear: if $U_1$ and $U_2$ are solutions, so is $U_1 + U_2$. The
field at any point is the *vector sum of amplitudes* — phasors added
tip-to-tail — while the intensity, being quadratic, is not the sum of
the separate intensities:

<Widget type="math" id="com.github.richbai90.optics.huygens-superposition.math-superposition" />

The cross term is the whole subject of interference: it can be positive
(brighter than either beam), negative (darker), or zero (beams that carry
no fixed phase relation — the failure mode that
[coherence](31-coherence.md) will explain). Two equal beams in phase
give $4I_0$; opposed, zero; at 120°, back to $I_0$ — the arithmetic
[the phasor lesson](24-wave-equation-phasors.md#harmonic-waves-and-phasors)
already computed.

<Widget type="quiz" id="com.github.richbai90.optics.huygens-superposition.quiz1" />

## Huygens' construction

[The eikonal lesson](23-rays-to-waves.md) treated wavefronts as given.
Huygens (1678) generates them: **every point of a wavefront is a source
of spherical secondary wavelets**, and the wavefront a moment later is
the surface tangent to all of them. Three consequences fall out of the
picture:

- **Light travels straight** in a uniform medium, because the tangent
  envelope of a family of equal spheres is the next parallel wavefront.
- **Reflection** obeys $\theta_r = \theta_i$, because the envelope built
  from wavelets bouncing off the surface touches it symmetrically.
- **Refraction** obeys Snell's law, because wavelets slow down or speed
  up together, tilting the envelope — the wave explanation that
  [reflection and refraction](05-reflection-and-refraction.md) promised
  two centuries later:

<Widget type="stepper" id="com.github.richbai90.optics.huygens-superposition.stepper-snell" />

<Widget type="quiz" id="com.github.richbai90.optics.huygens-superposition.quiz2" />

## Kirchhoff's upgrade

Huygens asserted; Fresnel added interference to the wavelets and won
1818's prize (see [Fresnel zones](18-fresnel-zones.md)); Kirchhoff
finally *derived* the construction from the wave equation itself. The
derived secondary source has an **obliquity factor**
$(1 + \cos\theta)/2$ — full strength forward, half at 90°, zero
backward — which kills Huygens' own embarrassment (why does light not
re-radiate backward?) and turns the construction into a theorem. Every
diffraction argument in this course quietly uses Kirchhoff's factor.

<Widget type="quiz" id="com.github.richbai90.optics.huygens-superposition.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.huygens-superposition.card-superposition" />

<Widget type="flashcard" id="com.github.richbai90.optics.huygens-superposition.card-huygens" />

## Recommended reading and viewing

Lecture 15 pairs this construction with interferometers and Fresnel
diffraction; OpenStax §1.7 states the principle in its textbook form.

<Widget type="resource-link" id="com.github.richbai90.optics.huygens-superposition.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.huygens-superposition.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.huygens-superposition.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle;
  interferometers; Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec15/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.7 (Huygens's Principle) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Wavelet-Snell example verified numerically for $n_1 = 1 \to n_2 = 1.5$
  at $\theta_1 = 45°$: $\theta_2 = 28.1°$
