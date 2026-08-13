---
layout: article
title: "The Frame Is Not the Experiment"
description: "A molecular-dynamics trajectory may contain millions of frames, but time correlation means that sample size is a scientific question—not a row count."
date: 2026-08-13 00:45:00 -0400
topics:
  - Molecular dynamics
  - Statistical reasoning
  - Reproducibility
---

A molecular-dynamics trajectory can be enormous and still contain surprisingly few independent pieces of evidence.

The reason is simple: neighboring frames are related by dynamics. A structure saved at time `t + 1` is not a fresh draw from nature; it is the immediate continuation of the structure at time `t`. Saving coordinates more frequently creates a smoother record, but it does not automatically create more independent experiments.

This distinction becomes especially important when a trajectory is converted into a time series of structural or topological measurements. Ten thousand values may look like a large dataset. If they come from one transition event, however, they may still describe only one event.

## Why row counts are misleading

Suppose a protein remains folded for a long interval, crosses a barrier once, and then remains unfolded. A frame-by-frame comparison could contain thousands of folded observations and thousands of unfolded observations. A conventional statistical test might report an extremely small uncertainty because it treats every row as independent.

But the scientific replication is not the number of saved frames. The central event—the transition—occurred once.

This is a form of pseudoreplication: repeated measurements of the same evolving system are mistaken for independent repetitions of the phenomenon. The problem cannot be solved merely by collecting frames at a finer interval. In fact, denser saving can make the apparent sample size grow while the underlying information changes very little.

Time correlation is not a defect in molecular dynamics. It is part of the phenomenon we are trying to study. The mistake is to forget it when making claims.

## Windows overlap, too

Temporal descriptors make the dependence even more explicit. A sliding-window calculation might summarize frames 1–100, then 2–101, then 3–102. Those two neighboring windows share 99 percent of their coordinates. Their outputs should be expected to resemble one another.

This applies to RMSD histories, contact histories, and topological summaries such as an H1 Zigzag-persistence lifetime. A smooth curve can be scientifically useful—it can reveal when organization changes—but its smoothness is not evidence that every point is an independent confirmation.

The correct unit of evidence depends on the claim. If the question concerns folding transitions, independent transition events or independent trajectories may be the relevant units. If the question concerns transfer across proteins, the protein—not the frame—may be the important unit. A method that succeeds on many windows from one molecule has not necessarily shown that it generalizes to another molecule.

## Prediction can leak through time

Temporal dependence also makes validation deceptively difficult. Randomly dividing frames into training and test sets can place nearly identical neighboring structures on opposite sides of the split. A model or threshold may then appear to predict unseen data while actually recognizing the local neighborhood of data it has already seen.

The same risk exists without machine learning. If a distance cutoff, window length, or normalization is chosen after inspecting the full trajectory, the eventual test interval has already influenced the method.

A stronger design keeps whole temporal blocks, transition events, trajectories, or proteins separate. The analysis protocol is fixed on one group and evaluated on another. The separation should follow the level at which the final claim is made.

## A more honest hierarchy of evidence

For the kinds of topological questions I study, I find it useful to distinguish four levels:

1. **Frames** show the instantaneous structural record.
2. **Windows** describe local temporal organization.
3. **Events or trajectories** provide repeated dynamical tests.
4. **Proteins or experimental systems** test whether an interpretation transfers.

Each level can answer a different question. Confusion begins when evidence from one level is used to support a claim at another.

For example, a topological quantity may track unfolding within one heating trajectory. That is evidence of association in that trajectory. It is not yet evidence that the quantity predicts thermodynamic stability across proteins, ranks mutations, or detects transitions prospectively. Those claims require their own independent units and controls.

## What a careful analysis looks like

A defensible workflow does not discard frames. It uses them while assigning uncertainty at the appropriate level.

Independent trajectories should be retained as independent trajectories. Transition events should be identified without consulting the signal being evaluated. Comparisons can then be summarized per event and resampled at the event or trajectory level. Temporal shifts or block permutations can serve as negative controls while preserving some of the data's correlation structure.

Most importantly, the protocol should be frozen before the decisive test: atom selection, distance scale, sampling interval, window length, homology dimension, normalization, and statistical comparison. Otherwise the abundance of correlated observations creates many opportunities to find a pattern that will not survive transfer.

## The useful question

The size of a simulation file is a computational fact. The amount of independent evidence in it is a scientific judgment.

That judgment should be visible in the analysis. When a trajectory produces a compelling curve, I want to know not only how many points are on it, but how many independent events support the interpretation, how the temporal split was made, and whether the same protocol worked on an untouched system.

The frame is an observation. The trajectory is a history. The experiment is the test we design from them—and those three things should not be counted as if they were the same.
