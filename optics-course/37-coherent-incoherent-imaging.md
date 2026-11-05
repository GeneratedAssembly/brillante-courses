---
title: Coherent and Incoherent Imaging
description: Two ways to form an image — summing amplitudes or summing intensities — and everything that follows — doubled cutoffs, speckle, invisible phase, and the illumination choices that manage both.
order: 37
section: imaging-systems-resolution
---

Point the same objective at a self-luminous scene and at a laser-lit
one, and you get different images — not worse or better, different.
Coherent light superposes *amplitudes* across the pupil; incoherent
light superposes *intensities*. The distinction runs through the whole
imaging stack: transfer functions, resolution, noise texture, and what
a detector can see at all.

## The two linearity regimes

An image is a sum over object points, and the question is what gets
summed. Incoherent (self-luminous or extended-white-light) imaging sums
*intensities*: the image is the object intensity convolved with the
PSF's intensity,

<Widget type="math" id="com.github.richbai90.optics.coherent-incoherent-imaging.math-incoherent" />

and the transfer function is the pupil autocorrelation — the ramp of
[the previous lesson](36-transfer-functions.md#the-optical-transfer-function),
passing frequencies out to $2\,\mathrm{NA}/\lambda$. Coherent imaging
sums *amplitudes* in the pupil,

<Widget type="math" id="com.github.richbai90.optics.coherent-incoherent-imaging.math-coherent" />

with the pupil acting as a hard low-pass at $\mathrm{NA}/\lambda$ — the
[frequency-plane](34-spatial-filtering.md#the-frequency-plane) cutoff —
and the intensity-detector square taken at the end. Interference
between *neighboring object points* survives in the coherent case and
averages away in the incoherent case; that one difference generates
every effect below.

<Widget type="plot" id="com.github.richbai90.optics.coherent-incoherent-imaging.plot-otfs" />

<Widget type="quiz" id="com.github.richbai90.optics.coherent-incoherent-imaging.quiz1" />

## What the modes do differently

- **Edges and ringing.** A coherent system's hard spectral cutoff
  convolves edges with a [transform that
  rings](32-fraunhofer-fourier.md#apertures-are-fourier-transforms):
  bright fringes appear parallel to every high-contrast edge. Incoherent
  imaging's gentler ramp rings far less.
- **Resolution.** The doubled cutoff helps incoherent imaging resolve
  fine structure (365 versus 182 cycles/mm at NA = 0.1) — though its
  midband contrast is weaker, so the "better" system is not uniformly
  better.
- **Phase invisibility.** An intensity detector squares before it sees:
  a uniform-amplitude phase object images as *nothing* in either mode
  unless the optics convert phase to intensity
  ([Zernike's route](34-spatial-filtering.md#phase-objects-and-phase-contrast)).
- **Speckle.** Coherent light on a rough surface: neighboring surface
  points scatter with path-dependent phases, and the interference of
  this incoherent-in-name weave leaves grainy intensity noise with
  correlation size ~ $\lambda/\mathrm{NA}$. Speckle is the coherent
  mode's signature — and its tax.

<Widget type="quiz" id="com.github.richbai90.optics.coherent-incoherent-imaging.quiz2" />

## Illumination as a design decision

Microscopes manage the choice with **Köhler illumination**: the source
is imaged into the *objective's pupil*, not onto the object, so each
object point is illuminated from the full condenser cone and the
effective illumination coherence is set by the condenser NA. Fill the
objective's pupil with the condenser image and the mode crosses toward
incoherent; close the condenser and the image sharpens into coherent
contrast (dark-field is the limit). Laser illumination, by contrast,
brings full coherence and full speckle — which is why metrology systems
choose it for phase sensitivity and microscopy usually fights it. The
same objective, two different instruments, decided at the source.

<Widget type="quiz" id="com.github.richbai90.optics.coherent-incoherent-imaging.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.coherent-incoherent-imaging.card-modes" />

<Widget type="flashcard" id="com.github.richbai90.optics.coherent-incoherent-imaging.card-kohler" />

## Recommended reading and viewing

Lecture 22 works the two imaging modes side by side; lecture 23 carries
them to a single lens on the bench.

<Widget type="resource-link" id="com.github.richbai90.optics.coherent-incoherent-imaging.link-lecture-22" />

<Widget type="resource-link" id="com.github.richbai90.optics.coherent-incoherent-imaging.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.coherent-incoherent-imaging.link-lecture-23" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 22 — coherent and
  incoherent
  imaging](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-22-coherent-and-incoherent-imaging/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 22 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec22/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 23 — imaging with a single
  lens](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-23-imaging-with-a-single-lens/)
  (CC BY-NC-SA 4.0)
- Cutoffs verified: coherent NA/λ = 182 cycles/mm, incoherent
  2NA/λ = 365 cycles/mm at NA = 0.1, λ = 550 nm
