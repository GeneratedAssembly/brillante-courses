---
title: Astigmatism, Field Curvature, and Distortion
description: The field aberrations — tangential and sagittal foci, the Petzval surface, and the one error that bends the image without blurring it. How stop position and glass choice control them.
order: 21
section: aberrations-optical-design
---

With spherical aberration and coma under control, the remaining third-order
errors are the field aberrations: they afflict off-axis points even with a
small aperture. Three of them matter for imaging — astigmatism, field
curvature, and distortion — and they differ in kind, not just degree:
astigmatism splits the focus, field curvature bends it, distortion moves
it without blurring it.

## Astigmatism

For an off-axis point, the ray fan in the plane containing the optical
axis (the **tangential** plane) and the fan in the perpendicular
(**sagittal**) plane see different effective surface powers, because they
strike the lens surfaces at different obliquities. The two fans focus at
two different distances. Between them the beam passes through a shape
called the **conoid of Sturm**: line focus, ellipse, circle of least
confusion, ellipse, line focus. No single plane catches a sharp point.

<Widget type="math" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.math-astig" />

Astigmatism grows with the square of the field angle and the square of
the aperture. Its most familiar case is the eye: a cornea whose curvature
differs between axes (see [the eye and the camera](11-eye-camera.md)).
A cylindrical or toric corrective surface supplies the missing power
difference along one axis — the same Sturm conoid, folded back onto
itself.

<Widget type="quiz" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.quiz1" />

## Field curvature

Even a lens with zero astigmatism does not place all of a flat object's
image on a flat plane. The natural image surface of any real positive
lens is a bowl — the **Petzval surface** — and its curvature adds up
from every powered element in the train:

<Widget type="math" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.math-petzval" />

The catch is structural: the Petzval sum depends on powers and glass
indices, and no choice of bending or stop position changes it. A positive
crown lens always contributes positive Petzval curvature, so a fast flat-field
lens must carry a negative element of high index — the flint in a doublet
earns its keep twice — or the film plate is curved, as in classic
astrographic cameras. With astigmatism present the tangential and
sagittal image shells straddle the Petzval surface; the designer splits
the difference and puts the flat plane where the astigmatic blur is
least.

<Widget type="quiz" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.quiz2" />

## Distortion

The last error moves image points without unsharping them. Paraxial
theory maps object height to image height linearly, but the exact mapping
through the aperture involves the tangent:

<Widget type="math" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.math-distortion" />

The gap between $f\tan\theta$ and the linear $f\theta$ grows steeply —
at a 30° field angle a 100 mm lens separates the two mappings by more
than 5 mm. Third-order distortion adds a term in the cube of image
height, and its sign is a design choice: **pincushion** (magnification
rising toward the corner) or **barrel** (falling). Because every ray
still passes through its correct point, straight *object* lines map to
straight *image* lines under $f\tan\theta$ — the **rectilinear**
condition — while scan and laser lenses deliberately choose the linear
$f\theta$ mapping instead, trading geometric faithfulness for constant
scan speed:

<Widget type="plot" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.plot-tantheta" />

<Widget type="quiz" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.quiz3" />

## The five, in one frame

The classical list now stands complete. One chromatic error (first order)
and five monochromatic Seidel aberrations (third order): spherical
aberration and coma (aperture-driven), astigmatism, field curvature,
distortion (field-driven). Every multi-element camera lens is a
negotiation among the six, using the levers this and the previous lesson
listed — bending, stop position, glass choice, element splitting — and
the exact point pairs that
[aplanatic optics](22-optical-design-grin.md#aplanatic-points) provides
for free.

<Widget type="flashcard" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.card-seidel" />

<Widget type="flashcard" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.card-petzval" />

## Recommended reading and viewing

Lecture 9 carries all three field aberrations together with the design
and GRIN material of the next lesson; the OpenStax eye section supplies
astigmatism's everyday case.

<Widget type="resource-link" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.link-lecture-9" />

<Widget type="resource-link" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.astigmatism-field-curvature-distortion.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 9 — more aberrations; optical
  design; GRadient INdex
  (GRIN)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-9-more-aberrations-optical-design-gradient-index-grin/)
  (CC BY-NC-SA 4.0) — astigmatism, field curvature, distortion
- MIT OCW 2.71 Optics, Spring 2009, [lecture 9 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec09/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.6 (The Eye) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- The $f\tan\theta$ versus $f\theta$ field mappings follow standard
  scan-lens design (f-theta lenses); curve values computed from
  $\tan\theta$ at 5°–30° for $f = 100$ mm
