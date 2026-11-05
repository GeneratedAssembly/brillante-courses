---
title: Shift Invariance, Transfer Functions, and the Talbot Effect
description: Imaging as convolution — the point-spread function, the optical transfer function's graceful slide to zero, pupils as knobs, and the Talbot carpet of self-imaging gratings.
order: 36
section: imaging-systems-resolution
---

A lens images every point of a scene the *same* way — shifted, but not
reshaped. That single property, **shift invariance**, turns imaging from
a ray problem into a linear-systems problem: the image is the scene
convolved with one function, and the frequency-domain cost of that
convolution is a transfer function you can read off the pupil. This
lesson builds the machinery and ends on a spectacle: light that images
itself.

## Shift invariance and the point-spread function

Paraxial imaging is shift-invariant: move the object point across the
field, and its image moves without changing form (aberrations
[destined for the design lesson](22-optical-design-grin.md) spoil this
slowly, off-axis). The image of a point is the **point-spread
function** (PSF), and the image of anything is the sum — the
*convolution* — of shifted PSFs:

<Widget type="math" id="com.github.richbai90.optics.transfer-functions.math-convolution" />

For incoherent light the PSF is the intensity pattern of a single
point — for a circular aperture, the
[Airy disk](32-fraunhofer-fourier.md#the-circular-aperture-the-airy-disk).
Coherent light superposes *amplitudes*, so its PSF is the aperture's
[transform](32-fraunhofer-fourier.md#apertures-are-fourier-transforms)
and the detector's squaring comes afterward — a distinction with
teeth, expanded in [the next lesson](37-coherent-incoherent-imaging.md).

<Widget type="quiz" id="com.github.richbai90.optics.transfer-functions.quiz1" />

## The optical transfer function

Convolution in space multiplies in frequency, so the imaging system owns
a transfer function. The **optical transfer function (OTF)** is the
Fourier transform of the PSF — and, for a diffraction-limited system,
the *autocorrelation of the pupil*:

<Widget type="math" id="com.github.richbai90.optics.transfer-functions.math-otf" />

Incoherent light spreads the passband to $2\mathrm{NA}/\lambda$ — twice
the coherent cutoff of
[the frequency plane](34-spatial-filtering.md#the-frequency-plane) —
but spends it on a ramp that has already sagged to 0.39 at midband:

<Widget type="plot" id="com.github.richbai90.optics.transfer-functions.plot-otf" />

The magnitude is the **MTF** that lens data sheets plot; the phase
carries asymmetries (coma's ghosting shifts). At
$\nu_{max} = 2\,\mathrm{NA}/\lambda$ the response dies exactly — 365
cycles/mm at NA = 0.1, λ = 550 nm — and detail beyond that is not soft,
it is absent.

<Widget type="quiz" id="com.github.richbai90.optics.transfer-functions.quiz2" />

## Pupil engineering

The OTF formula hands the designer a knob: change the pupil, change the
transfer function. **Apodization** (a soft, brightest-at-center pupil)
trades throughput for a clean PSF — Gaussian-pupil systems show no
sidelobe rings, which coronagraphs and metrology pay for. **Phase
pupils** redistribute the OTF instead of the intensity: a cubic phase
mask buys an image tolerant to meters of defocus, recovered by
computational deconvolution — wavefront coding. And
[binary pupil masks](35-fourf-system.md#binary-amplitude-and-pupil-masks)
are the crude version of both. The pupil is the frequency-domain
address space of the instrument; pupil engineering is programming it.

<Widget type="quiz" id="com.github.richbai90.optics.transfer-functions.quiz3" />

## The Talbot effect

Give the transform machinery a periodic input and it performs a
credibility check on itself. A grating of period $d$, lit by a plane
wave, reproduces *itself* — a sharp image of the grating — in empty
space at regular distances, with a half-period contrast reversal
between. The phase bookkeeping says why: the $m$-th diffraction order
lags order zero by $\pi z m^2 \lambda/d^2$ after distance $z$, and when
that lag is a whole cycle for every order the field reassembles:

<Widget type="math" id="com.github.richbai90.optics.transfer-functions.math-talbot" />

A 10 µm-period grating at 550 nm self-images every $z_T = 0.36$ mm,
contrast-reversed at 0.18 mm. The "Talbot carpet" of interim planes is
the grating's spectrum interfering with itself, plane by plane —
self-imaging without any lens at all, exploited in Talbot lithography
and X-ray phase contrast.

<Widget type="flashcard" id="com.github.richbai90.optics.transfer-functions.card-otf" />

<Widget type="flashcard" id="com.github.richbai90.optics.transfer-functions.card-talbot" />

## Recommended reading and viewing

Lecture 20 covers shift invariance, pupil engineering, and the Talbot
effect in one pass.

<Widget type="resource-link" id="com.github.richbai90.optics.transfer-functions.link-lecture-20" />

<Widget type="resource-link" id="com.github.richbai90.optics.transfer-functions.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.transfer-functions.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 20 — shift invariance;
  pupil engineering; the Talbot
  effect](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-20-shift-invariance-pupil-engineering-the-talbot-effect/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 20 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec20/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §4.6 (Circular Apertures and
  Resolution) — [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- The OTF is the pupil autocorrelation (Goodman, *Introduction to
  Fourier Optics*); $H(\nu_c/2) = 0.391$ for the diffraction-limited
  incoherent ramp
- Talbot distance $z_T = 2d^2/\lambda$ derived from the order-phase lag
  $\pi z m^2\lambda/d^2$: d = 10 µm, λ = 550 nm → $z_T = 0.364$ mm,
  contrast reversal at 0.182 mm
