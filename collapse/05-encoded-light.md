---
title: Encoded Light
description: The real forward model — wavelength-dependent transport, overlapping transfer functions, and null-space averaging. The same collapse wearing optics.
order: 5
section: real
---

Now the real problem. A single grayscale measurement must carry several
spectral channels, encoded *spatially* by wavelength-dependent optics. When
the reconstruction model trained on it outputs three nearly identical,
signature-free channels, it is running the Lesson 1–4 playbook — but the
forward model adds a structural reason of its own: **the measurement barely
distinguishes the channels in the first place**.

## The forward model

An optical system maps a spatio-spectral distribution onto a 2-D sensor
through a wavelength-dependent transport operator — diffractive phase masks,
chromatic aberration, rainbow apertures. Each wavelength's energy is blurred
and shifted by its own point spread function, and the sensor sums the result:

<Widget type="math" id="com.github.richbai90.collapse.l5.math_forward" />

The transform $T_\lambda$ is the encoding: it is *supposed* to stamp a
wavelength-distinct spatial signature onto each channel so that one gray
frame can be untangled into three. The reconstruction network must invert
$g \mapsto \{I_{\lambda_1}, I_{\lambda_2}, I_{\lambda_3}\}$.

## Overlapping transfer functions

Whether that untangling is possible is decided in Fourier space. Each PSF
$h_\lambda$ has a transfer function $H_\lambda = \mathcal{F}\{h_\lambda\}$
describing which spatial frequencies it passes. If the three PSFs share
spatial support and most of their energy sits near DC, their transfer
functions overlap heavily — and the measurement stops separating the bands.
Watch the combined response as the bands separate:

<Widget type="interactive" id="com.github.richbai90.collapse.l5.inter_overlap" />

When the two bumps merge, the sensor reports one blended number per
frequency: no inverse operator — learned or otherwise — can say which band
contributed what. The information about *which band is where* has been
destroyed by the optics, not by the network. When the bumps only *partially*
overlap, the separation is possible but expensive — and that is exactly the
regime where $L_2$ training gives up.

## From optics to a matrix

Discretize and the structure becomes a matrix statement. One stepper:

<Widget type="stepper" id="com.github.richbai90.collapse.l5.stepper_nullspace" />

This is **null-space averaging**: the network projects the solution onto the
dominant singular directions — the spatial mean across wavelengths — and
strips the high-frequency signature as if it were noise. Notice how cleanly
the Lesson 3 and Lesson 4 results dock onto this: the signature lives along
small singular values (little energy), its gradients cancel (oscillating
residuals), and the architecture would rather smooth it anyway (spectral
bias). Three mechanisms, one direction of failure.

How badly the measurement entangles two channels is quantified by their
correlation $\rho$. For the canonical two-channel case the amplification of
the channels' *difference* direction under exact inversion is:

<Widget type="slider" id="com.github.richbai90.collapse.l5.slider_noise" />

At $\rho = 0.9$ the difference direction is amplified $10\times$ — while the
*sum* direction is damped ($1/(1+\rho) \approx 0.53$). Exact inversion
amplifies precisely the component the loss ignores. An $L_2$-trained network,
graded by energy, does the opposite of what inversion needs.

<Widget type="quiz" id="com.github.richbai90.collapse.l5.quiz_conditioning" />

<Widget type="quiz" id="com.github.richbai90.collapse.l5.quiz_signature" />

## The through-line

You observed that the spectral decoding model's predictions "remove the
transformation signature." Now you can say precisely why:

- the signature is **present** in $g$ — the optics encoded it;
- it is **weak** — overlapping transfer functions push it into low-singular-
  value territory, where it contributes almost nothing to the measurement's
  energy;
- it is **unrewarded** — Parseval's accounting and cancelling gradients mean
  $L_2$ barely grades it;
- it is **unwelcome** — the architecture's smoothness prior prefers outputs
  without it.

None of that is specific to optics. It is the gray wall of [Lesson
1](01-gray-wall.md), rebuilt one level down: a well-posed-looking
inverse problem whose loss landscape has a wide, comfortable basin labeled
"average." What is new here is the tool that fixes it: the forward model
itself. [Lesson 6](06-forcing-the-signature.md) builds the fix
taxonomy around it.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l5.quiz_throughline" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l5.card_psf" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l5.card_nullspace" />