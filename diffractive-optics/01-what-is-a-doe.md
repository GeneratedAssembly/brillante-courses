---
title: What Is a Diffractive Optical Element?
description: A taxonomy of DOEs — kinoforms, binary optics, CGHs — the continuum from a hybrid lens to a general wavefront transformer, and the two classic elements every DOE descends from.
order: 1
section: foundations
---

Engineers use a pile of overlapping names for light controlled by diffraction:
*binary optics, kinoforms, computer-generated holograms, diffractive optical
elements, grating*. The book standardizes on **diffractive optical element
(DOE)** and defines the field it lives in:

> Diffractive optics is the field that describes the control and generation of
> wavefronts by **segmenting initial wavefronts and redirecting the segments
> through the use of interference and phase control**.

It is a subfield of *physical optics* (the propagation of electromagnetic
waves), and it is best understood in terms of **wavefronts** — surfaces
perpendicular to the ray paths on which the field has the same phase — rather
than rays. A positive lens, wavefront-wise, converts a plane wavefront into a
converging spherical wavefront centered on the focus.

## A taxonomy worth memorizing

<Widget type="flashcard" id="com.github.richbai90.diffractive.doe.card-taxonomy" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.doe.card-binary" />

<Widget type="quiz" id="com.github.richbai90.diffractive.doe.quiz-kinoform" />

## The continuum of devices

The book surveys DOEs along a continuum from a classic element to something
with no classic counterpart:

- **Hybrid lens** — a conventional refractive lens with a diffractive structure
  etched onto one surface. The diffractive surface's *dispersion* (how its
  power changes with wavelength) is so strong that a **weak** diffractive lens
  added to a normal lens corrects its color — see
  [Hybrid Lenses](09-hybrid-lenses.md).
- **Pure diffractive lenses and mirrors** on flat surfaces — where size and
  weight matter; **wavefront correctors** that flatten a known aberrated
  wavefront; **null correctors** for optical testing.
- **Beam samplers and lens arrays** — counterparts of conventional components.
- **Pattern generators** — under monochromatic light a periodic structure makes
  an array of beams whose angles obey the grating equation, and the profile
  *inside each period* controls the relative intensities.
- **Subwavelength structures** — shrink the period until no diffracted orders
  exist at all, and you get antireflective ("moth's-eye") surfaces and
  artificial-index films: see
  [Electromagnetic Methods](06-electromagnetic-methods.md).
- **General wavefront transformers** — fanouts, portraits, optical-computing
  interconnects: arbitrary patterns "made to order."

## The grating equation: where the light goes

Every pattern-generating application starts here:

<Widget type="math" id="com.github.richbai90.diffractive.doe.math-grating" />

<Widget type="interactive" id="com.github.richbai90.diffractive.doe.int-angle" />

Two facts the whole design chapter rides on: **the period Λ sets the angles**,
and **the structure inside one period sets how much power goes to each angle**.
Notice what happens as Λ shrinks toward λ: the first order marches toward 90°,
and below Λ = λ there is no first order at all — the doorway to the subwavelength
regime.

## Ancestor one: the Fresnel lens

A **Fresnel lens** is a refractive lens with all the glass that does not bend
rays toward the focus removed: the surface profile that carries the optical
power survives; the volume and weight do not. It is still a *classic* element —
rays refract at each zone's surfaces — but it teaches the central trick:
**a staircase profile can do what a smooth profile does.** The diffractive lens
applies the same idea to wavefronts instead of rays.

## Ancestor two: the blazed grating

Take a right-angle prism that steers a beam by refraction; slice it into
one-wavelength-high pieces and delete the material that contributes no path
change. What remains is a **sawtooth (blazed) grating** that steers the beam by
diffraction — and, designed right, sends **all** the light into one order:

<Widget type="flashcard" id="com.github.richbai90.diffractive.doe.card-blaze" />

The prism's deflection comes from dispersion (index vs wavelength); the
blazed grating's comes from its periodicity (grating equation). This is "one of
the simplest demonstrations of the difference between a classic optical element
and a diffractive optical element."

<Widget type="quiz" id="com.github.richbai90.diffractive.doe.quiz-blaze" />

## Stitching wavefronts

A **kinoform** lens (a smooth, continuously varying DOE profile) works by
wavefront surgery: plane-wavefront segments emerge one wavelength deep at a
time from successive zones, and the zones' edges are chosen so the segments
line up into a converging spherical wavefront. The element *stitches*
wavefronts together — and equivalently, it is a set of variably spaced blazed
gratings deflecting the local wavefront. Start from **any** desired output
wavefront, slice the required profile into 2π-phase segments, collapse them,
and you have the element that makes it. Wavefronts can be made to order —
with limits that come from feature sizes and fabrication, which is what the
rest of this course is about.

<Widget type="quiz" id="com.github.richbai90.diffractive.doe.quiz-theme" />
