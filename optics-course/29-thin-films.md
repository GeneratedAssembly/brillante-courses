---
title: Thin Films
description: Soap bubbles, oil slicks, and anti-reflection coatings — interference between the two faces of a film, with the half-wavelength bookkeeping that a phase flip at reflection demands.
order: 29
section: interference-coherence
---

A soap bubble's swirl of colors is an interference pattern drawn by a
film thinner than a wavelength stack of them. The physics is
[two-beam interference](28-two-slit-interference.md) with a twist: the
two interfering beams are the reflections from the film's two *faces*,
and one of them may pick up a half-wavelength phase flip on the way.
Getting the flips right is the entire difficulty.

## The phase flip at reflection

[Maxwell's interface bookkeeping](25-maxwell-em-waves.md#the-fresnel-coefficients-derived)
showed the amplitude reflection coefficient
$r = (n_1 - n_2)/(n_1 + n_2)$: negative when light reflects off a
*denser* medium. A negative $r$ is a $\pi$ phase flip — the reflected
wavecrest leaves inverted. So:

- **Low → high index** (air to glass): the reflection flips phase.
- **High → low index** (glass to air): no flip.

This one rule, plus the extra path $2nt$ that the second reflection
travels inside the film, sets every thin-film color in nature and every
coating in the lab.

<Widget type="math" id="com.github.richbai90.optics.thin-films.math-conditions" />

<Widget type="quiz" id="com.github.richbai90.optics.thin-films.quiz1" />

## Soap bubbles and oil slicks

A soap film ($n \approx 1.33$) sits in air on both faces: the top
reflection flips, the bottom does not — one flip total. Different
thicknesses therefore favor different wavelengths in reflection: at
$2nt = 266$ nm (about 100 nm thick) green is constructively reinforced
($\lambda = 532$ nm, $m = 0$), while at 200 nm the same film drains
green ($m = 1$ term lands on 532 nm destructively) and boosts only weak
violet ($m = 1$ constructive at 368 nm). Drain and boost
shift across the film as gravity thins it, and the swirl follows. Since
only *some* wavelengths are reinforced in reflection, the transmitted
light carries the complement — the reason a bubble's dark patches (zero
reflection) transmit almost everything.

<Widget type="interactive" id="com.github.richbai90.optics.thin-films.int-film" />

<Widget type="quiz" id="com.github.richbai90.optics.thin-films.quiz2" />

## The anti-reflection coating

The most valuable film in optics is a quarter-wave of magnesium fluoride
($n_f = 1.38$) deposited on each lens surface. Air → MgF₂ flips; MgF₂ →
glass ($1.38 \to 1.5$) also flips — two flips cancel, so the coating's
condition inverts: reflection is *destroyed* when $2n_ft = \lambda$
(m = 1) — with minimum thickness the quarter-wave value
$t = \lambda_0/(4n_f)$:

<Widget type="math" id="com.github.richbai90.optics.thin-films.math-arcoating" />

For $\lambda_0 = 550$ nm, $t \approx 100$ nm. The bare surface reflected
$4\%$; the coated surface reflects $(|r_1| - |r_2|)^2 \approx 1.4\%$ at
the design wavelength — imperfect, because $r_1 \neq |r_2|$ for
real glasses, which is why multi-layer coatings and
[doublets](20-chromatic-spherical-coma.md#the-achromatic-doublet) share
the load in serious lenses. Coated lenses look purple in reject light:
the design kills green, leaving the complement to remind you the coating
is there.

<Widget type="quiz" id="com.github.richbai90.optics.thin-films.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.thin-films.card-flips" />

<Widget type="flashcard" id="com.github.richbai90.optics.thin-films.card-coating" />

## Recommended reading and viewing

OpenStax covers thin-film interference with worked bubble and coating
examples; lecture 15 supplies the two-beam machinery it assumes.

<Widget type="resource-link" id="com.github.richbai90.optics.thin-films.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.thin-films.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle;
  interferometers; Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0) — two-beam interference machinery
- OpenStax University Physics III, §3.5 (Interference in Thin Films) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: MgF₂ quarter-wave $t = 550/(4 \times 1.38) =
  99.6$ nm; $r_1 = -0.160$, $r_2 = -0.042$, residual
  $R = (0.160-0.042)^2 \approx 1.4\%$; soap film ($n = 1.33$)
  constructive reflection wavelengths at $t = 100/200/300$ nm:
  532 / 368 / 532 nm (one-flip case, $m = 0, 1, 1$; green destroyed at
  $t = 200$ nm)
