---
title: Fraunhofer Diffraction and the Fourier Transform
description: The far field of any aperture is its Fourier transform — single slits, circular apertures, the Airy disk, and the punchline that turns a lens into a spectrum analyzer.
order: 32
section: diffraction-fourier-optics
---

[Fresnel zones](18-fresnel-zones.md) handled the near field, where a
wavefront interferes with itself zone by zone. Step far enough back and
the zone bookkeeping collapses into something cleaner: the field's
angular pattern becomes a *transform* of the aperture. Fraunhofer
diffraction is the far-field regime, and the transform idea is the
punchline that carries the rest of this course.

## The far field, and the lens that fakes it

The Fraunhofer (far-field) regime begins where the Fresnel number is
small — observation distance $L \gg a^2/\lambda$. For a 0.1 mm slit at
550 nm the boundary is $a^2/\lambda \approx 18$ mm: a meter of bench is
comfortably far field. But for a 5 cm lens the boundary is
$D^2/\lambda \approx 4.5$ km — you cannot stand far enough away. The
lens loophole: a lens placed one focal length from the aperture brings
its own infinity to the focal plane (C = 0 in the matrix language of
[ray transfer matrices](08-ray-transfer-matrices.md#reading-images-off-the-matrix)).
Every result below holds in the lens's focal plane, on a desktop.

## The single slit

A slit of width $a$ splits its wavefront into elements that interfere
across the aperture. Pairing elements half an aperture apart shows the
minima immediately:

<Widget type="math" id="com.github.richbai90.optics.fraunhofer-fourier.math-singleslit" />

The full pattern is the squared ratio

<Widget type="plot" id="com.github.richbai90.optics.fraunhofer-fourier.plot-sinc2" />

with the central maximum carrying about 90% of the transmitted power.
The intuition runs backwards: *narrower slit, wider pattern*. A 0.1 mm
slit at λ = 550 nm puts its first minimum at $\sin\theta = 5.5\times
10^{-3}$ — 11 mm from center on a 2 m screen, central lobe 22 mm wide.
The first sidelobe peaks at $4.7\%$, the tail of a sinc.

<Widget type="quiz" id="com.github.richbai90.optics.fraunhofer-fourier.quiz1" />

## The circular aperture: the Airy disk

For a circular aperture the same sum runs in polar coordinates, and the
zeros move to the Bessel-function sweet spot:

<Widget type="math" id="com.github.richbai90.optics.fraunhofer-fourier.math-airy" />

The pattern is a bright disk — the **Airy disk** — with a faint ring
structure. The eye (5 mm pupil, 550 nm): first zero at $1.34\times
10^{-4}$ rad, about 28 arcseconds; an 8 m telescope: 0.017 arcseconds.
This angle is the *best any instrument can do* — the Rayleigh criterion
built on it sets the resolution limits of
[imaging systems](39-resolution-defocus.md), and the Abbe bound of
[the 4f system](35-fourf-system.md#abbe-s-view-the-image-as-a-sum-of-orders)
is its Fourier-dual statement.

<Widget type="quiz" id="com.github.richbai90.optics.fraunhofer-fourier.quiz2" />

## Apertures are Fourier transforms

Here is the punchline. In the far field, the field radiated by an
aperture $A(x)$ is, up to scaling and phase,

$$U(\theta) \;\propto\; \int A(x)\,e^{-i 2\pi x \sin\theta/\lambda}\,dx,$$

which is exactly the Fourier transform of the aperture, evaluated at
spatial frequency $\nu = \sin\theta/\lambda$. Every result above is a
transform identity: a rectangle transforms to a sinc; two delta slits
transform to a cosine-modulated pair of patterns — the fringe spacing
of [two-slit interference](28-two-slit-interference.md) is the transform
of the slit separation, and its envelope the transform of each slit
width (zeroes at $a\sin\theta = m\lambda$, about $2d/a$ fringes under
the central lobe). Aperture *engineering* becomes spectrum *engineering*
— the move [spatial filtering](34-spatial-filtering.md) makes explicit.

<Widget type="quiz" id="com.github.richbai90.optics.fraunhofer-fourier.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.fraunhofer-fourier.card-singleslit" />

<Widget type="flashcard" id="com.github.richbai90.optics.fraunhofer-fourier.card-airy" />

## Recommended reading and viewing

Lecture 17 is the single source for this lesson — Fraunhofer patterns
and the transform theorems together.

<Widget type="resource-link" id="com.github.richbai90.optics.fraunhofer-fourier.link-lecture-17" />

<Widget type="resource-link" id="com.github.richbai90.optics.fraunhofer-fourier.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.fraunhofer-fourier.link-openstax-singleslit" />

<Widget type="resource-link" id="com.github.richbai90.optics.fraunhofer-fourier.link-openstax-gratings" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 17 — Fraunhofer diffraction;
  Fourier transforms and
  theorems](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-17-fraunhofer-diffraction-fourier-transforms-and-theorems/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 17 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec17/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §4.2 (Single-Slit Diffraction) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- OpenStax University Physics III, §4.6 (Circular Apertures and
  Resolution) — same book (CC BY 4.0)
- Verified numbers: 0.1 mm slit, λ = 550 nm: first minimum at
  $\sin\theta = 5.5\times10^{-3}$ (11.0 mm at L = 2 m), central lobe
  22.0 mm, first sidelobe 4.72% at β = 1.4303π; far-field boundaries
  $a^2/\lambda$: 18.2 mm (0.1 mm slit), 4.5 km (5 cm optic); Airy
  first-zero angles 1.22λ/D: 28.0 arcsec (5 mm eye), 0.017 arcsec
  (8 m telescope)
