---
title: The Gray Wall
description: MSE regression is a machine for computing conditional means — and the conditional mean of a multimodal world is a blend that no example has.
order: 1
section: toy
---

You are training a deterministic network $f_\theta$ — a U-Net, say — to
predict a target channel $C$ (the red channel, or the $a$/$b$ axes of CIE
Lab) directly from the grayscale image $Y$, using an $L_2$ (MSE) or $L_1$
loss. Training converges. The output looks like a desaturated, low-contrast
version of $Y$. This lesson builds the standard explanation from the ground
up.

## The conditional mean

What does minimizing expected squared error actually ask for? For a fixed
input $Y = y$, choose the prediction $\hat C$ that minimizes the average
squared mistake over *everything the dataset could contain at that input*:

<Widget type="math" id="com.github.richbai90.collapse.l1.math_conditional_mean" />

That is the whole story, and it is worth reading slowly. Squared-error
regression is a machine for computing **conditional expectations**. The
network is not asked to be right about *your* shirt; it is asked to be right
*on average* about every shirt that ever shared this gray pattern.

## Averaging a multimodal world

Now suppose the conditional distribution $p(C \mid Y=y)$ has more than one
peak. A gray patch of a certain intensity could come from a red shirt or a
green shirt — grayscale simply does not distinguish them. (Why that happens
structurally is the next lesson's subject: metamers.) Watch what the loss
prefers:

<Widget type="interactive" id="com.github.richbai90.collapse.l1.inter_mixture" />

The two peaks are the two plausible shirts. The MSE-optimal prediction is
$\mathbb{E}[C \mid Y] = w\,\mu_1 + (1-w)\,\mu_2$ — a point in the *valley
between the modes*. With the default sliders: $0.5 \cdot 0.25 +
0.5 \cdot 0.75 = 0.50$, a channel value that **neither shirt has**.

Because $Y$ and $C$ share their structure — the same edges, the same
boundaries, the same high-frequency geometry — the conditional expectation
keeps all of that shared structure while averaging away the part that
differs: dynamic range, saturation, color. What survives is the geometry of
$Y$ with its contrast compressed. The gray wall.

<Widget type="quiz" id="com.github.richbai90.collapse.l1.quiz_mean_prediction" />

## The identity shortcut

There is a second force pointing the same direction. Grayscale $Y$ is not a
neutral starting point for predicting $C$ — it is an *exceptionally good
baseline*: the two share nearly all their spatial structure. Early in
training, the cheapest large loss reduction is $f(Y) \approx k \cdot Y$, a
scaled copy of the input. The loss landscape settles into that basin, and
climbing out requires gradients large enough to break the correlation between
input and output — exactly the gradients that a DC-dominated $L_2$ landscape
does not supply (that arithmetic is [Lesson
3](03-error-energy.md)).

<Widget type="quiz" id="com.github.richbai90.collapse.l1.quiz_shortcut" />

The two mechanisms compound: the conditional mean *wants* to look like a
blended $Y$, and the identity basin *hands* the network a blended-$Y$ local
minimum to live in.

## Why this is not a network failure

Nothing here is a bug in the optimizer or a capacity problem. The network is
delivering precisely what the objective rewards: the expected channel given
the input. The fix is never "more layers" — it is changing what the objective
rewards, by reformulating the target ([classification instead of
regression](06-forcing-the-signature.md#fixing-multimodality)), by
changing the loss (adversarial, perceptual), or by changing the
representation (predict the residual or the chromaticity, not the raw
channel). Those are the subject of [Lesson
6](06-forcing-the-signature.md); first we need to understand why
the conditional is multimodal at all.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.collapse.l1.quiz_mean_blame" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.collapse.l1.card_mean" />

<Widget type="flashcard" id="com.github.richbai90.collapse.l1.card_l2_blur" />