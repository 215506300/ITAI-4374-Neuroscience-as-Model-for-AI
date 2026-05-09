# ITAI 4374 — Module 04: Neurons & Spiking Neural Networks
**Houston City College · AI & Robotics Program · Spring 2026**

---

## Overview

Module 04 bridges the single LIF neuron from Module 03 to full spiking neural networks (SNNs), covering how they are built, trained, and deployed on neuromorphic hardware. By the end of this module you will have simulated spiking neurons in both Wolfram Language and Python, trained a convolutional SNN on MNIST with snnTorch, and understood why specialized chips are required to unlock the efficiency advantages of spike-based computing.

---

## Student Learning Outcomes

| # | Outcome | Bloom's Level |
|---|---------|---------------|
| SLO 2 | Implement neuron/network simulations using Wolfram System Modeler or snnTorch to demonstrate energy-efficient inference | Create |
| SLO 6 | Develop and present a neuro-inspired AI system addressing a real-world engineering constraint (power, data scarcity, adaptability) | Create |

---

## Module Structure

### Part 1 — From Single Neurons to Spiking Networks
| Section | Topic |
|---------|-------|
| 1 | Bridge from Module 03 |
| 2 | The Three Generations of Neural Networks |
| 3 | Why Spikes Matter — Energy, Latency, Temporal Processing |
| 4 | From LIF Neurons to SNNs |
| 5 | Encoding Input Data as Spikes |

### Part 2 — Training Spiking Neural Networks
| Section | Topic |
|---------|-------|
| 6 | The Training Problem — Why Backpropagation Breaks |
| 7 | Surrogate Gradients — The Elegant Solution |
| 8 | Backpropagation Through Time (BPTT) in SNNs |
| 9 | snnTorch — Your Tool for Building SNNs |

### Part 3 — Neuromorphic Hardware
| Section | Topic |
|---------|-------|
| 10 | What Is Neuromorphic Computing? |
| 11 | Intel Loihi 2 and the Hala Point System |
| 12 | The Broader Neuromorphic Ecosystem |
| 13 | Lab Preview — Training an SNN on MNIST |
| 14 | Key Takeaways & Bridge to Module 05 |

---

## Key Concepts

**Leaky Integrate-and-Fire (LIF) Neuron** — The core building block. Membrane potential accumulates weighted inputs, leaks back toward rest, and fires a binary spike when it crosses threshold. Described by:

```
tau * V'[t] = -(V[t] - V_rest) + R * I[t]
```

**Surrogate Gradients** — Because the Heaviside spike function has zero gradient everywhere, standard backpropagation fails. The fix: use real spikes in the forward pass but swap in a smooth function (e.g. fast sigmoid) during the backward pass.

**BPTT** — Spiking networks unroll across time steps, making them equivalent to very deep RNNs. Gradients flow backward through both layers and time simultaneously.

**Spike Encoding Methods**

| Method | Principle | Best For |
|--------|-----------|----------|
| Rate Coding | Higher value → more spikes | Static images (MNIST, CIFAR) |
| Latency Coding | Higher value → earlier spike | Fast inference, edge devices |
| Delta Modulation | Spike only on change | Video, DVS cameras |
| Direct Input | Feed raw values, let network encode | When encoding is unclear |

---

## Assignments

### Wolfram Assignment — `A04_FirstName_LastName_ITAI4374.nb/.pdf`
Simulate the LIF differential equation using `NDSolve` and `WhenEvent` in Wolfram Language.

| Part | Task |
|------|------|
| A | Solve and plot the LIF equation with spike reset |
| B | Build an interactive `Manipulate[]` dashboard (threshold, tau, current sliders) |
| C | Generate the f–I (firing rate vs. current) curve |
| D | Encode a sine-wave signal as spikes |
| E | Run ≥ 3 experiments from the experiment menu |
| F | Final reflection (5 questions) |

**Experiment Menu (choose ≥ 3):** Threshold Sweep · Time Constant Comparison · Noisy Input · Refractory Period · Two f–I Curves · Frequency Encoding

---

### Python Lab — `L04_FirstName_LastName_ITAI4374.ipynb`
Build spiking neuron simulations from scratch in Python using NumPy/Matplotlib on Google Colab.

