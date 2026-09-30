---
title: The Propagation of Light
description: Light as an electromagnetic wave, the spectrum, wavefronts and rays, and when the ray model is valid.
order: 3
section: nature-of-light
---

Light is an electromagnetic wave: a traveling oscillation of electric and
magnetic fields that sustains itself through empty space. Every such wave is
characterized by its **wavelength** $\lambda$ and **frequency** $f$, locked
together by the propagation speed $c$ — in vacuum, a constant of nature:

<Widget type="math" id="com.github.richbai90.optics.the-propagation-of-light.math-cflambda" />

The visible band is a sliver of the full electromagnetic spectrum, roughly
$380\text{–}750\,\text{nm}$. Optics as a discipline mostly means this band —
plus its near neighbors (infrared, ultraviolet) that the same math governs.

| Band | Wavelength | Notes |
|---|---|---|
| Gamma / X-ray | $\lesssim 10\,\text{nm}$ | photons dominate the picture |
| Ultraviolet | $10\text{–}380\,\text{nm}$ | ionizing near the short end |
| **Visible** | $380\text{–}750\,\text{nm}$ | violet → red |
| Infrared | $750\,\text{nm}\text{–}1\,\text{mm}$ | thermal imaging, telecom |
| Radio / microwave | $\gtrsim 1\,\text{mm}$ | wave optics at huge scale |

## Wavefronts and rays

Picture ocean waves viewed from above: the crests are **wavefronts** —
surfaces of constant phase. A **ray** is the perpendicular to the wavefront
pointing along the direction of travel. The two pictures are fully equivalent
for describing propagation, and the choice is pragmatic:

> Experiments show that when light interacts with an object several times
> larger than its wavelength, it travels in straight lines and acts like a
> ray. Its wave characteristics are not pronounced in such situations.
> — OpenStax University Physics III, §1.2
> (<https://openstax.org/details/books/university-physics-volume-3>, CC BY 4.0)

So the rule of thumb for the whole course:

- Object sizes $\gg \lambda$ (lenses, mirrors, raindrops): **ray optics**
  works, and it fills the next four sections.
- Object sizes comparable to $\lambda$ (slits, apertures edges): **wave
  optics** is unavoidable — sections on interference and diffraction.
- The wavelength of visible light is around half a micrometer: a pinhole is
  wave-optics territory; a camera lens is ray-optics territory.

<Widget type="quiz" id="com.github.richbai90.optics.the-propagation-of-light.quiz1" />

## Speed, media, and the constant $c$

In vacuum, $c = 299{,}792{,}458\,\text{m/s}$ (defined exactly, since 1983, via
the meter). In matter, light slows down by a factor called the **index of
refraction** of the medium — the next lesson's main character. The slowing is
a microscopic interference effect between the driving wave and the field
re-radiated by the medium's charges, not a literal stop-and-go of photons;
treating it as $v = c/n$ is exact for our purposes.

Two consequences to keep in mind:

1. Frequency never changes crossing a boundary (the wave must stay continuous
   in time); wavelength therefore shrinks inside a denser medium.
2. A pulse of light travels at the *group velocity*; in most transparent
   media it equals $c/n$, but near absorption resonances it can deviate
   wildly — a preview of [dispersion](04-light-in-matter.md).

<Widget type="quiz" id="com.github.richbai90.optics.the-propagation-of-light.quiz2" />

<Widget type="flashcard" id="com.github.richbai90.optics.the-propagation-of-light.card-wavefront" />

<Widget type="flashcard" id="com.github.richbai90.optics.the-propagation-of-light.card-spectrum" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.the-propagation-of-light.link-lecture-1" />

<Widget type="resource-link" id="com.github.richbai90.optics.the-propagation-of-light.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 1 — course organization;
  introduction to optics](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-1-course-organization-introduction-to-optics/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.2 (The Propagation of Light) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)