---
title: Scalar Diffraction Theory
description: From Maxwell's equations to the Rayleigh–Sommerfeld integral — and the far-field shortcut that turns diffraction into a Fourier transform.
order: 3
section: foundations
---

Light obeys Maxwell's equations. The vector form is hard, so scalar diffraction
theory strips it down with a chain of explicit assumptions. The book's warning
is the most important sentence in the chapter:

> When designing an optical element using any mathematical model, it is
> critical to know that the model is accurate for your design.

**Scalar theory fails when the wavelength is comparable to or smaller than the
diffractive features** — the subject of
[Electromagnetic Methods](06-electromagnetic-methods.md). Everything else, it
handles beautifully.

## Maxwell down to the wave equation

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-maxwell" />

Four assumptions about the medium make these tractable: (1) uncharged and
nonconducting ($\rho = 0$, $\sigma = 0$ — conductors absorb light);
(2) homogeneous and uniform; (3) isotropic; (4) linear. Then taking the curl
again yields the wave equation, whose constant is the (squared) propagation
speed:

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-wave" />

and the index of refraction is just $n = c/v = c\sqrt{\mu\varepsilon}$. Because
the medium is isotropic, each *scalar component* of $\mathbf{E}$ and
$\mathbf{B}$ separately obeys the wave equation. Splitting off the time factor
$\exp(-ikct/n)$ leaves the spatial part $P$ satisfying the **Helmholtz
equation**:

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-helmholtz" />

## The Rayleigh–Sommerfeld integral

Geometry: a field defined in an **aperture plane** $(x, y, 0)$ — where the DOE
sits — evaluated in a parallel **evaluation plane** a distance $Z$ away. Four
more assumptions: (5) time dependence separated; (6) plane-to-plane
propagation; (7) aperture large compared with λ; (8) propagation distance large
compared with λ. The solution for $P(X, Y, Z)$ is the **Rayleigh–Sommerfeld
(RS) integral**:

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-rs" />

Every point inside the aperture contributes a spherical wavelet to every point
on the evaluation plane — Huygens, made quantitative. Assumptions 1–4 hold for
air, vacuum, and most glasses; 5–8 hold for beams propagating between planes.
(Assumptions 2 and 7 fail *inside* the microstructure — the workaround is to
compute the DOE's complex transmission function analytically, then propagate
it plane-to-plane.)

## The far field: diffraction becomes a Fourier transform

Add assumption (9) — the **far-field** (Fraunhofer) condition: $Z$ very large
compared with the aperture size. Then the path length from an aperture point to
an evaluation point collapses to a linear expression:

<Widget type="stepper" id="com.github.richbai90.diffractive.scalar.math-farfield" />

where $\alpha = X/R$, $\beta = Y/R$ are the **direction cosines** of the
observation point. The field in the evaluation plane becomes

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-ft" />

a two-dimensional **Fourier transform of the aperture function**. For a phase
element, $u(x,y,0) = u_0(x,y)\,e^{i\phi_0(x,y)}$: the DOE simply multiplies the
incident field by a position-dependent phase factor. In direction-cosine form
(Eq. 2.19, reused constantly in Chapter 3):

<Widget type="math" id="com.github.richbai90.diffractive.scalar.math-pws" />

<Widget type="quiz" id="com.github.richbai90.diffractive.scalar.quiz-farfield" />

## What you measure

Detectors see **irradiance** $\propto |P|^2$, not the field. But all the
heavy lifting — computing what a DOE does — is the transform of its aperture
function. And because the integral is a convolution, it can be **inverted**:
known output ⇒ (with care) known element. That inversion idea is the seed of
[grating design](10-fanout-grating-design.md).

<Widget type="flashcard" id="com.github.richbai90.diffractive.scalar.card-rs" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.scalar.card-farfield" />

<Widget type="quiz" id="com.github.richbai90.diffractive.scalar.quiz-assumptions" />

<Widget type="quiz" id="com.github.richbai90.diffractive.scalar.quiz-what" />
