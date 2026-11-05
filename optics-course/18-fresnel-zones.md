---
title: Fresnel Zones and the Poisson Spot
description: Half-period zones turn a whole wavefront into an alternating sum — why an unobstructed wave is worth half its first zone, how the Fresnel number marks the near field, and the bright spot at the center of a round shadow.
order: 18
section: fresnel-optics
---

The [Fresnel equations](17-fresnel-equations.md) settled how much light an
interface turns back. The harder question — the one Augustin-Jean Fresnel
won the 1818 prize for — is what light does when *no* interface is present
and an obstacle merely clips the beam. The ray model predicts a crisp
shadow with a crisp edge. Everything from laser speckle to the Airy disk
says otherwise, and the device that says it first is a counting trick:
divide the open wavefront into **half-period zones** and add them up.

## Fresnel's addition to Huygens

[Huygens' principle](03-the-propagation-of-light.md#wavefronts-and-rays)
already said every point of a wavefront launches a secondary wavelet.
Fresnel's addition, in one sentence: **the wavelets interfere.** The field
at an observation point $P$ is not the sum of wavelet *intensities* but the
phasor sum of wavelet *amplitudes* — each arriving with the phase its path
length assigns it. Fresnel's three working assumptions:

- a wavelet's amplitude falls off as $1/r$ with distance to $P$;
- wavelets favor the forward direction (an *obliquity factor* — strong
  forward, vanishing backward; Kirchhoff's formal theory, met later in
  [Huygens' principle and superposition](27-huygens-superposition.md),
  earns this factor rather than assuming it);
- wavelets of the same frequency add as rotating phasors (the machinery of
  [wave equation and phasors](24-wave-equation-phasors.md)).

With those, a whole wavefront becomes a computable sum. The trick that makes
the sum tractable is to group its terms before evaluating any of them.

## Half-period zones

Surround $P$ with spheres of radii $d + \lambda/2$, $d + \lambda$,
$d + 3\lambda/2$, … (for a plane wavefront at distance $d$). Each sphere
cuts the wavefront in a circle, and the wavefront becomes a set of
concentric **Fresnel zones** — annuli whose far edges are a half wavelength
farther from $P$ than their near edges.

<Widget type="math" id="com.github.richbai90.optics.fresnel-zones.math-zoneradii" />

Two facts make the construction magical:

- Every zone sweeps the *same* $\pi$ of phase across itself, so the net
  contribution of zone $m$ is a phasor pointing opposite to zone $m-1$'s.
- The annuli all have the same area: zone $m$ spans
  $\pi r_m^2 - \pi r_{m-1}^2 = \pi\lambda d$, independent of $m$. Equal
  area, nearly equal distance, nearly equal obliquity — so all zone
  contributions have nearly equal size $a$ and strictly alternating sign:

$$A \;=\; a_1 - a_2 + a_3 - a_4 + \cdots \;\approx\; \tfrac{a_1}{2}.$$

An *unobstructed* wavefront at $P$ is worth **half the first zone**. That
sounds like a paradox until you run the aperture experiment below: block
zone 1 and the rest sum to $+\tfrac{a_1}{2}$ again; open exactly one zone
and you collect the full $a_1$ — *four times* the free intensity, from less
aperture.

<Widget type="interactive" id="com.github.richbai90.optics.fresnel-zones.int-zones" />

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-zones.quiz1" />

## The Fresnel number

How many zones an aperture opens is one number:

<Widget type="math" id="com.github.richbai90.optics.fresnel-zones.math-fresnel-number" />

It partitions the optical world into two regimes. With $N_F \gtrsim 1$
(macroscopic aperture, nearby screen) you are in the **near field** —
enough zones interfere for the zone picture to be the right language, and
shadows have structure. With $N_F \ll 1$ (small aperture, far screen) you
are in the **far field**, where Fraunhofer diffraction and Fourier methods
take over ([Fraunhofer diffraction and Fourier
transforms](32-fraunhofer-fourier.md)). Feel the boundary: an opening of
radius $a = 1$ mm with $\lambda = 500$ nm gives $N_F = 2$ at $d = 1$ m but
$N_F = 0.2$ at $d = 10$ m — the same aperture is near-field hardware on a
bench and a point source across a hall.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-zones.quiz2" />

## The Poisson spot

Now the move that changed physics. Replace the aperture with an opaque
**disk** centered on the axis to $P$, blocking exactly the first $m$ zones.
The wavefront still open to $P$ contributes

$$A \;=\; a_{m+1} - a_{m+2} + a_{m+3} - \cdots \;\approx\; \tfrac{a_{m+1}}{2} \;>\; 0,$$

so the on-axis field behind a round shadow is *never zero*: there is a
bright point at the exact center of the geometric shadow, for any disk size
(paraxially). In 1818 the French Academy posed the prize question on
diffraction; the judge Siméon Denis Poisson, a committed emission theorist,
derived this absurd consequence of Fresnel's wave theory as a
*reductio ad absurdum*. François Arago looked, and **the spot was there**.
The "Poisson spot" (or Arago spot) is the most spectacular confirmation
ever extracted from a counting argument — and the same logic governs every
edge in the next lesson.

<Widget type="quiz" id="com.github.richbai90.optics.fresnel-zones.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-zones.card-zones" />

<Widget type="flashcard" id="com.github.richbai90.optics.fresnel-zones.card-fresnel-number" />

## Recommended reading and viewing

MIT's lecture 15 builds the zone construction on the way to Fresnel
diffraction; OpenStax §1.7 states Huygens' principle in its textbook form.

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-zones.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-zones.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.fresnel-zones.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle,
  interferometers, Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec15/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.7 (Huygens's Principle) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- The 1818 prize episode follows the standard history of the wave theory
  (compare [a brief history of optics](02-a-brief-history-of-optics.md)).
