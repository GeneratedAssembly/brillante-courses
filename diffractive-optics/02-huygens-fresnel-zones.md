---
title: Huygens, Zones, and the First Diffractive Lenses
description: Point sources, phasor sums, the zone plate that concentrates light 36-fold, the phase plate that doubles it again — and why two-level optics are only 41% efficient.
order: 2
section: foundations
---

Before any machinery of integrals, the book builds diffraction from
**Huygens' construction** — three steps that explain everything a DOE does:

1. Treat the original wavefront as evenly populated by a series of **point
   sources**.
2. Each point source emits a **spherical wavelet**, all in phase with one
   another.
3. The **envelope** of the wavelets after time $t$ is the propagated wavefront.

Because the wave extends *beyond* the width of any aperture, every obstruction
spreads light — that is diffraction — and the diameter of a circular aperture
"can profoundly affect the strength and distribution of the light behind it."

## Fresnel zones: canceling light with arithmetic

Put a screen a distance $r_0$ behind a circular aperture, on the axis. Draw
circles in the aperture whose distances to the on-axis point $P$ are
$r_0 + m\lambda/2$: the central disk and the annuli between them are the
**Fresnel zones**. Two facts do all the work:

- Every zone has **exactly the same area**, so each contributes the same
  amplitude at $P$.
- Consecutive zones differ in path by $\lambda/2$ — a **π phase shift** — so
  zone 2's contribution is equal in magnitude and *opposite* in direction to
  zone 1's.

<Widget type="stepper" id="com.github.richbai90.diffractive.zones.step-phasors" />

An aperture of exactly two zones cancels itself out. As it opens through more
zones, the on-axis field oscillates between nearly zero and nearly **twice**
the unobstructed field $E_0$, tracing a spiral of shrinking phasors that ends
at $E_0$.

## The zone plate: a diffractive lens made of holes

Block every other zone; transmit zones 1, 3, 5. The three contributions add
**in phase**: each open zone supplies about $2E_0$, so the on-axis field is
$6E_0$ and the irradiance is

$$I = (6E_0)^2 = 36 \times \text{(unobstructed irradiance)}.$$

This amplitude mask is a **Fresnel zone plate**, and it focuses like a lens.
Now the smarter version: instead of *blocking* alternate zones, **shift their
phase by π** so their light also arrives in phase. Six contributing zones give
$12E_0$ — an on-axis irradiance **144×** the unobstructed value. That is a
**Fresnel phase plate**, the two-level grandfather of every diffractive lens.

The depth that produces the π shift follows from optical path difference:

<Widget type="math" id="com.github.richbai90.diffractive.zones.math-pidepth" />

<Widget type="quiz" id="com.github.richbai90.diffractive.zones.quiz-depth" />

## Why two levels are not enough

A Fresnel phase plate focuses, but barely half its light cooperates: **about
41% of the transmitted light lands on axis, and another 41% is focused by the
same structure acting as a *negative* lens** — it has the focal length for the
wrong sign too. (The 41% is no accident: it is the $m = \pm1$ efficiency of a
binary π-phase grating, $(2/\pi)^2 = 40.5\%$, derived in
[Binary Grating Efficiency](05-binary-grating-efficiency.md).)

Adding phase levels fixes this. The book's Fig. 1.15 ladder — two-level phase
plate → four-level → eight-level → smooth **kinoform** — is the efficiency
ladder 40% → 81% → 95% → ~100%:

<Widget type="interactive" id="com.github.richbai90.diffractive.zones.int-levels" />

<Widget type="quiz" id="com.github.richbai90.diffractive.zones.quiz-levels" />

## Fanout: the first "impossible" element

Conventional beamsplitter networks get awkward fast — surfaces and alignment
multiply with the number of beams. A DOE splits one beam into **many
controlled-intensity beams in a single thin element**: a *fanout grating*. The
simplest is the **Dammann grating**: a two-level (0/π) phase grating with
several phase transitions *within* each period, positioned so the zero order
and the first $N$ orders all have equal intensity. Because binary structures
diffract symmetrically, a two-level Dammann grating gives $2N+1$ equal beams.

<Widget type="flashcard" id="com.github.richbai90.diffractive.zones.card-dammann" />

Multilevel or smooth profiles raise efficiency further — and almost always
require an optimization algorithm, which
[Iterative Design](11-iterative-design.md) supplies.

## The theme to carry forward

<Widget type="flashcard" id="com.github.richbai90.diffractive.zones.card-theme" />

Everything after this lesson is a variation on measuring, computing, and
fabricating **edges and depths**.

<Widget type="quiz" id="com.github.richbai90.diffractive.zones.quiz-plate" />
