---
title: Thick and Composite Lenses
description: Real lenses have thickness, and real instruments stack several. Principal planes and the composite-lens formula keep the algebra manageable.
order: 10
section: lenses-image-formation
---

No real lens is thin. The glass has thickness, the refractions happen at
genuinely different planes, and useful instruments chain several elements.
The ray-matrix formalism from [lesson 8](08-ray-transfer-matrices.md) absorbs
all of this without new physics — the thin lens was a special case, and this
lesson is what it was a special case of.

## Thick lenses: two refractions, one translation

Trace a marginal ray through a lens of finite thickness $t$ and index $n$:
refract at the first surface, translate through the glass, refract at the
second. The system matrix is the product
$\mathcal{R}_2\,T(t)\,\mathcal{R}_1$ of three matrices you already know, and
every imaging property of the thick lens sits in its four entries. Nothing
about the matrix method changes because the glass is thick — the thin lens
was the approximation $t \to 0$, which collapsed the two refractions into one
plane.

<Widget type="quiz" id="com.github.richbai90.optics.thick-composite.quiz1" />

## Principal planes

A thick (or composite) system no longer has *one* place to measure $f$ from.
It has two: the **principal planes**. Any paraxial system in air behaves, from
object space to image space, exactly like a thin lens of focal length $F$ —
except that the "lens plane" splits in two:

- a ray entering aimed at the **first principal plane** $H$ exits from the
  second principal plane $H'$ at the same height, as if it had translated
  between them with unit magnification;
- the **effective focal length** $F$ is measured between a principal plane
  and the corresponding focus.

For a system matrix $M = \begin{pmatrix} A & B \\ C & D \end{pmatrix}$ in
air, the effective focal length reads directly off the lower-left entry:

<Widget type="math" id="com.github.richbai90.optics.thick-composite.math-cfeq" />

This is why the matrix formalism earns its keep: the same four numbers that
tell you *whether* the system images ($B = 0$) also tell you its focal length
($C$) and magnification ($A$) — for one thick lens or a whole zoom barrel.

## Two lenses apart: the composite formula

The workhorse case is two thin lenses, $f_1$ then $f_2$, separated by $d$.
The stepper below derives the composite focal length straight from the matrix
product $\mathcal{L}_2\,T(d)\,\mathcal{L}_1$:

<Widget type="stepper" id="com.github.richbai90.optics.thick-composite.stepper-composite" />

<Widget type="math" id="com.github.richbai90.optics.thick-composite.math-composite" />

The formula contains everything in this lesson as special cases. In contact
($d \to 0$) the powers simply add — the rule your optometrist uses when
stacking a −5.0 D lens and a +2.0 D lens into a −3.0 D prescription. And
separation is a design *resource*: moving $d$ changes $F$ without changing
either element.

<Widget type="interactive" id="com.github.richbai90.optics.thick-composite.int-focal" />

<Widget type="quiz" id="com.github.richbai90.optics.thick-composite.quiz2" />

## What separation buys: telephoto and afocal

Two arrangements deserve names:

- **Telephoto**: a positive front element followed by a negative rear element,
  separated by enough that the poles and signs work out to a *long* effective
  focal length in a *short* barrel — the compact "long lens" of every camera
  bag, and (with the signs flipped) the reverse-telephoto design that leaves
  room for a sensor behind a wide-angle lens.
- **Afocal**: at $d = f_1 + f_2$ the composite power vanishes
  ($1/F = 0$) — parallel rays in, parallel rays out. The pair no longer
  focuses at all; it *changes angle*. That is a telescope (covered properly in
  the [instruments section](15-telescopes.md)).

<Widget type="quiz" id="com.github.richbai90.optics.thick-composite.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.thick-composite.card-principal" />

<Widget type="flashcard" id="com.github.richbai90.optics.thick-composite.card-telephoto" />

<Widget type="flashcard" id="com.github.richbai90.optics.thick-composite.card-afocal" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.thick-composite.link-lecture-5" />

<Widget type="resource-link" id="com.github.richbai90.optics.thick-composite.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.thick-composite.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 5 — thick lenses, the composite
  lens, the
  eye](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-5-thick-lenses-the-composite-lens-the-eye/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.5 (Thin Lenses) — the thin-lens
  idealization that thick-lens and composite theory generalize;
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
