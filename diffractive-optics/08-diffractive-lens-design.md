---
title: Designing Diffractive Lenses
description: Zone radii, the kinoform phase profile, etch depths, multilevel efficiency, wavelength detuning, and the minimum f-number that fabrication imposes.
order: 8
section: design
---

A lens is a wavefront converter: plane in, sphere out. A **diffractive lens**
converts the same wavefronts using only the *geometry of a relief profile* —
so its design reduces to writing down where the phase must change by $2\pi$,
and how deep to make it.

## Zone geometry

<Widget type="stepper" id="com.github.richbai90.diffractive.dlens.step-zones" />

<Widget type="math" id="com.github.richbai90.diffractive.dlens.math-period" />

The local grating period shrinks inversely with radius — a diffractive lens is
a blazed grating whose period decreases as $f\lambda/r$, finest at the edge.
For a two-level (π-phase) zone plate the zone radii shrink by a factor of
$\sqrt{2}$: $r_p^2 = p\lambda f$.

## From phase to depth

Phase accumulated traversing a thickness $t$ of index $n$:
$\Delta\phi = 2\pi(n-1)t/\lambda$. Equating the lens's OPD to the spherical
wavefront's, $\mathrm{OPD} = r^2/2f$, recovers the thin-lens result
$\varphi = (n-1)/R$ — the diffractive and refractive descriptions agree where
they should. The **kinoform** takes the continuous phase profile
$\phi(r) = \frac{2\pi}{\lambda_0}(n_0 - 1) z(r)$ and *fractures* it: wherever
the phase wraps by $2\pi$ (one wavelength of OPD), drop back to the start.

The depth of a full $2\pi$ cycle is the single most-used formula in DOE
fabrication:

<Widget type="math" id="com.github.richbai90.diffractive.dlens.math-depth" />

With $N$ binary masks ($2^N$ levels), each etch step is $\lambda/[2^N(n-1)]$
and the total depth approaches $\lambda/(n-1)$ from below:
$d = (2^N - 1)\lambda/[2^N(n-1)]$. Fused silica at HeNe: $2\pi$ depth
$= 0.6328/0.4572 = 1.384\,\mu$m; a π step is $0.692\,\mu$m — the number you
will see again in the [fabrication](12-from-equation-to-component.md) lessons.

## Efficiency: levels, wavelength, and depth errors

A perfect kinoform puts 100% into order 1 — *at its design wavelength, with
perfect depth*. Three failures bite:

**1. Finite levels.** The staircase blaze gives $\eta_1 = [\sin(\pi/N)/(\pi/N)]^2$:

| Levels | 2 | 4 | 8 | 16 | linear blaze | kinoform |
|---|---|---|---|---|---|---|
| η₁ | 40% | 81% | 95% | 99% | 99% | 100% |

**2. Off-design wavelength.** Define the **detuning parameter** (Eq. 4.26)

<Widget type="math" id="com.github.richbai90.diffractive.dlens.math-alpha" />

so $\alpha = 1$ is perfect design. The kinoform's first-order efficiency is a
sinc² dip (Eq. 4.27), $\eta = \sin^2[\pi(\alpha - 1)]/[\pi(\alpha-1)]^2$ —
broad and forgiving near $\alpha = 1$. But a *multilevel* element's phase
steps were sized for $\lambda_0$, so efficiency falls off much faster as
$\lambda$ detunes; and the focal length itself scales as
$f(\lambda) = (\lambda_0/\lambda) f_0/m$: **diffractive power grows linearly
with wavelength** — the opposite of glass, and the origin of its negative
Abbe number ([Hybrid Lenses](09-hybrid-lenses.md)).

**3. Depth error.** An element etched to depth $d$ behaves as designed at
$\lambda = d(n-1)$, so a fractional depth error $\varepsilon$ is exactly a
detuning $\alpha \approx 1 \pm \varepsilon$ (Eq. 4.29):

<Widget type="interactive" id="com.github.richbai90.diffractive.dlens.int-depth" />

| Depth error | 0 | 1% | 2% | 5% | 10% | 20% |
|---|---|---|---|---|---|---|
| Efficiency | 100.0% | 100.0% | 99.9% | 99.2% | 96.8% | 87.5% |

The book's rule of thumb: **depth must be off by more than ~5% before it
matters — but small errors in *transition locations* can drastically reduce
efficiency.** Etch-depth control is forgiving; pattern placement is not.

<Widget type="quiz" id="com.github.richbai90.diffractive.dlens.quiz-depth" />

## The minimum f-number

The edge zones are the finest features, and fabrication sets a floor. With
$2^N$ levels, minimum fabricable feature $\Delta r_{\min}$, and clear radius
$r_{\max}$ (Eq. 4.34):

<Widget type="math" id="com.github.richbai90.diffractive.dlens.math-fnum" />

<Widget type="interactive" id="com.github.richbai90.diffractive.dlens.int-fnum" />

Worked numbers at $\lambda = 0.6328\,\mu$m: two-level ($N=1$) with
$\Delta r_{\min} = 10\,\mu$m limits you to f/15.8; with 1-µm features, f/1.6 —
and **each added mask level doubles the fastest f-number you can make**. In
the mid-wave IR ($\lambda \approx 10\,\mu$m) the same rule relaxes everything
by an order of magnitude — one reason diffractive optics flourished there
first.

A last subtlety from Sec. 4.3.2: even a perfect diffractive lens leaks zero-
and higher-order light into the focal plane as a weak, broad background. It
barely moves the spot size but **craters the MTF at low spatial frequencies**
— a contrast pedestal, not a resolution loss.

<Widget type="quiz" id="com.github.richbai90.diffractive.dlens.quiz-fnum" />

<Widget type="quiz" id="com.github.richbai90.diffractive.dlens.quiz-alpha" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.dlens.card-kinoform" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.dlens.card-edge" />
