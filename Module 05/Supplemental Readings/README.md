# Module 05 — Supplemental Readings
**Course:** ITAI 4374 — Sensory Processing & AI Perception  
**Institution:** Houston City College  
**Term:** Spring 2026

---

## Purpose

These four readings extend and deepen Module 05 content beyond the lecture slides. They range from an accessible scholarly book review to primary research articles published in top-tier journals. Together they address the four major frontiers introduced in the module: how predictions shape perception, how sensory integration works in the body, the role of recurrent processing in consciousness, and whether sensory systems optimize for accuracy or survival fitness.

---

## Readings

### 1. Hacking the Predictive Mind
**File:** `Hacking_the_predictive_mind.pdf`  
**Source:** *Brain*, Oxford University Press, 2024 (Vol. 147, pp. 1589–1592)  
**Author:** Stephen M. Fleming (UCL)  
**Type:** Scholarly book review

**Summary:** A review of Andy Clark's *The Experience Machine* (2023), this article provides an accessible but rigorous introduction to predictive processing — the framework in which the brain is not a passive receiver of sensory information but actively generates predictions and updates them based on prediction errors. The review connects predictive processing to clinical conditions (functional neurological disorders, autism, schizophrenia), active inference (Karl Friston), and the hard problem of consciousness. Critically evaluates how well predictive processing handles clinical and philosophical challenges.

**Module Connection:** Directly extends Module 05's discussion of **top-down modulation (Principle 6)** — the one principle not yet well-implemented in standard AI. Also connects to Module 02 (Thousand Brains / Predictive Coding) and provides context for why attention mechanisms in transformers are the closest current AI analog to top-down prediction.

**Key Terms:** Predictive processing, predictive coding, active inference, prediction error, precision-weighting, hierarchical Bayesian brain

---

### 2. Sensory Integration
**File:** `physio-pedia_com-Sensory_Integration.pdf`  
**Source:** Physiopedia (physio-pedia.com/Sensory_Integration)  
**Type:** Clinical reference / educational resource

**Summary:** A comprehensive clinical overview of sensory integration theory (originating with A. Jean Ayres), covering all eight sensory systems — including proprioception, the vestibular system, and interoception alongside the classic five. Explains sensory processing dysfunction, hyper- and hypo-responsiveness to sensory inputs, and the Pyramid of Learning framework. Includes practical applications of sensory integration therapy (SIT) for children with cerebral palsy and developmental conditions, with discussion of evidence quality.

**Module Connection:** Extends the module's coverage of the **somatosensory system** (proprioception, touch), **vestibular sensing** (not covered in the lecture), and **interoception** — all relevant to robotics and human-robot interaction. Provides the clinical dimension of sensory processing: what happens when integration breaks down. Also connects to the module's AI analogy for proprioception (joint encoders + IMUs in robotics).

**Key Terms:** Sensory integration, proprioception, vestibular system, interoception, exteroception, sensory processing disorder, sensory homunculus, Pyramid of Learning

---

### 3. Recurrent Processing Theory and the Function of Consciousness
**File:** `selfawarepatterns_com-Recurrent_processing_theory_and_the_function_of_consciousness.pdf`  
**Source:** selfawarepatterns.com (January 25, 2020)  
**Type:** Scholarly blog / science communication

**Summary:** An accessible explanation of Victor Lamme's Recurrent Processing Theory (RPT) of consciousness. RPT proposes that recurrent (feedback) processing in sensory regions — not just feedforward sweeps — is sufficient for conscious experience. The article walks through Lamme's four stages of sensory processing, from superficial feedforward sweeps to widespread recurrent processing, and critically evaluates RPT against global workspace theory (GWT) and integrated information theory (IIT).

**Module Connection:** Directly addresses the **missing piece in standard CNNs** — recurrent feedback connections. The module notes that biological vision uses massive recurrence that standard CNNs lack; this reading explains why that recurrence may matter not just for performance but potentially for something like awareness. Also connects to the module's discussion of the **binding problem** and why feedforward-only architectures may be fundamentally limited.

**Key Terms:** Recurrent processing theory (RPT), feedforward vs. feedback processing, global workspace theory (GWT), integrated information theory (IIT), Victor Lamme, consciousness, split-brain patients

---

### 4. Sensory Perception Relies on Fitness-Maximizing Codes
**File:** `Sensory_perception_relies_on_fitness__maximizing_codes.pdf`  
**Source:** *Nature Human Behaviour*, Vol. 7, July 2023, pp. 1135–1151  
**Authors:** Schaffner, Bao, Tobler, Hare & Polania (University of Zurich / ETH Zurich)  
**Type:** Primary research article (peer-reviewed)

**Summary:** Challenges the long-held assumption that sensory systems maximize perceptual accuracy. Using behavioral experiments with human participants, blowfly retinal neuron data, fMRI, and deep neural networks with information bottlenecks, the authors demonstrate that sensory encoding strategies are flexibly adapted to maximize fitness (reward) rather than accuracy. Early sensory structures (V1–V3) reorganize their representations based on the behavioral goals of the organism, and artificial neural networks with capacity constraints independently discover the same fitness-maximizing codes.

**Module Connection:** Provides a rigorous counterpoint to the simple "accurate sensor" model of sensory systems introduced in the module. Connects to **top-down modulation (Principle 6)**, the **fitness vs. accuracy debate** in sensory coding, and the **AI parallel** — showing that DNNs with information bottlenecks independently converge on the same solutions as biological systems. Advanced reading for students interested in the normative theory of perception.

**Key Terms:** Efficient coding, fitness maximization, infomax coding, power-law efficient codes, information bottleneck, Fisher information, blowfly LMC neurons, retinotopic specificity, variational information bottleneck (VIB)

---

## Reading Difficulty Guide

| Reading | Accessibility | Best For |
|---------|--------------|----------|
| Hacking the Predictive Mind | ★★☆☆☆ Accessible | All students — start here for predictive processing |
| Sensory Integration (Physiopedia) | ★★☆☆☆ Accessible | Students interested in clinical/rehab applications or robotics |
| Recurrent Processing Theory | ★★★☆☆ Intermediate | Students interested in consciousness and AI limitations |
| Fitness-Maximizing Codes | ★★★★★ Advanced | Students with quantitative background; optional deep dive |

---

## Thematic Connections Across Readings

All four readings orbit a central question from Module 05: **Is sensory processing passive or active?**

- **Predictive Mind** — Perception is active prediction, not passive reception
- **Sensory Integration** — The brain actively integrates and modulates 8+ sensory channels; breakdown has real functional consequences
- **Recurrent Processing** — Consciousness may arise from the active feedback loops the brain adds on top of feedforward input
- **Fitness-Maximizing Codes** — Even the earliest sensory neurons actively reshape their coding to serve the organism's goals, not just to record the world

---

*ITAI 4374 — Houston City College — Spring 2026*
