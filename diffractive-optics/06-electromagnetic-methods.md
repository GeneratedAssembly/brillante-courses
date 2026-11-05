---
title: Rigorous Electromagnetic Methods
description: Where scalar theory fails at wavelength-scale features, and the four tools that replace it — plane-wave spectrum, modal/RCWA analysis, FDTD, and effective medium theory.
order: 6
section: vector-theory
---

Scalar theory treats a DOE as a passive phase screen: multiply the incident
field by $e^{i\phi_0(x,y)}$ and propagate. That is a *model*, and the book's
rule for when it breaks: **when feature sizes approach the wavelength, the
boundary of the structure couples to the electromagnetic field in ways a phase
screen cannot express.** FDTD calculations along a grating boundary at
$\lambda = 1\,\mu$m show the field amplitude becoming progressively more
nonuniform as the grating period shrinks toward $\lambda$ (Fig. 3.2). Two
practical consequences:

- Scalar efficiency predictions drift high for **low f-number** diffractive
  lenses (Fig. 3.5: scalar vs FDTD efficiency vs f/# — the gap widens as the
  outer zones shrink to subwavelength size).
- But if you sample the field **several wavelengths away** from the structure,
  the coupling effects have radiated away and scalar propagation *between
  planes* is fine again. Hence the hybrid strategy used everywhere: rigorous
  solver at the boundary, fast propagation beyond it.

## Plane-wave spectrum (PWS) propagation

Any field is a superposition of plane waves (Maxwell is linear). Decompose the
aperture field into spatial frequencies $f_x, f_y$ — a 2-D Fourier transform —
propagate **each component independently**, and recombine. Each plane wave's
direction cosines satisfy $\alpha = \lambda f_x$, $\beta = \lambda f_y$,
$\gamma = \sqrt{1 - \alpha^2 - \beta^2}$, and propagation over $z$ is a pure
phase multiplication (Eq. 3.12):

<Widget type="math" id="com.github.richbai90.diffractive.emath.math-pws" />

Two regimes hide in that square root:

- $\alpha^2 + \beta^2 \le 1$: **propagating** waves — unit-modulus phase factor.
- $\alpha^2 + \beta^2 > 1$: **evanescent** waves — the root is imaginary and
  the component dies off exponentially within about a wavelength. They carry
  the near-field boundary information scalar theory gives up.

PWS is FFT-friendly: propagation costs $O(N\log N)$ instead of the $O(N^2)$ of
point-by-point Huygens summation. Its one fatal weakness: it is **only as good
as the field you feed it** — garbage at the source plane propagates unchanged.

<Widget type="quiz" id="com.github.richbai90.diffractive.emath.quiz-evanescent" />

## The modal method / RCWA

For **periodic** structures, solve Maxwell's boundary-value problem exactly by
expanding the fields in the grating region into modes (or, in RCWA's original
formulation, coupled plane waves — the two were proven equivalent). Geometry:
three regions — superstrate $n_1$, a grating slab of thickness $h$ with
periodic permittivity $\varepsilon(x)$, substrate $n_2$; TE case, $E_y$
nonzero. The mechanism in four moves:

<Widget type="stepper" id="com.github.richbai90.diffractive.emath.step-rcwa" />

The Rayleigh condition, $\alpha_m = \alpha_0 + 2\pi m/\Lambda$, is momentum
conservation modulo the grating's reciprocal lattice — the diffraction orders,
propagating when $|\alpha_m| \le n k_0$ and evanescent otherwise. Efficiencies
follow from Poynting-flux normalization, $\eta_{T_m} = \mathrm{Re}(t_m/r_0)\,
|T_m|^2$ (Eq. 3.36). Applied to the fused-silica square-wave grating of the
last lesson ($n = 1.457$, HeNe $\lambda = 0.633\,\mu$m) with periods 1, 2, 5,
10 µm, RCWA shows the scalar constants (40.5%, 4.5%, …) recovered **only when
the period is large compared with λ**.

<Widget type="quiz" id="com.github.richbai90.diffractive.emath.quiz-rcwa" />

## FDTD: brute force that always works

Aperiodic structures kill the modal method. The **finite-difference
time-domain** method instead puts a grid over the region, replaces the
time-dependent curl equations by second-order central differences, and
**marches E and H forward in time** on a staggered lattice — E and H offset by
half a cell in space and half a step in time (the leapfrog scheme; the book's
Fig. 3.9, universally known as the Yee grid). Material parameters enter cell
by cell, so arbitrary shapes and lossy media are handled directly. The book's
design rules: **cell spacing ≈ λ/20 in the material**, run to steady state,
hand the exit plane to PWS. Accuracy is second order in space and time.

<Widget type="flashcard" id="com.github.richbai90.diffractive.emath.card-fdtd" />

## Effective medium theory: the subwavelength shortcut

When features are **much smaller than a wavelength**, a rigorous solve is
overkill: assume the field is constant across one period, enforce boundary
conditions, and the two-material stack becomes a **homogeneous film with an
artificial index** (Eq. 3.45):

<Widget type="math" id="com.github.richbai90.diffractive.emath.math-emt" />

The TE and TM formulas differ, so the film is **artificially birefringent** —
*form birefringence*, the operating principle of subwavelength wave plates.
Validity: period $\Delta \le \lambda/(2n)$ — beyond that, more than half a
wavelength fits in a period and the constant-field assumption dies.

<Widget type="interactive" id="com.github.richbai90.diffractive.emath.int-emt" />

Farn's trick closes the loop back to design: a *blazed* grating can be
realized subwavelength by replacing the sawtooth with binary features whose
start/stop points follow $\alpha_i = i/(N{+}1)$, $\beta_i = i/N$ (Eq. 3.46) —
a continuous phase ramp out of rectangles. Subwavelength devices get their own
application tour in [Applications Survey](17-applications-survey.md).

<Widget type="quiz" id="com.github.richbai90.diffractive.emath.quiz-emt" />

<Widget type="quiz" id="com.github.richbai90.diffractive.emath.quiz-choose" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.emath.card-ladder" />
