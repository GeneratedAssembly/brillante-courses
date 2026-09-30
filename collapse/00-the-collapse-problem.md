---
title: The Collapse Problem
description: Two models, one pathology — rebuilding the mean and discarding the signature. What this course builds intuition for, and in what order.
order: 0
---

You train a network to do something that sounds easy: extract a single color
channel from a grayscale image. The channel contributed to that grayscale
value, so the information is in there. The network trains to a suspiciously
low loss — and its output is a *less-contrasting version of the input*. Not a
color channel. A gray clone.

This is the toy problem. The real problem behind it is nastier: decode a
continuous spectral signal from a wavelength-dependent, spatially transformed
encoded black-and-white measurement, $\hat y_j = T[y_j;\lambda]$. Three
wavelengths of interest, ground truth encoded in RGB space — and the trained
model reproduces the failure exactly, except now it *removes the
transformation signature*: the wavelength-dependent spatial pattern the optics
deliberately stamped onto the measurement.

## The same collapse, twice

Both models exhibit the same behavior: instead of producing the distinct
target, they produce something that *shares the dominant statistics of the
input* — the average-like component — and quietly discards everything that
makes the target different.

The claim of this course is that this is not one bug but a chain of three
forces that all point the same way:

1. **The loss.** Squared-error regression minimizes risk by predicting the
   *conditional mean* — and when many different targets are consistent with
   the same input, the mean is a blend that is none of them. This produces
   the "gray wall."
2. **The signal.** Measured in squared error, almost all the energy of a
   natural signal sits at low frequencies. A mistake in the DC level costs
   hundreds of times more loss than a mistake in a weak high-frequency
   carrier — Parseval's accounting.
3. **The learner.** Gradient descent fits low frequencies first and
   convolutional architectures lean smooth even before training. The learner
   inherits the bias the loss rewards.

Then we put the real problem on the table — encoded light, overlapping point
spread functions, near-null forward operators — and see that it is the same
collapse wearing optics. Finally we walk the fix taxonomy the literature
actually uses, matched to the failure each fix targets.

<Widget type="quiz" id="com.github.richbai90.collapse.l0.quiz_diagnosis" />

## Reading

Two of the papers this course is built around, if you want the sources early:

<Widget type="resource-link" id="com.github.richbai90.collapse.l0.link_colorization" />

<Widget type="resource-link" id="com.github.richbai90.collapse.l0.link_spectral_bias" />

## The route

- [The Gray Wall](01-gray-wall.md) — why L2 regression outputs the
  conditional mean, and why that is a blend no example has.
- [One Gray, Many Colors](02-one-gray-many-colors.md) — metamerism:
  the projection that makes the conditional multimodal in the first place.
- [Where the Error Energy Lives](03-error-energy.md) — Parseval,
  DC dominance, and the constructive-versus-cancelling gradient arithmetic.
- [Spectral Bias](04-spectral-bias.md) — the F-principle and the
  deep image prior: networks are low-pass filters by construction.
- [Encoded Light](05-encoded-light.md) — the real forward model,
  transfer-function overlap, and null-space averaging.
- [Forcing the Signature](06-forcing-the-signature.md) — the fix
  taxonomy: classification, adversarial and perceptual losses, re-projection,
  decorrelation, unrolled architectures, Fourier features.

Each lesson ends with a self-check quiz set and recall cards. The math is kept
to what the intuition needs; every equation carries a collapsible definitions
panel so no symbol is ever load-bearing from memory.