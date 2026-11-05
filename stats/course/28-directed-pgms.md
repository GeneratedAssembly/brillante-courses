---
title: Graphs as Factorizations
description: Joint distributions over data and latents, Bayes nets as products of conditionals, conditional independence, and d-separation with explaining away. After Bishop, chapter 8, and Barber, chapter 3.
order: 28
section: module-4
---

# Graphs as Factorizations

Every model so far assumed a shape: a mixture picks one hidden class,
factor analysis picks one hidden vector, the observation model of
[Lesson 1](/course/stats/observation-model) fixed the generative equation by
hand. A probabilistic graphical model does the same thing in a second
language: it draws the assumptions. Nodes are random variables, edges are
direct dependencies, and the graph, read correctly, tells you which
independencies you bought and at what computational price. After Bishop,
chapter 8, and Barber, chapter 3.

## Products of conditionals

<Widget type="math" id="com.github.richbai90.stats.28-directed-pgms.factorization" />

The directed factorization is the chain rule with a causal accent: each
variable is conditioned only on its parents. Every joint distribution
factors over *some* ordering; the graph commits to one ordering and
certifies, with an arrow, that the conditioning set stops at the parents.
Fewer arrows mean fewer parameters and fewer numbers to estimate: a joint
over $K$ binary variables needs $2^K - 1$ entries in a table, but a chain
needs $K$.

## Conditional independence

The graph is a statement about conditional independence, and three arrow
patterns carry all of it:

<Widget type="math" id="com.github.richbai90.stats.28-directed-pgms.dsep" />

Chains and forks transmit dependence; colliders block it until you observe
the collider, and then they create dependence between causes that were
independent a priori. That reversal is the reason a shared observation
drives two independent causes into competition.

<Widget type="interactive" id="com.github.richbai90.stats.28-directed-pgms.inter_explaining" />

Move the LED prior and watch the posterior belief in the laser fall as the
alternative cause strengthens.

<Widget type="quiz" id="com.github.richbai90.stats.28-directed-pgms.quiz_collider" />

## Reading paths: d-separation

Conditional independence claims follow from the graph mechanically. Walk
each path between the query nodes; a path is blocked by a non-collider
whose value is in the conditioning set, and by a collider unless the
collider (or one of its descendants) is in the conditioning set. If every
path is blocked, the independence holds in every distribution the graph
can express.

<Widget type="stepper" id="com.github.richbai90.stats.28-directed-pgms.stepper_dsep" />

The guarantee is directional: d-separation implies independence in every
compatible distribution, but a distribution may have independencies the
graph does not show. The graph is a contract on what is *forbidden*, not
an inventory of everything that happens.

<Widget type="quiz" id="com.github.richbai90.stats.28-directed-pgms.quiz_dsep" />

## What the graph buys

Two things, and they trade against each other. Inference: a graph with
many missing edges decomposes the joint, and on tree structures exact
conditioning costs linear time instead of the exponential cost of working
with the raw joint. Modeling: the edges you draw are parameters you never
estimate. The discipline from
[Lesson 1](/course/stats/observation-model) applies unchanged: decide the
structure first, check what it implies, then fit.

<Widget type="flashcard" id="com.github.richbai90.stats.28-directed-pgms.card_dsep" />

<Widget type="flashcard" id="com.github.richbai90.stats.28-directed-pgms.card_explaining" />

## Teach it back

Conditional independence is the grammar of Module 4. Teach the three
arrow patterns and d-separation before the mixtures lesson builds on
them.

<Widget type="teach" id="com.github.richbai90.stats.28-directed-pgms.teach" />
