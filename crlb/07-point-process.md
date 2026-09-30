---
title: Events as a Point Process
description: Building the likelihood for exact timestamps and polarities — the marked point process, the survival integral, and the exact binned equivalence.
order: 7
---

The forward model produces a conditional rate $r_{jp}(t;\theta)$ for events
at pixel $j$, polarity $p$, time $t$. What is the *likelihood* of an
observed event stream under that rate? Binning and counting is the
reflex — and it silently discards the stream's most valuable structure:
exact timing.

## Why not just count?

A binned PMF assigns probability to *how many* events landed in each bin.
Two data are conflated: a bin with ten events spread evenly and a bin with
ten events bunched into one microsecond are scored identically. The
timestamps carry parameter information the counts alone cannot. Worse, a
bin with **zero** events still carries information — "nothing happened
here" constrains the rate — but the PMF's $k=0$ term is easy to
misread as uninformative silence.

The correct model treats the stream for what it is: a **marked point
process** — random event times, each carrying a mark $(j, p)$.

## The likelihood

For events $e_k = (j_k, p_k, t_k)$ observed on a window $[0, T]$, the
log-likelihood of a regular simple point process is:

<Widget type="math" id="com.github.richbai90.crlb2.math_pointprocess_ll" />

Two terms with two jobs:

- $\sum_k \ln r_{j_k p_k}(t_k;\theta)$ — each observed event contributes the
  log of the conditional rate *at its exact timestamp and polarity*;
- $-\int_0^T \sum_{j,p} r_{jp}(t;\theta)\,\mathrm{d}t$ — the **survival
  (compensator) integral**, which scores every interval in which *no* event
  occurred. Quiet time is evidence too.

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_survival" />

## The score and the point-process FIM

Differentiating the likelihood gives the score as a compensated integral:

<Widget type="math" id="com.github.richbai90.crlb2.math_pointprocess_score" />

The compensated increment
$\mathrm{d}N_{jp}(t) - r_{jp}(t;\theta)\,\mathrm{d}t$ has conditional mean
zero — $\mathbb{E}[\mathrm{d}N_{jp}(t) \mid \mathcal{H}_t] =
r_{jp}\,\mathrm{d}t$ — which is the zero-mean score property
([score lesson](/course/crlb/score)) reborn in continuous time. Distinct
marks $(j,p)$ have zero quadratic covariation, so the score covariance
collapses to a single integral — the **point-process Fisher information**:

<Widget type="math" id="com.github.richbai90.crlb2.math_pointprocess_fim" />

This is the event-stream form of everything the course built up: information
integrated over exact timestamps, polarities entering through the marked
rates, the sign derivative included ([the sensor lesson](/course/crlb/sensor)
designed for this).

## The binned stage, rehabilitated

The continuous FIM involves an expectation over a point process — awkward.
Partition $[0,T]$ into $n$ bins of width $\Delta t$ and suppose the rate is
constant on each bin. Then the marks decouple into independent Poisson
counts $K_{jp,b}$ with means $\mu_{jp,b} = \Delta t\, r_{jp,b}$, and the
[Poisson lesson](/course/crlb/poisson) applies verbatim:

<Widget type="math" id="com.github.richbai90.crlb2.math_binned_fim" />

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_binned_fim" />

Because $\mu_{jp,b} = \Delta t\, r_{jp,b}$ with $\Delta t$ constant, the
factorization is exact — and for piecewise-constant rates the continuous
integral evaluates term-by-term over the bins, so the two forms **coincide
exactly**:

<Widget type="math" id="com.github.richbai90.crlb2.math_binned_equals_continuous" />

For smooth $r$, the binned expression is the Riemann-sum stage of the
continuous one; the idealized smooth model is recovered in the refinement
limit. Nothing was wrong with counting — what was wrong was counting the
wrong thing. Binned rates of a marked point process (means carrying the
optical background) vs raw event counts of a bare log-derivative.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_bin_refinement" />

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_survival_integral" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_binned_exact" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_point_process" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_compensator" />