---
title: Ray Transfer Matrices
description: Reduce every paraxial element to a 2×2 matrix — translation, refraction, thin lenses — and read imaging conditions off the product.
order: 8
section: rays-reflection-refraction
---

Paraxial optics is *linear*, and linear systems have matrices. The ray
transfer matrix (ABCD matrix) formalism packs an arbitrarily long train of
lenses, mirrors, and spaces into one 2×2 matrix — the algebra behind camera
zoom design, laser cavities, and optical benches.

## The ray vector and the three building blocks

A ray crossing a plane perpendicular to the axis is described by two numbers:
its height $y$ and its angle $\theta$ (radians, small-angle regime). Both are
signed with the standard convention: **light travels left to right; $y$ is
positive up; $\theta$ is positive if the ray points upward.**

<Widget type="math" id="com.github.richbai90.optics.ray-transfer-matrices.math-vector" />

Three elements cover everything in this course:

<Widget type="math" id="com.github.richbai90.optics.ray-transfer-matrices.math-translation" />

<Widget type="math" id="com.github.richbai90.optics.ray-transfer-matrices.math-refraction" />

<Widget type="math" id="com.github.richbai90.optics.ray-transfer-matrices.math-thinlens" />

<Widget type="quiz" id="com.github.richbai90.optics.ray-transfer-matrices.quiz1" />

## Cascading: matrices multiply in reverse order

For a sequence of elements, each acts on the ray in turn, so the system matrix
is the matrix product taken **right to left** — the last element the ray meets
stands leftmost in the product. Determinants always equal
$n_{\text{first}}/n_{\text{last}}$ (1 in air), a quick arithmetic check.

<Widget type="stepper" id="com.github.richbai90.optics.ray-transfer-matrices.stepper-thinlens" />

## Reading images off the matrix

Suppose an object plane emits a ray at height $y_0$ with any angle $\theta_0$,
and the system matrix to the image plane is $\begin{pmatrix} A & B \\ C &
D\end{pmatrix}$. For *all* such rays to meet at one image height, the output
height must not depend on $\theta_0$ — that is, $B = 0$:

<Widget type="math" id="com.github.richbai90.optics.ray-transfer-matrices.math-imaging" />

$A$ is then the (lateral) magnification: $y_1 = A\,y_0$. The imaging condition
and magnification read straight off $A$ and $B$ — no sign-convention
bookkeeping beyond the matrix rules. When a matrix also satisfies $D = 0$, an
angular bundle focuses to a point too, giving $C = 0$ as the condition for
focal-plane to focal-plane (Fourier-transforming) behavior — the fact the
[4f system](35-fourf-system.md) section exploits.

<Widget type="interactive" id="com.github.richbai90.optics.ray-transfer-matrices.int-translation" />

<Widget type="quiz" id="com.github.richbai90.optics.ray-transfer-matrices.quiz2" />

<Widget type="quiz" id="com.github.richbai90.optics.ray-transfer-matrices.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.ray-transfer-matrices.card-abcdb" />

<Widget type="flashcard" id="com.github.richbai90.optics.ray-transfer-matrices.card-det" />


## Recommended reading and viewing

Ray transfer matrices live in the supplementary lecture notes rather than the video itself.

<Widget type="resource-link" id="com.github.richbai90.optics.ray-transfer-matrices.link-lecture-3" />

<Widget type="resource-link" id="com.github.richbai90.optics.ray-transfer-matrices.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.ray-transfer-matrices.link-openstax" />

## Assignments

The back half of MIT's Homework 1 is this section distilled: Fermat's
lifeguard, the trapezoidal prism, and the ellipsoidal refractor — perfect
focusing and matrices under your fingers. (Its first two problems pair with
[light in matter](04-light-in-matter.md#assignments).)

<Widget type="resource-link" id="com.github.richbai90.optics.ray-transfer-matrices.link-hw1" />

<Widget type="resource-link" id="com.github.richbai90.optics.ray-transfer-matrices.link-hw1-sol" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 3 — focusing, imaging, and the
  paraxial
  approximation](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-3-focusing-imaging-and-the-paraxial-approximation/)
  (CC BY-NC-SA 4.0; ray transfer matrices are developed in the course's
  supplementary notes)
- OpenStax University Physics III, §2.5 (Thin Lenses, "Thin-Lens Equations" via
  matrix derivation) — [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)