---
title: The Eye and the Camera
description: Two imaging systems that solve the same problem with opposite strategies — the eye bends its lens to focus, the camera moves its lens.
order: 11
section: lenses-image-formation
---

The eye and the camera are the same instrument with one degree of freedom
swapped. Each forms a real, inverted image on a photosensitive plane with a
positive lens. Each must focus objects from arm's length to infinity. The
eye does it by *changing its focal length*; the camera does it by *changing
its lens distance*. Every idea from
[thin lenses](09-thin-lenses.md) applies to both.

## Two ways to focus

The thin-lens equation ties three quantities together: $s$, $s'$, $f$. A
camera fixes $f$ and slides the lens until the sensor plane matches $s'$ —
that's the focus ring. The eye cannot slide its lens: the retina is fixed.
Instead it *accommodates* — the ciliary muscles change the crystalline
lens's shape, and therefore $f$, until the image lands on the fixed retina.

<Widget type="quiz" id="com.github.richbai90.optics.eye-camera.quiz1" />

## The eye as an optical instrument

Most of the eye's refraction (roughly two thirds of its ~60 diopters) happens
at the **cornea**, at the large index step from air (~1.00) into the cornea
(~1.38). The crystalline lens, immersed in fluid on both sides, contributes
the remainder *and* all of the accommodation. The relaxed eye is focused at
the **far point** (infinity for a normal eye); at maximum accommodation a
young eye focuses down to a **near point** of about 25 cm. With age the lens
stiffens and the near point recedes — **presbyopia** — which reading glasses
compensate with added positive power.

<Widget type="flashcard" id="com.github.richbai90.optics.eye-camera.card-accommodation" />

## Refractive errors and their correction

Refractive errors are mismatches between the eye's power and its length, and
corrective lenses are [thin lenses](09-thin-lenses.md) placed in front of the
eye to move the effective image plane:

- **Myopia** (nearsighted): the eye's power is too strong or the eyeball too
  long — the images of distant objects form *in front of* the retina. The
  far point is finite, at some distance $x_F$. A **diverging** lens must take
  an object at infinity and form a virtual image at the far point, where the
  eye can focus it:

<Widget type="math" id="com.github.richbai90.optics.eye-camera.math-myopia" />

<Widget type="interactive" id="com.github.richbai90.optics.eye-camera.int-myopia" />

- **Hyperopia** (farsighted): the reverse mismatch — the eye cannot converge
  strongly enough even for nearby objects, and a **converging** correction
  supplies the missing power.
- **Astigmatism**: the cornea's curvature differs between axes; correcting it
  needs a cylindrical element, a preview of the [aberrations
  section](17-chromatic-spherical-coma.md).

<Widget type="quiz" id="com.github.richbai90.optics.eye-camera.quiz2" />

## The camera: focus by distance, exposure by aperture

A camera lens images the scene onto its sensor; the ring moves $s'$. That
leaves one more variable the eye does not have: the **aperture
diameter** $D$. Light gathering is set by the **f-number**:

<Widget type="math" id="com.github.richbai90.optics.eye-camera.math-fnumber" />

Each full stop multiplies $D$ by $\sqrt{2}$ — and therefore the exposure by 2.
Stopping down (larger $N$) buys a larger depth of field at the price of
light, a trade-off quantified in the [resolution
lesson](37-resolution-defocus.md); stopping up brightens the sensor but
shrinks the in-focus range and, for real lenses, adds aberration and
diffraction blur.

<Widget type="quiz" id="com.github.richbai90.optics.eye-camera.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.eye-camera.card-myopia" />

<Widget type="flashcard" id="com.github.richbai90.optics.eye-camera.card-fnumber" />


## Recommended reading and viewing

The eye half of this lesson comes from lecture 5; the camera half from lecture 6.

<Widget type="resource-link" id="com.github.richbai90.optics.eye-camera.link-lecture-5" />

<Widget type="resource-link" id="com.github.richbai90.optics.eye-camera.link-lecture-6" />

<Widget type="resource-link" id="com.github.richbai90.optics.eye-camera.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 5 — thick lenses, the composite
  lens, the
  eye](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-5-thick-lenses-the-composite-lens-the-eye/)
  and [lecture 6 — terms, apertures, stops, pupils, and windows; single lens
  camera](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-6-terms-apertures-stops-pupils-and-windows-single-lens-camera/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.6 (The Eye), §2.7 (The Camera) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