| Part | Task |
|------|------|
| A | Implement the LIF simulation loop; plot membrane potential |
| B | Implement rate coding and temporal (latency) coding; create raster plots |
| C | Connect a 5-neuron spiking network with synaptic weights |
| D | Run ≥ 3 experiments from the experiment menu |
| E | Final reflection (5 questions) |

**Experiment Menu (choose ≥ 3):** Threshold Sensitivity · Time Constant Effects · Varying Input Current · Noisy Input · Network Weight Changes · f–I Curve

---

## Tools & Setup

| Tool | Purpose |
|------|---------|
| **Wolfram Cloud** (wolframcloud.com) | Wolfram assignment — no install needed |
| **Google Colab** (colab.research.google.com) | Python lab — no install needed |
| `numpy`, `matplotlib` | Python simulation and plotting |
| `snnTorch` + `PyTorch` | Module lab: training SNNs on MNIST |
| `torchvision` | MNIST dataset |

---

## Neuromorphic Hardware Reference

| System | Neurons | Power | Efficiency |
|--------|---------|-------|------------|
| Human Brain | ~86 billion | ~20 W | >500 TOPS/W |
| NVIDIA H100 GPU | ~1B parameters | ~700 W | ~0.3 TOPS/W |
| Intel Hala Point | 1.15 billion | 2,600 W | up to 15 TOPS/W |
| BrainChip Akida | — | — | Commercial edge AI |

**Key insight:** SNNs running on a GPU are often *less* efficient than a conventional ANN. The energy advantages only materialize on hardware designed to exploit event-driven, sparse computation.

---

## Files in This Module

| File | Description |
|------|-------------|
| `ITAI_4374_Module_04_Booklet.pdf` | Core reading — all theory, diagrams, knowledge checks |
| `Module_04_Wolfram_Assignment_Guide.pdf` | Step-by-step Wolfram assignment instructions |
| `Module_04_Python_Lab_Guide.pdf` | Step-by-step Python lab instructions |
| `L04_Module04_Spiking_Neurons_Lab.ipynb` | Starter notebook for Python lab |
| `spectrum_ieee_org-Neuromorphic_Hardware_Solves_Complex_Math_Efficiently.pdf` | Supplemental reading (IEEE Spectrum, Feb 2026) |
| `A04_FirstName_LastName_ITAI4374.pdf` | **Your submission** — Wolfram assignment |
| `L04_FirstName_LastName_ITAI4374.ipynb` | **Your submission** — Python lab notebook |

---

## Quick Reference — LIF Parameters

| Parameter | Symbol | Typical Value | Meaning |
|-----------|--------|---------------|---------|
| Membrane time constant | `tau` | 20 ms | How fast voltage decays toward rest |
| Resting potential | `V_rest` | −70 mV | Baseline voltage with no input |
| Spike threshold | `V_thresh` | −55 mV | Voltage at which a spike fires |
| Reset potential | `V_reset` | −75 mV | Voltage after a spike (hyperpolarization) |
| Decay factor | `β` | 0.9 | snnTorch discrete-time leak (0 = fast, 1 = slow) |

---

## Bridge

**← Module 03:** Brain anatomy, the single LIF neuron, neural coding basics.

**→ Module 05:** Sensory Processing & Perception — the visual cortex hierarchy (V1→IT), how it inspired CNNs, event-based vision with DVS cameras, multimodal integration.

---

## Key References

- Eshraghian et al. (2023). *Training Spiking Neural Networks Using Lessons From Deep Learning.* Proceedings of the IEEE, 111(9).
- Neftci, Mostafa & Zenke (2019). *Surrogate Gradient Learning in Spiking Neural Networks.* IEEE Signal Processing Magazine, 36(6).
- Gygax & Zenke (2025). *Elucidating the Theoretical Underpinnings of Surrogate Gradient Learning.* Neural Computation, 37(5).
- Bourzac, K. (2026, Feb 2). *Neuromorphic Hardware Solves Complex Math Efficiently.* IEEE Spectrum.
- snnTorch documentation: [snntorch.readthedocs.io](https://snntorch.readthedocs.io)
