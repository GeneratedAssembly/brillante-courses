---
title: The Wider Fabrication Landscape
description: Direct writing, interferometric and gray-scale lithography, near-field holography, machining, and replication — how each method trades fidelity, throughput, and cost.
order: 14
section: fabrication
---

Binary optics is the mature core, but the fabrication toolbox has three
families — **lithographic, direct machining, replication** — chosen by two
questions: what function do you need, and what will you pay? This lesson is
the survey, with the book's numbers.

## Lithographic methods beyond binary masks

**Direct writing.** Expose the resist *with the beam itself* — no masks.
Electron beam (spots ~0.1 µm) or focused laser (HeCd/Ar⁺, spots 1–5 µm), with
**beam intensity or dwell time set locally from the resist response curve**, so
depth follows dose and one pass yields **essentially continuous relief, 256+
levels**. Perfect for prototypes; fatal for volume: it is **serial**. Three
physics caveats: finite spots ⇒ **nonvertical sidewalls**; profile fidelity
tracks resist chemistry; and the transfer etch must be anisotropic with
**predictable selectivity** — $S = 1$ copies the resist depth exactly,
$S<1$/S>1 etch shallower/deeper than designed. (Tuning knob: in fused-silica
RIE, more oxygen eats resist faster ⇒ lower selectivity. Beware **loading**
effects: as the resist area shrinks mid-etch, selectivity drifts.)

**Interferometric exposure.** Cross coherent beams, develop and etch the
fringe pattern: the cheapest route to **extremely small periods — below
0.3 µm** — for AR surfaces and wave plates. But only straight, periodic
structures.

**Gray-scale lithography.** The mask itself has **spatially varying
transmission**, imaged through contact or projection lithography; local depth
∝ local dose, so **multilevel relief in ONE exposure and ONE etch**. Benefits:
arbitrary level counts, wafer-level parallel, **no mask-to-mask alignment
errors**. Costs: gray-scale masks are hard to obtain and can exceed a full
binary mask set in price; and the process is *far more sensitive* to litho
parameter variation than binary — yield eats some of the savings. Demonstrated
on 30-µm-period blazed gratings in fused silica.

**Near-field holography (NFH).** Expose resist with the *near-field
interference pattern of a phase mask*: the ±1 orders of a 1.0-µm-period mask
interfere to a **0.5-µm-period** fringe — period-halving **beyond contact
lithography's reach**, in parallel, cheaply. The high-frequency market:
waveguide couplers, subwavelength AR, WDM gratings.

<Widget type="quiz" id="com.github.richbai90.diffractive.fabsurvey.quiz-serial" />

## Refractive micro-optics in the same fab

Microlenses (next lesson's arrays) are made lithographically too: pattern a
resist **cylinder** with a binary mask, then **reflow** it — melt it on a hot
plate and **surface tension pulls it into a lens** (works when diameter/height
is in the right range). Refractive microstructures are *big* compared to DOEs:
dozens of microns tall versus 3–4 µm of relief. That height is the problem:
**a 40-µm-tall lens needs >33 hours** of 20 nm/min RIE in fused silica. Refractive
wins on efficiency and bandwidth; it loses on aspheres and aspect ratio.

<Widget type="flashcard" id="com.github.richbai90.diffractive.fabsurvey.card-reflow" />

## Direct machining

No resist, no etch — cut the optic. **Ruling engines** (Fraunhofer and Rowland
to modern CNC) scrape blazed grooves with a diamond stylus at **thousands of
grooves/mm** — straight lines only. **Single-point diamond turning** rotates
the substrate under the tool — kinoforms and IR refractive surfaces, **radially
symmetric only**; a triangular stylus can cut a whole blaze in one pass, but
its angle must be rotated for different zone widths. Both share the same
limit: a finite tip cannot cut a perfectly smooth profile. **FIB milling**
(sputter, resolution ≈ e-beam writing) and **excimer laser ablation**
(resolution ≈ laser writing; can even image a whole mask pattern at once)
machine arbitrary surfaces directly in the final material. Machined parts are
slow and serial — which historically makes them the **masters** for the next
family.

## Replication: where the millions are made

Sequence: make a **master** (machined or lithographic) → electroform a nickel
**shim** → press or cast a polymer → separate. Four methods:

- **Injection molding** (PC, PMMA): molten plastic into a mold insert —
  *literally millions of parts per month*, quality below the master, for DOEs
  that don't need tight tolerances.
- **Thermal embossing**: heat a thermoplastic past its glass transition
  $T_g$, press the shim in; roller versions run continuously — it is how
  credit-card **security holograms** are made.
- **Casting / UV embossing**: liquid photopolymer sandwiched against the shim,
  cured by UV (or baked thermoset) — **the highest-fidelity replicas**; sol-gel
  variants cure down to SiO₂ for glass-like copies (watch shrinkage).
- **Soft lithography**: elastomeric stamps. **Microcontact printing** inks a
  self-assembled monolayer onto metal as an etch mask; **microtransfer
  molding** casts against the rubber stamp. Features **below 100 nm**, curved
  surfaces possible — but multilevel fidelity and registration keep it a
  research tool.

<Widget type="quiz" id="com.github.richbai90.diffractive.fabsurvey.quiz-rep" />

## Choosing a method

<Widget type="flashcard" id="com.github.richbai90.diffractive.fabsurvey.card-choose" />

The book's summary rule: **some methods are better for volume, some for small
quantities; the material can limit the method; and the optical function can
drive the choice** — a 2-D spot array generator is essentially impossible on a
ruling engine or a diamond lathe, and a 1-D grating does not need four aligned
masks.

<Widget type="quiz" id="com.github.richbai90.diffractive.fabsurvey.quiz-match" />
