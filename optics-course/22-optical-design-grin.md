---
title: Optical Design and Gradient-Index Optics
description: The designer's toolkit — exact aplanatic points, the structural archetypes of multi-element lenses, and lenses made of glass whose index changes with position.
order: 22
section: aberrations-optical-design
---

Correction, not elimination, is the design game: the six aberrations of
the last two lessons trade against each other, and a lens is a stack of
glass chosen so the residual errors cancel where it counts. This lesson
collects the tools that make the negotiation tractable — one exact gift
of geometry, a few structural archetypes, and a class of optics that
bends rays without surfaces at all.

## Aplanatic points

A single refracting spherical surface can image one pair of axial points
with *no* spherical aberration *and* no coma — exactly, not to third
order. Place the object inside the glass at a distance
$R n'/n$ from the surface's center of curvature (with $n$ the glass
index, $n'$ the outside medium):

<Widget type="math" id="com.github.richbai90.optics.optical-design-grin.math-aplanatic" />

Every ray from that point refracts through the surface and diverges
exactly as if from a virtual point at $R\,n/n'$ on the same side. The
pair is stigmatic for all zones, and it obeys the Abbe sine condition,
so the image is aplanatic: the transverse magnification comes out as
$(n/n')^2$ — for glass to air, $2.25$ — for every ray at every angle.
The pair distances follow the classical vertex form
$R(n+n')/n$ and $R(n+n')/n'$ measured from where the axis meets the
sphere.

The microscope exploits this directly. An oil-immersion front lens
(sample oil, index matched to the glass, sitting on a hemispherical
front element) places the specimen near an aplanatic point; each
aplanatic refraction multiplies the collection angle down by the index
ratio without introducing spherical aberration or coma, which is how
numerical apertures near 1.4 stay aberration-free
(see [magnifiers and microscopes](14-magnifiers-microscopes.md)).

<Widget type="quiz" id="com.github.richbai90.optics.optical-design-grin.quiz1" />

## Design structure: archetypes and levers

A first-order layout (thin lenses, from
[ray transfer matrices](08-ray-transfer-matrices.md)) fixes focal length
and pupil placement; aberration correction then drives the structure:

- **Splitting the work.** Spreading power over several shallow surfaces
  cuts each surface's aberration contribution steeply (third-order terms
  go as the cube of the surface angle) — the reason a camera lens has
  six elements where a magnifier needs one.
- **Symmetry.** A system symmetric about the stop cancels coma,
  distortion, and lateral color automatically, at the price of
  astigmatism that the outer elements must then correct — the
  double-Gauss recipe inside most 50 mm camera lenses.
- **Structural signatures.** Positive front, negative rear (**telephoto**)
  moves the physical barrel behind the focal plane; negative front,
  positive rear (**retrofocus**) pushes the back focus out so an SLR
  mirror can swing; negative meniscus field flatteners buy back Petzval
  curvature (see [field curvature](21-astigmatism-field-curvature-distortion.md#field-curvature)).
- **Glass choice.** Crown-flint pairs fix chromatic error
  ([the achromat](20-chromatic-spherical-coma.md#the-achromatic-doublet));
  high-index glass lowers every monochromatic error at once, because
  shallower curvatures do the same work.

The modern loop closes with ray tracing: lay out first order, balance
third order by hand, then let optimization trade hundreds of ray
intercepts against a merit function. The hand balance still decides the
structure, and structure decides what the optimizer can reach.

<Widget type="quiz" id="com.github.richbai90.optics.optical-design-grin.quiz2" />

## GRIN optics: lenses without surfaces

Refractive index can vary *inside* a material. A parabolic radial profile

<Widget type="math" id="com.github.richbai90.optics.optical-design-grin.math-grin" />

makes the paraxial ray equation a harmonic oscillator, so rays through a
**gradient-index (GRIN)** medium oscillate sinusoidally about the axis
instead of bending at discrete surfaces:

<Widget type="interactive" id="com.github.richbai90.optics.optical-design-grin.int-grin" />

A rod of this material becomes a lens. A quarter-pitch length (one
quarter of the oscillation period) converts a point at its face into a
collimated beam, with focal length $f = 1/(n_0 g)$ — a millimeter-long
fiber-coupling lens with $n_0 = 1.6$ and $g \approx 1.57\ \mathrm{mm}^{-1}$
focuses at $f \approx 0.4$ mm. GRIN lenses collimate fiber outputs,
relay images inside endoscopes, and remove the alignment cost of curved
polished surfaces.

Nature got there first. The crystalline lens of the eye is GRIN — its
index falls from about 1.41 at the center to 1.37 at the shell — which
adds power smoothly and tames the spherical aberration a homogeneous
lens of that curvature would suffer
(see [the eye and the camera](11-eye-camera.md)). A heated layer of air
near a road is an axial-GRIN medium, and the mirage is its ray trace.

<Widget type="quiz" id="com.github.richbai90.optics.optical-design-grin.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.optical-design-grin.card-aplanatic" />

<Widget type="flashcard" id="com.github.richbai90.optics.optical-design-grin.card-grin" />

## Recommended reading and viewing

Lecture 9 is the single source for this lesson — aplanatic points,
design practice, and the GRIN treatment together.

<Widget type="resource-link" id="com.github.richbai90.optics.optical-design-grin.link-lecture-9" />

<Widget type="resource-link" id="com.github.richbai90.optics.optical-design-grin.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.optical-design-grin.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 9 — more aberrations; optical
  design; GRadient INdex
  (GRIN)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-9-more-aberrations-optical-design-gradient-index-grin/)
  (CC BY-NC-SA 4.0) — aplanatic points, design archetypes, GRIN optics
- MIT OCW 2.71 Optics, Spring 2009, [lecture 9 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec09/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.6 (The Eye) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Aplanatic-pair distances and magnification $m = (n/n')^2$ verified by
  direct ray tracing (vector Snell) for $n = 1.5 \to 1.0$, $R = 10$ mm:
  zero axis-crossing spread and exact sine condition
- GRIN example numbers: quarter-pitch length 1.0 mm, $g = \pi/(2L)
  \approx 1.571\ \mathrm{mm}^{-1}$, $f = 1/(n_0 g) \approx 0.398$ mm
- Eye-lens GRIN values are representative of adult crystalline-lens
  measurements (center $\approx 1.41$, shell $\approx 1.37$)
