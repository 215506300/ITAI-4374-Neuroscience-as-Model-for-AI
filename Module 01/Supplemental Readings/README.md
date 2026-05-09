# Module 1 Supplemental Readings

This folder contains three papers at the intersection of neuroscience and artificial intelligence — collectively forming the theoretical and motivational backbone of the **NeuroAI** perspective introduced in Module 1.

---

## Papers

### 1. Brain-Inspired Computational Intelligence via Predictive Coding
**Authors:** Salvatori, Mali, Buckley, Lukasiewicz, Rao, Friston, Ororbia (2023)
**File:** `Brain_Inspired_Computational_Inteligence_via_Predictive_Coding_Aug_2023.pdf`

A comprehensive survey of **predictive coding (PC)** — a neuroscience-grounded learning framework rooted in Bayesian inference and variational free energy minimization. The paper covers:

- The theoretical foundations of PC as an alternative to backpropagation
- Three major computational implementations: Rao & Ballard PC, Neural Generative Coding (NGC), and BC-DIM
- Applications across supervised learning, NLP, computer vision, temporal modeling, continual learning, and robotics
- Biological plausibility considerations and hardware/software ecosystem
- Open research challenges and future directions

**Key concept:** In PC, every neuron maintains a *prediction* and a *prediction error*, and learning proceeds by minimizing those local errors — eliminating the need for a global backward pass.

---

### 2. Catalyzing Next-Generation Artificial Intelligence through NeuroAI
**Authors:** Zador, Escola, Richards, Ölveczky, Bengio, Boahen, et al. (2022)
**File:** `Catalizing_Next_Generation_Artificial_INtellignece_through_Neuro_AI.pdf`

A position paper by a broad coalition of neuroscientists and AI researchers arguing that progress in AI requires renewed investment in **NeuroAI** — the intersection of neuroscience and AI. Core arguments include:

- Current AI systems, despite impressive performance on narrow benchmarks, fail to match the sensorimotor flexibility, energy efficiency, and robustness of even simple animals
- The authors propose the **Embodied Turing Test**: an AI system passes not by conversing like a human, but by behaving indistinguishably from its animal counterpart in physical interaction with the world
- A roadmap organized around three needs: training dual-fluency researchers, building shared computational platforms, and funding fundamental neural computation research

**Key concept:** The bottleneck for next-gen AI is not language or reasoning, but the 500-million-year-old sensorimotor intelligence shared by all animals — which AI has barely begun to replicate.

---

### 3. Towards NeuroAI: Introducing Neuronal Diversity into Artificial Neural Networks
**Authors:** Fan, Li, Peng, Zeng, Wang (2023)
**File:** `Towards_Neural_AI_INtroducing_Neuronal_Diversity_into_ANN.pdf`

A perspective paper arguing that the most actionable near-term path toward NeuroAI is introducing **neuronal diversity** into artificial networks. The biological brain uses thousands of morphologically and functionally distinct neuron types; current ANNs use essentially one. The paper covers:

- Biological foundations: morphological and functional neuronal diversity
- Four categories of novel artificial neuron designs: activation function variants, polynomial neurons, dendritic neurons, and spiking neurons
- Potential gains in **efficiency**, **interpretability**, **memory** (catastrophic forgetting), and **robustness**
- Real-world applications in medical imaging, fault diagnosis, PDE solving, and computer vision
- Open challenges including neuronal synergy, task-based neuron design, and theory for heterogeneous networks

**Key concept:** Rather than copying the brain, artificial networks should *draw inspiration* from it — designing task-specific neuron types to encode useful inductive biases rather than relying on a single generic unit.

---

## How These Papers Connect

| Theme | Predictive Coding | NeuroAI Manifesto | Neuronal Diversity |
|---|---|---|---|
| Motivation | Limits of backprop | Limits of current AI | Limits of uniform neurons |
| Biological grounding | Cortical hierarchy, free energy | Sensorimotor evolution | Neuronal morphology & function |
| Core proposal | PC as alternative learning rule | Embodied Turing Test roadmap | New neuron types for ANNs |
| Primary challenge addressed | Biological plausibility, robustness | Flexibility, efficiency | Efficiency, interpretability, memory |

Together, these readings frame the central question of Module 1: **What can the brain teach us about building better AI?**

---

## Suggested Reading Order

1. **NeuroAI Manifesto** — sets the high-level motivation and research agenda
2. **Neuronal Diversity** — introduces a concrete, near-term approach grounded in biology
3. **Predictive Coding** — deep technical dive into one of the most developed brain-inspired learning frameworks
