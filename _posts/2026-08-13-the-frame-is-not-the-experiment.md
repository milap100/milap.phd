---
layout: article
title: "Same Temperature Is Not the Same Experiment"
description: "Why comparing protein mutants at one absolute temperature can hide the very stability difference we want to measure—and how a temperature-aware topological test can expose it."
date: 2026-08-13 00:45:00 -0400
topics:
  - Molecular dynamics
  - Thermal stability
  - Topological data analysis
---

In molecular dynamics, “same temperature” sounds like a fair comparison. Every protein receives the same thermostat setting, the same simulation length, and the same analysis. What could be more controlled?

For questions about melting, that symmetry can be misleading.

Two proteins at 300 K may occupy very different positions on their thermal landscapes. A stabilizing mutation can move the unfolding transition upward; a destabilizing mutation can move it downward. Equal absolute temperature does not therefore imply equal proximity to failure.

## A concrete example from T4 lysozyme

T4 lysozyme provides an unusually clear test. Wild type melts at 66.48 °C. The S117V mutation raises the melting temperature by 5.1 °C and increases stability by about 2.0 kcal/mol. G30F lowers the melting temperature by 4.9 °C and decreases stability by about 1.5 kcal/mol ([Shoichet et al., PNAS, 1995](https://doi.org/10.1073/pnas.92.2.452)).

We simulated all three variants at 300 K, equivalent to 26.85 °C. At that temperature, S117V was 44.73 °C below its melting point, wild type was 39.63 °C below, and G30F was 34.73 °C below.

The thermostat was identical. The thermal challenge was not.

And because even G30F remained nearly 35 °C below its melting temperature, all three systems were being observed in a comparatively mild regime. A 100 ns trajectory there can characterize native-state fluctuations, but it is not a thermal-denaturation experiment.

## Why the topology did not reproduce the melting order

Our analysis follows H1 loop-like organization across time using Zigzag persistent homology. The resulting lifetime summary asks how long topological structures remain identifiable as the molecular geometry changes.

At 300 K, the measured order was not the experimental stability order. That result is scientifically important because it prevents a category error: **native-state topological persistence is not automatically equivalent to thermodynamic stability.**

A protein can have a higher melting temperature without displaying a larger value of every dynamical observable far below that temperature. Stability is a property of a free-energy landscape and a transition between ensembles. A short trajectory deep in one basin samples only a small portion of that landscape.

This is especially important for new descriptors. If every scalar that changes in a trajectory is immediately called a “stability metric,” the language becomes stronger than the evidence. Topological persistence earns a physical interpretation only through a test designed around the physical transition in question.

## A temperature-aware test

The stronger experiment is not complicated in principle.

First, freeze the topological protocol: C-alpha representation, distance scale, H1 construction, sampling interval, window length, normalization, and statistics. No parameter should be adjusted to improve the final ordering.

Second, simulate independent replicas across a temperature ladder for every variant. The ladder should cover the stable native regime and extend toward the experimentally known melting region.

Third, compare the variants in two complementary ways:

1. At the same absolute temperatures, ask when each protein begins to show persistent structural reorganization.
2. At matched distance from its own melting point, ask whether the topological dynamics become comparable across variants.

Finally, benchmark the topological signal against established structural observables. The valuable question is not whether topology can be forced to agree with melting temperature, but whether it detects a reproducible temporal reorganization that standard summaries miss or localize less clearly.

## The prediction that can fail

A convincing research program needs a prediction that nature can reject.

For these T4 lysozyme variants, the expected order of transition temperatures is G30F, wild type, then S117V. If topological persistence is genuinely sensitive to thermally driven loss of molecular organization, its transition should follow that same temperature order under the frozen protocol.

If the signal changes at unrelated temperatures, disappears across replicas, or adds nothing beyond conventional measures, then it should not be presented as a stability marker. If the transition shifts reproducibly with the experimental melting point, we gain evidence for a narrower and more defensible claim: temporal topology can report how molecular organization changes as a protein approaches thermal destabilization.

That is more interesting than claiming one number predicts stability everywhere. It connects topology to a mechanism, specifies the regime in which the claim applies, and tells us exactly how to prove it wrong.

## Negative results are maps

The 300 K study did not produce the ranking we initially wanted. It produced something more valuable than a convenient confirmation: it identified the boundary of the claim.

At low temperature, the trajectories describe fluctuations inside the folded basin. Near the melting region, they can test resistance to thermal reorganization. Those are different scientific questions, and they should not be answered with the same interpretation.

The lesson is simple: temperature is not merely a simulation setting. It is part of the hypothesis.

Once that is recognized, the failed ranking stops looking like a dead end. It becomes the design principle for the experiment that can genuinely test the research.
