---
title: Forcing the Signature
description: The fix taxonomy — classification for multimodal conditionals, re-projection and decorrelation for stripped signatures, unrolling and Fourier features for the learner's bias.
order: 6
section: real
---

Every lesson so far explained a different face of one collapse. This lesson
organizes the literature's fixes by *which failure each one targets* —
because they are not interchangeable, and picking the wrong family of fixes
is the most expensive mistake in this problem class.

## Two failure classes

| Symptom | Root cause | Where |
|---|---|---|
| Low-contrast copy of the input; averaged colors | Conditional mean over a multimodal conditional (metamers) | Lessons 1–2 |
| Signature stripped; near-identical output channels | Energy asymmetry, cancelling gradients, spectral bias, near-null forward operator | Lessons 3–5 |

A collapsed model may exhibit both at once. Diagnose before prescribing.

## Fixing multimodality

**Regression → classification.** Quantize the target channel into discrete
bins and train a softmax with cross-entropy instead of regressing a scalar
(Zhang et al., 2016, with class-balancing to boost rare saturated colors, and
annealed sampling at inference). Cross-entropy does not average: it
concentrates probability mass, so two plausible modes stay two modes instead
of blending into the valley. Note that switching $L_2 \to L_1$ does *not* do
this — $L_1$'s optimum is the conditional median, which for a bimodal
conditional is still some arbitrary point of the in-between plateau.

**Adversarial training.** A discriminator penalizes outputs that look like
washed-out scaled inputs, matching *distributions* rather than values
(Goodfellow et al., 2014) — the generator is no longer rewarded for the mean.

**Perceptual loss.** Penalize differences in a high-level feature space
rather than pixel space (Johnson et al., 2016); high-frequency structure
stops being cheap to average away. Structure-sensitive pixel metrics like
SSIM (Wang et al., 2004) push the same direction.

**Change the representation.** Predict chromaticity ($a/b$ in CIE Lab, or
$C_b/C_r$) instead of raw channel intensities, or predict the residual $D = C
- Y$ or ratio $C/(Y + \epsilon)$. These remove the trivial shortcut $\hat C
\approx k \cdot Y$ *by construction* — the network must learn what makes the
channel distinct from the luminance profile.

<Widget type="quiz" id="com.github.richbai90.collapse.l6.quiz_fix_classification" />

## Fixing the signature: re-projection

For the stripped-signature failure, the decisive trick is to stop grading the
output only in the target domain, and grade its **consistency with the
measurement**:

<Widget type="math" id="com.github.richbai90.collapse.l6.math_reproject" />

The re-encoding term passes the predicted channels back through the known
forward operator $T_\lambda$ — simulated wave optics, diffraction integrals,
or measured PSFs — and compares against the *actual* input $g$. Why this
works is worth stating carefully: the average-channel shortcut fails this
check, because smooth outputs re-encode to a smooth $g'$ that cannot
reproduce the encoded fringes in $g$. The loss constrains *consistency*, not
closeness to a mean. It does not out-shout the DC band in gradient
magnitude — it makes the DC-only solution *invalid*.

## Decorrelate the outputs

A collapsed spectral reconstruction has three near-identical channels —
pairwise correlation close to 1. Penalize exactly that:

<Widget type="math" id="com.github.richbai90.collapse.l6.math_decorr" />

Forcing cross-channel decorrelation obliges the network to assign unique
spatial structure to each band, attacking the "three copies of the average"
collapse directly. The same reasoning motivates the correlation-minimization
penalty on the toy problem — penalize the similarity between input $Y$ and
output $\hat C$ so the identity basin is no longer comfortable.

## Unrolled architectures and adjoint pre-filtering

Instead of a black-box U-Net, use networks whose layers *are* iterations of a
classical reconstruction algorithm: ADMM-Net, learned ISTA, learned
primal-dual. Each block applies the real forward operator or its adjoint
$T_\lambda^{\mathsf{T}}$ to the measurement residual, so the encoding
signature is physically wired into the network's computation — it cannot be
stripped without failing the block's own data-fidelity step. A lighter-weight
variant: pre-filter the input with $T_\lambda^{\mathsf{T}}[g]$ so the network
starts from demultiplexed channels instead of raw encoded fringes. And where
the learner's own spectral bias is the binding constraint, Fourier features
([Lesson 4](04-spectral-bias.md#fourier-features-moving-the-target-into-reach))
move high-frequency structure into reach.

<Widget type="stepper" id="com.github.richbai90.collapse.l6.stepper_diagnose" />

<Widget type="quiz" id="com.github.richbai90.collapse.l6.quiz_fix_signature" />

## Reading

<Widget type="resource-link" id="com.github.richbai90.collapse.l6.link_gan" />

<Widget type="resource-link" id="com.github.richbai90.collapse.l6.link_tancik" />

<Widget type="resource-link" id="com.github.richbai90.collapse.l6.link_admm" />

<Widget type="resource-link" id="com.github.richbai90.collapse.l6.link_primaldual" />

<Widget type="resource-link" id="com.github.richbai90.collapse.l6.link_ssim" />

## The meta-lesson

The unifying sentence of this course: **your loss is your model's real
objective, and MSE's objective is the conditional mean of a DC-dominated
projection.** Every fix above works by changing what the objective can
distinguish — between modes (classification, adversarial), between
frequencies (perceptual losses, Fourier features), between the measurement
and its average (re-projection), or between output channels
(decorrelation). The network was never broken; it was doing exactly what it
was paid for.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l6.quiz_matching" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l6.card_reproject" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l6.card_decorr" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l6.card_unrolling" />