---
title: About This Course
description: The source text, the prerequisites, and the roadmap from wavefront thinking to a tested diffractive optical element.
order: 0
section: start-here
---

This course follows **Diffractive Optics: Design, Fabrication, and Test** by
Donald C. O'Shea, Thomas J. Suleski, Alan D. Kathman, and Dennis W. Prather
(SPIE Press Tutorial Texts in Optical Engineering, Vol. TT62, 2004,
ISBN 0-8194-5171-1). The book grew out of a hands-on short course taught at the
Georgia Institute of Technology since 1994, and its structure — theory, design,
fabrication, test, applications — is exactly the structure of these lessons.

The book is © SPIE; all rights reserved. This course **paraphrases and teaches
its material** with the book cited throughout: equations carry the book's numbers
(2.27, 4.34, 5.7, …) so you can check them against the printed text, but nothing
here reproduces the book's figures verbatim. If you are doing real DOE work, buy
the book — it is inexpensive and it is the map for this entire field.

<Widget type="resource-link" id="com.github.richbai90.diffractive.about.res-wikipedia" />

## What a diffractive optical element is

A **diffractive optical element (DOE)** controls light not by refraction at a
smooth curved surface, but by *segmenting a wavefront and redirecting the
segments through interference and phase control* — micro-structured surface
relief, typically a few wavelengths deep, patterned lithographically. The whole
subject turns on one sentence from the book's introduction:

<Widget type="flashcard" id="com.github.richbai90.diffractive.about.card-theme" />

## Prerequisites

You should be comfortable with:

- **Basic optics** — rays, lenses, focal length, refractive index. The thin
  lens and ray-matrix machinery used freely here is the subject of the
  companion *Optics* course on this server.
- **Waves and interference** — phasors, superposition, wavelength.
- **Fourier transforms** at the level of "I have seen a sinc function" —
  everything is rebuilt from scratch in
  [Fourier Analysis of DOEs](04-fourier-analysis-of-does.md) anyway.
- Integrals and complex numbers. The book's own bar for admission: "can stand
  the sight of an integral or two."

## The roadmap

The course walks the full engineering chain — the same chain the book walks:

1. **Foundations** — the wavefront viewpoint, Huygens and Fresnel zones,
   Rayleigh–Sommerfeld scalar diffraction, Fourier analysis of periodic
   structures, and the efficiency of binary gratings.
2. **Rigorous theory** — what happens when features approach the wavelength:
   plane-wave spectrum propagation, the modal method (RCWA), FDTD, and
   effective medium theory.
3. **Design** — lens design vocabulary, diffractive lenses and kinoforms,
   hybrid refractive–diffractive lenses, fanout grating design, and the
   iterative optimization algorithms (bidirectional, annealing, genetic).
4. **Fabrication** — turning a phase function into a surface relief: masks,
   photoresist, etching, the binary-optics multilevel process, and the wider
   survey of writing and replication methods.
5. **Testing** — profilometry, AFM, SEM, interferometry, scatterometry — and
   how fabrication errors degrade optical performance.
6. **Applications** — scan lenses, landscape lenses, superzones, thermal
   athermalization, lens arrays, beam shapers, Talbot illuminators,
   subwavelength structures, and optical communications.

Every lesson ends with quizzes and flashcards; key equations carry expandable
term definitions; interactive plots let you move the design variables yourself.

<Widget type="quiz" id="com.github.richbai90.diffractive.about.quiz-seq" />

<Widget type="quiz" id="com.github.richbai90.diffractive.about.quiz-prereq" />
