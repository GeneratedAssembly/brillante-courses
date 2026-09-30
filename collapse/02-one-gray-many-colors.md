---
title: One Gray, Many Colors
description: The luminance projection throws away two of three color degrees of freedom — metamerism is why the conditional is multimodal, and no network can be blamed for it.
order: 2
section: toy
---

The last lesson treated $p(C \mid Y)$ as multimodal as a raw fact. This
lesson shows where the multimodality comes from: grayscale is a *projection*
of color, and projections destroy information on purpose.

## Luminance and metamers

Standard grayscale is a weighted sum of the color channels — the ITU-R BT.601
luminance weights:

<Widget type="math" id="com.github.richbai90.collapse.l2.math_luminance" />

This weighted sum approximates perceived brightness: green contributes most,
blue least. It is also a map from a three-dimensional space (every RGB
triple) down to a one-dimensional one (one gray value). Such a map cannot be
invertible, and the collisions have a name: **metamers** — distinct colors
that produce the identical measured response.

<Widget type="interactive" id="com.github.richbai90.collapse.l2.inter_isoluminant" />

Every point on the plotted line renders to the *same gray value* $Y$: the
green level required to hold luminance fixed as the red level moves (with
blue held at its slider). Slide $B$ and the whole line sweeps a plane. A
single gray value is consistent with a two-parameter family of colors — and
a dataset drawn from that family gives you a conditional distribution
$p(C \mid Y)$ that spreads across it.

## Counting the lost degrees of freedom

The arithmetic is worth doing once. One linear equation in three unknowns:

$$0.299\,R + 0.587\,G + 0.114\,B = Y$$

leaves $3 - 1 = 2$ free directions. So the gray wall is not an edge case or a
quirk of a particular dataset — for *every* input patch, most of the color
content is unobserved, and the conditional distribution is generically
spread out. The conditional mean then lands wherever the data's modes
balance — a color that occurs nowhere — while the shared structure between
$Y$ and $C$ survives intact in the prediction. Averaged color, preserved
geometry: desaturation of exactly the kind you observed.

<Widget type="quiz" id="com.github.richbai90.collapse.l2.quiz_metamer" />

<Widget type="quiz" id="com.github.richbai90.collapse.l2.quiz_projection" />

## Why the network can't be blamed

Put the two lessons together and the gray wall stops looking like a failure
mode of neural networks at all. It is the *correct answer to the posed
question*: given only what $Y$ distinguishes, what is the average channel?
The information to do better is genuinely absent from $Y$ alone *as a
target* — the network had no loss-level reason to prefer the red shirt over
the green one.

That observation tells you where every successful fix must intervene: not in
the optimizer, but in what the objective can distinguish. Either change the
target so metamers stop competing (predict chromaticity, hue, or the
residual $D = C - Y$), or change the loss so averages stop winning
(classification over bins, adversarial, perceptual). Those are [Lesson
6](06-forcing-the-signature.md)'s toolkit. But first there is a
second, more physical half of the story: *even when the target is fully
determined*, squared-error training still favors one specific wrong answer —
the low-frequency one. That arithmetic starts next.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l2.quiz_residual_idea" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l2.card_metamer" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l2.card_luminance" />