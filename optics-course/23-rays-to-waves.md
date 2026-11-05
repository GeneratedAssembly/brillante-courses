---
title: From Rays to Waves
description: Fermat's stationary time, the eikonal equation, and rays as normals of wavefronts — the bridge on which geometric optics becomes an approximation to wave optics.
order: 23
section: wave-optics-foundations
---

Half a course of ray optics has worked. Lenses focused, telescopes
magnified, aberrations yielded to design — all without ever asking what
light *is*. The ray is a bookkeeping device. This section rebuilds light
from its actual equations, and the bridge is a single mathematical idea:
the **eikonal**, the phase surface whose normals happen to be rays. The
ray picture survives as the short-wavelength limit, and everything it
could not explain — why shadows are soft, why interfaces split beams —
becomes computable.

## Fermat's principle

The ray version of dynamics is a variational statement, Fermat's
principle: *between two points, light takes the path whose optical path
length is stationary* —

<Widget type="math" id="com.github.richbai90.optics.rays-to-waves.math-fermat" />

"Stationary" usually means least time, which is why the principle is
remembered as least time. Snell's law falls out of it in four lines:

<Widget type="stepper" id="com.github.richbai90.optics.rays-to-waves.stepper-fermat" />

Nothing here knew about waves — and that is the point. A variational
principle that predicts Snell's law without a wave in sight is begging
for a deeper origin. The deeper origin is that light's phase accumulates
along every possible path, and paths far from stationarity cancel each
other; only near-stationary paths survive constructive addition. Rays
are the survivors.

<Widget type="quiz" id="com.github.richbai90.optics.rays-to-waves.quiz1" />

## The eikonal equation

Monochromatic light of vacuum wavelength $\lambda_0$ carries a spatial
phase $S(\mathbf{r})$ whose level surfaces $S = \text{const}$ are the
**wavefronts**. The requirement that the phase advance by $2\pi$ per
wavelength *of local wavelength* $\lambda_0/n$ compresses into one
equation:

<Widget type="math" id="com.github.richbai90.optics.rays-to-waves.math-eikonal" />

This is the **eikonal equation**. For a uniform medium it has the plane-wave
solution $S = n\,\hat{\mathbf{s}}\cdot\mathbf{r}$ (wavefronts are planes,
$\hat{\mathbf{s}}$ their normal). In general the wavefronts curve, and
the rays — the curves perpendicular to every wavefront they cross — bend
wherever $\nabla n$ points. A paraxial ray in a medium whose index grows
linearly upward, $n(y) = n_0 + \alpha y$, behaves like a thrown ball: a
parabola with "gravity" $\alpha/n_0$.

<Widget type="interactive" id="com.github.richbai90.optics.rays-to-waves.int-gradient" />

This is the physics of mirages and heat shimmer: hot air near a road has
lower index, the gradient points down toward the cool side, and rays
curve away from the road until total reflection bounces the sky into
your eye. The same equation, run with a parabolic profile, drove the
GRIN lenses of [optical design](22-optical-design-grin.md#grin-optics-lenses-without-surfaces).

<Widget type="quiz" id="com.github.richbai90.optics.rays-to-waves.quiz2" />

## Rays ⊥ wavefronts, always

The eikonal picture ties every ray result to a wave statement:

- **Refracting surfaces reshape wavefronts.** A lens is a phase mask: it
  delays the beam's center more than its rim (or the reverse), converting
  a plane wavefront into a converging sphere. The lensmaker's equation of
  [thin lenses](09-thin-lenses.md) is the paraxial bookkeeping of that
  delay.
- **Snell's law is phase matching.** Fields must connect continuously
  across an interface, so the phase pattern along the surface must agree
  on both sides — $k_{1\parallel} = k_{2\parallel}$ — which is Snell's
  law in vector clothing. (Lesson 17 used the consequences; the boundary
  conditions behind this statement are derived in
  [Maxwell's equations and light](25-maxwell-em-waves.md).)
- **The ray is a limit, not a truth.** When apertures, edges, or
  wavelength-scale structure interrupt the wavefront, normals stop being
  enough. [Fresnel zones](18-fresnel-zones.md) showed what the eikonal
  misses at an edge; the rest of this course works in the fuller language.

<Widget type="quiz" id="com.github.richbai90.optics.rays-to-waves.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.rays-to-waves.card-fermat" />

<Widget type="flashcard" id="com.github.richbai90.optics.rays-to-waves.card-eikonal" />

## Recommended reading and viewing

Lecture 11 develops Hamilton's optical-mechanical analogy and the eikonal;
the OpenStax propagation section grounds the wavefront vocabulary.

<Widget type="resource-link" id="com.github.richbai90.optics.rays-to-waves.link-lecture-11" />

<Widget type="resource-link" id="com.github.richbai90.optics.rays-to-waves.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.rays-to-waves.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 11 — the Hamiltonian
  formulation; introduction to
  waves](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-11-the-hamiltonian-formulation-introduction-to-waves/)
  (CC BY-NC-SA 4.0) — Fermat, the eikonal equation, rays as wavefront
  normals
- MIT OCW 2.71 Optics, Spring 2009, [lecture 11 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec11/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.2 (The Propagation of Light) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Fermat-step example verified numerically: $h_1 = 2$, $h_2 = 3$,
  $D = 5$, $n_1 = 1 \to n_2 = 1.5$ gives crossing $x = 3.000$ mm,
  $\theta_1 = 56.31^\circ$, $\theta_2 = 33.69^\circ$,
  $n_1\sin\theta_1 = n_2\sin\theta_2 = 0.8321$
