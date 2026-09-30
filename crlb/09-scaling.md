---
title: Scaling with Light
description: What actually happens to information as illumination grows — three noise domains, a conditional scaling analysis, and the fall of a tempting universal law.
order: 9
---

A historical aside — the one place this course discusses the manuscript that
started it — because the way a scaling claim fails teaches more about
modeling than a dozen correct derivations.

## The claim

An early derivation of this material concluded that the event-sensor error
bound grows linearly with total photon count $N$: decompose the intensity
as $I = N \hat I$ with $\hat I$ the normalized spatial shape, note that the
constant $N$ cancels entirely out of the log-intensity derivative (the
contrast is invariant to absolute brightness), then append a background
*event* rate $\Lambda_0(N)$ that grows with photon count to the rate model.
Since Fisher information goes as the inverse total rate, the conclusion
drawn was:

<Widget type="math" id="com.github.richbai90.crlb2.math_scaling_claim" />

An event sensor, on this account, would perform *best* in dim light —
worse the more light arrives. Paired against a frame sensor whose error
falls as $1/N$, the claim predicted a crossover at low illumination.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_scaling_claim" />

## Why it fails

The premise was never a physical noise law. Appending a background rate
$\Lambda_0(N)$ *after* an illumination-invariant contrast is a modeling
choice — one that manufactures the low-light optimum out of the assumption
that more light means more noise events. Photon statistics say the opposite
at the front-end: photocurrent shot noise has standard deviation
$\propto \sqrt N$, and the logarithmic front-end compresses it, so
log-domain noise *falls* as $\sigma_{\ln I} \propto 1/\sqrt{N}$. Relative
log-domain precision **improves** with illumination.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_shot_noise" />

The ideal model — zero events in the absence of signal — is mathematically
sound for a noiseless circuit. Treating the background as directly
proportional to $N$ is what breaks against real photon statistics.

## The conditional decomposition

The corrected analysis separates every factor into its own domain and
refuses to assert a universal law:

- **Photon domain.** Shot noise on the photocurrent: $\sigma_{\ln I}
  \propto 1/\sqrt N$ after log compression. Relative log-domain precision
  improves with illumination.
- **Circuit domain.** The spurious rate $b_{jp}(I)$ adds
  parameter-independent events; through the denominator of the Fisher
  entries ([spectral lesson](/course/crlb/spectral-fim)) it dilutes
  information per unit time — but its dependence on $I$ is a *calibrated
  device property*, not a universal law.
- **Optical domain.** The background $B_j$ both enables observability
  ($\nabla_s q_j \propto B_j$) and dilutes contrast
  ($\propto 1/(B_j + a f_j)^2$); its optimal level is a *design parameter*
  of the acquisition, bounded below by the observability requirement.

The full information keeps every factor:

<Widget type="math" id="com.github.richbai90.crlb2.math_conditional_scaling" />

No universal $\mathrm{CRLB} \propto N$ exists. Every factor — the
$N$-dependence of $B_j$, $f_j$, $b_{jp}$, threshold noise, pixel bandwidth
— is modeled separately and calibrated. The low-light optimum does not
survive the corrected model; consistent with real measurements, tracking
error bounds fall monotonically as photon counts rise.

## The modeling lesson

When a derivation hands you a free universal law, check what it cost. Here
the cost was collapsing two physically distinct noise sources — optical
background before the log, circuit noise after contrast — into one rate
appended at the end, then letting it scale with the world. The
[sum-before-log lesson](/course/crlb/sum-before-log) established the
distinction; this lesson shows the conclusion it guards against.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_scaling_retraction" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_log_compression" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_three_domains" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_shot_noise" />