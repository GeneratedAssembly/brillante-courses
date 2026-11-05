---
title: Magnifiers and Microscopes
description: Angular magnification and the 25 cm near point; the eyepiece; the compound microscope as two magnifiers in series — and why a billionfold magnification buys you nothing.
order: 14
section: apertures-pupils-instruments
---

Your eye's job is to form a real image on the retina, and the retinal image
grows as the object gets closer. So the cheapest microscope is simply
bringing the object nearer — until you hit the wall: the eye cannot focus
on anything inside its **near point**, about 25 cm (and the wall moves out
with age; see [the eye](11-eye-camera.md)). Everything in this lesson is a
way past that wall.

## Angular magnification

What "magnification" must mean for an instrument that ends in a *virtual*
image — something no screen can catch, but your eye can (see
[real and virtual images](09-thin-lenses.md#real-and-virtual-images)) — is
the angle the final image subtends at the eye, compared with the angle the
object would subtend unaided:

<Widget type="math" id="com.github.richbai90.optics.magnifiers-microscopes.math-angmag" />

The unaided comparison is made at the near point — the closest the eye can
possibly pull the object — so it is the *most generous* baseline.

## The simple magnifier

A single converging lens with the object inside its focal length produces a
virtual, upright, enlarged image (the magnifying glass of
[lesson 9](09-thin-lenses.md)). That virtual image replaces the
object-and-lens pair as far as the eye is concerned: the eye images the
virtual image onto the retina as if it were a real, more distant, larger
object.

Two standard usage modes bracket what a magnifier can do:

<Widget type="math" id="com.github.richbai90.optics.magnifiers-microscopes.math-twomodes" />

- **Relaxed eye** (object at the front focal point): the lens emits
  collimated light, the virtual image sits at infinity, and the eye
  focuses it with zero strain. Magnification $25\,\mathrm{cm}/f$.
- **Near-point viewing** (lens pressed to the eye, image at 25 cm):
  slightly stronger, $1 + 25\,\mathrm{cm}/f$, but the accommodated eye
  strains.

<Widget type="interactive" id="com.github.richbai90.optics.magnifiers-microscopes.int-magnifier" />

<Widget type="quiz" id="com.github.richbai90.optics.magnifiers-microscopes.quiz1" />

## The eyepiece

Put the same magnifying glass at the *end of an instrument* and it earns a
new name: the **eyepiece**, or ocular. It is designed to two
specifications: the intermediate image sits in its front focal plane so
the exit beam is collimated (a virtual image at infinity — a relaxed eye),
and the instrument's **exit pupil** lands about 10 mm behind the eyepiece,
at the **eye relief**, where the observer's eye belongs. Eye at the wrong
place: a black disc, or a cropped field — the
[pupils and windows](13-stops-pupils.md) vocabulary at work.

## The compound microscope

To see detail smaller than a magnifier can deliver, magnify twice:
an **objective** (very short focal length) forms a *real*, magnified,
inverted intermediate image of a nearby specimen, and the eyepiece then
treats that intermediate image exactly as a magnifier treats any object.

<Widget type="math" id="com.github.richbai90.optics.magnifiers-microscopes.math-microscope" />

The **tube length** $L$ — from the objective's back focal point to the
eyepiece's front focal point — is standardized at 160 mm, which is why
"40× objective, 10× eyepiece" multiplies to a predictable 400× on any
microscope. The final image is virtual, inverted, and infinitely far away
for a relaxed eye; the instrument's field stop sits at the intermediate
image plane, cropping the specimen.

<Widget type="interactive" id="com.github.richbai90.optics.magnifiers-microscopes.int-microscope" />

<Widget type="quiz" id="com.github.richbai90.optics.magnifiers-microscopes.quiz2" />

## The wall at the end of magnification

Why stop at a few hundred ×? Because magnification is not resolution: at
some point the intermediate image is magnifying *blur*. The limit is the
wavelength of light — details below roughly a micrometer do not form
usable images no matter how strongly you magnify (see [diffraction and
imaging](39-resolution-defocus.md)). Chasing $f \to 1\,\mu\mathrm{m}$ also
means a lens curved so sharply that the paraxial approximation itself
collapses. Practical objective focal lengths run from a few millimeters to
a centimeter, and the microscope saturates around 1000×.

<Widget type="flashcard" id="com.github.richbai90.optics.magnifiers-microscopes.card-nearpoint" />

<Widget type="flashcard" id="com.github.richbai90.optics.magnifiers-microscopes.card-tube" />

<Widget type="flashcard" id="com.github.richbai90.optics.magnifiers-microscopes.card-eyepiece" />

<Widget type="quiz" id="com.github.richbai90.optics.magnifiers-microscopes.quiz3" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.magnifiers-microscopes.link-lecture-7" />

<Widget type="resource-link" id="com.github.richbai90.optics.magnifiers-microscopes.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 7 — basics of mirrors,
  magnifiers, and
  microscopes](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-7-basics-of-mirrors-magnifiers-and-microscopes/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.8 (The Simple Magnifier), §2.9
  (Microscopes and Telescopes) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
