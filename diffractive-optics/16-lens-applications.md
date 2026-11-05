---
title: Diffractive Lenses in Instruments
description: The Seidel coefficients of a diffractive lens, the Sweatt model, f–θ scan lenses, landscape lenses, superzones, and thermal athermalization.
order: 16
section: applications
---

Chapter 4 designed a diffractive singlet; this lesson runs it through the
aberration calculus and puts corrected versions into real instruments.

## The aberrations a diffractive lens actually has

The third-order wavefront error expands in pupil radius $\rho$, field $h$,
azimuth $\theta$ with the five Seidel coefficients (Eq. 10.1); for a thin lens
they close-form in the **bending parameter** $B = (c_1+c_2)/\varphi$ and
**conjugate parameter** $T = (m+1)/(m-1)$ (Eqs. 10.2–10.3). A diffractive lens
is the $n \to \infty$ limit — and the limit does something remarkable:

<Widget type="math" id="com.github.richbai90.diffractive.apps.math-dseidel" />

**A diffractive lens has zero field curvature ($S_{\mathrm{IV}} = 0$) and zero
distortion ($S_{\mathrm V} = 0$) inherently.** Spherical remains (it scales as
$y^4/f^3$, correctable with a fourth-order phase term $G$ or the right
substrate curvature), and coma/astigmatism are killed by stop placement.
On axis: $T = -1$ and $B = 2$ — **the substrate must be concentric with the
focus** — kills $S_{\mathrm I}$ and $S_{\mathrm{II}}$ together. A flat-substrate
diffractive lens is therefore *not* aplanatic; the curved-substrate version is.

## The Sweatt model: DOEs in programs that don't know DOEs

Old ray tracers have no diffractive surface type? Model the DOE as a **thin
wedge of absurdly high index** (Eq. 10.7: $\sin\theta_d - \sin\theta_i =
n\,dt/dr \equiv m\lambda/\Lambda(r)$):

<Widget type="stepper" id="com.github.richbai90.diffractive.apps.step-sweatt" />

At $n = 10{,}000$ a 100-mm-EFL lens becomes a plano-convex element with
$R = 10^6$ mm and 50-nm sag — physically silly, numerically exact for
monochromatic aberration work (its dispersion must be overridden for color).

## The f–θ scan lens

Laser printers and barcode readers need a flat-field lens rotating a polygon
mirror at constant angular rate $\theta(t)$: an ordinary lens puts the spot at
$y = f\tan\theta$ — accelerating scan, curved field. Build in exactly the right
**negative distortion** so $y = f\theta$. The diffractive singlet with stop
shift ($B = -1$: substrate $R = -2f$, scanner facet at $2f/3$ in front) gives
$S_{\mathrm{II}} = S_{\mathrm{III}} = S_{\mathrm{IV}} = 0$ with distortion
$S_{\mathrm V} = 2H^3/[y^2(B+2T)]$ — the f–θ condition *is* the designed
distortion.

<Widget type="interactive" id="com.github.richbai90.diffractive.apps.int-ftheta" />

Worked design: $f = 150$ mm at 633 nm, ±20° scan: nearly diffraction-limited
**16-µm spot over an 8.5-inch line ≈ 1600 dots/inch**. The flat-substrate
shortcut ($B = 0$) still satisfies f–θ but admits coma: 35-µm spot, ~700
dots/inch.

<Widget type="quiz" id="com.github.richbai90.diffractive.apps.quiz-ftheta" />

## The landscape lens and the telescope

**Landscape lens** (a singlet imaging a wide field): shift the stop to
$t = f$ in front of the lens — telecentric — and *coma and astigmatism vanish
while field curvature was already zero*: third-order quality uniform across
the field, limited only by spherical. The book's comparison: one 25-mm f/2
diffractive singlet with a 9-mm stop 50 mm ahead matches a three-element Cooke
triplet (50 mm EFL, f/5.6, 18° field) with 25% less edge distortion; stop down
to f/8 and it is diffraction-limited. (Polychromatic use is hopeless —
$S_{\mathrm I} \propto (\lambda/\lambda_c)^3$ — but in narrow IR bands it beats
a Ge f/3 lens out to 10°.)

**Diffractive telescopes**: put a Keplerian pair in front of an IR scanner —
FOV shrinks by the magnification, resolution on the array grows — with the
**exit pupil matched to the scanner's entrance pupil** for radiance
efficiency. Worked 10.6-µm design, −5×: 200-mm f/2 objective + 40-mm eyepiece
at f/0.75, minimum feature a comfortable 16 µm, wavefront error **< λ/60**
over the 4° input field.

## Superzones: one profile, many wavelengths

A kinoform fractured at OPD $= q\lambda_0$ instead of $\lambda_0$ (Eq. 10.17:
height $h = q\lambda_0/(n_0-1)$) makes the features $q$ times wider —
fabricable — and focuses at $f_0$ whenever $\lambda = q\lambda_0/m$
(Eqs. 10.18–10.20), each wavelength with its own sinc² efficiency peak.
$ q = 2, \lambda_0 = 640$ nm also focuses 427 nm in order 3 — **91% of light
into the two phosphor lines** in a telecentric landscape geometry; $q = 21$
diamond-turned versions image natural scenes in white light about as well as a
simple refractor. Price: narrow efficiency peaks and **shadowing** of off-axis
rays by the tall steps.

<Widget type="flashcard" id="com.github.richbai90.diffractive.apps.card-staircase" />

## Thermal compensation

Every lens defocuses with temperature; the figure of merit is the
**coefficient of thermal defocus** $x_f = (1/f)\,df/dT$ in ppm/°C
(Eqs. 10.21–10.23):

<Widget type="math" id="com.github.richbai90.diffractive.apps.math-thermal" />

| Material | Refractive $x_f^r$ | Diffractive $x_f^d$ (on same substrate) |
|---|---|---|
| Fused silica | −21.1 | +1.10 |
| BK7 | +0.98 | +14.2 |
| ZnSe | −28.1 | +14.5 |
| Ge | −125.0 | +11.3 |
| Polycarbonate | +246 | +131 |

Two facts leap out: diffractive CTD is **positive and set by the substrate's
expansion doubled** ($x_f^d = 2\alpha$ — zone radii scale as $f\lambda$, lengths
scale as $\alpha$, twice over; the substrate's $dn/dT$ barely enters), and
refractive glasses span huge negative values. An **aluminum mount**
($\alpha = 23$ ppm/°C) holding a fused-silica 100-mm lens drifts focus by
$100 \times 10 \times (23 + 21.1) = 44.1\,\mu$m over 10 °C — athermalization
means **matching the lens CTD to the mount CTE, independent of focal length**.
Solving the power/CTD split for a 100-mm hybrid: a −101.4-mm refractive silica
element paired with a +50.3-mm diffractive surface lands $x_f = 23$ exactly —
and the general rule: **one material can athermalize or achromatize, not both;
doing both needs three glasses or two glasses plus a DOE surface** (the book's
BK7 + polycarbonate + DOE solution: $V = \infty$, $x_f = 23.0$, $\varphi$ sum
= 1 by construction).

<Widget type="quiz" id="com.github.richbai90.diffractive.apps.quiz-thermal" />

<Widget type="quiz" id="com.github.richbai90.diffractive.apps.quiz-sweatt" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.apps.card-zero" />
