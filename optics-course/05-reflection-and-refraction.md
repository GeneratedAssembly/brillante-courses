---
title: Reflection and Refraction
description: The law of reflection, Snell's law, reversibility, and total internal reflection — the two rules on which all ray optics stands.
order: 5
section: rays-reflection-refraction
---

Two laws govern every ray-optics device in this course — mirrors, prisms,
fibers, lenses. Both were known quantitatively by the 17th century; both were
only *explained* two centuries later, by the wave theory (see
[Huygens' principle](27-huygens-superposition.md)) and ultimately by
Maxwell's equations.

## The law of reflection

> The law of reflection states that the angle of reflection equals the angle
> of incidence — θᵣ = θᵢ. The angles are measured relative to the
> perpendicular to the surface at the point where the ray strikes the surface.
> — OpenStax University Physics III, §1.3
> (<https://openstax.org/details/books/university-physics-volume-3>, CC BY 4.0)

Whether you see a *mirror image* or a *diffuse glint* depends on surface
roughness compared to $\lambda$: a smooth surface sends all parallel rays to
one direction (specular reflection); a rough surface scatters them (diffuse
reflection) — which is why paper is visible from any angle but a mirror is
not.

Two classic consequences:

- **Corner reflector**: two (or three) mutually perpendicular mirrors return
  any incoming ray exactly antiparallel to its arrival — independent of the
  incidence angle. Bicycle reflectors, lunar ranging arrays, and laser
  cavities all exploit this.
- **Plane-mirror imaging**: your image stands exactly as far behind the mirror
  as you stand in front — but left and right are swapped along the viewing
  axis.

## Snell's law

When a ray crosses into a medium with a different index $n$, it bends. The
rule discovered by Ibn Sahl (984 CE) and Willebrord Snellius (1621):

<Widget type="math" id="com.github.richbai90.optics.reflection-and-refraction.math-snell" />

Read it physically: with $n_2 > n_1$ (into glass), $\sin\theta_2$ must shrink,
so the ray bends **toward the normal**; leaving glass, it bends away. The path
is exactly **reversible**: reverse any ray and it retraces its route — the
basis of *principle of least time* arguments (Fermat's principle) used later
for [perfect focusing](07-perfect-focusing-and-the-paraxial-approximation.md).

<Widget type="interactive" id="com.github.richbai90.optics.reflection-and-refraction.int-snell" />

<Widget type="quiz" id="com.github.richbai90.optics.reflection-and-refraction.quiz1" />

## Total internal reflection

Going from a denser to a rarer medium ($n_1 > n_2$), the ray bends *away* from
the normal — and there is an incidence angle beyond which no ray escapes at
all. Setting $\theta_2 = 90°$ in Snell's law gives the **critical angle**:

<Widget type="math" id="com.github.richbai90.optics.reflection-and-refraction.math-critical" />

Beyond $\theta_c$, **total internal reflection (TIR)** returns 100% of the
light — better than any metal mirror, which is why TIR prisms outperform
aluminum mirrors in binoculars and cameras.

Applications worth remembering:

- **Optical fibers**: the cladding index is lower than the core index, so
  grazing rays stay trapped over kilometers of fiber.
- **Diamond's sparkle**: with $n = 2.42$, $\theta_c \approx 24.4°$ — light
  entering a cut stone bounces internally many times before finding a facet
  pointing where it can escape, and dispersion (next lesson) splits it into
  fire.

<Widget type="quiz" id="com.github.richbai90.optics.reflection-and-refraction.quiz2" />

<Widget type="quiz" id="com.github.richbai90.optics.reflection-and-refraction.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.reflection-and-refraction.card-snell" />

<Widget type="flashcard" id="com.github.richbai90.optics.reflection-and-refraction.card-tir" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.reflection-and-refraction.link-lecture-2" />

<Widget type="resource-link" id="com.github.richbai90.optics.reflection-and-refraction.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 2 — reflection and refraction,
  prisms, waveguides, and
  dispersion](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-2-reflection-and-refraction-prisms-waveguides-and-dispersion/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.3 (The Law of Reflection), §1.4
  (Refraction), §1.5 (Total Internal Reflection) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)