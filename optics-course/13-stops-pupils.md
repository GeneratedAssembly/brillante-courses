---
title: Stops, Pupils, and Windows
description: Every real instrument is finite — the aperture stop that rations light, the pupils it casts through the optics, the field stop that crops the scene, and the numbers (NA, f/#) that price admission.
order: 13
section: apertures-pupils-instruments
---

An ideal point source emits into $4\pi$ steradians and an ideal instrument
accepts all of it. Every real instrument is finite: a lens has a rim, an eye
has an iris, a camera has an aperture. This lesson is the vocabulary of that
finiteness — which physical element limits what, and the two numbers,
numerical aperture and f-number, that price light admission. It is also the
grammar every later instrument lesson ([magnifiers and
microscopes](14-magnifiers-microscopes.md), [telescopes](15-telescopes.md))
is written in.

## The aperture stop

The **aperture stop** is the physical element that limits the angle of
acceptance of the system for a point source on the optical axis. Trace rays
from an on-axis object point outward: the ray cone they form must pass
through every element, and exactly one element clips it widest-shaping —
that element is the aperture stop. Familiar examples: the adjustable iris
inside a camera lens, and the pupil of the human eye, which opens in the
dark and closes in bright light (see [the eye](11-eye-camera.md)).

Which element plays the role is a property of the *system*, not of any
single part: moving an iris along the barrel changes its effect, and the
same physical plate can be the stop for one object distance and not for
another.

## Entrance and exit pupils

In a multi-element system you never look at the aperture stop directly —
you look at its *images* through the optics around it. Image the aperture
stop backwards through the elements in front of it: the result is the
**entrance pupil**, the stop as the object sees it. Image it forward
through the elements behind it: the **exit pupil**, the stop as the image
side sees it. Both may be virtual, and both may be magnified relative to
the physical stop.

Two special rays organize the whole picture:

- The **chief ray** from an off-axis object point passes through the
  *center* of the aperture stop — and therefore through the centers of
  both pupils.
- The **marginal ray** grazes the *rim* of the aperture stop — the last
  ray that just clears it — and therefore grazes the rims of both pupils.

Both rays leave the object point and meet again at the image point: they
are members of the same bundle, so every tool from
[imaging](09-thin-lenses.md) applies to them.

<Widget type="stepper" id="com.github.richbai90.optics.stops-pupils.stepper-trace" />

## A camera, worked through

Take a single thin lens of focal length $f$ with a physical aperture of
diameter $a$ a distance $z$ in front of it — a very simplified eye model —
and a detector at the image plane, a distance $s'$ behind. With nothing to
the aperture's left, it is simultaneously the aperture stop *and* the
entrance pupil. The exit pupil is the image of the stop through the lens:

<Widget type="math" id="com.github.richbai90.optics.stops-pupils.math-exitpupil" />

Because the stop sits between the front focal point and the lens, $z < f$
and $z' < 0$: the exit pupil is *virtual*, in front of the lens. That is
the concrete meaning of "you see the stop's image, not the stop."

<Widget type="interactive" id="com.github.richbai90.optics.stops-pupils.int-exitpupil" />

## Numerical aperture and f-number

The acceptance angle is priced in two currencies, one per community:

<Widget type="math" id="com.github.richbai90.optics.stops-pupils.math-na" />

Photography quotes the **f-number**; microscopy quotes the **numerical
aperture**. They are inverses up to a factor of two. Two consequences worth
pausing on:

- The index $n$ appears in NA so that NA is *conserved across flat
  refracting interfaces* — refraction changes the angle $\theta$ and the
  index exactly reciprocally (see
  [refraction](05-reflection-and-refraction.md)). A high-NA immersion
  objective with oil of index $\approx 1.5$ outside the glass can honestly
  claim NA $> 1$.
- Where does your money go? In an expensive microscope objective you pay
  for large NA; in an expensive camera lens you pay for a low f-number.
  Either way you are buying admitted optical energy — and, as we will see
  in [imaging systems and resolution](39-resolution-defocus.md), better
  resolution.

<Widget type="quiz" id="com.github.richbai90.optics.stops-pupils.quiz1" />

<Widget type="quiz" id="com.github.richbai90.optics.stops-pupils.quiz2" />

## The field stop and windows

The aperture stop decides how much light each point gets; a second element
decides which points get imaged at all. The **field stop** limits the
angle of acceptance of *chief rays*: chief rays steeper than the edges of
the field stop simply miss. The angle between the two chief rays that just
clear its edges is the **field of view** — quoted as an angle, not a size,
because zooming changes the image size while preserving the angle. A
camera's sensor is its field stop; so is the active chemical area of film.

As with pupils, the field stop casts images: the **entrance window**
(through the preceding elements) and the **exit window** (through the
succeeding). In a well-behaved system the entrance window coincides with
the object plane and the exit window with the image plane — if it does
not, something is wrong with the design.

## Vignetting

Ideally the acceptance angle (the NA as seen by the system) is the same at
every point in the field. Real systems fall short: the off-axis decrease
of effective acceptance is **vignetting**, and it shows up as darkened
image edges. It generally traces to placing the aperture stop in the wrong
place for the system — there is no universal rule, which is part of what
lens designers are paid for. The worked camera above shows it honestly:
the on-axis marginal cone is visibly wider than the cone that makes it
through the detector edges.

<Widget type="flashcard" id="com.github.richbai90.optics.stops-pupils.card-stop" />

<Widget type="flashcard" id="com.github.richbai90.optics.stops-pupils.card-rays" />

<Widget type="quiz" id="com.github.richbai90.optics.stops-pupils.quiz3" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.stops-pupils.link-lecture-6" />

<Widget type="resource-link" id="com.github.richbai90.optics.stops-pupils.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.stops-pupils.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 6 — terms: apertures, stops,
  pupils, and windows; single-lens
  camera](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-6-terms-apertures-stops-pupils-and-windows-single-lens-camera/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.7 (The Camera) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
