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
[
r(t) = g \cdot s(t) + \eta(t)
]

* (s(t)): stimulus
* (g): attention gain
* (\eta(t)): noise

**Result:**
Attention increases the signal-to-noise ratio (SNR), improving encoding fidelity.

---

### 2. Population Coding with Attention

We extend the model to a population of neurons with Gaussian tuning curves:
[
r_i(x) = \exp\left(-\frac{(x - \mu_i)^2}{2\sigma^2}\right)
]

Attention selectively enhances neurons tuned to a target stimulus:
[
r_i^{att}(x) = A_i \cdot r_i(x)
]

**Result:**
Attention sharpens population responses, effectively increasing representational precision.

---

### 3. Competitive Network (Selection Mechanism)

We model attention as a result of **competition between neural populations**, implemented via softmax and dynamical inhibition.

**Key idea:**
Attention biases competition, allowing one representation to dominate.

**Result:**
Small biases in input lead to strong selection effects, consistent with winner-take-all dynamics observed in cortical circuits.

---

### 4. Temporal (Dynamical) Attention Model

We model attention as a **time-varying control signal**:
[
r(t) = A(t) \cdot s(t) + \eta(t)
]

where (A(t)) evolves over time.

We further incorporate temporal integration:
[
\tau \frac{dV}{dt} = -V + A(t)s(t)
]

**Result:**
Attention dynamically gates input, shaping:

* temporal integration
* response variability
* effective filtering of sensory signals

---

## Key Results

* Attention improves signal-to-noise ratio through gain modulation
* Population-level effects reveal sharpening of stimulus representations
* Competitive dynamics provide a mechanism for selective attention
* Temporal modulation suggests attention acts as a **control parameter in neural dynamics**, rather than a static multiplier

---

## Conceptual Insight

Across all models, attention emerges not as a single mechanism, but as a **unifying dynamical principle**:

> Attention can be interpreted as a control signal that shapes neural dynamics across multiple scales — from single neurons to populations to recurrent networks.

---

## Repository Structure

attention-models/
├── gain_modulation.py
├── population_attention.py
├── competitive_network.py
├── temporal_attention.py

---

## Future Directions

* Incorporating stochastic attention fluctuations
* Linking to recurrent neural networks and learned attention mechanisms
* Connecting variability modulation to experimental observables (e.g., Fano factor)
* Extending to biologically realistic spiking networks

---

## Motivation

This project is motivated by a broader interest in understanding how **neural dynamics give rise to computation, variability, and temporal processing** in the brain.

---

