---
title: The Spectral Fisher Matrix
description: The rate chain rule with polarity, the spectral Fisher block, its three regimes, identifiability caveats, and nuisance elimination.
order: 8
---

Every ingredient now exists: the sensitivity of contrast to the spectrum
([sum-before-log](/course/crlb/sum-before-log)), the marked event rate
([the sensor lesson](/course/crlb/sensor)), and the Fisher identity for
point processes ([the previous lesson](/course/crlb/point-process)). Assemble
them into the matrix this course has been driving toward.

## The rate chain rule

Parameter dependence enters the rate through the contrast $q_j$. For the
ideal response $g(x) = [x]_+$ on a branch where $p\,q_j$ does not change
sign:

<Widget type="math" id="com.github.richbai90.crlb2.math_rate_chain" />

Two subtleties live in this one line:

- the **polarity factor** $p$ flips $\partial_s r$ between ON and OFF
  streams — the sign of the rate derivative genuinely depends on polarity;
- because the Fisher information uses *products* $\partial_i r\,
  \partial_j r$, the sign cancels in the information — while the **branch**
  ($q_j > 0$ vs $q_j < 0$) remains through $r_{jp}$ in the denominator.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_polarity_branches" />

## The spectral Fisher block

Substituting the sensitivity engine $\nabla_s q_j$ and the chain rule into
the binned FIM, for the ideal response on the positive branch
($r_{j+} = b_{j+}(I_j) + q_j/C_{j+}$):

<Widget type="math" id="com.github.richbai90.crlb2.math_spectral_fim" />

Three regimes are visible directly in the equation:

1. **$B_j \to 0$** kills the block — the degeneracy of the
   sum-before-log lesson;
2. **large $B_j$** quenches sensitivity through the $(B_j + a f_j)^2$
   denominator — background dilution;
3. **the denominator $r_{j+}$** couples the block to the spurious circuit
   rate, which dilutes information without carrying any signal.

The entry is nonzero exactly when the encoding is nonzero, the probe moves
the code non-proportionally ($\dot a \neq 0$ against a nonzero reference),
and the rate is finite.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_spectral_entry" />

## Identifiability: when can the matrix be inverted at all?

Two structural caveats govern whether $J$ carries usable information about
$s$.

**Kernel.** With fixed $H$ and scalar gating, all data depend on $s$ only
through $H s$. Whatever lies in $\ker H$ is invisible to any estimator — the
rank obeys $\operatorname{rank} J \le \operatorname{rank} H$. A full
spectral cube requires adequate independent temporal coding (or a justified
lower-dimensional scene model). The correct diagnostic for a mask design is
**the rank of the event Jacobian** — not how visually distinctive the PSF
looks.

**Gauge.** With zero reference *and* brightness-independent event noise,
the map $s \mapsto c\,s$ leaves the ideal contrast unchanged even under
dithering. The recoverable object is the **normalized spectral shape**
unless a scale gauge is fixed or an intensity anchor is added. Bounds are
meaningful only in identifiable, appropriately scaled coordinates.

## Nuisance elimination

In practice the joint parameter vector mixes the unknown spectrum $s$ with
nuisance parameters $\nu$ — motion, calibration, mask geometry. The joint
Fisher information partitions into blocks, and the effective information
about $s$ after profiling or marginalizing the nuisance is the **Schur
complement**:

<Widget type="math" id="com.github.richbai90.crlb2.math_schur" />

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_schur" />

The off-diagonal blocks $J_{s\nu}$ quantify cross-coupling between the
spectrum and, e.g., mask geometry — the price of jointly estimating things
that talk to each other.

## Reconstruction: why the reference must never be zero

For a settled gate transition $a: 0 \to 1$ with a symmetric threshold, the
signed event sum at pixel $j$ approximates:

<Widget type="math" id="com.github.richbai90.crlb2.math_reconstruction" />

Polarity-weighted threshold counts recover the *encoded code* $f_j$ — but
only relative to the reference. Never set the baseline to zero inside the
logarithm: $B_j$ is what converts event counts into a spectral measurement,
and its shot noise belongs in the calibration.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_sign_cancellation" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_schur" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_reconstruction" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_spectral_block" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_kernel_gauge" />