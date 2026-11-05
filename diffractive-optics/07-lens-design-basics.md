---
title: Lens Design Basics
description: The vocabulary a diffractive designer must share with the refractive world — prescriptions, the lensmaker's equation, Abbe numbers, Seidel aberrations, and ray intercept curves.
order: 7
section: design
---

Diffractive lenses do not live alone: the interesting devices in chapters 4
and 10 are **hybrids**, judged by conventional lens-design standards. So the
book opens design with the conventional side. This lesson is the vocabulary
lesson; skip it only if you already speak fluent optical design.

## Describing an optical system

A design is two data sets. The **prescription**: for every surface, radius of
curvature, thickness to the next surface, refractive index, clear-aperture
radius (flat surfaces entered with radius 0, meaning infinity). The
**specifications**: object location, field heights, stop and entrance-pupil
location, operating wavelengths, and a resolution measure (spot size or MTF).
The **f-number** $F = f_{\text{EFL}}/D_{\text{entrance pupil}}$ sets both
light gathering and, in the absence of aberrations, the diffraction limit.
Design is a loop: start from a guess, compute a **merit function** (weighted
target deviations), vary parameters, re-ray-trace, repeat until the merit
function goes to zero. (Keep the loop in mind —
[Iterative Design](11-iterative-design.md) runs the same loop for DOEs.)

## The lensmaker's equation

For a thick lens (center thickness $t$, index $n$):

<Widget type="math" id="com.github.richbai90.diffractive.lensbasics.math-thick" />

and in the thin-lens limit, with power $\varphi = 1/f$ and surface curvatures
$c_i = 1/R_i$:

<Widget type="math" id="com.github.richbai90.diffractive.lensbasics.math-thin" />

<Widget type="interactive" id="com.github.richbai90.diffractive.lensbasics.int-planoconvex" />

Power is **linear in the index contrast** $n-1$. "Bending" a lens — trading
$R_1$ against $R_2$ at fixed power — changes the aberrations without changing
the focal length; the bending knob reappears with diffractive surfaces later.

## Chromatic aberration and the Abbe number

Glass index depends on wavelength, and $n$ is larger at blue: **blue focuses
shorter than red**. The standard dispersion measure is the **Abbe V-number**
(Eq. 4.5), built on the hydrogen and helium lines:

<Widget type="math" id="com.github.richbai90.diffractive.lensbasics.math-abbe" />

Crowns run $V \approx 70$ (weak dispersion), flints down to $V \approx 25$
(strong). The fractional power change across the F–C band is simply $1/V$
(Eq. 4.7).

Correcting color means pairing elements whose **powers sum but whose
dispersions cancel** (Eqs. 4.8–4.11):

<Widget type="math" id="com.github.richbai90.diffractive.lensbasics.math-achromat" />

Since every glass has $V > 0$, an achromat needs one positive and one negative
element with $\varphi_a/V_a = -\varphi_b/V_b$ — and correcting at two
wavelengths leaves residual **secondary color**. Hold that equation; in the
next-but-one lesson the diffractive surface walks in with $V \approx -3.45$
and does the same job with almost no power.

<Widget type="quiz" id="com.github.richbai90.diffractive.lensbasics.quiz-abbe" />

## The third-order (Seidel) aberrations

Five named ways real systems fail, each with a coefficient $S_{\mathrm I}$–
$S_{\mathrm V}$:

<Widget type="flashcard" id="com.github.richbai90.diffractive.lensbasics.card-seidels" />

- **Spherical** $S_{\mathrm I}$: marginal rays focus nearer than paraxial —
  measured longitudinally (LSA) or transversely (TSA).
- **Coma** $S_{\mathrm{II}}$: off-axis; annular zones land at different
  heights — a comet.
- **Astigmatism** $S_{\mathrm{III}}$ and **field curvature** $S_{\mathrm{IV}}$:
  a flat object images onto a curved Petzval surface, tangentially and
  sagittally at different radii.
- **Distortion** $S_{\mathrm V}$: magnification varies with field — pincushion
  or barrel, blur-free.

## Reading ray intercept curves

The book's diagnostic plot: ray error $\Delta y$ at the evaluation plane vs
ray height $y$. Learn the signatures once and you can read a design's health
at a glance (they recur in every figure of chapters 4 and 10):

<Widget type="flashcard" id="com.github.richbai90.diffractive.lensbasics.card-intercept" />

An S-curve = spherical; a U-curve = coma; a *family of identical curves
separated per wavelength* = chromatic. Moving the evaluation plane rotates the
spherical S about the origin.

<Widget type="quiz" id="com.github.richbai90.diffractive.lensbasics.quiz-signature" />

<Widget type="quiz" id="com.github.richbai90.diffractive.lensbasics.quiz-achromat" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.lensbasics.card-power" />
