---
title: Spectral Bias
description: The F-principle and the deep image prior — gradient descent and convolutional architectures are low-pass filters before the loss even gets a vote.
order: 4
section: toy
---

Lessons 1–3 established that an $L_2$ loss spends its attention on the
conditional mean and the DC band. The remaining question: does the *network*
fight this bias or amplify it? It amplifies it — twice over.

## The F-principle

Train a standard network by gradient descent to fit a target function
containing many frequencies, and watch which components the fit acquires:
low frequencies are learned first, and the time needed to fit frequency $f$
grows roughly exponentially with $f$. This is the **spectral bias** or
**F-principle** of gradient descent (Rahaman et al., 2019). The curves below
sketch the shape of the result — residual energy of a frequency-$f$ target
component against training step, with the time constant growing like $f^2$:

<Widget type="plot" id="com.github.richbai90.collapse.l4.plot_convergence" />

Read the plot against Lesson 3's accounting. The component the loss barely
penalizes (the carrier, $0.25\%$ of the energy) is also the component the
optimizer reaches last. Early in training the model satisfies the objective
by locking onto $A_{\mathrm{DC}}$ and abandoning $A_{\mathrm{HF}}$ entirely —
and since the abandoned part contributes almost nothing to the loss, there is
no pressure to ever go back.

<Widget type="quiz" id="com.github.richbai90.collapse.l4.quiz_order" />

## Deep image prior

The bias is not only in the training dynamics; it is in the *architecture*.
The deep image prior result (Ulyanov et al., 2018) shows that a randomly
initialized convolutional network — never trained on any data — already maps
noise to images that are smooth and low-frequency. Convolutional layers act
as implicit low-pass filters: to a CNN, the hypothesis space itself leans
smooth before a single gradient step.

For our failure mode this means the network's inductive bias *prefers* the
output that a high-frequency-encoding problem must avoid. A spatially encoded
measurement contains carrier fringes and dispersion signatures; a
smoothness-preferring architecture trained against an $L_2$ loss will treat
them as structure to be smoothed away — stable local minimum, three nearly
identical desaturated channels.

<Widget type="quiz" id="com.github.richbai90.collapse.l4.quiz_dip" />

To feel the scale of what is being asked of the network: this is the
component it must produce *on top of* the DC term, all by itself:

<Widget type="interactive" id="com.github.richbai90.collapse.l4.inter_carrier" />

## Fourier features: moving the target into reach

Spectral bias is not a life sentence. If the network reaches the target
through a **Fourier feature map** instead of the raw coordinate, high-frequency
structure is lifted into the regime the network handles easily (Tancik et
al., 2020):

<Widget type="math" id="com.github.richbai90.collapse.l4.math_fourier_features" />

Instead of asking the network to build $\sin(2\pi f x)$ out of $x$ —
exponentially expensive under the F-principle — you hand it features that
*already oscillate* at the frequencies of interest, and fitting the carrier
becomes a shallow, linearly-reachable operation.

This reframes the real problem nicely: in the spectral decoding task, the
**optics already did the Fourier feature embedding**. The wavelength-dependent
transform $T[y_j;\lambda]$ stamped a high-frequency, wavelength-distinct
carrier onto the measurement. The information is not missing and not even
hard to *represent* — it is simply not rewarded by an $L_2$ loss on
DC-dominated signals, and it fights the smoothness prior on the way in.
[Lesson 5](05-encoded-light.md) makes the forward model precise.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l4.quiz_features_vs_optics" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l4.card_fprinciple" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l4.card_dip" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l4.card_fourier" />