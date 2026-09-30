---
title: Machine-Verified in Lean 4
description: Every quantitative identity of the course, formalized in Lean 4 with Mathlib — sorry-free. The theorem-to-equation map, what is proven, and what is deliberately not.
order: 10
---

The derivation does not rest on careful reading alone. Its quantitative
skeleton is formalized and proven in **Lean 4** (toolchain `v4.30.0-rc2`)
against the Mathlib library, with **no axioms beyond Lean's standard three**
(`propext`, `Classical.choice`, `Quot.sound`) and no `sorry` placeholders.

## What "machine-verified" means

A Lean proof leaves no room for algebra slips: every identity below is
checked from the axioms of mathematics themselves. What it does *not* do is
verify the physical modeling — the response function $g$, the spurious rate
$b_{jp}(I)$, threshold noise, and pixel bandwidth remain calibrated inputs.
The theorems certify the **information identities**; the hardware model is
out of scope by design.

## Layer 1 — the Poisson count facts

Built by direct manipulation of the exponential series: normalization,
mean, second factorial moment, second moment — then converted to
measure-theoretic statements about `poissonMeasure` and the Fisher
information in both the bin-mean and the rate parametrization.

<Widget type="math" id="com.github.richbai90.crlb2.math_lean_poisson" />

<Widget type="math" id="com.github.richbai90.crlb2.math_lean_poisson_fim" />

These certify the Poisson algebra of the [Poisson lesson](/course/crlb/poisson):
normalization, the mean, and $I(\mu) = 1/\mu$, $I(\Lambda) = \Delta t/\Lambda$.

## Layer 2 — the joint law

The joint law of independent bins is built as `Measure.pi` of per-bin
Poisson measures; coordinate marginals come from the projection lemma
`integral_comp_eval`. From linearity of expectation plus marginal means
alone:

<Widget type="math" id="com.github.richbai90.crlb2.math_lean_zero_mean" />

Notably, independence enters **only** through the construction of the joint
law — the FIM identity itself uses first moments, exactly as the
[Poisson lesson](/course/crlb/poisson) emphasized.

## Layer 3 — differentiation and the continuum limit

Differentiating the log-likelihood: the score equals the first derivative,
and the second derivative lands on the Fisher entries. Then the reduction of
the continuous-time rate integral to the binned sum for piecewise-constant
intensities — *exact* in that regime:

<Widget type="math" id="com.github.richbai90.crlb2.math_lean_continuous" />

This is the machine-verified form of the exact binned↔continuous
coincidence of the [point-process lesson](/course/crlb/point-process).

## Layer 4 — the forward-model derivatives

The derivatives of the optical stage: quotient-rule sensitivity, the
zero-background degeneracy, the rate chain rule, polarity-sign cancellation,
and the per-bin spectral entry.

<Widget type="math" id="com.github.richbai90.crlb2.math_lean_forward" />

The per-bin entry $\Delta t\, q'^2 / (C\,(C\Lambda_0 + q))$ is the
single-bin specialization of the spectral block of the
[spectral lesson](/course/crlb/spectral-fim).

## The theorem-to-equation map

| Lean theorem | Statement | Course lesson |
|---|---|---|
| `poisson_sum_one` | $\sum_k \mu^k e^{-\mu}/k! = 1$ | [Poisson](/course/crlb/poisson) |
| `poisson_mean` | $\mathbb{E}[K] = \mu$ | [Poisson](/course/crlb/poisson) |
| `poisson_second_moment` | $\mathbb{E}[K^2] = \mu^2 + \mu$ | [Poisson](/course/crlb/poisson) |
| `poisson_fisher_mu` | $I(\mu) = 1/\mu$ (bin-mean coordinate) | [Poisson](/course/crlb/poisson) |
| `poisson_fisher_rate` | $I(\Lambda) = \Delta t/\Lambda$ | [Poisson](/course/crlb/poisson) |
| `jointPM_coord_mean` | joint-law marginal $\mathbb{E}[K_b] = \mu_b$ (projection/Fubini) | [Point process](/course/crlb/point-process) |
| `score_zero_mean` | $\mathbb{E}[\partial_i \ell] = 0$ (multi-bin) | [Score](/course/crlb/score) |
| `deriv_logL_score` | $\partial_\theta \ell$ = score (multi-bin) | [Score](/course/crlb/score) |
| `deriv_score_dScore` | $\partial_\theta^2 \ell$ = Fisher entries | [Fisher](/course/crlb/fisher) |
| `fam_fim` / `fam_fim_logL` | $-\mathbb{E}[\partial_i^2 \ell] = \sum_b (\partial_i \mu_b)^2/\mu_b$ | [Point process](/course/crlb/point-process) |
| `continuous_fim` | $\int_0^T (\partial_i r)^2/r\,\mathrm{d}t = \sum_b \Delta t\,(\partial_i r_b)^2/r_b$ | [Point process](/course/crlb/point-process) |
| `quotient_rule_general` | $\partial_s q_j$ for general encoded $f$ | [Sum before log](/course/crlb/sum-before-log) |
| `quotient_rule_sensitivity` | $\partial_s q_j = \dot a B_j h_j/(B_j + a f_j)^2$ | [Sum before log](/course/crlb/sum-before-log) |
| `degenerate_zero_ref` | $B_j = 0 \Rightarrow \partial_s q_j = 0$ | [Sum before log](/course/crlb/sum-before-log) |
| `rate_chain_ideal` | $\partial_s r_{j+} = p\,(\partial_s q_j)/C_{j+}$ | [Spectral FIM](/course/crlb/spectral-fim) |
| `fim_sign_invariant` | squared rate derivative is polarity-independent | [Spectral FIM](/course/crlb/spectral-fim) |
| `ideal_fim_entry` | per-bin spectral entry $\Delta t\,q'^2/(C(C\Lambda_0 + q))$ | [Spectral FIM](/course/crlb/spectral-fim) |

The CRLB inequality itself ([Fisher lesson](/course/crlb/fisher)) is carried
into the formalization's foundations rather than re-proven there, and the
continuous-time marked point process form for smooth intensities is stated
as the refinement limit of the binned stage — both deliberate scope
boundaries.

## Where this leaves you

The full arc: probability toolkit → score → Fisher information → Poisson
counts → the event sensor's physics → sum before log → the point-process
likelihood → the spectral Fisher matrix → conditional scaling — every
quantitative step machine-checked. The original manuscript this material
revised exists as history; the derivation now stands on its own.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_lean_scope" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_lean_scope" />