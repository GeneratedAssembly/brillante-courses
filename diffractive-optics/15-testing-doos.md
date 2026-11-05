---
title: Testing Diffractive Optical Elements
description: Metrology — what the stylus, the AFM, the SEM, and the interferometer can and cannot see — plus efficiency tests and the quantitative way fabrication errors wreck a design.
order: 15
section: testing
---

Two questions must both be answered: **did I make what I designed?**
(metrology: feature widths, transition locations, depths, sidewall verticality,
edge rounding, roughness) and **does it work?** (optical performance). Geometry
measurements troubleshoot the process, but they cannot catch a *wrong design* —
hence both categories, always.

## The metrology toolkit

<Widget type="flashcard" id="com.github.richbai90.diffractive.test.card-metrology" />

- **Optical microscopy**: the everyday tool — gross defects and quick lateral
  widths with an eyepiece reticle or video calipers. Diffraction-limited, poor
  at depth.
- **Mechanical profilometry**: a stylus (ball-on-cone, or a bar for tracing
  lens apices) dragged across the surface; depth accuracy **~10 Å on large
  features**, scan ranges µm to mm. Two traps: the tip can **damage** resist
  (too light and it *skips*), and the trace is the **convolution of the profile
  with the tip geometry** — tip radii 2–12.5 µm with shank angles ≥120° ride
  over trenches and corners, reading *shallow* on narrow features.
- **AFM**: same idea, but sensing atomic forces with a tip **< 10 nm**, no
  contact "except by accident"; images individual atoms. Scan areas shrink to
  <1 µm–tens of µm; long flared tips probe sidewalls.
- **SEM**: electrons at 1000 V have λ ≈ 0.4 Å (scaling as $V^{-1/2}$); 60,000×
  shows 0.5-µm and sub-0.5-µm features. Insulating DOEs need a Au/Pt overcoat
  (charge-up), and true **cross-sections require pairing with a FIB cut**.
  Viewing at tilt means apparent widths must be angle-scaled.
- **Phase-shifting interferometry (PSI)**: reference and test wavefronts given
  a time-varying phase shift; the **height is recovered point-by-point from
  recorded interferograms** — vertical resolution in **angstroms**, lateral
  ~1 µm. The finite focused spot (like a stylus) blurs small features, and
  sidewalls need high-NA objectives. Substrates get checked the same way:
  fringe distortion ⇒ peak-to-valley and rms wavefront error (typical wafers
  λ/4 to λ/20 rms).

<Widget type="quiz" id="com.github.richbai90.diffractive.test.quiz-stylus" />

## Optical performance tests

- **Scatterometer**: pinhole + detector scanned by computer (LabView) in the
  near or far field — measures light where it should go **and where it must
  not** (stray scatter). Precision = pinhole size × stage steps (a 2-µm pinhole
  example); alignment is finicky and slow.
- **CCD arrays**: fast 2-D irradiance in the focal plane; 8–16-bit digitizers
  (256–65,536 levels); pixel size limits precision, arrays are a few mm on a
  side. The workhorse for **uniformity** of spot patterns.
- **Rotating slit scanner (RSS)**: a slit several mm long, 0.5–1 µm wide, on a
  drum spinning 10–20×/s with a detector inside — micrometer-sampled 1-D
  profiles, far better resolution than a CCD. But it **integrates along the
  slit**, so discrete 2-D patterns get misleading numbers; use it for 1-D or
  circularly symmetric distributions. Worked example: a 1 × 7 Dammann grating,
  period 200 µm at 632.8 nm, measured 15.8 mm away — order spacing
  $z\lambda/\Lambda = 15.8 \times 0.6328/200 \approx 50\,\mu$m, and since
  $\Lambda^2/\lambda = 63$ mm, genuinely near-field.
- **Array testing**: pinhole detector stepped to each spot's center measures
  power per order; mounted on a fixed post with the *wafer* on the stage, it
  tests every die. Indirect-efficiency trick: a lens **designed for 650 nm
  tested at 670 nm** ($\alpha = 650/670 = 0.970$) still shows a kinoform at
  ~99.7% first-order efficiency — while multilevel devices degrade faster,
  because their quantization steps were sized for 650.

<Widget type="quiz" id="com.github.richbai90.diffractive.test.quiz-rss" />

## Fabrication errors, quantitatively

The error taxonomy: **systematic** errors — etch depth, feature size, corner
rounding, transition positions, grating period, nonvertical sidewalls,
mask-to-mask misalignment — **redistribute light among orders**; **random**
error — surface roughness — does not change relative orders, it **robs all of
them equally into the background**.

**Binary π grating (the 1 × 2 splitter)**: ideal = 0% in zero order, 40.5% in
each ±1. A ±10% *depth* error moves first orders to ~39.5% and leaks ~2% into
the zero order — depth is forgiving, as the sinc² law predicts:

<Widget type="interactive" id="com.github.richbai90.diffractive.test.int-depth" />

<Widget type="interactive" id="com.github.richbai90.diffractive.test.int-zero" />

**Binary 1 × 5 Dammann grating** (perfect: 15.48% per central order, 77.4%
total): +10% depth error ⇒ zero order balloons to 17.6%, the other four sit at
15.1% — bad. But shifting **one transition point by 3% of the period**
($x_4$: 0.73532 → 0.70532) does *even more damage* than the depth error.
General rules: depth errors raise the zero order and uniformly depress the
rest (binary); multilevel fanouts get nonuniformity across **all** orders from
depth errors plus misalignment; for **lenses**, errors cut focal-spot power
and the Strehl ratio.

<Widget type="quiz" id="com.github.richbai90.diffractive.test.quiz-error" />

The closing tradeoff links back to process choice: gray-scale and direct-write
parts have **nonvertical sidewalls and dose-shape errors but no alignment
errors**; binary optics has **sharp walls, dose robustness, and alignment
errors**. "The type, effect, and likelihood of fabrication errors must be
weighed against cost and performance requirements."

<Widget type="flashcard" id="com.github.richbai90.diffractive.test.card-errorrule" />

<Widget type="quiz" id="com.github.richbai90.diffractive.test.quiz-rough" />
