---
title: Hybrid Lenses
description: Why a whisper of diffractive power corrects a shout of glass color — the negative Abbe number of every diffractive surface, and how a phase polynomial enters a ray tracer.
order: 9
section: design
---

The payoff of everything so far: a **hybrid lens** — refractive element plus
one diffractive surface — corrects chromatic aberration with a structure so
weak it barely perturbs anything else. To see why, compare the two dispersions.

## Diffractive power is linear in wavelength

For a lens zone of period $\Lambda(r)$, the grating equation gives the local
diffractive power $\varphi(r) = \lambda/(r\,\Lambda(r))$. The *profile* is
fixed at manufacture, so $r\Lambda(r)$ is an invariant of the design and
(Eq. 4.36)

<Widget type="math" id="com.github.richbai90.diffractive.hybrid.math-disp" />

Power **grows** with wavelength — the opposite of glass, where $dn/d\lambda <
0$ makes power shrink. Compute the equivalent Abbe number of *any* diffractive
surface (Eq. 4.39, evaluated at the same F/C/d lines as glass):

<Widget type="math" id="com.github.richbai90.diffractive.hybrid.math-vdiff" />

**Every diffractive surface, of every shape and power, has $V \approx -3.45$
in the visible** — enormously dispersive, and negative. Glass is +25 to +70.
That is the whole reason a *weak* DOE corrects a *strong* lens.

## The design arithmetic

The achromat condition from [Lens Design Basics](07-lens-design-basics.md),
$\varphi_a/V_a = -\varphi_b/V_b$, now has a trivial solution:

<Widget type="stepper" id="com.github.richbai90.diffractive.hybrid.step-example" />

A diffractive surface with $f = 1.86$ m — a nearly *flat* relief structure —
cancels the color of a 100-mm BK7 singlet. (The book prints the hybrid focal
length as 94.5 mm; recomputing from its own numbers gives ≈ 94.9 mm — the
point, a ~5% power addition, stands either way.)

<Widget type="quiz" id="com.github.richbai90.diffractive.hybrid.quiz-weak" />

## Putting a DOE into a ray-trace program

Design programs (CODE V, Zemax, OSLO) accept diffractive surfaces as **phase
or OPD polynomials**. The paraxial diffractive lens is just the quadratic term
(Eq. 4.40):

<Widget type="math" id="com.github.richbai90.diffractive.hybrid.math-opd" />

and the optimizable generalization adds even powers (Eqs. 4.41–4.42):

<Widget type="math" id="com.github.richbai90.diffractive.hybrid.math-poly" />

The workflow: optimize $A_1 \dots A_4$ like any aspheric coefficients to
drive the aberration merit function down — then **fracture** the resulting
phase profile by integral wavelengths into the mask data of a kinoform. The
book traces a 100-mm f/5 singlet (Newport SPX022 quartz: $R_1 = 45.702$ mm,
thickness 4.79 mm, $n = 1.4585$) whose ray-intercept plot shows a big S
(spherical) plus wavelength-separated curves (color); adding an optimized
diffractive surface to the flat side of a fused-silica plano-convex lens
($R_1 = 48.803$ mm, $A_1 = -3.1365\times10^{-4}$, $A_2 = +3.5180\times10^{-7}$,
$A_3 = -2.4772\times10^{-11}$, $A_4 = +4.4228\times10^{-14}$, in mm units)
flattens the central-wavelength S-curve to a wiggle about zero and crosses the
color curves — color-corrected spherical-free imaging from two manipulated
surfaces.

<Widget type="flashcard" id="com.github.richbai90.diffractive.hybrid.card-fracture" />

## What hybrids buy you

<Widget type="flashcard" id="com.github.richbai90.diffractive.hybrid.card-payoff" />

The book's payoff table (details in [Lens Applications](16-lens-applications.md)):

- **IR Petzval objective**: 2 ZnS menisci with asphere + DOE surfaces replace
  a 4-element, 3-material design — 1.1 kg instead of 1.9 kg, ~⅓ the material
  cost.
- **Eyepieces**: Erfle's 5 lenses → 3, ~72% lighter, eye relief 1.36×, less
  lateral color.
- **LWIR telescopes**: diffractive + aspheric surfaces drop two elements and
  dramatically cut lateral color.

<Widget type="quiz" id="com.github.richbai90.diffractive.hybrid.quiz-vdiff" />

<Widget type="quiz" id="com.github.richbai90.diffractive.hybrid.quiz-workflow" />
