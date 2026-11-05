---
title: Applications Survey — Arrays, Shapers, and Subwavelength Optics
description: Lens arrays, beam shapers, spot generators, Talbot illuminators, subwavelength gratings, and the optical-communications module that ties the whole book together.
order: 17
section: applications
---

Conventional optics are ground and polished — exquisite, but the technique
limits the *kinds* of optics possible. DOE fabrication is "extremely flexible,"
and this lesson tours what that flexibility buys. (The book's own list,
"by no means complete": optical computing, laser machining, imaging, displays,
barcode scanning, illumination, position encoders, data storage, lithography
enhancement, optical communications, biosensors.)

## Arrays of lenses

Microlens arrays were nearly impossible before lithography; now they come with
**exact pitch, nested rectangular or hexagonal — no wasted area**.

- **Coupling**: VCSEL arrays (lasers tens–hundreds of µm apart on a wafer) →
  microlens array → fiber array; the same geometry, with MEMS mirrors between
  two lens arrays (collimate, switch, focus), is the optical cross-connect.
  Honest caveat: broadband 1310–1550 nm work often goes *refractive* — DOEs
  are wavelength-sensitive.
- **Beam steering**: a decentered Galilean pair deflects a collimated beam by
  $\Delta\theta = \Delta x/f$; two thin DOE substrates replace the fat lenses,
  so big angles come from tiny motion — at the price of a **discretized scan**
  (spot spacing ~$\lambda/d$, $d$ = microlens diameter).
- **Sensors**: a lens array one focal length above a detector aims light that
  would hit dead space onto the active area (fill-factor boost); give each
  lens a *subarray* of detectors and it becomes a **Shack–Hartmann wavefront
  sensor** — spot displacement per subaperture = local wavefront slope,
  interpolated into a full wavefront (bench-top testing, astronomy's
  atmospheric correction).
- **Homogenizers**: excimer beams (KrF, ArF) are wildly nonuniform; a lens $f_1$
  plus a microlens array $f_2$ overlaps the sub-images into a **top hat** of
  width $W \approx D f_1/f_2$ ($D$ = one microlens) — width tuned by $f_1$.

<Widget type="quiz" id="com.github.richbai90.diffractive.apps2.quiz-shack" />

## Beam shaping

A **focusing beam shaper** maps a Gaussian input 1:1 into a focal spot of
*chosen* shape — round, square, super-Gaussian, linear ramps — the inner zones
redirecting the central light outward. Applications: laser machining,
dermatology, welding dissimilar materials (shape the energy for both metals at
once); two surfaces can shape **amplitude and phase together** for a collimated
flat-top. DOEs even live *inside* laser resonators — phase plates or
diffractive mirrors that select modes conventional cavities cannot reach.

## Grating applications, revisited

- **Beam sampler**: deliberately *shallow* grating — most light stays in the
  zero order (a flat window is the extreme), a few percent diffracts to a
  monitor detector: real-time power *and* profile, one thin element.
- **Spot array generators**: equal-intensity arrays for splitting, interconnect
  distribution, barcode scanning, machine vision; a CO₂ laser + spot array
  drills printed-circuit boards with a whole array of holes per pulse.
- **Talbot array illuminators**: the near-field cousin — a periodic structure
  self-images at multiples of the **Talbot distance**

<Widget type="math" id="com.github.richbai90.diffractive.apps2.math-talbot" />

and at *fractional* Talbot planes certain phase gratings (e.g. crossed 400-µm
binary gratings, duty 1/3, phase step 2π/3) produce arrays of nearly 100%
contrast spots at ~100% efficiency. Killer feature: **more spots = illuminate
more periods — no redesign**.

<Widget type="interactive" id="com.github.richbai90.diffractive.apps2.int-talbot" />

- **Controlled-angle diffusers**: lithography's boomerang — DOEs that smear
  many orders into prescribed angular shapes (circles, annuli, dipoles,
  quadrupoles) delivering **custom off-axis illumination** to steppers,
  optimizing resolution and process latitude for different feature types —
  some designs optimizing *millions* of orders.

## Subwavelength gratings: the artificial index

$\Lambda < \lambda$: one order only, and the structure is a **film with an
engineered index** from effective medium theory ([Electromagnetic
Methods](06-electromagnetic-methods.md)): $\varepsilon_{\text{eff}}$ from the
fill factor, different for TE and TM — **form birefringence**.

- **AR surfaces**: no material exists at $n_1 = \sqrt{n_i n_s}$ (air→glass:
  1.225)? Etch a binary SWG to that effective index, λ/4 deep, with
  $\Lambda \le \lambda/(2n_s)$ — a coating **as tough as the substrate**, wide
  field and band; **moth's-eye** cones taper the impedance instead.
- **Wave plates**: different fill factors in orthogonal directions ⇒ full/half/
  quarter-wave plates in a lithographic film (telecom polarization scramble
  correction).
- **Subwavelength optics**: Farn's $\alpha_i = i/(N{+}1)$, $\beta_i = i/N$
  blaze; the book's showcase — **Mait's 36-µm-diameter, 65-µm-focal-length
  fused-silica lens (f/1.8) with 60-nm minimum features**, fabricated by
  Scherer, validated against FDTD — binary subwavelength structure beating
  multilevel optics on efficiency without any alignment steps.
- **Photonic crystals**: push the period to ~λ and propagation bands open —
  waveguide bends, microcavities (1.55 µm demos), "great promise."

<Widget type="quiz" id="com.github.richbai90.diffractive.apps2.quiz-swg" />

## Integration and the communications module

The four drivers — **performance, new function, miniaturization, cost** — push
toward hybrid integration: die/wire bonding of actives and micro-optics, with
**alignment fiducials, bonding pads, and self-centering reliefs printed into
the optics themselves**, and wafer-level fabrication + dicing (the LS-120
drive head did it). The capstone example, a **1 × 12 VCSEL datacom
transmitter** (datacom = 850 nm, hundreds of meters, cheap and fast; telecom =
1310/1550 nm, thousands of km): each channel runs VCSEL → **diffractive beam
shaper** → refractive microlens on the same wafer → fiber. The DOE does three
jobs at once:

1. its embedded lens shares the focusing power budget with the refractive lens;
2. it shapes **amplitude and phase** to load the GRIN multimode fiber's *skew
   modes* — steering light around the centerline index defect that causes
   differential mode delay and limits data rates (a vortex, doughnut-focus
   shaper);
3. its surface is figured so **back-reflections miss the VCSEL** — stable
   lasers.

One thin lithographic element, three simultaneous functions, twelve of them per
module, all passive-aligned: design, theory, fabrication, and test in a single
part. "Only the laws of physics and the creativity of modern optical designers
limit the uses of diffractive optics."

<Widget type="quiz" id="com.github.richbai90.diffractive.apps2.quiz-vcsel" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.apps2.card-recap" />
