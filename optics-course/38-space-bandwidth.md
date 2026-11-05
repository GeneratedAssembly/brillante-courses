---
title: The Space-Bandwidth Product
description: Counting the pixels an optical system can actually deliver — field area times passband area — and what the count says about matching lenses to sensors, and the hard ceiling on superresolution.
order: 38
section: imaging-systems-resolution
---

Optical instruments trade two currencies: where (field of view) and how
fine (resolution). The **space-bandwidth product** (SBP) is their
product — the number of independent pixels an instrument can deliver —
and it is the quantity that decides whether a lens outruns its sensor,
whether a zoom really creates information, and why superresolution has
a hard ceiling.

## Counting the pixels

Each image dimension carries spatial frequencies out to the diffraction
cutoff, so the countable degrees of freedom are field area times
passband area:

<Widget type="math" id="com.github.richbai90.optics.space-bandwidth.math-sbp" />

Work a full-frame camera. At f/8, λ = 550 nm, the incoherent cutoff
$2\nu_c = 2/(\lambda N)$ is 455 cycles/mm; across a 36 mm field that is
$16{,}364$ countable pixels per row — nearly double the sensor's 8640.
At f/2.8 the lens delivers $46{,}753$: five sensor pixels per
countable pixel, wasted unless the sensor shrinks its pitch. The
diffraction-limited pixel for a given aperture is

<Widget type="interactive" id="com.github.richbai90.optics.space-bandwidth.int-sbp" />

<Widget type="quiz" id="com.github.richbai90.optics.space-bandwidth.quiz1" />

## Matching lenses to sensors

Nyquist closes the loop in both directions. A sensor with pixel pitch
$p$ resolves up to $1/(2p)$ cycles/mm — feed it more and you alias;
feed it less and pixels waste lens. Setting the lens's diffraction
cutoff $\nu_c = 1/(\lambda N)$ equal to the sensor's Nyquist frequency
gives the aperture at which a camera stops gaining sharpness by
stopping down:

<Widget type="math" id="com.github.richbai90.optics.space-bandwidth.math-nyquist" />

For 4 µm pixels at 550 nm, $N = 2p/\lambda = 14.5$ — hence the
practical rule that past roughly f/11–f/16, small-pixel cameras soften
by diffraction alone
([the defocus trade of the next lesson](39-resolution-defocus.md#the-trade-aberration-defocus-diffraction)
joins in from the other side). Every camera review that says
"diffraction limited past f/11" is quoting this arithmetic.

<Widget type="quiz" id="com.github.richbai90.optics.space-bandwidth.quiz2" />

## The invariance, and the ceiling

SBP is invariant under magnification — a 10× magnifier cannot multiply
it, because magnifying space shrinks the bandwidth by the same factor
(the Lagrange invariant of [stops and pupils](13-stops-pupils.md#numerical-aperture-and-f-number)
in information clothing). And it bounds superresolution: recovering
frequencies beyond $\nu_{max}$ requires light that was never collected.
Structured illumination borrows the nonlinearity of fluorescence to mix
frequencies down into the passband — clever, but each such scheme
spends something else (time, photons, prior knowledge) rather than
beating the count. Instruments are information channels; SBP is their
capacity.

<Widget type="quiz" id="com.github.richbai90.optics.space-bandwidth.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.space-bandwidth.card-sbp" />

<Widget type="flashcard" id="com.github.richbai90.optics.space-bandwidth.card-pixelmatching" />

## Recommended reading and viewing

Lecture 20's shift-invariance machinery is what the product counts;
the OpenStax resolution section supplies the cutoff language.

<Widget type="resource-link" id="com.github.richbai90.optics.space-bandwidth.link-lecture-20" />

<Widget type="resource-link" id="com.github.richbai90.optics.space-bandwidth.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.space-bandwidth.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 20 — shift invariance;
  pupil engineering; the Talbot
  effect](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-20-shift-invariance-pupil-engineering-the-talbot-effect/)
  (CC BY-NC-SA 4.0) — the transfer machinery the SBP counts
- MIT OCW 2.71 Optics, Spring 2009, [lecture 20 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec20/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §4.6 (Circular Apertures and
  Resolution) — [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- SBP framing follows Goodman's treatment of degrees of freedom
  (*Introduction to Fourier Optics*; expanded in MIT 2.710)
- Verified numbers: $2\nu_c = 2/(\lambda N)$: 455 cycles/mm at f/8,
  1299 at f/2.8 (λ = 550 nm); 36 mm field → 16 364 / 46 753 pixels
  across versus a sensor's 8640; diffraction-limited aperture for
  4 µm pixels: $N \approx p/(2\lambda) \approx 3.6$ per pixel pair
