---
title: From Equation to Component
description: The geometry half of fabrication — phase-to-depth formulas, the book's worked 1 × 2 beamsplitter, mask generation economics, and the constraints that decide what can actually be made.
order: 12
section: fabrication
---

The book poses the fabrication questions that chapters 6–9 answer: How does a
function in a computer become a component? What material? What limits? How do
you know what you made? Start with the good news: in the scalar thin-phase
world, **the geometry splits into two independent parts**:

- the **lateral transition points** — where the phase profile jumps by $2\pi$
  (or a fraction of it) — which carry the *optical function*;
- the **depth** — set only by the wavelength and the two refractive indices —
  which carries the *efficiency*.

## The two master equations

**Angles** come from the grating equation at incidence $\theta_i$ (Eq. 6.1):

<Widget type="math" id="com.github.richbai90.diffractive.fab.math-grating" />

**Depth** comes from OPD (Eqs. 6.2a/6.2b):

<Widget type="math" id="com.github.richbai90.diffractive.fab.math-depth" />

<Widget type="interactive" id="com.github.richbai90.diffractive.fab.int-depth" />

## The worked example: a 1 × 2 beamsplitter

<Widget type="stepper" id="com.github.richbai90.diffractive.fab.step-1x2" />

An SEM of the actual grating (book's Fig. 6.3, from Digital Optics Corp.)
shows the 0.69-µm-deep, 2-µm-wide grooves — design and reality, to scale.

<Widget type="quiz" id="com.github.richbai90.diffractive.fab.quiz-depth" />

## Masks: where the money goes

Every photolithographic DOE starts with **binary transmission masks** — chrome
on glass, clear/opaque. The industry-standard path is an **e-beam mask writer**
(raster-scanned electrons in the **MEBES** format: the pattern is *fractured*
into rectangles and trapezoids, written per stripe of $32768 \times 1024$
address units). The economics are brutal and worth memorizing:

- a new e-beam writer costs **> $5 million** — so you buy masks from a
  **mask foundry** instead;
- a simple mask at 0.5-µm address units ≈ **$1000**; a complex one at 0.1 µm ≈
  **$20,000+**;
- stage **butting errors** leave nanometer discontinuities between stripes;
- curved patterns (lenses!) suffer **fit error** $\varepsilon$ from
  rectilinear primitives, giving local wavefront error
  $\varepsilon \sin\theta / \lambda$ — more trapezoids or smaller address
  units fix it, at cost and write time.

The book's educational alternative (its own Georgia Tech path): write patterns
in PostScript from Mathematica or CODE V, output on a graphic-arts
**imagesetter** — letter-sized transparencies for **$25 in a day**, floor
~30 µm features; **photoreduce** onto glass plates and the floor drops to ~7
µm. Enough to learn on; the 1 × 5 Dammann example below shows why it is not
enough for production.

<Widget type="quiz" id="com.github.richbai90.diffractive.fab.quiz-masks" />

## The constraints that shape designs

**Minimum feature size.** Easiest way to fail: design a DOE that cannot be
fabricated. Set the fab floor as a constraint *inside* the iterative design
loop. **Aspect ratio** $\mathrm{AR} = d/b$: keep it **below 1** as a rule;
deep structures need thick resist, thick resist diffracts the exposing light,
and pattern fidelity dies. AR 5–10 is possible with hard masks (chrome,
aluminum, dielectric etch-stops) and special chemistries.

Worked feasibility check — the **1 × 5 Dammann grating**: 7.5° between orders
at $\lambda = 1.310\,\mu$m ⇒ $\Lambda = 10\,\mu$m; its minimum feature is ~7%
of the period = **0.7 µm**, with depth 1.48 µm in fused silica — inside
contact/projection lithography, **beyond PostScript masks**, and at aspect
ratio > 2:1 ("challenging but achievable").

**Thin-film coatings.** DOEs reflect like refractive surfaces (≈4% per surface
in glass, ≈30% in silicon), so they get AR coatings — but a "thin" film is a
*significant fraction of the relief geometry*: dielectric stacked on the **side
walls** changes the grating profile and can *reduce* efficiency in the desired
orders even while raising total transmission. Use anisotropic deposition
(sputtering, evaporation, ion-assisted) that prefers horizontal tops, and
model the coated profile before trusting the part.

**Materials** (Table 6.1, abridged):

| Material | λ range | n | Notes |
|---|---|---|---|
| Fused silica | 0.15–3 µm | ~1.5 | material of choice, UV through near-IR |
| BK7 | 0.35–2 µm | ~1.5 | impurities make precision microstructures hard |
| Si | 1–7 µm | ~3.5 | IR; high index helps shadowing, hurts depth tolerance |
| Ge | 2–20 µm | ~4.0 | mid-IR |
| ZnSe / ZnS | 0.6–18 / 4–13 µm | ~2.4 / ~2.2 | night vision, CO₂ lasers |
| CaF₂ | 0.15–7 µm | ~1.4 | UV–IR, challenging to fabricate |
| Plastics | 0.4–1.6 µm | 1.4–1.6 | cheap; reduced optical/environmental performance |

High index ⇒ shallow structures (small AR, less shadowing) **but** punishing
depth tolerances: a 1% phase error at 1.55 µm is **17.5 nm in fused silica
versus 3 nm in silicon**.

## Facilities

Clean-room class = number of >0.5-µm particles per cubic foot: **class 1000
suffices for most DOEs; class 100 for fine, repeatable work** (microelectronics
goes to class 1). HEPA ceiling flow, positive pressure, 68 ± 1 °F, 45 ± 5% RH —
and the room temperature must match the temperature at which your mask was
written. The biggest contamination source is the operator ("imagine a giant
powdered jelly donut"). Substrates (20–150+ mm wafers) are interferometrically
checked for transmitted wavefront error — **λ/4 to λ/20 rms typical** — then
cleaned: solvent rinses, **RCA-1** (organics: NH₄OH/H₂O₂/water), **RCA-2**
(metals: HCl/H₂O₂/water), piranha, dehydration bake. Photoresist will not
adhere to a dirty or wet surface; nothing else in this chapter works if step
zero fails.

<Widget type="quiz" id="com.github.richbai90.diffractive.fab.quiz-ar" />

<Widget type="quiz" id="com.github.richbai90.diffractive.fab.quiz-material" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.fab.card-split" />
