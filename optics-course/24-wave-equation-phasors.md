---
title: The Wave Equation and Phasors
description: Light's one governing equation, the complex-exponential shorthand that makes it tractable, plane waves in three dimensions, and the two velocities a dispersive wave owns.
order: 24
section: wave-optics-foundations
---

The eikonal named the phase surfaces; this lesson builds the wave they
belong to. One linear partial differential equation governs all small
amplitude disturbances in a uniform medium — sound, strings, and light —
and one piece of notation, the complex phasor, turns solving it into
algebra. Everything this course does with interference, diffraction, and
imaging is a corollary of the equation and the notation introduced here.

## The wave equation

In a uniform medium with wave speed $v$, any small disturbance
$U(z, t)$ obeys

<Widget type="math" id="com.github.richbai90.optics.wave-equation-phasors.math-wave-eq" />

Its general solution is d'Alembert's: $U(z,t) = f(z - vt) + g(z + vt)$ —
arbitrary profiles $f$ and $g$ translating rigidly to the right and
left. Substitute and check: every derivative multiplies the profile by
$v^2$ in exactly the way the equation demands. The equation is *linear*,
so solutions add — the license for every superposition argument in this
course.

## Harmonic waves and phasors

Because the equation is linear and time-translation invariant, its
building blocks are sinusoids. Writing the complex representation

<Widget type="math" id="com.github.richbai90.optics.wave-equation-phasors.math-phasor" />

the physical field is the real part; the complex factor
$e^{i(kz - \omega t)}$ is the **phasor**. Its parameters pair off:
$\omega = 2\pi/T$ is the angular frequency, $k = 2\pi/\lambda$ the
wavenumber, and the speed ties them: $v = \omega/k$, so $\omega = vk$.
Green light, $\lambda = 500$ nm in air, oscillates at
$\nu \approx 600$ THz with $k \approx 1.26\times10^7\ \mathrm{rad/m}$ —
no detector or camera ever follows the oscillation; instruments measure
*time-averaged* intensity, which is why the complex bookkeeping, not the
instantaneous field, is the engineer's currency.

<Widget type="interactive" id="com.github.richbai90.optics.wave-equation-phasors.int-traveling" />

Phasors add like vectors. Two equal-amplitude beams arriving with phase
difference $\delta$ give a resultant intensity

$$I = 4I_0\cos^2\!\frac{\delta}{2},$$

which ranges from $4I_0$ (in phase) through $I_0$ at $\delta = 120°$ to
zero (opposed). In phase — four times one beam's intensity; in
opposition — darkness from two illuminated beams. Every fringe pattern
in this course is this one line, applied.

<Widget type="quiz" id="com.github.richbai90.optics.wave-equation-phasors.quiz1" />

## Plane waves in three dimensions

In three dimensions the harmonic solution generalizes to

<Widget type="math" id="com.github.richbai90.optics.wave-equation-phasors.math-planewave" />

with the wave vector $\mathbf{k}$: the wavefronts $S =
\mathbf{k}\cdot\mathbf{r} = \text{const}$ are planes perpendicular to
$\mathbf{k}$, and $|\mathbf{k}| = n\omega/c$ in a medium of index $n$.
Interfaces care only about the phase pattern *along the surface* —
matching $k_\parallel$ on both sides is Snell's law (as
[from rays to waves](23-rays-to-waves.md) promised, and
[the Fresnel equations](17-fresnel-equations.md) priced).

<Widget type="quiz" id="com.github.richbai90.optics.wave-equation-phasors.quiz2" />

## Phase velocity and group velocity

A single sinusoid in a nondispersive medium moves at $v = \omega/k$. Real
media are dispersive — $\omega$ is a function of $k$ (that is what the
index's wavelength dependence,
[lesson 4](04-light-in-matter.md#the-index-of-refraction), means) — and
then two velocities part company:

<Widget type="math" id="com.github.richbai90.optics.wave-equation-phasors.math-velocities" />

The **phase velocity** $v_p$ carries the crests; the **group velocity**
$v_g$ carries the envelope — the wave packet, and with it information and
energy. In normal-dispersion glass ($n$ falls as $\lambda$ grows) the
Cauchy model gives, at $\lambda = 550$ nm, $v_p = c/1.515 \approx
0.660\,c$ but $v_g = c/(n - \lambda\,dn/d\lambda) \approx 0.647\,c$: the
pattern outruns the packet. No signal outruns $c$ — it rides with
$v_g$.

<Widget type="quiz" id="com.github.richbai90.optics.wave-equation-phasors.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.wave-equation-phasors.card-dalembert" />

<Widget type="flashcard" id="com.github.richbai90.optics.wave-equation-phasors.card-velocities" />

## Recommended reading and viewing

Lecture 12 introduces the phasor bookkeeping and three-dimensional waves;
the OpenStax propagation section states the wave picture in its textbook
form.

<Widget type="resource-link" id="com.github.richbai90.optics.wave-equation-phasors.link-lecture-12" />

<Widget type="resource-link" id="com.github.richbai90.optics.wave-equation-phasors.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.wave-equation-phasors.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 12 — the wave equation;
  phasor representation; 3D
  waves](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-12-the-wave-equation-phasor-representation-3d-waves/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 12 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec12/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.2 (The Propagation of Light) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Group-velocity example computed from the course's Cauchy model
  $n = 1.50 + 0.0045/\lambda^2$ (λ in μm): at 0.55 μm,
  $dn/d\lambda = -0.0541\ \mu\mathrm{m}^{-1}$, giving
  $v_p = 0.660\,c$, $v_g = 0.647\,c$
