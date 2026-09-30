---
title: A Sensor That Sees Change
description: Event-sensor physics from first principles — the log front-end, signed trigger thresholds, and the contrast signal q_j that everything downstream consumes.
order: 5
---

Frame sensors integrate photons over fixed exposures. An **event sensor**
works differently, and the difference is what makes its Fisher information
unusual. Each pixel is an independent, asynchronous detector with a
*logarithmic front-end* and a *differential comparator*; it emits a
timestamped, signed event when local change crosses a threshold. Three
consequences drive the whole model:

- pixels are **independent** — information can be summed per pixel;
- the front-end is **logarithmic** — the sensor sees *relative* change;
- output is a **stream of timestamps**, not a frame — the statistical model
  will be a point process, not a binned count.

## The logarithmic front-end

Photocurrent $I_j$ at pixel $j$ spans orders of magnitude (a real sensor
handles 120 dB of dynamic range). The front-end compresses it:

<Widget type="math" id="com.github.richbai90.crlb2.math_log_frontend" />

Compression is multiplicative-to-additive: scaling the intensity by a
factor $c$ shifts $L_j$ by $\ln c$ regardless of magnitude. This is why the
sensor responds to *relative* change — a factor-2 change produces the same
shift in shadow as in sunlight.

## The trigger condition

Each pixel holds a **running reference** — the log-intensity at its last
accepted event — and compares the current value against it. Design the
thresholds signed, one per polarity:

<Widget type="math" id="com.github.richbai90.crlb2.math_trigger" />

An **ON event** (polarity $p = +1$) fires when the log-intensity has risen
by at least the positive threshold; an **OFF event** ($p = -1$) when it has
*fallen* by at least the negative threshold. The reference resets to the
current value after every accepted event, so thresholds measure change
*since the last event*, not since the dawn of time.

The signed structure is not cosmetic. A single unsigned inequality with
$\pm C$ — "the change magnitude exceeds some threshold" — admits both
polarities of crossing: an ON excursion could satisfy an OFF condition. The
signed form makes ON and OFF crossings structurally disjoint, and each
polarity keeps its own calibrated threshold scale.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_trigger" />

## From events to temporal contrast

What physical quantity drives these crossings? The derivative of the
log-intensity — the **temporal contrast**:

<Widget type="math" id="com.github.richbai90.crlb2.math_contrast" />

A pixel sitting in a static scene has $q_j = 0$ and stays quiescent: event
sensors are blind to static intensity. All information about parameters
enters through this signal.

## The material-derivative split

Careful with a moving source. The fixed pixel observes intensity change
from two distinct causes at once: the *field itself changing* (intrinsic
brightness or spectral content) and the *field being carried past the
pixel* by source motion. For a translating source with transverse velocity
$v$, the fixed-pixel derivative separates:

<Widget type="math" id="com.github.richbai90.crlb2.math_material" />

Both contributions carry parameter information and both enter the Fisher
analysis through $\partial_\theta q_j$ — motion and intrinsic change are
distinct, additive channels, not one conflated blob.

## What the sensor actually emits

One more modeling step, stated as a design principle rather than derived:
the sensor's marked output — which pixel $j$, which polarity $p$, at which
exact time $t$ — is governed by a **conditional event rate** $r_{jp}(t;
\theta)$. The rate has two physically distinct additive pieces:

<Widget type="math" id="com.github.richbai90.crlb2.math_rate_design" />

The **response term** converts signed contrast into events: $g \ge 0$ is a
smooth nonnegative response whose ideal limit is $g(x) = [x]_+$ — count
every monotonic log-intensity excursion spanning a multiple of the
threshold. The **spurious term** $b_{jp}(I_j) \ge 0$ is parameter-dependent
*illumination* but parameter-*independent* information: thermal leakage and
dark-current triggers that flood the window with events carrying no signal.
Keeping both terms — rather than one blended noise rate — is the physically
correct design, and the [scaling lesson](/course/crlb/scaling) shows why the
distinction is consequential.

The [point-process lesson](/course/crlb/point-process) takes the rate and
builds the likelihood.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_signed_thresholds" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_material_derivative" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_two_noises" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_temporal_contrast" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_reference_reset" />