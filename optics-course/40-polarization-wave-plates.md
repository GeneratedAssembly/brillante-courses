---
title: Wave Plates and Polarization Effects
description: Birefringence as engineering — retarders built from crystal thickness, the devices they enable in imaging systems, and the polarization errors that high-NA optics cannot avoid.
order: 40
section: imaging-systems-resolution
---

Light's polarization channel,
[built in the wave-optics foundations](26-polarization-poynting.md),
turns practical here: birefringent plates whose thickness sets a
retardance, the devices that retardance enables, and the polarization
aberrations that appear — uninvited — whenever optics run fast and
oblique. This is the imaging-systems section's polarization ledger.

## Retarders: phase engineering in crystal

A birefringent crystal (calcite, quartz) presents two indices to two
axes — the extraordinary axis sees a different $n$ than the ordinary
one. A plate of thickness $t$ delays one component relative to the
other:

<Widget type="math" id="com.github.richbai90.optics.polarization-wave-plates.math-retardance" />

Thickness *is* the design. A **quarter-wave plate** ($\delta = \pi/2$)
of crystalline quartz ($\Delta n = 0.0092$) at 550 nm is $t = 14.9\ \mu$m
thick — and 10.9 µm at 400 nm, which is why multiple-order plates (an
integer number of waves thicker) are ground with a compensating
zero-order pair to stay broadband. Point a quarter-wave plate at 45° to
linear polarization and out comes circular ([the
state-building rule](26-polarization-poynting.md#building-states-from-s-and-p));
point a **half-wave plate** ($\delta = \pi$) at angle $\theta$ and the
linear polarization rotates by $2\theta$ — an electrically unwittable,
mechanically precise polarization steering wheel.

<Widget type="interactive" id="com.github.richbai90.optics.polarization-wave-plates.int-retardance" />

<Widget type="quiz" id="com.github.richbai90.optics.polarization-wave-plates.quiz1" />

## Devices in the imaging train

Retarders plus [polarizers](26-polarization-poynting.md#polarizers-and-malus-s-law)
assemble the imaging toolbox:

- **Polarizing beamsplitter**: a birefringent cube splitting s and p
  into two ports — the backbone of polarization-resolving cameras and
  of every digital projector's modulator.
- **Liquid-crystal modulators**: voltage-tuned retardance, switching
  polarization in milliseconds — the pixel engine of displays and the
  wavefront shapers of adaptive optics.
- **Differential interference contrast (DIC)**: two orthogonally
  sheared pupil images, recombined with a bias retardance —
  [phase gradients become
  intensity](34-spatial-filtering.md#phase-objects-and-phase-contrast)
  with an adjustable bias, the microscope's sharpest relief of
  unstained structure.
- **Photoelasticity**: a stressed plastic part between crossed
  polarizers maps internal stress as interference colors — birefringence
  as a strain gauge.

<Widget type="quiz" id="com.github.richbai90.optics.polarization-wave-plates.quiz2" />

## Polarization aberrations

Even isotropic glass polarizes when rays strike surfaces obliquely —
each Fresnel reflection is slightly diattenuating and retarding
([the coefficients' angle
behavior](17-fresnel-equations.md#reflectance-and-the-4-rule)), and the
effects accumulate across a train. Two rules of thumb size it:
diattenuation and retardance scale as $\mathrm{NA}^2$ — invisible at
f/8, percent-level at NA 0.9, dominant in total-internal-reflection
prisms — and stress birefringence adds a spatially varying retardance
wherever lenses are molded or mounted hard. The cost is
[Malus-law](26-polarization-poynting.md#polarizers-and-malus-s-law)
contrast leak: a train specced for 10⁻⁴ extinction delivers less, and
the delivered polarization varies across the field. High-NA microscope
objectives carry a **polarization-free** design region for exactly this
reason; polarization aberration is now a standard budget line in
serious lens design.

<Widget type="quiz" id="com.github.richbai90.optics.polarization-wave-plates.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.polarization-wave-plates.card-plates" />

<Widget type="flashcard" id="com.github.richbai90.optics.polarization-wave-plates.card-aberrations" />

## Recommended reading and viewing

Lecture 26 pairs wave plates with depth-of-focus topics; OpenStax §1.8
grounds the polarization vocabulary.

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-wave-plates.link-lecture-26" />

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-wave-plates.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.polarization-wave-plates.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 26 — depth of focus and
  field; polarization; wave
  plates](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-26-depth-of-focus-and-field-polarization-wave-plates/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 26 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec26/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.8 (Polarization) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: quartz zero-order quarter-wave thickness
  $t = \lambda/(4\Delta n)$: 14.9 µm at 550 nm, 10.9 µm at 400 nm
  ($\Delta n = 0.0092$); diattenuation/retardance of surface films
  scale as NA² (standard polarization-aberration theory)
