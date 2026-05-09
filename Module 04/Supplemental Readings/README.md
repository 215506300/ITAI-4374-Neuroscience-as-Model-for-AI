# Module 4 Supplemental Readings

This folder contains four supplemental readings on **Spiking Neural Networks (SNNs) and Neuromorphic Computing**. Together, they provide a comprehensive look at the theory, hardware, applications, and real-world challenges of brain-inspired computing.

---

## Readings

### 1. Spiking Neural Networks: The Future of Brain-Inspired Computing
**Source:** Aribe Jr., S.G. — *International Journal of Engineering Trends and Technology*, Vol. 73, Issue 10, October 2025
**File:** `2510_27379v1_Spiking_Neural_Networks_The_Future_of_Brain-Inspired_Computing.pdf`

A peer-reviewed academic paper providing a comprehensive technical analysis of SNNs. Covers neuron models (LIF, Izhikevich), training strategies (surrogate gradient descent, ANN-to-SNN conversion, STDP), and a multi-metric performance evaluation across accuracy, latency, energy consumption, spike count, and convergence behavior. Key finding: surrogate gradient-trained SNNs achieve accuracy within 1–2% of ANNs while using up to 97% less energy.

**Key Topics:** LIF neuron model · Training algorithms · MNIST/CIFAR-10 benchmarks · Energy efficiency · Neuromorphic hardware

---

### 2. Neuromorphic Computing — Human Brain Project
**Source:** Human Brain Project (humanbrainproject.eu)
**File:** `humanbrainproject_eu-Neuromorphic_computing.pdf`

An overview of the neuromorphic computing platforms developed under the EU Human Brain Project (HBP), specifically the **BrainScaleS** and **SpiNNaker** systems. Describes how these machines implement biological neural networks in silicon, their complementary architectures (analogue vs. digital), and how researchers can access them via the EBRAINS Research Infrastructure. BrainScaleS runs at 1,000× biological real time; SpiNNaker operates at real time across over 1 million ARM cores.

**Key Topics:** BrainScaleS · SpiNNaker · EBRAINS platform · Neuromorphic hardware · Accelerated simulation

---

### 3. Simpler Can Be Better: Lessons from a Neural Decoding Challenge
**Source:** Ounnoughene, A.Z. — *Medium*, February 1, 2026
**File:** `medium_com-Simpler_Can_Be_Better_Lessons_from_a_Neural_Decoding_Challenge.pdf`

A reflective account of participating in the **IEEE BioCAS 2025 Grand Challenge on Neural Decoding for Motor Control**. Describes the use of SNNs in a closed-loop brain-machine interface (BMI) task, where neural spike data is decoded into motor velocity commands. The author's team explored supervised learning, continuous local learning (CLL), and TD-error modulated reinforcement learning — ultimately concluding that simpler methods outperformed more complex ones, especially under perturbations.

**Key Topics:** Brain-machine interfaces · Neural decoding · Closed-loop control · Continuous local learning · Lessons learned in SNN research

---

### 4. Spiking Neural Networks: The Next "Big Thing" in AI?
**Source:** Horak, D.S. — *Medium*, February 22, 2024
**File:** `medium_com-Spiking_Neural_Networks_The_next_Big_Thing_in_AI.pdf`

An accessible, practitioner-perspective essay on why SNNs may represent the next major paradigm shift in AI. Discusses their advantages over traditional ANNs and LLMs — including energy efficiency, temporal processing, neuromorphic hardware compatibility, and biological plausibility. Also addresses key challenges such as training complexity and limited hardware accessibility. Written for a general technical audience with connections to AGI research.

**Key Topics:** SNNs vs. LLMs · Energy efficiency · STDP · Neuromorphic chips · AGI implications

---

## How These Readings Connect

| Theme | Readings |
|---|---|
| SNN fundamentals & neuron models | 1, 4 |
| Training methods (STDP, surrogate gradient, conversion) | 1, 3, 4 |
| Neuromorphic hardware (Loihi, TrueNorth, SpiNNaker, BrainScaleS) | 1, 2, 4 |
| Real-world applications (BMI, robotics, edge AI) | 1, 3 |
| Energy efficiency & sustainability | 1, 4 |
| Challenges & future directions | 1, 2, 3, 4 |

---

## Suggested Reading Order

1. **Reading 4** (Horak) — Start here for a conceptual, accessible introduction to SNNs and why they matter.
2. **Reading 1** (Aribe) — Deep dive into the technical details, models, and benchmarks.
3. **Reading 2** (HBP) — Explore the real hardware platforms that run SNNs at scale.
4. **Reading 3** (Ounnoughene) — See how SNN research plays out in a hands-on challenge, with honest lessons learned.
