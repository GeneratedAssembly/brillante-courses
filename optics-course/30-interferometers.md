---
title: Interferometers
description: Measuring with waves — the Michelson interferometer's round-trip phase ruler, fringe counting as nanometrology, and the family of interferometers that test surfaces, indices, and gravitational waves.
order: 30
section: interference-coherence
---

A ruler's graduation is a wavelength, its travel a distance, its reading
a fringe count. Interferometers compare two paths of light and read the
difference in stripes — resolving motions of nanometers with hardware
built from mirrors and beamsplitters. Michelson invented the genre to
hunt for the ether and ended up measuring nothing with unprecedented
precision; the nothing was the discovery (see [a brief history of
optics](02-a-brief-history-of-optics.md)).

## The Michelson interferometer

A beamsplitter divides one beam into two arms; mirrors return them; they
recombine and interfere. The arms' *difference* in optical path length
sets the phase:

<Widget type="math" id="com.github.richbai90.optics.interferometers.math-michelson" />

The output intensity cycles once per $\lambda/2$ of mirror travel — the
round trip doubles the sensitivity. Counting fringes while a mirror
moves is the most precise ruler in classical physics:

<Widget type="interactive" id="com.github.richbai90.optics.interferometers.int-fringecount" />

Move a mirror by $1\ \mu$m at $\lambda = 550$ nm and the output blinks
$2\Delta L/\lambda \approx 3.6$ fringes. Slip a glass slide
($n = 1.5$, $t = 100\ \mu$m) into one arm and the optical path jumps by
$(n-1)t = 50\ \mu$m — $182$ fringes of shift, from a shard of glass no
thicker than a hair. Air currents, thermal expansion, table vibration:
each leaves its fingerprint in the count.

<Widget type="quiz" id="com.github.richbai90.optics.interferometers.quiz1" />

## What interferometers measure

- **Length and displacement** — fringe counting as above; the meter
  itself was redefined in 1960 as $1{,}650{,}763.73$ wavelengths of
  krypton-86's orange line, an interferometric ruler by fiat.
- **Refractive index** — a gas cell in one arm; pump it out and count
  the fringes to read $(n - 1)$ at the $10^{-8}$ level.
- **Surface figure** — lay a reference flat over a test optic: the
  fringe contours are a topographic map of the surface error, read at
  fractions of a wavelength (the same trick as the diffractive-optics
  course's testing lesson).
- **Gravitational waves** — LIGO is two 4-km Michelson arms whose
  differential strain, $10^{-19}$ m or so, still reads out as a fringe
  phase.

<Widget type="quiz" id="com.github.richbai90.optics.interferometers.quiz2" />

## The wider family

The Michelson's folded geometry is one choice among many. The
**Mach–Zehnder** keeps the arms on separate benches, which is what
phase-contrast imaging and integrated photonics want. The **Fizeau**
interferes a surface's own reflection against a reference in place — the
optical shop's daily tool. **Common-path** designs (shearing
interferometers) split a beam against its shifted self, immune to
vibration because both paths breathe together. All of them are the same
bookkeeping — two amplitudes, one phase difference — wearing different
geometry, and all of them pay the same toll: the light must be
[coherent](31-coherence.md) enough to interfere over the arm
difference.

<Widget type="quiz" id="com.github.richbai90.optics.interferometers.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.interferometers.card-counting" />

<Widget type="flashcard" id="com.github.richbai90.optics.interferometers.card-family" />

## Recommended reading and viewing

Lecture 15 introduces the Michelson and its fringe behavior; OpenStax
§3.6 walks the geometry and the ether-morality history.

<Widget type="resource-link" id="com.github.richbai90.optics.interferometers.link-lecture-15" />

<Widget type="resource-link" id="com.github.richbai90.optics.interferometers.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.interferometers.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 — Huygens' principle;
  interferometers; Fresnel
  diffraction](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-15-huygens-principle-interferometers-fresnel-diffraction/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 15 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec15/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §3.6 (The Michelson Interferometer) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: $2\Delta L/\lambda$ at $\lambda = 550$ nm gives
  3.64 fringes per µm of mirror travel; a $100\ \mu$m, $n = 1.5$ slide
  shifts $2(n-1)t/\lambda = 182$ fringes; the 1960 meter definition:
  $1{,}650{,}763.73$ wavelengths of Kr-86 (605.78 nm)
