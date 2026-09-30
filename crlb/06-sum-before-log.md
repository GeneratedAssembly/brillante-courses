---
title: Sum Before Log
description: The hyperspectral forward model — why band intensities and background must be summed before the logarithmic front-end, the degeneracy that proves it, and the sensitivity engine.
order: 6
---

The statistical machine is ready. Now build the optical model it will
consume — and design it so the sensor's log front-end does not destroy the
very quantity we want to estimate.

## Hyperspectral encoding

The scene carries a spectrum we want: let $s \in \mathbb{R}^K$ be the vector
of **spectral band coefficients** (for a spatially structured scene, stack
$R$ spatial cells × $K$ bands into $s \in \mathbb{R}^{RK}$; the algebra
below is unchanged). A **diffractive phase mask** — an engineered surface
that maps wavelength to spatial pattern — converts the spectrum into a
calibrated spatial intensity code:

<Widget type="math" id="com.github.richbai90.crlb2.math_encoding" />

The **encoding vector** $h_j(t) \in \mathbb{R}^K$ collects how strongly each
spectral band contributes at pixel $j$. The mask is the physical
information channel: its design fixes which spectral directions the sensor
can see at all (the [identifiability lesson](/course/crlb/spectral-fim)
returns to this).

The **optical background** $B_j(t) \ge 0$ collects everything else hitting
the pixel in the photon domain — ambient light, backlight bleed,
out-of-focus fluorescence, dark current. It is a property of the *optical
stage*.

## The temporal probe

An event sensor is blind to static intensity ([the sensor lesson](/course/crlb/sensor)),
so the scene must be probed with a known **temporal modulation** $a(t) \ge
0$ — gating, dithering, or motion. The gated intensity at pixel $j$:

<Widget type="math" id="com.github.richbai90.crlb2.math_probe" />

The encoded signal $f_j \triangleq h_j^{\mathsf T} s$ rides on the probe
amplitude, against the additive background.

## The correction: sum before log

The front-end compresses *total* intensity. The band contributions and the
background must therefore be summed **before** the logarithm — not after:

<Widget type="math" id="com.github.richbai90.crlb2.math_sum_before_log" />

Why does placement matter? Follow the contrast signal through the log:

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_sum_before_log" />

The corrected contrast:

<Widget type="math" id="com.github.richbai90.crlb2.math_contrast_corrected" />

The denominator is the whole point. Because the sum sits inside the
logarithm, $f_j$ survives into it — the encoded spectrum does **not** cancel
out of the contrast.

## The degeneracy that proves it

What if the background is truly absent? Set $B_j = 0$:

<Widget type="math" id="com.github.richbai90.crlb2.math_degenerate" />

The encoded spectrum cancels from the contrast *entirely*. A blinking
target on a true-black background yields **zero sensitivity** to $s$,
regardless of the mask design — common brightness modulation cannot make a
static spectrum visible.

Why, then, do laboratory demonstrations of exactly this work? Because a
physical "off" state is never true zero: monitor bleed and ambient light
provide a nonzero $B_j$. The experiment was *gating against a calibrated
additive reference* all along — which is precisely what the model demands.

## The sensitivity engine

For $B_j > 0$, differentiate the contrast with respect to a spectral
coefficient. The quotient rule gives:

<Widget type="math" id="com.github.richbai90.crlb2.math_qsens" />

Read it three ways:

1. **Observability:** sensitivity survives iff $B_j > 0$ — the degeneracy
   reappears as the $B_j \to 0$ limit.
2. **Dilution:** the factor $B_j / (B_j + a f_j)^2$ *falls* as background
   grows — the background that makes the code visible also dilutes it.
3. **Geometry:** the gradient points along $h_j$, the encoding vector —
   mask design directly shapes the information geometry.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_dilution" />

The sensitivity peaks exactly at $B = a f$: the background matched to the
signal size. Below it, sensitivity dies for lack of a reference; above it,
sensitivity dies by dilution. Zero is forbidden — but more is not better.

<Widget type="slider" id="com.github.richbai90.crlb2.slider_background" />

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_sum_before_log" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_degenerate" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_encoding_vector" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_two_domains" />