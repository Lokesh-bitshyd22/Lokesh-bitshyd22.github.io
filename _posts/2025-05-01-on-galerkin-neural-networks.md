---
layout: post
title: "What I Learned Working on Galerkin Neural Networks"
date: 2025-05-01
tags: [research, mathematics, machine learning]
---

Over the past year I worked on a project that sat at an unusual intersection —
using neural networks not as black-box function approximators, but as structured
solvers grounded in classical variational methods.

## The Setup

The Galerkin method is a classical technique for solving partial differential equations.
Instead of solving the PDE directly, you project it onto a finite-dimensional space of
basis functions and solve a weaker, integral form. The key question our project asked:
what if the basis functions themselves are neural networks?

## Why JAX

JAX was a natural fit. Automatic differentiation is central to both the Galerkin
residual computation and the optimization loop. JAX's `vmap` and `jit` made
batching and compilation straightforward, and `grad` handled the variational
derivatives cleanly.

## What Actually Took Time

The theory is elegant. The implementation surface is not.

Domain decomposition — splitting the PDE domain into subregions and patching
solutions together — sounds clean on paper. In practice, enforcing continuity
at interfaces while keeping the optimization stable took most of the debugging time.

## The Result

The project culminated in a joint manuscript with Prof. Reddy and Prof. Seshaiyer.
It taught me how to think systematically and combine elegant ideas from different domains toward a concrete application. I also learnt that translating numerical experiments into precise mathematical claims is a skill in itself.

## What I'd Tell Someone Starting This

Read the classical numerical analysis first. Neural PDE solvers are easier to
understand and debug when you know what they're approximating and why the
variational formulation is the right one to use.
