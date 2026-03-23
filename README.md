# Neural Models of Attention as Dynamical Modulation

## Overview

Attention is often described as a mechanism that enhances relevant sensory signals while suppressing irrelevant information. While classical models treat attention as a static gain factor, growing evidence suggests that attention is inherently **dynamic, population-level, and competitive**.

In this project, I develop a series of computational models to explore attention as a **dynamical process that modulates neural responses across time, populations, and networks**.

---

## Key Questions

* How does attention improve signal encoding in noisy environments?
* Can attention be understood as a control parameter in neural dynamics?
* How do competitive interactions give rise to selective attention?
* What role does temporal modulation play in shaping neural responses?

---

## Models Implemented

### 1. Gain Modulation Model

We begin with a minimal model in which attention acts as a **multiplicative gain** on sensory input:

`r(t) = g * s(t) + η(t)`

* `s(t)` = stimulus
* `g` = attention gain
* `η(t)` = noise

**Result:**
Attention increases the signal-to-noise ratio (SNR), improving encoding fidelity.

---

### 2. Population Coding with Attention

We extend the model to a population of neurons with Gaussian tuning curves:

`r_i(x) = exp(-(x - μ_i)^2 / (2σ^2))`

Attention selectively enhances neurons tuned to a target stimulus:

`r_i_att(x) = A_i * r_i(x)`

**Result:**
Attention sharpens population responses, effectively increasing representational precision.

---

### 3. Competitive Network (Selection Mechanism)

We model attention as a result of **competition between neural populations**, implemented via softmax-like normalization:

`x_i = exp(β * I_i) / Σ_j exp(β * I_j)`

**Key idea:**
Attention biases competition, allowing one representation to dominate.

**Result:**
Small biases in input lead to strong selection effects, consistent with winner-take-all dynamics observed in cortical circuits.

---

### 4. Temporal (Dynamical) Attention Model

We model attention as a **time-varying control signal**:

`r(t) = A(t) * s(t) + η(t)`

We further incorporate temporal integration:

`τ * dV/dt = -V + A(t) * s(t)`

**Result:**
Attention dynamically gates input, shaping:

* temporal integration
* response variability
* effective filtering of sensory signals

---

### 5. Tripartite Synapse Model (Neuron–Astrocyte Interaction)

To incorporate biological realism, we extend the framework to a **tripartite synapse**, where astrocytes modulate synaptic transmission.

Astrocytic calcium dynamics:

`τ_c * dC/dt = -C + S(t)`

Astrocyte activity:

`τ_a * dA_astro/dt = -A_astro + C(t)`

Postsynaptic response with attention-modulated astrocytic input:

`τ * dV/dt = -V + w_s * S(t) + w_a * A(t) * A_astro(t)`

* `S(t)` = presynaptic input
* `C(t)` = astrocytic calcium
* `A_astro(t)` = astrocyte activity
* `A(t)` = attention signal
* `w_s, w_a` = synaptic weights

**Result:**
Astrocyte-mediated modulation introduces a slower timescale that stabilizes neural responses and reduces variability.

---

## Conceptual Insight

Across all models, attention emerges not as a single mechanism, but as a **unifying dynamical principle**:

> Attention acts as a control signal that shapes neural dynamics across multiple scales — from single neurons to populations to neuron–glia interactions.

---



## Motivation

This project is motivated by a broader interest in understanding how **neural dynamics give rise to computation, variability, and temporal processing** in the brain.


