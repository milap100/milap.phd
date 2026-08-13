---
layout: article
title: "Why Zigzag Persistence for Molecular Dynamics?"
description: A changing protein is not a collection of unrelated snapshots. Zigzag persistence offers a way to study which topological structures survive through time.
topics:
  - Zigzag persistence
  - Molecular dynamics
  - Protein structure
---

Molecular-dynamics simulations are often analyzed one frame at a time. At each saved moment, we measure a distance, count native contacts, or construct a geometric summary. These measurements are useful, but the simulation itself is not a bag of independent structures. It is a path: a protein continually reorganizes, and the history of that reorganization may carry information that no single frame contains.

My research asks whether **zigzag persistent homology** can describe part of that history.

## From coordinates to changing topology

A protein trajectory begins as a time-ordered sequence of atomic coordinates. I focus on a coarse geometric representation built from the protein's C-alpha atoms. At a chosen distance scale, nearby atoms define edges and higher-dimensional simplices, producing a topological complex for each frame.

Ordinary persistent homology is usually organized around a one-directional filtration: features appear as a scale increases. Molecular dynamics creates a different situation. Between consecutive frames, contacts can form and disappear. The corresponding complexes therefore move in both directions rather than growing monotonically.

Zigzag persistence is designed for this setting. It connects neighboring complexes through unions or other intermediate maps, allowing a topological feature to be followed while the underlying structure gains and loses relationships.

## What the bars mean

The resulting barcode records the intervals over which topological features remain identifiable through the trajectory. In the first homology group, H1, those features are loop-like structures in the changing contact geometry. They are not literal holes inside the protein, and they should not automatically be assigned a biological mechanism. They are mathematical signatures of coordinated organization at a specified scale.

One summary I study, `tau_top`, weights longer barcode intervals more strongly:

> `tau_top = sum(L_i^2) / sum(L_i)`, using positive finite lifetimes `L_i`.

The quantity is measured in saved-frame units unless it is converted to physical time. It depends on the atom selection, distance cutoff, sampling interval, window length, homology dimension, and normalization. Those choices are part of the definition—not implementation details that can be hidden later.

## The scientific question

The useful question is not simply whether `tau_top` changes. Many scalar summaries change when a protein unfolds. The stronger question is whether temporal topology provides an interpretable and reproducible description of structural organization that complements conventional observables such as RMSD, native-contact fraction, radius of gyration, and secondary structure.

In an internal mdCATH study, normalized H1 topological lifetime generally decreased as temperature increased and tracked structural disruption across protein domains. I treat that result as evidence worth pursuing, but not as final validation: the distance scale was selected and evaluated within the same development panel.

## What this does not establish

This work does **not** currently show that a topological lifetime is a direct predictor of melting temperature, mutation stability, or free-energy change. A matched T4 lysozyme mutation study did not reproduce the experimental stability ordering. Held-out transition tests also did not establish reliable timing beyond structural baselines.

Those negative results sharpen the project. The defensible aim is to test whether a fixed, native-reference-free topological description can track folding organization across genuinely untouched trajectories—not to rename a scalar as thermodynamic stability.

## What comes next

The next meaningful test is prospective. The atom selection, H1 dimension, distance scale, sampling, windows, normalization, and statistics should be frozen before examining new proteins. Fast-folding systems such as a WW domain, NTL9, or Protein G offer a stronger benchmark because folding labels and physical times can be defined independently of the topological analysis.

A positive result would show that the same topological description transfers without outcome-based retuning. A negative result would be equally informative: it would reveal which parts of the apparent signal were specific to the original data or protocol.

That is the standard I want this research to meet—an idea made precise enough that nature can say no.
