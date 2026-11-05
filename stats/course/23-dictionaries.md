---
title: Dictionaries and Pursuit
description: Sparse and redundant representations, matching pursuit and OMP, coherence and uniqueness, and the K-SVD idea. After Elad, chapters 2, 3, and 12.
order: 23
section: module-3
---

# Dictionaries and Pursuit

Until now, physics handed us every operator's columns: kernel
samples, filter taps, endmember spectra. Sparse modeling asks a sharper
question (after Elad, chapter 1): what if the *dictionary itself* is a
design variable? A redundant family of atoms, wider than the signal
dimension, can represent each signal with only a few active atoms. Finding
those few atoms is pursuit; learning the atoms is dictionary learning.
Together they are the modern reading of the classical claim, due to
Wiener, that the best basis is the one the signal itself suggests.

## The sparse coding model

<Widget type="math" id="com.github.richbai90.stats.23-dictionaries.objective" />

Redundancy ($M > N$) is what buys sparsity: with more atoms than
dimensions, typical signals sit closer to low-dimensional atom spans, and
the few-atom representation gets shorter. The cost is ambiguity (many
coefficient vectors can produce the same signal), so uniqueness needs a
guard.

## When the sparse solution is unique

<Widget type="math" id="com.github.richbai90.stats.23-dictionaries.coherence" />

The spark counts how few atoms are needed to build a linear dependency; the
coherence is its cheap, computable surrogate. Below half the spark, or below
the coherence bound, the sparsest representation is provably the only one;
the ambiguity of redundancy is bounded away. Uniqueness is what makes
[Lesson 27](/course/stats/assign-3b) worth solving by hand: the pursuit
answer is not just *an* answer, it is *the* answer.

<Widget type="quiz" id="com.github.richbai90.stats.23-dictionaries.quiz_coherence" />

## Matching pursuit and OMP

Greedy pursuit builds the representation one atom at a time, after Elad
chapter 3. Matching pursuit picks the atom most correlated with the current
residual and subtracts its contribution. Orthogonal matching pursuit adds one act of
honesty: after each pick, re-fit all chosen atoms by least squares, so the
residual is orthogonal to everything used so far:

<Widget type="stepper" id="com.github.richbai90.stats.23-dictionaries.stepper_omp" />

<Widget type="quiz" id="com.github.richbai90.stats.23-dictionaries.quiz_omp" />

## Learning the dictionary

<Widget type="math" id="com.github.richbai90.stats.23-dictionaries.ksvd" />

Alternate minimization closes the loop: given the dictionary, find sparse
codes (pursuit); given the codes, refit the dictionary (MOD, or the
atom-by-atom K-SVD). Each half is a problem the previous lessons already
solved. The learned atoms are the empirical answer to *what should the
columns of $\mathbf{H}$ be*, data-driven structure replacing the
physics-driven structure of [Lesson 11](/course/stats/signal-modeling).

## What carries forward

Two threads continue. The sparse code is a latent variable (the signal
generated from something unobserved), and Module 4 treats latent variables
properly, with mixtures, EM, and variational inference; the Dirichlet
concentration of [Lesson 24](/course/stats/unmixing) is the first taste.
And the alternating scheme (codes then dictionary) is EM in spirit: fix one
block, optimize the other, repeat.

<Widget type="flashcard" id="com.github.richbai90.stats.23-dictionaries.card_omp" />

<Widget type="flashcard" id="com.github.richbai90.stats.23-dictionaries.card_coherence" />
