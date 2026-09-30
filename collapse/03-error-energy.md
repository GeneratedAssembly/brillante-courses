---
title: Where the Error Energy Lives
description: Parseval's accounting — why a small DC mistake outweighs a catastrophic carrier mistake, and why DC gradients add while high-frequency gradients cancel.
order: 3
section: toy
---

Metamers explain *averaged color*. But they do not explain why a model with a
fully determined target still strips a deliberate high-frequency signature.
For that we need to know where squared error *spends its budget*: which
components of the signal dominate the loss, and therefore the gradient.

## Signals are mostly DC

Model one row of an image as a strong constant plus a weak carrier:

$$g(x) = A_{\mathrm{DC}} + A_{\mathrm{HF}}\,\sin(2\pi f_0 x),
\qquad A_{\mathrm{DC}} \gg A_{\mathrm{HF}}$$

with the numbers below: $A_{\mathrm{DC}} = 0.8$, $A_{\mathrm{HF}} = 0.04$,
$f_0 = 10$ cycles across the row. Natural signals look like this — measured
power spectral densities of images fall off roughly like $1/f^2$, so the
low-frequency content dwarfs the high-frequency content. Below, the truth
$g$ (indigo) and a prediction $\hat g$ that gets the carrier *completely
wrong* — phase error $p = \pi/2$, the worst possible (emerald):

<Widget type="plot" id="com.github.richbai90.collapse.l3.plot_signal" />

The two curves are visually indistinguishable, and the total squared error
between them is $a^2(1 - \cos p) = 0.0016$ — an RMSE of $0.04$, exactly one
carrier amplitude. **The entire carrier is wrong and the loss barely
notices.** A DC error one-eighth that size would cost four times more.

## Parseval's accounting

Why is squared error so lopsided? Parseval's theorem: squared error is a
*frequency-summed* quantity — pixel-space and Fourier-space errors are the
same number:

<Widget type="math" id="com.github.richbai90.collapse.l3.math_parseval" />

MSE has no frequency preference of its own. But *signals* do: their spectral
power density collapses exponentially with frequency, so the error budget is
spendable almost entirely at the low end. A tiny relative error in the DC
level moves every pixel in the image coherently; the same relative error in a
weak carrier moves almost no total energy.

## Two mistakes, two very different energies

Make the two error channels explicit. Let the prediction carry a DC error $d$
and a carrier phase error $p$: $\hat g(x) = (A_{\mathrm{DC}} + d) +
a\sin(2\pi f_0 x + p)$. The residual, and its average square:

<Widget type="interactive" id="com.github.richbai90.collapse.l3.inter_residual" />

<Widget type="math" id="com.github.richbai90.collapse.l3.math_mse_decomp" />

Two numbers drive everything:

- **DC error is energy-linear:** $d = 0.08$ costs $0.0064$ — every pixel,
  always, in phase.
- **Carrier error is amplitude-squared:** even the *maximal* phase error
  $p = \pi/2$ costs $a^2 = 0.0016$ when $a = 0.04$.

The slider makes the asymmetry quantitative — the fraction of the signal's
total energy that the carrier holds:

<Widget type="slider" id="com.github.richbai90.collapse.l3.slider_energy" />

At $a = 0.04$ against $A_{\mathrm{DC}} = 0.8$ (so $A^2 = 0.64$), the carrier
holds about $0.25\%$ of the signal energy. An $L_2$ loss literally cannot
see more than a quarter-percent of the signal's information without being
told to look.

## Gradients: constructive versus cancelling

The loss asymmetry becomes a gradient asymmetry, which is what training
actually feels. The full derivation, one step at a time:

<Widget type="stepper" id="com.github.richbai90.collapse.l3.stepper_mse" />

The punchline deserves its own statement. DC residuals are **spatially
correlated**: every pixel's residual has the same sign, so their gradient
contributions reinforce constructively and produce large, smooth gradient
fields. Carrier residuals **oscillate in sign** across small pixel
neighborhoods, so their contributions partially cancel in the sum — unless
the model's phase alignment is already near-perfect, which it is not early in
training. Functionally, the high-frequency gradient signal acts as noise
underneath the DC pull.

<Widget type="quiz" id="com.github.richbai90.collapse.l3.quiz_dc_vs_hf" />

<Widget type="quiz" id="com.github.richbai90.collapse.l3.quiz_constructive" />

So to the opening question of the source discussion: *yes* — under $L_2$, DC
bias carries more gradient weight than high-frequency low-amplitude
oscillations, by energy accounting (Parseval), by gradient coherence
(constructive versus cancelling sums), and, as the next lesson shows, by the
learning dynamics of the network itself.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l3.quiz_parseval_meaning" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l3.card_parseval" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l3.card_energy_share" />