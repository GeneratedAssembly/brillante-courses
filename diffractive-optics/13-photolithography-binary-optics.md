---
title: Photolithography and the Binary Optics Process
description: Resist chemistry, spin coating, exposure and development, anisotropic etching — and the N-mask / 2^N-level process that made DOE manufacturing real.
order: 13
section: fabrication
---

The microelectronics industry's entire photolithographic toolset transfers to
DOEs: the same resists, the same steppers, the same plasmas. This lesson walks
one wafer through the process, then assembles the steps into the **binary
optics** multilevel sequence — the flagship DOE fabrication method.

## Photoresist

A **photoresist is a light-sensitive conformal polymer** with three
constituents: a **photoactive compound** (in positive resists, diazo
naphthoquinone, DNQ), a **solvent carrier**, and a **novolak resin** matrix.
Definitions that must not be mixed up:

<Widget type="flashcard" id="com.github.richbai90.diffractive.photo.card-tone" />

Resist response is quantified by the **Dill parameters**: bleachable
absorption $A$ (before exposure, 1/µm), non-bleachable absorption $B$ (after,
1/µm), and rate constant $C$ (cm²/mJ) for how fast exposure acts.

Coating: prime the clean wafer with **HMDS** for adhesion, dispense resist,
**spin at thousands of RPM** — final thickness is set by viscosity × spin
speed; then the **softbake** drives solvent and is "a critical step in resist
imaging." Particles cause comet tails; striations call for leveling agents.

## Exposure and development

Exposure dose is **lamp power × time (mJ/cm²)** through the mask. Development
of positive DNQ resist: UV creates carboxylic acid and releases nitrogen, so
exposed areas dissolve in aqueous base (NaOH, KOH, or **TMAH**). The
**resist response curve** (remaining thickness vs dose) has a *knee* whose
slope beyond it is the contrast, and a **dose to clear $E_0$**. Binary
lithography uses only two points — below the knee and above $E_0$; the region
*between* is what [gray-scale lithography and direct writing](14-fabrication-survey.md)
exploit for continuous relief.

Printing modes and their floors:

<Widget type="flashcard" id="com.github.richbai90.diffractive.photo.card-modes" />

On reflective substrates the exposure sets up a **standing wave** in the resist
— corrugated sidewalls — cured by a **postexposure bake (PEB)** that smears
the chemical gradient, or by an antireflection coating; residual "scum" in
opened channels gets an oxygen-plasma **descum**.

<Widget type="quiz" id="com.github.richbai90.diffractive.photo.quiz-er0" />

## Etching

Resist alone rarely survives as the optic — its optical and mechanical
properties are wrong — so the pattern is transferred into the substrate, and
**dry etching dominates**:

<Widget type="math" id="com.github.richbai90.diffractive.photo.math-select" />

- **Kinetic** processes (ion milling: Ar/Kr sputtering) etch almost anything,
  isotropically.
- **Reactive** processes (F₂ chemistry for fused silica, Cl or F for silicon,
  O₂ for resist) etch chemically, isotropically.
- **RIE combines both**: plasma ions, biased *vertically* into the wafer —
  highly anisotropic, the workhorse. (RIBE/CAIBE are the beam-type cousins.)
- Fused silica RIE runs **15–50 nm/min** (up to ~1000); silicon **15–3000
  nm/min**. The one common **wet** option, buffered HF on fused silica, is
  cheap and glass-smooth at ~100 nm/min — but isotropic: undercut, sloped
  walls, unsuitable for fine patterns, and HF is extremely dangerous.

Selectivity **2–3+** is wanted for high-aspect-ratio binary features; **S ≈ 1**
is wanted when transferring a *continuous* profile (next lesson).

<Widget type="quiz" id="com.github.richbai90.diffractive.photo.quiz-etch" />

## Binary optics: N masks → 2^N levels

Pre-1980s, N masks gave $N+1$ steps. The MIT Lincoln Laboratory binary-optics
process (mid-1980s; Swanson's Report 854) changed the arithmetic:

<Widget type="math" id="com.github.richbai90.diffractive.photo.math-levels" />

<Widget type="interactive" id="com.github.richbai90.diffractive.photo.int-levels" />

The sequence: coat, expose through mask 1, develop, etch depth $d$; strip,
recoat, align mask 2, etch $d/2$; mask 3 etches $d/4$… Each mask's pattern
encodes the *binary decomposition* of the final staircase — and each successive
etch is half as deep: with $N$ masks, each level step is
$\lambda/[2^N(n-1)]$ (see [Diffractive Lens Design](08-diffractive-lens-design.md)).

<Widget type="stepper" id="com.github.richbai90.diffractive.photo.step-eight" />

Two process rules the book insists on:

- **Pattern the smallest features first, largest last.** Resist on a nonplanar
  surface coats unevenly, and small features at different heights cannot be
  printed with equal fidelity; the critical lithography wants a planar wafer.
- **Alignment is a real error budget.** Level-to-level registration is
  reducible to ~**0.1 µm** with advanced methods — and misalignment is one of
  the systematic errors [Testing](15-testing-doos.md) quantifies.

Eight levels (3 masks) ⇒ 95% theoretical efficiency; 16 levels (4 masks) ⇒ 99%.
The cost: multiple processing steps, multiple masks, multiple alignments —
against which stands the semiconductor industry's maturity: wafer-level,
parallel, characterized, repeatable, with economies of scale nothing else in
this chapter can match.

<Widget type="quiz" id="com.github.richbai90.diffractive.photo.quiz-binary" />

<Widget type="quiz" id="com.github.richbai90.diffractive.photo.quiz-order" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.photo.card-summary" />
