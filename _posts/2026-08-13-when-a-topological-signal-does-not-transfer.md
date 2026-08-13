---
layout: article
title: "When a Negative Result Reveals the Real Experiment"
description: "A T4 lysozyme mutation test did not reproduce the experimental stability order at 300 K. That result exposes the variable the next experiment must control: distance from the melting transition."
date: 2026-08-13 00:30:00 -0400
topics:
  - Protein stability
  - Molecular dynamics
  - Zigzag persistence
---

The most useful result in research is sometimes the one that refuses to support the simple story.

We tested whether a topological lifetime extracted from molecular-dynamics trajectories would reproduce the known stability order of three T4 lysozyme variants: wild type, the strongly stabilizing mutation S117V, and the destabilizing mutation G30F. It did not.

That is not the end of the idea. It is the moment the scientific question becomes sharper.

## What the simulations actually tested

The campaign was substantial: three independent 100 ns replicas for each of three systems, giving nine trajectories and 900 ns of explicit-solvent simulation. Every system was simulated at 300 K, or 26.85 °C, and analyzed with the same frozen H1 Zigzag-persistence protocol.

The mean topological lifetime, `tau_top`, was 0.0854 for wild type, 0.0738 for S117V, and 0.0860 for G30F. In other words, the 300 K result did not rank the variants by experimental thermal stability.

It is tempting to call that a failed validation. But first we have to ask a more basic question: **Was the simulation performed in the physical regime where the experimental distinction becomes visible?**

## The missing variable was thermal distance

The experimental wild-type melting temperature is 66.48 °C. S117V raises it by 5.1 °C, while G30F lowers it by 4.9 °C. Those values place the transitions near 71.58 °C for S117V, 66.48 °C for wild type, and 61.58 °C for G30F. These measurements were reported in the original T4 lysozyme study by Shoichet and colleagues ([PNAS, 1995](https://doi.org/10.1073/pnas.92.2.452)).

At the simulated temperature of 26.85 °C, the three systems were therefore:

| Variant | Melting temperature | Distance above the 300 K simulation |
|---|---:|---:|
| S117V | 71.58 °C | 44.73 °C |
| Wild type | 66.48 °C | 39.63 °C |
| G30F | 61.58 °C | 34.73 °C |

The simulation held absolute temperature constant, but it did **not** hold thermodynamic challenge constant. More importantly, all three trajectories were run far below their melting transitions. We asked a native-state simulation to reproduce a difference measured through thermal denaturation.

That is like testing three bridges in a light breeze and using their small vibrations to predict the order in which they will fail in a hurricane. The measurements in the breeze may be real and reproducible, but they do not apply the stress that separates the structures.

## What the negative result rules out

The result matters because it rejects an overly easy claim: a topological lifetime measured during a 300 K, 100 ns trajectory is not automatically a direct proxy for melting temperature or mutation free energy.

That claim should be discarded.

But the broader research question remains open. Zigzag persistence was designed to follow topological structures as molecular contacts form and disappear through time. If thermal destabilization reorganizes those structures, the correct test is to observe the topology while the proteins approach comparable thermal regimes—not while all of them remain comfortably inside the folded basin.

This distinction is central. **The method did not fail to detect an unfolding transition; the simulations did not contain one.**

## The decisive next experiment

The next test should preserve the analysis protocol and change only the physical design. For each variant, simulations should span a temperature ladder from the native basin toward its experimentally measured transition. Comparisons can then be made at matched offsets below each melting temperature, or at matched reduced temperatures, rather than only at one absolute temperature.

The prediction is falsifiable:

- G30F should show sustained topological reorganization at a lower temperature than wild type.
- S117V should resist that reorganization until a higher temperature.
- The temperature at which H1 persistence changes should shift in the same direction as the experimental melting temperature.

The atom selection, distance cutoff, homology dimension, sampling interval, windowing, normalization, and statistical analysis must remain fixed before the new trajectories are examined. Conventional observables such as RMSD, native-contact fraction, secondary structure, and radius of gyration should be evaluated beside the topological signal.

If the predicted shift does not appear under that design, the stability interpretation is unsupported. If it does, the result will be much stronger than a correlation obtained by tuning a metric after seeing the answer.

## Why this strengthens the research

Science is not defended by pretending every result is positive. It is defended by showing that a negative result changed the experiment in a precise, physically motivated, and testable way.

Our 300 K campaign established what `tau_top` does **not** mean. It also revealed the key comparison the next campaign must make: not simply protein against protein at the same thermostat setting, but topology against topology at a comparable distance from thermal transition.

That is progress. The first experiment gave us a number. The negative result gave us the right question.
