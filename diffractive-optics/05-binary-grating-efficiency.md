---
title: Efficiency of Binary and Multilevel Gratings
description: The 40.5% binary grating, the (2/mπ)² odd-order ladder, the sin(π/N)/(π/N) multilevel formula, and the shadowing correction that keeps theorists honest.
order: 5
section: foundations
---

The blazed grating diffracts everything into one order — *if you can make it*.
Sawtooth profiles were made for decades on **ruling engines**, but the
precision photolithography and ion etching demonstrated in the early 1980s
(MIT Lincoln Laboratory, Honeywell) is what opened the field: complicated
profiles, built from **binary masks**. So the practical question becomes:
how well does a *stepped* approximation of a blaze perform?

## The square-wave grating

The simplest binary structure: two levels, 50% duty cycle, depth chosen for a
π phase difference, $d = \lambda/(2(n-1))$. In convolution language the unit
cell is two offset rects, one with a phase flip (Eq. 2.28):

<Widget type="math" id="com.github.richbai90.diffractive.binary.math-cell" />

and the grating is that cell convolved with a comb (Eq. 2.29). The unit-cell
transform is a difference of sincs; at the order frequencies $q = m/\Lambda$
(Eq. 2.32) it collapses to

<Widget type="math" id="com.github.richbai90.diffractive.binary.math-eta" />

**zero for every even order**, and for odd orders

<Widget type="math" id="com.github.richbai90.diffractive.binary.math-odd" />

Why no zero order? Pair each base section with its π-step partner: equal light,
opposite phase, perfect cancellation — in *every* pair.

<Widget type="plot" id="com.github.richbai90.diffractive.binary.plot-orders" />

The +1 and −1 orders each carry $(2/\pi)^2 = 40.5\%$: the binary grating is an
**81%-efficient 1 × 2 beamsplitter** — equally a crude blaze in either
direction, since it is symmetric.

<Widget type="interactive" id="com.github.richbai90.diffractive.binary.int-duty" />

## The efficiency ladder

Etch additional steps at π/2 phase differences and the negative first order
vanishes while the first doubles to 81%; keep refining and the profile
approaches the ideal blaze. For $N$ uniform levels (Eq. 2.34):

<Widget type="math" id="com.github.richbai90.diffractive.binary.math-nlevel" />

<Widget type="interactive" id="com.github.richbai90.diffractive.binary.int-levels" />

| Levels $N$ | 2 | 4 | 8 | 16 | kinoform |
|---|---|---|---|---|---|
| First-order efficiency | 40.5% | 81% | 95% | 99% | ~100% |
| Masks needed (binary process) | 1 | 2 | 3 | 4 | — |

The gains are steep at the bottom of the ladder and nearly flat at the top —
which is exactly why real devices are usually 8 or 16 levels and not 256.

<Widget type="quiz" id="com.github.richbai90.diffractive.binary.quiz-ladder" />

## Extended scalar theory: shadowing

Everything so far assumed an **infinitesimally thin** structure — valid only
while depth $d \ll \Lambda$. At significant diffraction angles (more than a few
degrees) the facets of the sawtooth cast "gaps": the emerging beamlet from each
period is narrower than the period, with **fill factor** $\Lambda'/\Lambda < 1$
(Fig. 2.11). The correction is beautifully simple:

1. The optimal blaze depth gets *shallower* (Eq. 2.37):
   $d' = \dfrac{\lambda}{n - \cos\theta_d}$.
2. The efficiency gets multiplied by the fill factor squared (Eq. 2.38):
   $\eta_{\text{net}} = \eta_{\text{scalar}} \times (\Lambda'/\Lambda)^2$.

The book's worked example: a **four-level grating, period 4.0 µm, $n = 1.5$,
λ = 1.0 µm** — scalar theory says 81% at optimum depth 1.88 µm; the diffraction
angle is 14.48°, the fill factor is 0.878, so

$$\eta_{\text{net}} = 0.81 \times 0.878^2 = 0.81 \times 0.772 = \mathbf{0.625.}$$

Fifteen points of efficiency, invisible to plain scalar theory, predictable
with one geometric factor. Full vector theory (Chapter 3,
[Electromagnetic Methods](06-electromagnetic-methods.md)) does even better as
$\Lambda/\lambda$ shrinks toward 1.

<Widget type="quiz" id="com.github.richbai90.diffractive.binary.quiz-shadow" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.binary.card-405" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.binary.card-fill" />

<Widget type="quiz" id="com.github.richbai90.diffractive.binary.quiz-masks" />
