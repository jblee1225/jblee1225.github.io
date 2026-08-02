---
layout: page
permalink: /research-interest/
title: research interest
description: "main research topic: uncertainty quantification (UQ)"
nav: true
nav_order: 5
---

My research is built around **Uncertainty Quantification (UQ)** — understanding, modeling, and managing the uncertainties inherent in measurements, models, and predictions for the safety assessment of engineered systems.

<!-- TODO: figures from the original site will be added here (assets/img/research/) -->

#### Why Consider Uncertainties?

Real-world measurements and computational models are never exact. Material properties scatter, sensors are noisy, and models simplify physics. Ignoring these uncertainties can lead to overconfident — and unsafe — engineering decisions. Probabilistic approaches allow us to make decisions that are robust to what we do not know.

#### Topic 1 — Deterministic Input–Output Model Construction

Building the backbone models that map inputs to outputs, using both **data-driven approaches** (deep learning, Gaussian process regression) and **physics-based approaches** (finite element analysis, digital twins).

#### Topic 2-1 — Forward Uncertainty Quantification

Also called _forward uncertainty propagation_: propagating uncertainties in inputs (loads, material properties, environmental conditions) through a model to quantify the uncertainty in its outputs — e.g., probabilistic response prediction and fragility analysis.

#### Topic 2-2 — Inverse Uncertainty Quantification

Also called _inverse uncertainty propagation_: working backward from observed outputs to infer uncertain inputs or system states — e.g., Bayesian model updating, probabilistic estimation of corrosion from measurements, and flaw characterization in nondestructive testing.

#### Topic 2-3 — Model Uncertainty Quantification

Quantifying the uncertainty of the models themselves — model-form errors, discretization errors, and surrogate model uncertainty — so that predictions carry an honest statement of their own credibility.
