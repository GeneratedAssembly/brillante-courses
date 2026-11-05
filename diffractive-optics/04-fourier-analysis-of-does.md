---
title: Fourier Analysis of Diffractive Structures
description: Convolutions, delta functions, combs — the algebra of aperture functions — and the Fourier analysis of the blazed grating that says 100% efficiency is possible.
order: 4
section: foundations
---

The far field is a Fourier transform, so the whole theory of DOEs becomes an
algebra of **aperture functions** built from a few primitives. Three concepts
do all the work: the convolution, the Dirac delta, and the convolution
theorem.

## Convolution

The convolution of $f$ and $g$ is

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-conv" />

written $h = f \otimes g$. The mental picture: slide one function across the
other and accumulate the overlap. Convolving $\mathrm{rect}(x/b)$ with itself
grows linearly from zero overlap to full overlap — a **triangle** function.

## The Dirac delta and the comb

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-delta" />

Infinitely narrow, infinitely high, unit area. Alone it is a curiosity; inside
a convolution it *places* things. A double slit (Young's geometry, two rects
of width $b$ separated by $\Lambda$) is compactly written

$$\mathrm{rect}(x/b) \otimes \big[\delta(x+\Lambda/2) + \delta(x-\Lambda/2)\big].$$

Summing shifted deltas gives the **comb function**:

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-comb" />

and $\mathrm{rect}(x/b) \otimes \mathrm{comb}(x/2b)$ is a **square-wave
grating** — a whole grating from two words.

<Widget type="quiz" id="com.github.richbai90.diffractive.fourier.quiz-comb" />

## The convolution theorem — why all this matters

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-theorem" />

**Convolution in one domain is multiplication in the other.** The double slit's
far field is the single-slit sinc pattern *multiplied by* the two-beam
interference fringes; the square-wave grating's far field is a comb of delta
functions (the discrete diffraction orders) *weighted by* the transform of one
unit cell. That is the template for every grating calculation in the course:

- **comb ⇒ where** the light goes (orders at the grating-equation angles);
- **unit-cell transform ⇒ how much** goes into each order (the envelope).

## Computing it: FFTs and sampling rules

The RS integral *is* a convolution $u(x,y,Z) = u_0 \otimes H$ with an explicit
propagation kernel $H$ — the **plane-wave spectrum** idea, later formalized in
[Electromagnetic Methods](06-electromagnetic-methods.md). With an FFT the whole
operation is a 2-D complex array transform, provided the wavefront is sampled
densely enough. For a nearly collimated beam of diameter $D$ propagated a
distance $Z$ with sampling interval $\Delta$ and $N$ points, the book's three
rules:

<Widget type="flashcard" id="com.github.richbai90.diffractive.fourier.card-sampling" />

## The linear blazed grating, solved

A sawtooth phase grating of period $\Lambda$ and depth $d$ (Fig. 2.6) has
aperture function (Eq. 2.25)

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-blaze" />

where the total phase across one period is $\varphi = 2\pi(n-1)d/\lambda$.
Its orders sit at $\Lambda\sin\theta_m = m\lambda$ (Eq. 2.26), and the
fraction of light in order $m$ is the squared Fourier coefficient (Eq. 2.27):

<Widget type="math" id="com.github.richbai90.diffractive.fourier.math-eta" />

Now read the punchline: if the depth is chosen so that $\varphi = 2\pi$ —
i.e. **$(n-1)d = \lambda$** — then for $m = 1$ the denominator vanishes and
$\eta_1 = 1$. **All the light, into one order.** Scalar theory says a perfect
beam-steerer exists.

<Widget type="interactive" id="com.github.richbai90.diffractive.fourier.int-sinc" />

The envelope is a shifted sinc²: slide the order (parameter $m$) along $x$ and
watch efficiency peak exactly at the blaze condition $x = k = 1$. The caveat
the book adds immediately: this assumes the depth is small compared with the
period — as $d \to \Lambda$, **shadowing** eats the efficiency
([next lesson](05-binary-grating-efficiency.md)).

<Widget type="quiz" id="com.github.richbai90.diffractive.fourier.quiz-blaze" />

<Widget type="quiz" id="com.github.richbai90.diffractive.fourier.quiz-theorem" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.fourier.card-envelope" />
